# IMPACT Program — Objective Measurement Framework
## 3-Lens Composite Scoring System for AACSB & Dean's Report

**Date:** 2026-03-29
**Replaces:** Pure self-assessment scoring in the AACSB Learning Outcomes framework
**Purpose:** Reduce self-evaluation bias while maintaining AACSB pre/post evidence requirements
**Applies to:** All 5 Learning Outcomes (LO1–LO5) across 30 students / 5 projects

---

## Why This Framework Exists

Self-assessed Likert ratings (1–5, pre and post) suffer from three documented biases:

| Bias | Effect on Data |
|---|---|
| **Dunning-Kruger** | Low performers overestimate; high performers underestimate |
| **Social desirability** | Students rate up to look engaged and growth-oriented |
| **Gaming** | Easy to inflate delta by rating low on pre and high on post |

These biases make the "skill delta" number unreliable for the Dean's Advisory Board and vulnerable to challenge from AACSB reviewers. This framework does not eliminate self-assessment — it demotes it to 20% weight and adds two corroborating lenses that cannot be gamed.

---

## The 3-Lens Model

Each Learning Outcome produces one **Composite Score (0–5)** drawn from three independent lenses:

```
┌─────────────────────────────────────────────────────────────┐
│                   COMPOSITE SCORE (0–5)                     │
│                                                             │
│   Lens A (40%)          Lens B (40%)        Lens C (20%)   │
│   BEHAVIORAL            OBSERVER-RATED      SELF-REPORTED  │
│                                                             │
│   What did the          What did others      What does the  │
│   student DO?           OBSERVE?             student THINK? │
│                                                             │
│   • Timestamps          • PM BARS rubric     • Pre/Post     │
│   • Submission rate     • Peer nominations     confidence   │
│   • Deliverable         • Client Y/N           rating       │
│     quality checklist     checklist          • Knowledge    │
│   • SOP completion                             test score   │
└─────────────────────────────────────────────────────────────┘
```

### Composite Formula

```
LO_Composite = (Lens_A_Score × 0.4) + (Lens_B_Score × 0.4) + (Lens_C_Score × 0.2)
```

### Divergence Flags (Power BI — auto-calculated)

```
Lens_C minus Avg(Lens_A, Lens_B) > 1.0  →  ⚠  Self-overrating
Avg(Lens_A, Lens_B) minus Lens_C > 1.0  →  ↑  Underestimates growth
All three lenses within 1.0 of each other →  ✓  Aligned
```

A divergence flag is not a punishment — it is data quality information. A student who is ⚠ may need coaching on self-awareness. A student who is ↑ may need encouragement.

**AACSB note:** The pre/post evidence requirement is satisfied by Lens C (knowledge test delta + confidence rating delta). Lens A and B provide corroborating evidence of the same growth — which is stronger than self-assessment alone.

---

## Lens A — Behavioral Indicators

Derived entirely from existing SharePoint data. No new manual data entry required.

| LO | Behavioral Metric | Data Source | Calculation | Score (0–5) |
|---|---|---|---|---|
| LO1 Communication | % of weekly reports NOT flagged as incomplete by PM | Weekly Task Reports — Reviewed by PM | (Non-flagged / Total) × 5 | Linear |
| LO2 Analytical | Avg deliverable quality checklist score | Deliverable Quality Scorecard (new) | Avg(checklist %) × 5 | Linear |
| LO3 Professionalism | Blended submission + on-time delivery rate | Task Reports + Master Project List | ((Sub rate + Delivery rate) / 2) × 5 | Linear |
| LO4 Applied Knowledge | Client satisfaction — "usefulness" item only | Client Feedback Form Q1 | Direct 1–5 | Direct |
| LO5 Ethics | SOP completion + zero violations | Onboarding Tracker + Violation log | Both = 5 / One = 2.5 / Neither = 0 | Step |

### Deliverable Quality Scorecard

PM completes this checklist **per deliverable**, for each student who contributed to it. This is the primary Lens A input for LO2.

**Administered:** Upon PM review of each deliverable
**Scored by:** Project Manager
**Tool:** Microsoft Forms (PM-only link, one response per deliverable per student)

| Item | Observable Standard | Y / N |
|---|---|---|
| 1 | Executive summary or overview section is present | |
| 2 | At least one recommendation is supported by data, research, or a named business framework | |
| 3 | Action items specify a responsible owner AND a date | |
| 4 | Formatting meets professional standard: no spelling errors, clean layout, consistent fonts | |
| 5 | The deliverable answers the client's stated question or scope of work | |

**Score per deliverable** = (Y count / 5) × 5
**Student's LO2 Lens A score** = average across all deliverables they contributed to that semester

---

## Lens B — Observer-Rated Indicators

### Part 1: PM BARS Rubric (Behaviorally Anchored Rating Scales)

Replaces the impressionistic 1–5 rubric. PM checks observable behaviors — no subjective rating required. Score = checked items / total items per LO × 5.

**Administered:** Final week of semester
**Tool:** Microsoft Forms (PM-only link, one submission per student)

---

#### LO1 — Professional Communication
*(5 behaviors → max score = 5.0)*

| # | Observed Behavior | Check if Yes |
|---|---|---|
| 1 | Student submitted ≥90% of weekly task reports on time | [ ] |
| 2 | Zero deliverables were returned for major content revision (formatting issues excluded) | [ ] |
| 3 | Student initiated at least one client or PM update without being explicitly prompted | [ ] |
| 4 | Student presented to the client or PM without excessive prompting or coaching | [ ] |
| 5 | Student's written deliverables required ≤1 revision cycle for clarity | [ ] |

**LO1 BARS Score** = (# checked / 5) × 5

---

#### LO2 — Analytical & Critical Thinking
*(4 behaviors → max score = 5.0)*

| # | Observed Behavior | Check if Yes |
|---|---|---|
| 1 | At least one deliverable cites a named business framework, theory, or research source | [ ] |
| 2 | Recommendations address root causes, not just surface symptoms | [ ] |
| 3 | Student defended their reasoning when questioned without immediately abandoning their position | [ ] |
| 4 | Student identified at least one issue or opportunity the PM or client had not raised | [ ] |

**LO2 BARS Score** = (# checked / 4) × 5

---

#### LO3 — Project Management & Professionalism
*(4 behaviors → max score = 5.0)*

| # | Observed Behavior | Check if Yes |
|---|---|---|
| 1 | Weekly report submission rate ≥85% (auto-populated from SharePoint) | [ ] |
| 2 | Student met all agreed deadlines without requiring a reminder from PM | [ ] |
| 3 | Student flagged blockers proactively — did not wait until a deadline was already missed | [ ] |
| 4 | Student responded to PM messages or requests within 24 hours consistently | [ ] |

**LO3 BARS Score** = (# checked / 4) × 5

---

#### LO4 — Applied Business Knowledge
*(3 behaviors → max score = 5.0)*

| # | Observed Behavior | Check if Yes |
|---|---|---|
| 1 | Student referenced discipline-specific knowledge (from their major or coursework) unprompted in at least one deliverable | [ ] |
| 2 | Client directly noted or commented on the team's knowledge quality | [ ] |
| 3 | When asked, student could clearly articulate how their coursework connects to the project work | [ ] |

**LO4 BARS Score** = (# checked / 3) × 5

---

#### LO5 — Ethical & Stakeholder Awareness
*(3 behaviors → max score = 5.0)*

| # | Observed Behavior | Check if Yes |
|---|---|---|
| 1 | Student completed SOP training by the Week 2 deadline (auto-populated) | [ ] |
| 2 | No confidentiality, conduct, or data handling violations during the semester | [ ] |
| 3 | Student proactively raised at least one ethically relevant question or concern | [ ] |

**LO5 BARS Score** = (# checked / 3) × 5

---

### Part 2: Peer Nomination (Anonymous)

**Purpose:** Capture how teammates perceive each other — removes self-serving bias entirely.
**Administered:** Final week of semester, anonymous
**Tool:** Microsoft Forms (student-facing, anonymous)
**Rule:** Each student selects one teammate per question. Cannot nominate themselves.

**Questions:**

| Q | Prompt | LO Mapped |
|---|---|---|
| 1 | "Which team member most clearly explained a complex business idea or concept this semester?" | LO1 + LO2 |
| 2 | "Which team member was the most reliable and professional throughout the semester?" | LO3 |
| 3 | "Which team member best connected knowledge from their coursework to the client's actual problem?" | LO4 |

**Scoring:**

```
Nomination count per student per question: 0 to (team size - 1)
Normalized peer score = (nominations received / max possible nominations) × 5
Max possible nominations per question = team size - 1 (e.g., 5 on a 6-person team)
```

Peer nomination score feeds into Lens B alongside the PM BARS score.

**Lens B composite per student:**
```
Lens_B = (PM BARS avg across applicable LOs × 0.6) + (Peer nomination avg × 0.4)
```
*(Client Y/N checklist is a team-level score; it adjusts LO4 Lens B for team members where the client feedback was particularly strong or weak)*

---

### Part 3: Client Behavioral Y/N Checklist

Replaces the general satisfaction survey with specific observable behaviors.
**Administered:** Within 2 weeks of project completion
**Tool:** Microsoft Forms (client-facing, post-project)
**Attributed to:** All team members (team-level score, not individual)

| # | Observed Behavior | Y / N |
|---|---|---|
| 1 | The team proactively updated us on project progress without our team needing to ask | |
| 2 | The team asked clarifying questions before starting work — they didn't assume | |
| 3 | Recommendations were grounded in evidence or data, not just opinion | |
| 4 | We would trust this team with a higher-stakes or more sensitive project | |
| 5 | The team respected confidentiality and professional boundaries throughout | |

**Score** = (Y count / 5) × 5 → applied to all team members' LO4 (items 1–4) and LO5 (item 5) Lens B scores as a team-level modifier.

---

## Lens C — Self-Reported (Retained for AACSB)

Lens C is now a **blended score** — half knowledge test, half confidence rating — to reduce pure self-report dependence.

### Pre/Post Confidence Rating (retained, unchanged)

Delivered via Microsoft Forms. 1–5 Likert per LO. Administered Day 1 (pre) and final week (post).
This is the existing self-assessment instrument — no change to the questions.

### Pre/Post Knowledge Test (new)

**Administered:** Day 1 (pre) and final week (post) — same timing as confidence rating
**Tool:** Microsoft Forms, 10 questions, scored automatically
**Format:** Multiple choice, one correct answer per question

**Content areas (2 questions each):**

| Area | Sample Question |
|---|---|
| Project management | "Which of the following best describes a project scope statement?" |
| Business communication | "An executive summary should be written for which audience: the analyst, the reviewer, or both?" |
| Analytical frameworks | "SWOT analysis categorizes factors as: internal/external AND positive/negative. True or false?" |
| Ethical reasoning | "A client asks you to omit data that makes their strategy look weak. Your best response is..." |
| Applied business | "Which financial metric best measures a business's short-term ability to pay debts?" |

**Score:** (Correct / 10) × 5 → stored as `Knowledge_Test_Score_Pre` and `Knowledge_Test_Score_Post`

### Lens C Composite Formula

```
Lens_C = (Knowledge_Test_Score × 0.5) + (Self_Confidence_Rating × 0.5)
```

**AACSB pre/post delta from Lens C:**
```
Lens_C_Delta = Lens_C_Post - Lens_C_Pre
```
This delta is still a valid pre/post growth metric — now reinforced by an objective test score, not just perception.

---

## Scoring Summary — Per Student, Per LO

| LO | Lens A (40%) | Lens B (40%) | Lens C (20%) | Composite |
|---|---|---|---|---|
| LO1 | Report flag rate | BARS + peer (communication) | Confidence + knowledge test | Weighted avg |
| LO2 | Deliverable quality score | BARS + peer (analytical) | Confidence + knowledge test | Weighted avg |
| LO3 | Submission + on-time rate | BARS (professionalism) | Confidence + knowledge test | Weighted avg |
| LO4 | Client usefulness score | BARS + peer (knowledge) + client Y/N | Confidence + knowledge test | Weighted avg |
| LO5 | SOP completion + violations | BARS + client Y/N (ethics item) | Confidence + knowledge test | Weighted avg |

**Achievement threshold** (AACSB reporting): Composite ≥ 3.5

---

## Cohort-Level Reporting (Power BI)

For the Dean's report and AACSB, report at the **cohort level**:

| Metric | Definition |
|---|---|
| Achievement Rate | % of students with Composite ≥ 3.5 per LO |
| Avg Composite Delta | Avg(Composite_Post − Composite_Pre) across cohort |
| Lens Alignment Rate | % of students where all 3 lenses are within 1.0 of each other (no ⚠ or ↑ flag) |
| Self-Overrating Rate | % of students flagged ⚠ (Lens C > Lens A+B avg by >1.0) |
| Growth Confirmed Rate | % of students where Lens A AND Lens B both increased post vs. pre |

---

## Implementation Checklist

| Step | Action | Owner | When |
|---|---|---|---|
| 1 | Add Deliverable Quality Scorecard form (Microsoft Forms, PM-only link) | Operations | Before Week 3 |
| 2 | Add Pre/Post Knowledge Test to onboarding and exit forms | Operations | Before cohort start |
| 3 | Replace PM Evaluation rubric with BARS version (this document) | Operations | Before Week 14 |
| 4 | Add Peer Nomination form (anonymous, student-facing) | Operations | Week 14–15 |
| 5 | Update Client Feedback form with Y/N behavioral checklist | Operations | Before first project close |
| 6 | Update Power BI data model with new columns and DAX measures | Beth | After SharePoint lists updated |
| 7 | Brief PMs on BARS rubric — emphasize "check only what you observed" | Leadership | Before Week 14 |
| 8 | Add knowledge test questions to Microsoft Forms | Operations | Before cohort start |

---

*This framework is designed to be AACSB-defensible (pre/post Lens C delta preserved) while producing data credible enough for the Dean's Advisory Board (Lens A behavioral evidence + Lens B independent observer ratings). All instruments are native Microsoft 365 tools — no additional software or cost required.*
