# IMPACT Program — Power BI Dashboard Specification
## Design Document for Beth | Visual Support: Sydney & Naya

**Date:** 2026-03-29
**Audience:** Dean, Dean's Advisory Board, WSU Administration, AACSB, Kansas Legislature
**Scale:** 5 active projects × 30 enrolled students (Spring 2026 cohort)
**Data Sources:** SharePoint Lists (Student Roster, Master Project List, Weekly Task Reports, Success Stories)
**Tool:** Microsoft Power BI (connected to SharePoint via native connector)

---

## Dashboard Architecture — 5 Pages

| Page | Name | Primary Audience | Purpose |
|---|---|---|---|
| 1 | Executive Overview | Dean, Advisory Board | Headline story — program at a glance |
| 2 | Student Growth & AACSB Outcomes | Dean, AACSB, Faculty Liaison | Learning outcome achievement with skill deltas |
| 3 | Career Outcomes | Dean, Advisory Board, Legislature | Placements, salaries, career momentum |
| 4 | Project & Client Performance | Leadership, Advisory Board | Consulting delivery quality per team |
| 5 | Operational Health | Internal Leadership | Weekly cadence, submission rates, bottlenecks |

**Navigation:** Persistent left-side nav panel with IMPACT branding. Each page has a visible "Last Refreshed" timestamp in the footer (auto from Power BI).

---

## Data Model (SharePoint → Power BI)

```
Student Roster ──────────────────────────────────┐
 StudentID, Name, Major, Team, Cohort,             │
 Pre-Score, Post-Score, PM-Score,                  │
 Training_Complete, Status, Consent                │
        │                                          │
        │ (many-to-one on Team)                    │
        ▼                                          ▼
Master Project List ──── Success Stories
 ProjectID, Client, Sector, Kansas,               (StudentID, Outcome, Salary,
 Status, StartDate, EndDate_Plan,                  Employer, Date)
 EndDate_Actual, ClientSatScore,
 EstValueDelivered                                 │
        │                                          │
        ▼                                          │
Weekly Task Reports ◄──────────────────────────────┘
 StudentID, WeekEnding, HoursClient,
 HoursAdmin, HoursTraining,
 SubmissionTimestamp, ReviewedByPM
```

### Calculated Columns (add in Power BI)

```DAX
-- Skill Delta (aggregate across all 5 LOs)
SkillDelta = [Post_Assessment_Score] - [Pre_Assessment_Score]

-- Submission on time flag (within 24hr of Monday trigger)
OnTime = IF(WEEKDAY([SubmissionTimestamp]) = 2 AND
            HOUR([SubmissionTimestamp]) <= 23, 1, 0)

-- Deliverable on-time flag
OnTimeDelivery = IF([EndDate_Actual] <= [EndDate_Plan], 1, 0)

-- At threshold flag per student (PM Score >= 3.5)
AtThreshold = IF([PM_Evaluation_Score] >= 3.5, 1, 0)
```

### Key Measures (DAX)

```DAX
-- Program-level
Total Students = COUNTROWS('Student Roster')
Active Projects = COUNTROWS(FILTER('Master Project List', [Status] = "Active"))
Total Applied Hours = SUM('Weekly Task Reports'[HoursClient])
Estimated Value Delivered = SUM('Master Project List'[EstValueDelivered])

-- Skill growth
Avg Pre Score = AVERAGE('Student Roster'[Pre_Assessment_Score])
Avg Post Score = AVERAGE('Student Roster'[Post_Assessment_Score])
Avg Skill Delta = AVERAGE('Student Roster'[SkillDelta])
Pct Growth = DIVIDE([Avg Post Score] - [Avg Pre Score], [Avg Pre Score], 0)

-- AACSB thresholds
Cohort Achievement Rate =
    DIVIDE(
        COUNTROWS(FILTER('Student Roster', [PM_Evaluation_Score] >= 3.5)),
        [Total Students]
    )

-- Operational
Submission Rate =
    DIVIDE(
        COUNTROWS(FILTER('Weekly Task Reports', [OnTime] = 1)),
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
        COUNTROWS(FILTER('Success Stories', [OutcomeType] IN {"Full-Time Job", "Internship"})),
        [Total Students]
    )
Avg Starting Salary = AVERAGE('Success Stories'[StartingSalary])
```

---

## Page 1 — Executive Overview

**Design intent:** One glance should tell the Dean what IMPACT did this semester.
**Layout:** Full-width banner header → 5 KPI cards → 2 feature charts → 1 value story callout

---

### KPI Card Row (5 cards across the top)

| Card | Measure | Value (Sample) | Color Logic |
|---|---|---|---|
| Students Served | `Total Students` | **30** | Static — neutral brand color |
| Active Projects | `Active Projects` | **5** | Static — neutral |
| Avg Skill Growth | `Pct Growth` | **+24%** | Green if >10%, Yellow if 5–10%, Red if <5% |
| Client Satisfaction | `Avg ClientSatScore` | **4.3 / 5.0** | Green if ≥4.0, Yellow if 3.5–3.9, Red if <3.5 |
| Estimated Value Delivered | `Estimated Value Delivered` | **$189,000** | Static — always display with $ |

> **Value Delivered calculation basis (30 students × 5 projects):**
> 30 students × 12.6 hrs/week avg client work × 10 weeks × $50/hr = ~$189,000

---

### Chart 1 — Major Diversity Donut (center-left)

**Visual type:** Donut chart
**Field:** Student Roster → Major
**Legend labels:** Finance, MIS, Marketing, Management, Accounting, Economics, Other
**Purpose:** Shows cross-disciplinary reach of the program

**Sample data (30 students):**

| Major | Count | % |
|---|---|---|
| Finance | 7 | 23% |
| MIS | 6 | 20% |
| Marketing | 5 | 17% |
| Management | 5 | 17% |
| Accounting | 4 | 13% |
| Economics | 2 | 7% |
| Other | 1 | 3% |

---

### Chart 2 — Projects by Industry (horizontal bar, center-right)

**Visual type:** Horizontal bar chart
**Field:** Master Project List → IndustrySector
**Sort:** Descending by count

**Sample data (5 projects):**

| Industry | Projects |
|---|---|
| Healthcare | 2 |
| Finance | 1 |
| Nonprofit | 1 |
| Manufacturing | 1 |

---

### Callout Box — "The IMPACT Story in Numbers" (bottom, full width)

A styled text card (not a chart) — updated manually each semester. Example content:

> **30 graduate students** delivered **5 consulting engagements** to Kansas businesses this semester, logging an estimated **1,890 applied learning hours** and generating **~$189,000 in consulting value** for the state of Kansas — against a program cost that is a fraction of that figure.

Sydney / Naya: this box should use the Barton School brand yellow (#FFC82E) as the background accent. Font: Proxima Nova or WSU brand equivalent.

---

## Page 2 — Student Growth & AACSB Outcomes

**Design intent:** Show the "before and after" story for each learning outcome. This is the page the accreditation reviewer cares most about.
**Layout:** Header row of 5 outcome gauges → clustered bar chart → delta table → achievement rate summary

---

### Visual 1 — Pre vs. Post by Learning Outcome (clustered bar chart)

**Visual type:** Clustered bar chart (grouped)
**X-axis:** Learning Outcome (LO1–LO5)
**Y-axis:** Score (1–5 scale)
**Series:** Pre-Assessment Avg (gray) vs. Post-Assessment Avg (Barton yellow)
**Data labels:** On each bar, show the value

**Sample data (30 students):**

| LO | Competency | Pre Avg | Post Avg | Delta | % Growth |
|---|---|---|---|---|---|
| LO1 | Professional Communication | 3.2 | 4.1 | +0.9 | **+28%** |
| LO2 | Analytical & Critical Thinking | 2.9 | 3.8 | +0.9 | **+31%** |
| LO3 | Project Mgmt & Professionalism | 3.4 | 4.2 | +0.8 | **+24%** |
| LO4 | Applied Business Knowledge | 3.1 | 4.0 | +0.9 | **+29%** |
| LO5 | Ethical & Stakeholder Awareness | 3.6 | 4.3 | +0.7 | **+19%** |
| **Overall** | **All 5 domains** | **3.24** | **4.08** | **+0.84** | **+26%** |

**Note for Beth:** Add a dashed horizontal reference line at Y = 3.5 (the achievement threshold). Any Post bar that reaches or clears this line is an AACSB pass.

---

### Visual 2 — Cohort Achievement Rate Gauge per LO (5 gauge visuals)

**Visual type:** KPI gauge or simple scorecard card (5 arranged in a row)
**Measure:** `Cohort Achievement Rate` per LO (filtered)
**Target line:** AACSB target (80% for LO1–LO4; 85% for LO3; 90% for LO5)
**Color:** Green ≥ target, Yellow within 5% below, Red > 5% below target

**Sample data:**

| LO | Achievement Rate | Target | Status |
|---|---|---|---|
| LO1 | 87% | 80% | Green |
| LO2 | 83% | 80% | Green |
| LO3 | 90% | 85% | Green |
| LO4 | 80% | 80% | Green (borderline) |
| LO5 | 93% | 90% | Green |

---

### Visual 3 — Individual Skill Delta Distribution (histogram)

**Visual type:** Histogram (bin width = 0.5)
**Field:** Student Roster → SkillDelta
**X-axis:** Skill delta value (−0.5 to +3.0)
**Y-axis:** Count of students
**Purpose:** Shows that the majority of students improved; highlights outliers

**Reference line:** Vertical line at delta = 0 (no change). Students to the right = improved.

**Sample distribution (30 students):**

| Delta Range | # Students |
|---|---|
| −0.5 to 0.0 | 1 |
| 0.0 to 0.5 | 2 |
| 0.5 to 1.0 | 7 |
| 1.0 to 1.5 | 12 |
| 1.5 to 2.0 | 6 |
| 2.0+ | 2 |

> **Headline stat:** 29 of 30 students (97%) showed positive skill growth. Median delta: +1.1 points.

---

### Visual 4 — PM Evaluation Score by Team (box plot or dot plot)

**Visual type:** Bar chart with error bars, or scatter plot
**X-axis:** Team name (Team 1–5)
**Y-axis:** PM Evaluation Score (1–5)
**Show:** Average per team + individual dots overlaid
**Reference line:** 3.5 threshold

---

## Page 3 — Career Outcomes

**Design intent:** The most "boardroom-ready" page. Show that IMPACT produces career results.
**Layout:** 3 KPI cards → placement funnel → salary distribution → employer map (if Kansas coverage relevant)

---

### KPI Cards (3 cards)

| Card | Measure | Sample Value | Notes |
|---|---|---|---|
| Students with Placement | `Placement Rate` | **17 of 30 (57%)** | Includes internships + FT offers |
| Avg Starting Salary | `Avg Starting Salary` | **$62,400** | Voluntary disclosure subset |
| Net Promoter (Recommend Rate) | % recommending IMPACT | **93%** | From focus group Module 4 |

---

### Visual 1 — Career Outcome Funnel

**Visual type:** Funnel chart
**Stages (top to bottom):**

| Stage | Count | Notes |
|---|---|---|
| Total Students | 30 | |
| Completed Semester | 29 | 1 departed |
| Actively Seeking (or placed) | 25 | 4 not seeking (graduating later) |
| Interview credited to IMPACT | 18 | From focus group data |
| Offer received | 17 | |
| Full-time offer | 10 | |
| Internship | 7 | |

**Purpose for the Dean:** Shows conversion rate from enrollment to placement.

---

### Visual 2 — Placement Type Breakdown (donut)

**Visual type:** Donut
**Field:** Success Stories → OutcomeType

| Outcome | Count |
|---|---|
| Full-Time Job | 10 |
| Internship | 7 |
| Actively Seeking | 8 |
| Not Seeking (graduation later) | 4 |
| Departed | 1 |

---

### Visual 3 — Starting Salary Distribution (histogram + reference lines)

**Visual type:** Histogram (bin = $5,000)
**Note:** Only students who voluntarily disclosed (sample = 14 of 17 placed)

| Salary Bin | Count |
|---|---|
| $45,000–$50,000 | 1 |
| $50,000–$55,000 | 3 |
| $55,000–$60,000 | 3 |
| $60,000–$65,000 | 4 |
| $65,000–$70,000 | 2 |
| $70,000–$80,000 | 1 |

**Reference lines:**
- Vertical: WSU/Barton median starting salary benchmark (if available from career services)
- Average line annotation: $62,400

---

### Visual 4 — Time to Placement Scatter

**Visual type:** Scatter chart
**X-axis:** Weeks since IMPACT start
**Y-axis:** Starting salary (for placed students)
**Bubble size:** Not needed (keep simple)
**Purpose:** Shows that earlier engagers tend to place faster and higher

---

### Visual 5 — Employer/Industry Breakdown (horizontal bar)

**Visual type:** Horizontal bar chart
**X-axis:** Count of placements
**Y-axis:** Industry

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

**Design intent:** Show how each of the 5 projects performed. This is the team lead view.
**Layout:** Project summary table → client satisfaction scores → on-time delivery → estimated value delivered by project

---

### Visual 1 — Project Summary Table (matrix)

**Visual type:** Table / Matrix
**Rows:** One row per project

| Project | Client | Sector | Status | Start Date | End Date | On Time? | Client Sat | Value Delivered |
|---|---|---|---|---|---|---|---|---|
| Project Alpha | [Client A] | Healthcare | Active | Jan 15 | Apr 30 | On track | 4.5 | $42,000 |
| Project Beta | [Client B] | Finance | Active | Jan 15 | Apr 30 | On track | 4.2 | $38,500 |
| Project Gamma | [Client C] | Nonprofit | Active | Jan 22 | Apr 30 | On track | 4.8 | $35,000 |
| Project Delta | [Client D] | Manufacturing | Active | Jan 15 | Apr 30 | ⚠ At risk | 3.9 | $41,000 |
| Project Epsilon | [Client E] | Healthcare | Active | Feb 1 | Apr 30 | On track | 4.6 | $32,500 |

**Conditional formatting:**
- On Time = "On track" → green cell background
- On Time = "⚠ At risk" → yellow cell background
- Client Sat ≥ 4.0 → green; 3.5–3.9 → yellow; <3.5 → red

---

### Visual 2 — Client Satisfaction Comparison (bar chart)

**Visual type:** Horizontal bar chart, sorted descending
**X-axis:** Client Satisfaction Score (1–5)
**Y-axis:** Project name
**Reference line:** 4.0 (achievement threshold)
**Color:** Bars green if ≥ 4.0, yellow if 3.5–3.9, red if < 3.5

---

### Visual 3 — Value Delivered by Project (bar chart)

**Visual type:** Bar chart
**X-axis:** Project name
**Y-axis:** Estimated Value Delivered ($)
**Total annotated:** $189,000 above the chart as a callout
**Sub-note:** "Based on team hours × $50/hr market rate proxy (pending leadership approval per V14)"

---

### Visual 4 — Applied Learning Hours by Week (line chart)

**Visual type:** Multi-line chart
**X-axis:** Week number (Week 1–15)
**Y-axis:** Total client hours logged
**Series:** One line per team
**Purpose:** Shows engagement trajectory — dips signal potential issues early

**Sample pattern:**
- Weeks 1–2: Ramp-up (lower hours, onboarding)
- Weeks 3–12: Core execution (peak hours)
- Weeks 13–15: Wind-down / reporting

---

### Visual 5 — Team Size vs. Value Delivered (scatter)

**Visual type:** Scatter chart
**X-axis:** Team size (# students)
**Y-axis:** Estimated value delivered
**Bubble label:** Project name
**Purpose:** Check if larger teams deliver proportionally more value

---

## Page 5 — Operational Health

**Design intent:** Internal leadership page. Surface bottlenecks before they become problems.
**Layout:** 3 KPI cards → submission rate trend → onboarding funnel → open items flag

---

### KPI Cards (3)

| Card | Measure | Sample Value | Color Logic |
|---|---|---|---|
| Weekly Report Submission Rate | `Submission Rate` | **91%** | Green ≥ 90%, Yellow 80–89%, Red <80% |
| Training Completion Rate | `Training Complete Rate` | **97%** (29/30) | Green ≥ 90% |
| Avg Onboarding Days | `Avg Days to Onboard` | **3.4 days** | Green ≤ 5 days (target) |

---

### Visual 1 — Weekly Submission Rate Trend (line chart)

**Visual type:** Line chart with area fill below
**X-axis:** Week (1–current)
**Y-axis:** Submission rate (0–100%)
**Reference line:** 90% target (dashed horizontal)
**Color zones:** Fill green above 90%, yellow 80–90%, red below 80%

**Sample data (12 weeks):**

| Week | Submission Rate |
|---|---|
| 1 | 87% |
| 2 | 90% |
| 3 | 93% |
| 4 | 97% |
| 5 | 93% |
| 6 | 90% |
| 7 | 100% |
| 8 | 93% |
| 9 | 87% |
| 10 | 90% |
| 11 | 97% |
| 12 | 93% |

---

### Visual 2 — Submission Rate by Team (clustered bar, current week)

**Visual type:** Horizontal bar chart
**X-axis:** Submission rate %
**Y-axis:** Team name
**Reference line:** 90%
**Purpose:** Identify which specific team is lagging — actionable for PM

---

### Visual 3 — Onboarding Funnel

**Visual type:** Funnel or horizontal stacked bar
**Stages:**

| Stage | Count | % of 30 |
|---|---|---|
| HR Clearance Received | 30 | 100% |
| Welcome Email Sent | 30 | 100% |
| Onboarding Form Submitted | 29 | 97% |
| Access Provisioned | 29 | 97% |
| SOP Training Completed | 29 | 97% |
| Onboarding Complete | 28 | 93% |

---

### Visual 4 — Hours Distribution: Client vs. Admin vs. Training (stacked area)

**Visual type:** Stacked area chart
**X-axis:** Week
**Y-axis:** Total hours
**Series:** Client Work (brand yellow), Admin/Coordination (gray), Training (light blue)
**Purpose:** Show that admin overhead decreases as semester progresses (operational efficiency trend)

---

### Visual 5 — Open Items Flag (table)

**Visual type:** Simple table with conditional formatting
**Purpose:** Surfaces students or items needing attention before they become a problem

| Flag Type | Count | Detail |
|---|---|---|
| Missing submission this week | 2 | Student names (ops only — filter by permission) |
| Onboarding incomplete > 7 days | 1 | 1 student |
| PM evaluation not yet submitted | 0 | — |
| Client feedback pending | 1 | Project Delta |

---

## Design Specifications for Sydney & Naya

### Color Palette

| Element | Hex | Usage |
|---|---|---|
| Primary — Barton Yellow | `#FFC82E` | Positive bars, KPI accents, "Post" series, header highlights |
| Secondary — WSU Black | `#231F20` | Text, axis labels, table headers |
| Positive (Green) | `#2E8B57` | "On target," achievement met |
| Warning (Amber) | `#E8A020` | Near threshold, at risk |
| Negative (Red) | `#C0392B` | Below threshold, late |
| Neutral Gray | `#8C8C8C` | "Pre" series, background bars, secondary text |
| Light Background | `#F9F7F2` | Page background |
| Card Background | `#FFFFFF` | KPI cards, chart backgrounds |

### Typography

| Element | Font | Size | Weight |
|---|---|---|---|
| Page title | Barton/WSU brand font or Segoe UI | 20pt | Bold |
| Section header | Segoe UI | 14pt | SemiBold |
| KPI card value | Segoe UI | 36pt | Bold |
| KPI card label | Segoe UI | 11pt | Regular |
| Chart axis labels | Segoe UI | 10pt | Regular |
| Data table text | Segoe UI | 11pt | Regular |
| Footer / footnote | Segoe UI | 9pt | Regular, Italic |

### Layout Grid (each page)

```
┌─────────────────────────────────────────────────────────┐
│  [Left Nav]  │  [Page Title + Semester Badge]           │
│              │  [Last Refreshed]                         │
│  • Pg 1      ├─────────────────────────────────────────  │
│  • Pg 2      │  [KPI Card 1] [KPI Card 2] [KPI Card 3] │
│  • Pg 3      │  [KPI Card 4] [KPI Card 5]               │
│  • Pg 4      ├────────────────────┬────────────────────  │
│  • Pg 5      │  [Chart A]         │  [Chart B]          │
│              │                    │                      │
│  IMPACT Logo │                    │                      │
│              ├────────────────────┴────────────────────  │
│              │  [Chart C — full width]                  │
│              ├─────────────────────────────────────────  │
│              │  [Footer: Data sources | Refresh date]   │
└─────────────────────────────────────────────────────────┘
```

### Page-level Filters (persistent across all pages)

- **Semester Cohort** slicer — defaults to current semester
- **Team Name** slicer — allows drilling into one team
- Both slicers appear as pill-style buttons in the top right corner of every page

---

## Data Entry Assumptions (Spring 2026 Baseline)

This sample data is calibrated to 30 students × 5 projects. Use these figures to validate the dashboard during build; replace with live SharePoint data before presenting.

### Student Roster (30 records)

```
Teams: Alpha (6), Beta (6), Gamma (6), Delta (6), Epsilon (6)
Status distribution: 29 Active, 1 Completed
Training Completed: 29 Yes, 1 No
Pre-Assessment Score: Mean 3.24, SD 0.4, Range 2.2–4.0
Post-Assessment Score: Mean 4.08, SD 0.3, Range 3.1–4.8
PM Evaluation Score: Mean 3.9, SD 0.45, Range 2.8–5.0
Students at PM threshold (≥3.5): 26 of 30 (87%)
```

### Master Project List (5 records)

```
All 5 Kansas-based: Yes
All 5 Repeat Client: No (first semester — all new)
Client Sat Scores: 4.5, 4.2, 4.8, 3.9, 4.6
On-Time Delivery: 4 of 5 (Delta at risk)
Total Est. Value Delivered: $189,000
```

### Weekly Task Reports (30 students × 12 weeks = 360 expected records)

```
Avg hours/student/week (client work): 12.6
Avg hours/student/week (admin): 2.1
Avg hours/student/week (training): 0.8 (front-loaded in weeks 1–2)
Submission rate: 91% (328 of 360 submitted on time)
```

### Success Stories / Career Outcomes (17 placed of 30)

```
Full-time offers: 10
Internships: 7
Voluntarily disclosed salary: 14 of 17
Disclosed salary range: $47,000–$73,000
Disclosed salary average: $62,400
```

---

## Build Sequence for Beth

| Step | Action | Time Estimate |
|---|---|---|
| 1 | Connect Power BI Desktop to SharePoint (Student Roster, Master Project List, Weekly Task Reports, Success Stories) | 30 min |
| 2 | Build calculated columns (SkillDelta, OnTime, AtThreshold, OnTimeDelivery) | 20 min |
| 3 | Write all 12 DAX measures | 45 min |
| 4 | Build Page 1 — Executive Overview | 1 hr |
| 5 | Build Page 2 — AACSB Outcomes | 1 hr |
| 6 | Build Page 3 — Career Outcomes | 45 min |
| 7 | Build Page 4 — Project Performance | 45 min |
| 8 | Build Page 5 — Operational Health | 45 min |
| 9 | Apply design system (palette, fonts, layout grid) — Sydney & Naya | 1.5 hr |
| 10 | Add persistent nav panel + Semester/Team slicers | 30 min |
| 11 | Publish to Power BI Service → share link with Leadership | 20 min |
| 12 | Validate with live data when SharePoint is populated | ongoing |

**Total estimated build time: ~8 hours**

---

## SharePoint Connection Note

In Power BI Desktop:
1. Get Data → SharePoint Online List
2. Paste the Operations Team Site URL
3. Connect to: Student Roster, Master Project List, Onboarding Tracker
4. Repeat for each Team Site to get Weekly Task Reports (or consolidate into a unified Tier 2 list if Q7 resolves that way — recommended for Power BI simplicity)
5. Hub Site → Success Stories

> **Recommended:** Resolve Open Question Q7 (unified vs. per-team list) in favor of a **single Tier 2 list** before building the Power BI model. This eliminates the need to UNION 5 separate task report lists in Power BI and dramatically simplifies the data model.

---

*This specification was prepared for the Spring 2026 semester. All sample data is illustrative — replace with live SharePoint data before presenting to the Dean or Advisory Board.*
