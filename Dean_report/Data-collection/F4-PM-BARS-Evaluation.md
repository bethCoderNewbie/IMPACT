# F4 — PM BARS Evaluation
## Microsoft Forms Specification

**Form title:** IMPACT — Project Manager End-of-Semester Evaluation (BARS)
**Subtitle:** Complete one evaluation per student on your team. Check only behaviors you personally observed — do not estimate. If you are unsure, leave it unchecked. This replaces the 1–5 rating scale with a checklist of observable behaviors.
**Administered:** Final week of semester (Week 14–15)
**Sent by:** Operations — PM-only link (one link per PM; PM submits once per student)
**Recipient:** Project Manager only
**SharePoint destination:** Student Roster — Tier 2 (updates PM_BARS_Score fields per student)
**Estimated completion time:** 8–10 minutes per student

---

## Section 1 — Evaluation Identity
*Header text: "Fill out one form per student. Submit separately for each person."*

| Q# | Question Text | Type | Required | Options | SharePoint Field |
|---|---|---|---|---|---|
| 1 | Your name (Project Manager) | TEXT-S | Yes | — | PM_Name |
| 2 | Your WSU email | TEXT-S | Yes | — | PM_Email |
| 3 | Which project team are you evaluating? | MC | Yes | Alpha / Beta / Gamma / Delta / Epsilon | Team |
| 4 | Which student are you evaluating? | MC | Yes | [Student names on this team — pre-populated by Operations] | Student_Evaluated |
| 5 | Semester | MC | Yes | Spring 2026 / Fall 2026 / ... | Semester |

---

## Section 2 — LO1: Professional Communication
*Header text: "Check every behavior below that you personally observed this student demonstrate this semester. Leave unchecked if you did not observe it — not observed ≠ did not happen, it means you cannot confirm it."*

| Q# | Observed Behavior | Type | Required | SharePoint Field |
|---|---|---|---|---|
| 6 | The student submitted ≥90% of weekly task reports on time. *(Check your records before answering.)* | YN | Yes | BARS_LO1_Q1 |
| 7 | Zero of the student's deliverables were returned for major content revision. *(Formatting issues do not count — this is about content clarity.)* | YN | Yes | BARS_LO1_Q2 |
| 8 | The student initiated at least one client or PM update without being explicitly prompted or reminded. | YN | Yes | BARS_LO1_Q3 |
| 9 | The student presented to the client or PM without requiring excessive coaching or prompting beforehand. | YN | Yes | BARS_LO1_Q4 |
| 10 | The student's written deliverables required ≤1 revision cycle to reach an acceptable clarity standard. | YN | Yes | BARS_LO1_Q5 |

*Score calculation (Power Automate): LO1_BARS_Score = (sum of Yes answers / 5) × 5*

---

## Section 3 — LO2: Analytical & Critical Thinking
*Header text: "Check every behavior you personally observed."*

| Q# | Observed Behavior | Type | Required | SharePoint Field |
|---|---|---|---|---|
| 11 | At least one of this student's deliverables cited a named business framework, theory, or research source. | YN | Yes | BARS_LO2_Q1 |
| 12 | This student's recommendations addressed root causes — not just surface symptoms of the client's problem. | YN | Yes | BARS_LO2_Q2 |
| 13 | When questioned by you or the client, this student defended their reasoning without immediately abandoning their position. | YN | Yes | BARS_LO2_Q3 |
| 14 | This student identified at least one issue or opportunity that the PM or client had not already raised. | YN | Yes | BARS_LO2_Q4 |

*Score: LO2_BARS_Score = (sum / 4) × 5*

---

## Section 4 — LO3: Project Management & Professionalism
*Header text: "Check every behavior you personally observed."*

| Q# | Observed Behavior | Type | Required | SharePoint Field |
|---|---|---|---|---|
| 15 | This student's weekly report submission rate was ≥85%. *(This is auto-calculated — confirm it matches your experience.)* | YN | Yes | BARS_LO3_Q1 |
| 16 | This student met all agreed deadlines without requiring a reminder from you. | YN | Yes | BARS_LO3_Q2 |
| 17 | This student flagged at least one blocker or concern proactively — before a deadline was already missed. | YN | Yes | BARS_LO3_Q3 |
| 18 | This student consistently responded to your messages or requests within 24 hours. | YN | Yes | BARS_LO3_Q4 |

*Score: LO3_BARS_Score = (sum / 4) × 5*

---

## Section 5 — LO4: Applied Business Knowledge
*Header text: "Check every behavior you personally observed."*

| Q# | Observed Behavior | Type | Required | SharePoint Field |
|---|---|---|---|---|
| 19 | This student referenced discipline-specific knowledge from their major or coursework — unprompted — in at least one deliverable or discussion. | YN | Yes | BARS_LO4_Q1 |
| 20 | The client directly noted or commented (verbally or in writing) on this team's knowledge quality. | YN | Yes | BARS_LO4_Q2 |
| 21 | When asked, this student could clearly articulate how their coursework connected to the project work. | YN | Yes | BARS_LO4_Q3 |

*Score: LO4_BARS_Score = (sum / 3) × 5*

---

## Section 6 — LO5: Ethical & Stakeholder Awareness
*Header text: "Check every behavior you personally observed."*

| Q# | Observed Behavior | Type | Required | SharePoint Field |
|---|---|---|---|---|
| 22 | This student completed the required SOP training by the Week 2 deadline. *(Check Onboarding Tracker before answering.)* | YN | Yes | BARS_LO5_Q1 |
| 23 | This student had zero confidentiality, conduct, or data handling violations during the semester. | YN | Yes | BARS_LO5_Q2 |
| 24 | This student proactively raised at least one ethically relevant question or concern during the semester. | YN | Yes | BARS_LO5_Q3 |

*Score: LO5_BARS_Score = (sum / 3) × 5*

---

## Section 7 — Open-Ended PM Observations
*Header text: "These responses are used to build the Dean's Report narrative and to coach students. They are not scored."*

| Q# | Question Text | Type | Required | Notes | Use |
|---|---|---|---|---|---|
| 25 | Describe one specific moment this semester where this student exceeded your expectations. | TEXT-L | No | Optional but encouraged | Dean's report narrative |
| 26 | Describe one area where this student should focus for growth next semester. | TEXT-L | No | Not shared with student without their awareness | PM coaching notes |
| 27 | Is there anything about this student's performance you would like Operations or Faculty to know? | TEXT-L | No | — | Escalation / recognition flag |
| 28 | Would you recommend this student to a business partner or employer if asked? | MC | No | Strongly yes / Yes / With reservations / No | Employer recommendation proxy |

---

## Section 8 — Evaluation Completion Confirmation

| Q# | Question Text | Type | Required | Notes |
|---|---|---|---|---|
| 29 | I confirm that my responses above reflect behaviors I personally observed, to the best of my knowledge. | MC | Yes | Yes, I confirm / I need to review my notes and resubmit |

---

## Power Automate: On F4 Submission

```
Trigger: F4 submitted
  → Match student by name + team → find row in Student Roster
  → Calculate BARS scores per LO:
      LO1_BARS = (sum BARS_LO1_Q1-Q5) / 5 × 5
      LO2_BARS = (sum BARS_LO2_Q1-Q4) / 4 × 5
      LO3_BARS = (sum BARS_LO3_Q1-Q4) / 4 × 5
      LO4_BARS = (sum BARS_LO4_Q1-Q3) / 3 × 5
      LO5_BARS = (sum BARS_LO5_Q1-Q3) / 3 × 5
  → Update Student Roster: PM_BARS_LO1 through PM_BARS_LO5
  → Notify Operations: "PM evaluation submitted for [Student Name] by [PM Name]"
  → If all students on this team now have F4 submitted → notify Faculty Liaison
```

---

## Operations Reminder Workflow

```
Trigger: Week 14 Monday
  → Check Student Roster: which students do NOT yet have PM_BARS_LO1 populated?
  → Send PM reminder email for each student missing evaluation
  → Repeat: Week 15 Wednesday (final reminder)
  → Alert Operations if any PM has not submitted by Week 15 Friday
```

---

## Form Settings

| Setting | Value |
|---|---|
| Who can fill out | Specific people in my organization (PM accounts only) |
| Response receipt | Off |
| Show results | Off |
| One response per person | No *(PM submits once per student — multiple submissions needed)* |
| Start date | Week 14 Monday |
| End date | Week 15 Friday |
| Confirmation message | "Evaluation submitted for [student name]. Please return to the form to evaluate your next team member." |

---

## BARS Scoring Reference Card (include in PM briefing email)

> **How to use this form:** Check only behaviors you actually saw. A student not getting a check is not a failure — it means you didn't observe that specific behavior. The score is the count of checks divided by the total, scaled to 5. A student who gets 4 of 5 LO1 behaviors checked scores a 4.0.
>
> **Why this replaces the old 1–5 rating:** Two PMs rating the same student on a 1–5 scale often score differently because they have different internal benchmarks for what a "4" means. With a checklist, two PMs who observed the same behaviors will get the same score.
>
> **Important:** Do NOT look at the student's self-assessment scores before completing this form. Your evaluation should be independent.
