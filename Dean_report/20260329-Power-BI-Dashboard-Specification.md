# IMPACT Program — Power BI Dashboard Specification
## Design Document for Beth | Visual Support: Sydney & Naya

**Date:** 2026-03-29
**Updated:** 2026-03-29 — Added 3-lens composite scoring model; Page 2 redesigned for Lens A / B / C visibility
**Audience:** Dean, Dean's Advisory Board, WSU Administration, AACSB, Kansas Legislature
**Scale:** 5 active projects × 30 enrolled students (Spring 2026 cohort)
**Data Sources:** SharePoint Lists (Student Roster, Master Project List, Weekly Task Reports, Deliverable Quality Scores, Peer Nominations, Success Stories)
**Tool:** Microsoft Power BI (connected to SharePoint via native connector)

---

## Dashboard Architecture — 5 Pages

| Page | Name | Primary Audience | Purpose |
|---|---|---|---|
| 1 | Executive Overview | Dean, Advisory Board | Headline story — program at a glance |
| 2 | Student Growth & AACSB Outcomes | Dean, AACSB, Faculty Liaison | 3-lens composite scores, divergence flags |
| 3 | Career Outcomes | Dean, Advisory Board, Legislature | Placements, salaries, career momentum |
| 4 | Project & Client Performance | Leadership, Advisory Board | Consulting delivery quality per team |
| 5 | Operational Health | Internal Leadership | Weekly cadence, submission rates, bottlenecks |

**Navigation:** Persistent left-side nav panel with IMPACT branding. "Last Refreshed" timestamp in footer.

---

## Data Model (SharePoint → Power BI)

```
Student Roster ──────────────────────────────────┐
 StudentID, Name, Major, Team, Cohort             │
 Pre_Confidence[1-5], Post_Confidence[1-5]        │
 Pre_KnowledgeTest, Post_KnowledgeTest            │
 PM_BARS_Score[LO1-5]                             │
 Peer_Nomination_Score[LO1-3]                     │
 Training_Complete, Violations, Status, Consent   │
        │                                          │
        │ (many-to-one on Team)                    │
        ▼                                          │
Master Project List ──── Success Stories          │
 ProjectID, Client, Sector, Kansas                │ (StudentID, Outcome, Salary,
 Status, StartDate, EndDate_Plan                  │  Employer, Date)
 EndDate_Actual, ClientSatScore                   │
 ClientYN_Checklist[1-5]                          │
 EstValueDelivered                                │
        │                                         │
        ▼                                         │
Weekly Task Reports ◄────────────────────────────┘
 StudentID, WeekEnding, HoursClient
 HoursAdmin, HoursTraining
 SubmissionTimestamp, ReviewedByPM, Flagged

Deliverable Quality Scores (NEW)
 ProjectID, StudentID, DeliverableID
 Checklist[1-5] (Y/N per item)
 ChecklistScore (avg)

Peer Nominations (NEW — anonymous, aggregated only)
 NomineeID, Category (LO1, LO3, LO4)
 NominationCount, NormalizedScore
```

---

## Calculated Columns (add in Power BI)

```DAX
-- Lens C per student
LensC_Score[LO] =
    ([Post_KnowledgeTest_LO] * 0.5) + ([Post_Confidence_LO] * 0.5)

LensC_Pre[LO] =
    ([Pre_KnowledgeTest_LO] * 0.5) + ([Pre_Confidence_LO] * 0.5)

LensC_Delta[LO] = LensC_Score[LO] - LensC_Pre[LO]

-- Lens A per student (LO3 example)
LensA_LO3 =
    (([SubmissionRate] + [OnTimeDeliveryRate]) / 2) * 5

-- Composite per LO
Composite_LO[n] =
    ([LensA_LO[n]] * 0.4) + ([LensB_LO[n]] * 0.4) + ([LensC_LO[n]] * 0.2)

-- Divergence flag
Divergence_Flag =
    VAR AvgObjective = ([LensA] + [LensB]) / 2
    RETURN
        IF([LensC] - AvgObjective > 1.0, "⚠ Self-overrating",
        IF(AvgObjective - [LensC] > 1.0, "↑ Underestimates growth", "✓ Aligned"))

-- Legacy fields (backward compatibility for AACSB)
OnTime_Flag = IF(WEEKDAY([SubmissionTimestamp]) = 2
               AND HOUR([SubmissionTimestamp]) <= 23, 1, 0)
OnTimeDelivery = IF([EndDate_Actual] <= [EndDate_Plan], 1, 0)
AtThreshold = IF([Composite_Avg] >= 3.5, 1, 0)
```

---

## Key Measures (DAX)

```DAX
-- Program-level
Total Students = COUNTROWS('Student Roster')
Active Projects = COUNTROWS(FILTER('Master Project List', [Status] = "Active"))
Total Applied Hours = SUM('Weekly Task Reports'[HoursClient])
Estimated Value Delivered = SUM('Master Project List'[EstValueDelivered])

-- 3-Lens averages
Avg LensA = AVERAGE('Student Roster'[LensA_Avg])
Avg LensB = AVERAGE('Student Roster'[LensB_Avg])
Avg LensC = AVERAGE('Student Roster'[LensC_Avg])
Avg Composite = AVERAGE('Student Roster'[Composite_Avg])

-- Growth (Lens C preserves AACSB pre/post requirement)
LensC Delta = AVERAGE('Student Roster'[LensC_Delta])
Pct Growth = DIVIDE([Avg Composite] - AVERAGE('Student Roster'[LensC_Pre_Avg]),
                    AVERAGE('Student Roster'[LensC_Pre_Avg]), 0)

-- AACSB composite threshold
Cohort Achievement Rate =
    DIVIDE(
        COUNTROWS(FILTER('Student Roster', [Composite_Avg] >= 3.5)),
        [Total Students]
    )

-- Divergence metrics
Aligned Rate =
    DIVIDE(
        COUNTROWS(FILTER('Student Roster', [Divergence_Flag] = "✓ Aligned")),
        [Total Students]
    )
Self_Overrating Rate =
    DIVIDE(
        COUNTROWS(FILTER('Student Roster', [Divergence_Flag] = "⚠ Self-overrating")),
        [Total Students]
    )
Growth_Confirmed Rate =
    DIVIDE(
        COUNTROWS(FILTER('Student Roster',
            [LensA_Delta] > 0 && [LensB_Delta] > 0)),
        [Total Students]
    )

-- Operational
Submission Rate =
    DIVIDE(
        COUNTROWS(FILTER('Weekly Task Reports', [OnTime_Flag] = 1)),
        COUNTROWS('Weekly Task Reports')
    )
On-Time Delivery Rate =
    DIVIDE(
        COUNTROWS(FILTER('Master Project List', [OnTimeDelivery] = 1)),
        [Active Projects]
    )

-- Career
Placement Rate =
    DIVIDE(
        COUNTROWS(FILTER('Success Stories',
            [OutcomeType] IN {"Full-Time Job", "Internship"})),
        [Total Students]
    )
Avg Starting Salary = AVERAGE('Success Stories'[StartingSalary])
```

---

## Page 1 — Executive Overview

**Design intent:** One glance tells the Dean what IMPACT produced this semester.
**Layout:** Full-width banner → 5 KPI cards → 2 feature charts → 1 value callout

### KPI Card Row (5 cards)

| Card | Measure | Sample Value | Color Logic |
|---|---|---|---|
| Students Served | `Total Students` | **30** | Neutral brand |
| Active Projects | `Active Projects` | **5** | Neutral brand |
| Avg Skill Growth | `Pct Growth` | **+26%** | Green >10%, Yellow 5–10%, Red <5% |
| Client Satisfaction | `Avg ClientSatScore` | **4.3 / 5.0** | Green ≥4.0, Yellow 3.5–3.9, Red <3.5 |
| Estimated Value Delivered | `Estimated Value Delivered` | **$189,000** | Always display with $ |

### Chart 1 — Major Diversity Donut

| Major | Count | % |
|---|---|---|
| Finance | 7 | 23% |
| MIS | 6 | 20% |
| Marketing | 5 | 17% |
| Management | 5 | 17% |
| Accounting | 4 | 13% |
| Economics | 2 | 7% |
| Other | 1 | 3% |

### Chart 2 — Projects by Industry (horizontal bar)

| Industry | Projects |
|---|---|
| Healthcare | 2 |
| Finance | 1 |
| Nonprofit | 1 |
| Manufacturing | 1 |

### Callout Box — "The IMPACT Story in Numbers"

> **30 graduate students** delivered **5 consulting engagements** to Kansas businesses, logging an estimated **1,890 applied learning hours** and generating **~$189,000 in consulting value** for the state of Kansas.

*Sydney / Naya: Barton yellow `#FFC82E` background accent. Font: Proxima Nova or WSU brand equivalent.*

---

## Page 2 — Student Growth & AACSB Outcomes (Redesigned)

**Design intent:** Show all three lenses independently — then show the composite. Let the Dean and AACSB reviewer see that growth is confirmed from multiple directions, not just self-report.
**Layout:** 3-lens comparison chart → composite achievement gauges → divergence summary → individual score table

---

### Visual 1 — 3-Lens Comparison by Learning Outcome (grouped bar chart)

**Visual type:** Grouped bar chart — 3 bars per LO
**X-axis:** Learning Outcome (LO1–LO5)
**Y-axis:** Average Score (0–5)
**Series:**
- Lens A — Behavioral (dark gray)
- Lens B — Observer-rated (Barton yellow `#FFC82E`)
- Lens C — Self-reported (light gray)

**Reference line:** Dashed horizontal at Y = 3.5 (achievement threshold)
**Data labels:** Show value on each bar

**Sample data (30 students):**

| LO | Lens A (Behavioral) | Lens B (Observer) | Lens C (Self) | Composite |
|---|---|---|---|---|
| LO1 — Communication | 4.2 | 3.9 | 4.1 | **4.08** |
| LO2 — Analytical | 3.8 | 3.7 | 3.8 | **3.76** |
| LO3 — Professionalism | 4.5 | 4.1 | 4.2 | **4.26** |
| LO4 — Applied Knowledge | 4.3 | 3.8 | 4.0 | **4.04** |
| LO5 — Ethics | 4.7 | 4.4 | 4.3 | **4.52** |
| **Overall** | **4.30** | **3.98** | **4.08** | **4.13** |

> **Headline for Dean:** Lens A (behavioral) and Lens B (observer) both independently confirm what students report about themselves. Growth is real, not self-inflated.

---

### Visual 2 — Composite Achievement Rate Gauges (5 KPI gauges)

One gauge per LO. Measure: `Cohort Achievement Rate` (filtered per LO).
Target line at AACSB target. Green ≥ target; Yellow within 5% below; Red > 5% below.

| LO | Composite Achievement Rate | AACSB Target | Status |
|---|---|---|---|
| LO1 | 87% | 80% | Green |
| LO2 | 83% | 80% | Green |
| LO3 | 93% | 85% | Green |
| LO4 | 83% | 80% | Green |
| LO5 | 97% | 90% | Green |

---

### Visual 3 — NEW: Lens Alignment Summary (3 KPI cards)

| Card | Measure | Sample | Color |
|---|---|---|---|
| Aligned (✓) | `Aligned Rate` | **80%** (24/30) | Green |
| Self-Overrating (⚠) | `Self_Overrating Rate` | **10%** (3/30) | Yellow |
| Underestimates Growth (↑) | `Underestimates Rate` | **10%** (3/30) | Blue (positive finding) |

> **Note for Dean's Board:** The 10% self-overrating rate identifies students who may need coaching on self-awareness. The 10% "underestimates growth" group may need encouragement — their behavioral and observer scores are higher than they think.

---

### Visual 4 — Individual Score Table with Divergence Flags

**Visual type:** Table (paginated)
**Columns:** Student Name | Team | LO1–LO5 Composite Scores | Overall Composite | Divergence Flag
**Conditional formatting:**
- Composite ≥ 3.5 → green cell
- Composite 3.0–3.4 → yellow cell
- Composite < 3.0 → red cell
- Divergence Flag column: ⚠ = yellow background, ↑ = blue background, ✓ = no fill

**Note:** This table is filtered to show operations and faculty only. Dean's view shows cohort-level only (no individual names).

---

### Visual 5 — Pre/Post Lens C Delta (AACSB pre/post evidence)

**Visual type:** Bar chart
**X-axis:** LO (LO1–LO5)
**Y-axis:** Lens C Delta (Post − Pre)
**Color:** Green if delta > 0, Red if delta ≤ 0

This chart explicitly satisfies the AACSB pre/post requirement. It shows Lens C (knowledge test + confidence) improved across all five LOs.

| LO | Lens C Pre | Lens C Post | Delta |
|---|---|---|---|
| LO1 | 3.15 | 4.05 | **+0.90** |
| LO2 | 2.85 | 3.75 | **+0.90** |
| LO3 | 3.30 | 4.15 | **+0.85** |
| LO4 | 3.05 | 3.95 | **+0.90** |
| LO5 | 3.55 | 4.25 | **+0.70** |

---

### Visual 6 — NEW: Growth Confirmed Rate KPI Card

| Card | Measure | Sample | Description |
|---|---|---|---|
| Growth Confirmed | `Growth_Confirmed Rate` | **87%** (26/30) | Students where BOTH Lens A AND Lens B improved — not dependent on self-report |

> **For the Dean's board:** "87% of students showed growth confirmed by independent behavioral and observer evidence — not reliant on self-assessment."

---

## Page 3 — Career Outcomes

*(Unchanged from original specification — no impact from 3-lens update)*

### KPI Cards

| Card | Measure | Sample |
|---|---|---|
| Students with Placement | `Placement Rate` | **17 of 30 (57%)** |
| Avg Starting Salary | `Avg Starting Salary` | **$62,400** |
| Net Promoter | % recommending IMPACT | **93%** |

### Visual 1 — Career Outcome Funnel

| Stage | Count |
|---|---|
| Total Students | 30 |
| Completed Semester | 29 |
| Actively Seeking or Placed | 25 |
| Interview Credited to IMPACT | 18 |
| Offer Received | 17 |
| Full-Time Offer | 10 |
| Internship | 7 |

### Visual 2 — Placement Type Donut

| Outcome | Count |
|---|---|
| Full-Time Job | 10 |
| Internship | 7 |
| Actively Seeking | 8 |
| Not Seeking | 4 |
| Departed | 1 |

### Visual 3 — Starting Salary Histogram (bin = $5,000)

| Bin | Count |
|---|---|
| $45K–$50K | 1 |
| $50K–$55K | 3 |
| $55K–$60K | 3 |
| $60K–$65K | 4 |
| $65K–$70K | 2 |
| $70K–$80K | 1 |

Reference lines: avg ($62,400) + WSU Barton benchmark (if available from career services).

### Visual 4 — Employer/Industry Breakdown

| Industry | Count |
|---|---|
| Financial Services | 4 |
| Healthcare | 3 |
| Technology | 3 |
| Nonprofit | 2 |
| Manufacturing | 2 |
| Other | 3 |

---

## Page 4 — Project & Client Performance

### Visual 1 — Project Summary Table

| Project | Client | Sector | Status | On Time? | Client Sat | Value Delivered |
|---|---|---|---|---|---|---|
| Alpha | [Client A] | Healthcare | Active | On track | 4.5 | $42,000 |
| Beta | [Client B] | Finance | Active | On track | 4.2 | $38,500 |
| Gamma | [Client C] | Nonprofit | Active | On track | 4.8 | $35,000 |
| Delta | [Client D] | Manufacturing | Active | ⚠ At risk | 3.9 | $41,000 |
| Epsilon | [Client E] | Healthcare | Active | On track | 4.6 | $32,500 |

**Conditional formatting:** On track → green; At risk → yellow; Sat ≥4.0 → green; <3.5 → red.

### Visual 2 — Client Satisfaction by Project (bar chart, reference line at 4.0)

### Visual 3 — Value Delivered by Project (bar chart, $189K total callout)

### Visual 4 — Applied Learning Hours by Week (multi-line, one line per team)

### Visual 5 — NEW: Client Y/N Checklist Score by Project

**Visual type:** Horizontal bar chart
**X-axis:** Client behavioral Y/N score (0–5)
**Y-axis:** Project
**Reference line:** 4.0
**Purpose:** Shows which projects received strong behavioral endorsement from clients (not just general satisfaction)

---

## Page 5 — Operational Health

### KPI Cards

| Card | Measure | Sample | Color |
|---|---|---|---|
| Weekly Report Submission Rate | `Submission Rate` | **91%** | Green ≥90%, Yellow 80–89%, Red <80% |
| Training Completion Rate | — | **97%** (29/30) | Green ≥90% |
| Avg Onboarding Days | — | **3.4 days** | Green ≤5 days |

### Visual 1 — Submission Rate Trend (line chart, 90% reference line)

Sample (12 weeks): 87%, 90%, 93%, 97%, 93%, 90%, 100%, 93%, 87%, 90%, 97%, 93%

### Visual 2 — Submission Rate by Team (current week, horizontal bar)

### Visual 3 — Onboarding Funnel

| Stage | Count |
|---|---|
| HR Clearance Received | 30 |
| Welcome Email Sent | 30 |
| Onboarding Form Submitted | 29 |
| Access Provisioned | 29 |
| SOP Training Completed | 29 |
| Onboarding Complete | 28 |

### Visual 4 — Hours Split: Client vs. Admin vs. Training (stacked area by week)

### Visual 5 — Open Items Flag Table

| Flag | Count |
|---|---|
| Missing submission this week | 2 |
| Onboarding incomplete >7 days | 1 |
| PM BARS rubric not yet submitted | 0 |
| Deliverable quality scorecard overdue | 1 |
| Client Y/N checklist pending | 1 |

---

## Design Specifications for Sydney & Naya

### Color Palette

| Element | Hex | Usage |
|---|---|---|
| Primary — Barton Yellow | `#FFC82E` | Lens B bars, KPI accents, Post series, header highlights |
| Secondary — WSU Black | `#231F20` | Text, axis labels, table headers |
| Lens A — Dark Gray | `#4A4A4A` | Behavioral lens bars |
| Lens C — Light Gray | `#B0B0B0` | Self-reported lens bars |
| Composite — Deep Blue | `#1A5276` | Composite score line / overlay |
| Positive (Green) | `#2E8B57` | On target, achievement met, aligned flag |
| Warning (Amber) | `#E8A020` | Near threshold, at risk, ⚠ self-overrating |
| Informational (Blue) | `#2980B9` | ↑ Underestimates growth flag |
| Negative (Red) | `#C0392B` | Below threshold, late |
| Light Background | `#F9F7F2` | Page background |
| Card Background | `#FFFFFF` | KPI cards, chart backgrounds |

### Typography

| Element | Font | Size | Weight |
|---|---|---|---|
| Page title | WSU brand / Segoe UI | 20pt | Bold |
| Section header | Segoe UI | 14pt | SemiBold |
| KPI card value | Segoe UI | 36pt | Bold |
| KPI card label | Segoe UI | 11pt | Regular |
| Chart axis labels | Segoe UI | 10pt | Regular |
| Data table text | Segoe UI | 11pt | Regular |
| Lens label (A/B/C) | Segoe UI | 9pt | SemiBold, Italic |

### Page Layout Grid

```
┌─────────────────────────────────────────────────────────┐
│  [Left Nav]  │  [Page Title + Semester Badge]           │
│              │  [Last Refreshed]                         │
│  • Pg 1      ├─────────────────────────────────────────  │
│  • Pg 2      │  [KPI 1] [KPI 2] [KPI 3] [KPI 4] [KPI 5]│
│  • Pg 3      ├────────────────────┬────────────────────  │
│  • Pg 4      │  [Chart A]         │  [Chart B]          │
│  • Pg 5      │                    │                      │
│              ├────────────────────┴────────────────────  │
│  IMPACT Logo │  [Chart C — full width]                  │
│              ├─────────────────────────────────────────  │
│              │  [Footer: Data sources | Refresh date]   │
└─────────────────────────────────────────────────────────┘
```

### Persistent Filters (all pages)

- **Semester Cohort** slicer — defaults to current semester
- **Team Name** slicer — allows drilling into one team
- Pill-style buttons, top right corner of every page

---

## Data Entry Assumptions (Spring 2026 Baseline)

### Student Roster (30 records)
```
Teams: Alpha (6), Beta (6), Gamma (6), Delta (6), Epsilon (6)
Status: 29 Active, 1 Completed
Training Completed: 29 Yes, 1 No
LensA avg per LO: 4.30 / 3.80 / 4.50 / 4.30 / 4.70
LensB avg per LO: 3.90 / 3.70 / 4.10 / 3.80 / 4.40
LensC avg per LO: 4.10 / 3.80 / 4.20 / 4.00 / 4.30
Composite avg per LO: 4.08 / 3.76 / 4.26 / 4.04 / 4.52
Students at composite threshold (≥3.5): 26–29 of 30 per LO
Divergence flags: 3 ⚠, 3 ↑, 24 ✓
```

### Master Project List (5 records)
```
All Kansas-based: Yes / All first-time clients (new)
Client Sat: 4.5, 4.2, 4.8, 3.9, 4.6
Client Y/N Checklist scores: 4.5, 4.0, 5.0, 3.5, 4.5
On-time: 4 of 5 (Delta at risk)
Total Est. Value: $189,000
```

### Weekly Task Reports (360 expected records)
```
Submission rate: 91%
Avg hours/student/week client work: 12.6
```

### Success Stories / Career Outcomes
```
Placed: 17 of 30
Disclosed salary: 14 of 17
Salary avg: $62,400, range: $47K–$73K
```

---

## Build Sequence for Beth

| Step | Action | Est. Time |
|---|---|---|
| 1 | Connect Power BI to all SharePoint lists (including new Deliverable Quality Scores + Peer Nominations) | 45 min |
| 2 | Build calculated columns (LensA/B/C per LO, Composite, DivergenceFlag) | 45 min |
| 3 | Write all DAX measures (updated list above) | 1 hr |
| 4 | Build Page 1 — Executive Overview | 1 hr |
| 5 | Build Page 2 — 3-Lens AACSB view (redesigned) | 1.5 hr |
| 6 | Build Page 3 — Career Outcomes | 45 min |
| 7 | Build Page 4 — Project Performance (add Client Y/N chart) | 1 hr |
| 8 | Build Page 5 — Operational Health (add scorecard flag row) | 45 min |
| 9 | Apply design system — Sydney & Naya | 1.5 hr |
| 10 | Add nav panel + semester/team slicers | 30 min |
| 11 | Publish to Power BI Service | 20 min |

**Total estimated build time: ~10 hours**

---

## SharePoint Connection Note

Resolve Open Question Q7 (unified vs. per-team task report list) in favor of a **single Tier 2 list** before building the Power BI model. This eliminates the need to UNION 5 separate lists in Power BI.

New lists to add to Operations Site:
- `Deliverable Quality Scores` — one row per deliverable per student, PM-entered
- `Peer Nominations` — aggregated only (no individual nominator data stored)
- `Knowledge Test Scores` — auto-populated from Microsoft Forms

---

*Specification updated 2026-03-29. Sample data is illustrative — replace with live SharePoint data before presenting to the Dean or Advisory Board.*
