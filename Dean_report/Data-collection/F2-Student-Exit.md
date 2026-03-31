# F2 — Student Exit Form
## Microsoft Forms Specification

**Form title:** IMPACT Program — End-of-Semester Assessment & Career Outcomes
**Subtitle:** You made it! Complete this form in your final week. It takes about 10 minutes and captures your growth over the semester. Your honest responses help us improve the program for future students.
**Administered:** Final week of semester (Week 15)
**Sent by:** Operations team manually
**Recipient:** Student only
**SharePoint destination:** Student Roster — Tier 2 Operations Site (updates existing row)
**Estimated completion time:** 8–10 minutes
**Prerequisite:** Student must have completed F1 (Onboarding Form) — used for pre/post comparison

---

## Section 1 — Identity Confirmation
*Header text: "Let's confirm who you are so we can match your exit scores to your entry scores."*

| Q# | Question Text | Type | Required | Notes | SharePoint Field |
|---|---|---|---|---|---|
| 1 | Your full name | TEXT-S | Yes | Must match F1 entry | Student Name (lookup) |
| 2 | Your WSU email address | TEXT-S | Yes | Used to match to Student Roster row | WSU Email (key) |
| 3 | Your IMPACT team | MC | Yes | [Team names] | Team Assignment (confirm) |

---

## Section 2 — Post-Assessment: Self-Confidence Ratings (Lens C)
*Header text: "Rate your confidence NOW — after a full semester in IMPACT. Use the same scale as when you started: 1 = Not at all confident, 5 = Very confident."*
*Instruction: "Answer based on how you feel today, not how you felt in Week 1."*

| Q# | Question Text | Type | Required | Scale | LO | SharePoint Field |
|---|---|---|---|---|---|---|
| 4 | How confident are you NOW in your ability to communicate professionally in writing to a business audience? | RATE | Yes | 1–5 | LO1 | Post_Confidence_LO1 |
| 5 | How confident are you NOW in your ability to analyze a business problem and develop evidence-based recommendations? | RATE | Yes | 1–5 | LO2 | Post_Confidence_LO2 |
| 6 | How confident are you NOW in your ability to manage your time, meet deadlines, and hold yourself accountable professionally? | RATE | Yes | 1–5 | LO3 | Post_Confidence_LO3 |
| 7 | How well can you NOW apply concepts from your business courses to solve real-world client problems? | RATE | Yes | 1–5 | LO4 | Post_Confidence_LO4 |
| 8 | How aware are you NOW of your ethical obligations to clients, teammates, and your institution? | RATE | Yes | 1–5 | LO5 | Post_Confidence_LO5 |

---

## Section 3 — Post-Assessment: Knowledge Test (Lens C — Objective)
*Header text: "The same 10-question quiz from your first day. Give your best answer — your improvement on this quiz is part of how we measure your growth."*

*Use identical questions as F1 Q13–Q22. Present in same order. DO NOT tell students the correct answers — scores are calculated by Power Automate after submission.*

| Q# | Question Text | Type | Required | Correct Answer | LO |
|---|---|---|---|---|---|
| 9 | A project scope statement primarily describes: | MC | Yes | A | LO1 |
| 10 | An executive summary is written primarily for: | MC | Yes | B | LO1 |
| 11 | A SWOT analysis categorizes factors as: | MC | Yes | C | LO2 |
| 12 | When analyzing a business problem, identifying "root causes" rather than "symptoms" means: | MC | Yes | B | LO2 |
| 13 | Which behavior best demonstrates professional project management? | MC | Yes | A | LO3 |
| 14 | A Gantt chart is used to: | MC | Yes | C | LO3 |
| 15 | Porter's Five Forces is a framework used to analyze: | MC | Yes | B | LO4 |
| 16 | Which financial metric best measures a company's ability to pay short-term debts? | MC | Yes | A | LO4 |
| 17 | A client asks you to remove data that makes their strategy look weak. Your best response is: | MC | Yes | C | LO5 |
| 18 | Stakeholder analysis helps a consultant: | MC | Yes | B | LO5 |

*Same answer-shuffle setting as F1. Score calculated identically via Power Automate.*

---

## Section 4 — Career Outcomes
*Header text: "Help us track IMPACT's career outcomes. All salary information is voluntary and reported only in aggregate — never individually attributed."*

| Q# | Question Text | Type | Required | Options | SharePoint Field |
|---|---|---|---|---|---|
| 19 | What is your current employment status as you finish this semester? | MC | Yes | Secured full-time job offer / Secured internship offer / Have both a job and internship offer / Actively searching — no offer yet / Not currently searching (e.g., continuing studies, personal reasons) | Outcome_Type |
| 20 | Did IMPACT (the program, your project, your network) play a role in your job/internship search? | MC | BRANCH (if Q19 ≠ "Not currently searching") | Yes — directly (referral, client connection, PM connection) / Somewhat — improved my resume and interview talking points / No direct connection | IMPACT_Attribution |
| 21 | If you received an offer: What is your starting salary or total compensation? *(Completely voluntary — leave blank if you prefer)* | NUM | No | Dollar amount; blank allowed | Starting_Salary |
| 22 | What is your job title or role? *(Optional)* | TEXT-S | No | — | Job_Title |
| 23 | What is the name of the employer or organization? *(Optional)* | TEXT-S | No | — | Employer |
| 24 | What industry does this employer operate in? | MC | BRANCH (if Q19 = offer received) | Financial Services / Healthcare / Technology / Nonprofit / Manufacturing / Education / Government / Consulting / Other | Employer_Industry |

---

## Section 5 — Program Feedback
*Header text: "Your honest feedback helps make IMPACT better for the next group of students."*

| Q# | Question Text | Type | Required | Options / Notes | SharePoint/Report Use |
|---|---|---|---|---|---|
| 25 | What was the single most valuable thing you gained from IMPACT this semester? *(Be specific — describe something you did or produced, not a general feeling.)* | TEXT-L | Yes | Min 30 characters | Dean's Report quote bank |
| 26 | What is one thing you wish had been different about the program? | TEXT-L | Yes | — | Closed-loop improvement input |
| 27 | How likely are you to recommend IMPACT to a fellow graduate student? | RATE | Yes | 1–10 (1 = Definitely not, 10 = Definitely yes) | NPS score |
| 28 | In 1–2 sentences, how would you describe IMPACT to someone who's never heard of it? *(This may be used as a quote in the Dean's Annual Report — with your permission from the consent question below.)* | TEXT-L | Yes | — | Dean's Report pull quote |
| 29 | May we use your quote from Q28 in the Dean's Annual Report and program materials? | MC | Yes | Yes, with my name / Yes, anonymously (no name) / No, please don't use it | Quote_Consent |

---

## Section 6 — Story & Photo Consent (Final Confirmation)
*Header text: "Last step — confirm your consent for how your information may be used."*

| Q# | Question Text | Type | Required | Options | SharePoint Field |
|---|---|---|---|---|---|
| 30 | Do you consent to IMPACT featuring your career outcome (e.g., "Student secured a position at [Company] as a [Role]") in the Dean's Annual Report, alumni materials, or program website? | MC | Yes | Yes, with my name and employer / Yes, but only anonymized / No | Outcome_Consent |
| 31 | Do you have a project photo, team photo, or client meeting photo you'd like to share for the Dean's Report? | YN | No | Yes / No | Photo_Available |
| 32 | If yes — please upload your photo here. | File upload | BRANCH (if Q31 = Yes) | JPG/PNG, max 10MB | Photo (Asset Library) |

---

## Branching Logic Summary

| Trigger | Branch |
|---|---|
| Q19 = "Not currently searching" | Hide Q20, Q21, Q22, Q23, Q24 |
| Q19 = "Actively searching" | Show Q20; hide Q21–Q24 salary/role fields |
| Q19 = offer received (any) | Show Q20, Q21, Q22, Q23, Q24 |
| Q31 = "Yes" | Show Q32 (photo upload) |

---

## Power Automate: On F2 Submission

```
Trigger: F2 submitted
  → Match student by WSU Email → find row in Student Roster
  → Update: Post_Confidence_LO1–LO5 (Q4–Q8)
  → Calculate Post_KnowledgeTest_Score from Q9–Q18 → update Student Roster
  → Calculate Lens_C_Post = (Post_KnowledgeTest × 0.5) + (Post_Confidence_Avg × 0.5)
  → Calculate LensC_Delta = Lens_C_Post - Lens_C_Pre
  → Update: Outcome_Type, IMPACT_Attribution, Starting_Salary, Job_Title, Employer
  → If Outcome_Type = offer received → create row in Success Stories list
  → Set Student Status = Completed
  → Notify Operations: "[Student Name] has submitted exit form — career outcome: [Outcome_Type]"
```

---

## Form Settings

| Setting | Value |
|---|---|
| Who can fill out | Specific people in my organization |
| Response receipt | Off |
| Show results | Off |
| Shuffle questions | Off |
| Shuffle answers | On for Q9–Q18 (knowledge test) |
| One response per person | Yes |
| Start date | Week 14 start |
| End date | Week 15 end |
| Confirmation message | "Thank you for completing your exit assessment. Your IMPACT team will follow up shortly. Best of luck next semester!" |
