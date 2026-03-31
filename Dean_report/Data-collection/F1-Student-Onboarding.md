# F1 — Student Onboarding Form
## Microsoft Forms Specification

**Form title:** IMPACT Program — Welcome & Onboarding Assessment
**Subtitle:** Complete this form on your first day. It takes about 12 minutes. Your responses are used to personalize your IMPACT experience and to measure your growth over the semester.
**Administered:** Day 1 (Pre-assessment)
**Sent by:** Power Automate Flow 2 (triggered on HR clearance email)
**Recipient:** Student only
**SharePoint destination:** Student Roster — Tier 2 Operations Site
**Estimated completion time:** 10–12 minutes

---

## Section 1 — Personal Information
*Header text: "Let's get your profile set up."*

| Q# | Question Text | Type | Required | Options / Notes | SharePoint Field |
|---|---|---|---|---|---|
| 1 | Your full name (first and last) | TEXT-S | Yes | — | Student Name |
| 2 | Your WSU email address (@shockers.wichita.edu) | TEXT-S | Yes | Validate format | WSU Email |
| 3 | What is your academic major? | MC | Yes | Accounting / Finance / MIS / Marketing / Management / Economics / Other | Major |
| 4 | If "Other" — please specify your major | TEXT-S | BRANCH (if Q3 = Other) | — | Major (supplement) |
| 5 | What is your expected graduation date? | DATE | Yes | Month/Year format | Expected Graduation Date |
| 6 | Which IMPACT project team are you joining? | MC | Yes | [Team names — populated by Operations before sending] | Team Assignment |
| 7 | Which semester cohort is this? | MC | Yes | Spring 2026 / Fall 2026 / Spring 2027 / Fall 2027 | Semester Cohort |

---

## Section 2 — Pre-Assessment: Self-Confidence Ratings (Lens C)
*Header text: "Before you start, honestly rate your current confidence in each area. There are no right or wrong answers — this is your starting point, not a test."*
*Instruction: "Use the scale: 1 = Not at all confident, 5 = Very confident."*

| Q# | Question Text | Type | Required | Scale | LO | SharePoint Field |
|---|---|---|---|---|---|---|
| 8 | How confident are you in your ability to communicate professionally in writing to a business audience? | RATE | Yes | 1–5 (Not confident → Very confident) | LO1 | Pre_Confidence_LO1 |
| 9 | How confident are you in your ability to analyze a business problem and develop evidence-based recommendations? | RATE | Yes | 1–5 | LO2 | Pre_Confidence_LO2 |
| 10 | How confident are you in your ability to manage your time, meet deadlines, and hold yourself accountable in a professional setting? | RATE | Yes | 1–5 | LO3 | Pre_Confidence_LO3 |
| 11 | How well can you apply concepts from your business courses to solve real-world client problems? | RATE | Yes | 1–5 | LO4 | Pre_Confidence_LO4 |
| 12 | How aware are you of your ethical obligations to clients, teammates, and your institution? | RATE | Yes | 1–5 | LO5 | Pre_Confidence_LO5 |

---

## Section 3 — Pre-Assessment: Knowledge Test (Lens C — Objective)
*Header text: "Now a short 10-question quiz. Pick the best answer for each question. This is not graded — it helps us measure how much you learn over the semester."*

| Q# | Question Text | Type | Required | Correct Answer | LO |
|---|---|---|---|---|---|
| 13 | A project scope statement primarily describes: | MC | Yes | A) What the project will and will not deliver | LO1 |
| | A) What the project will and will not deliver | | | ✓ Correct | |
| | B) The project team's organizational chart | | | | |
| | C) The total cost of the project | | | | |
| | D) The risk assessment for the project | | | | |
| 14 | An executive summary is written primarily for: | MC | Yes | B) A decision-maker with limited time | LO1 |
| | A) The analyst who wrote the report | | | | |
| | B) A decision-maker with limited time | | | ✓ Correct | |
| | C) A technical audience wanting full detail | | | | |
| | D) An external auditor reviewing compliance | | | | |
| 15 | A SWOT analysis categorizes factors as: | MC | Yes | C) Internal/external AND helpful/harmful | LO2 |
| | A) Financial and non-financial | | | | |
| | B) Short-term and long-term | | | | |
| | C) Internal/external AND helpful/harmful | | | ✓ Correct | |
| | D) Quantitative and qualitative | | | | |
| 16 | When analyzing a business problem, identifying "root causes" rather than "symptoms" means: | MC | Yes | B) Finding the underlying reason the problem exists, not just describing its visible effects | LO2 |
| | A) Describing the problem in as much detail as possible | | | | |
| | B) Finding the underlying reason the problem exists, not just its visible effects | | | ✓ Correct | |
| | C) Listing every possible solution before choosing one | | | | |
| | D) Asking the client what they think the problem is | | | | |
| 17 | Which behavior best demonstrates professional project management? | MC | Yes | A) Flagging a potential blocker to your supervisor before the deadline is missed | LO3 |
| | A) Flagging a potential blocker to your supervisor before the deadline is missed | | | ✓ Correct | |
| | B) Completing tasks as fast as possible to get ahead of schedule | | | | |
| | C) Waiting until a deadline passes to report issues to avoid looking unprepared | | | | |
| | D) Asking for deadline extensions when workload is high | | | | |
| 18 | A Gantt chart is used to: | MC | Yes | C) Visualize project tasks, durations, and timelines | LO3 |
| | A) Track financial performance of a project | | | | |
| | B) Document stakeholder communication preferences | | | | |
| | C) Visualize project tasks, durations, and timelines | | | ✓ Correct | |
| | D) Assign risk scores to project deliverables | | | | |
| 19 | Porter's Five Forces is a framework used to analyze: | MC | Yes | B) The competitive intensity and profitability potential of an industry | LO4 |
| | A) A company's internal operational efficiency | | | | |
| | B) The competitive intensity and profitability potential of an industry | | | ✓ Correct | |
| | C) A company's marketing channel mix | | | | |
| | D) A project team's resource allocation | | | | |
| 20 | Which financial metric best measures a company's ability to pay short-term debts? | MC | Yes | A) Current ratio (current assets ÷ current liabilities) | LO4 |
| | A) Current ratio (current assets ÷ current liabilities) | | | ✓ Correct | |
| | B) Return on equity (ROE) | | | | |
| | C) Debt-to-equity ratio | | | | |
| | D) Net profit margin | | | | |
| 21 | A client asks you to remove data from your report that makes their strategy look weak. Your best response is: | MC | Yes | C) Explain that omitting relevant data would undermine the report's value and discuss how to frame it constructively | LO5 |
| | A) Remove the data — the client is always right | | | | |
| | B) Keep the data and say nothing to the client | | | | |
| | C) Explain that omitting relevant data undermines the report's value and discuss how to frame it constructively | | | ✓ Correct | |
| | D) Escalate immediately to your dean | | | | |
| 22 | Stakeholder analysis helps a consultant: | MC | Yes | B) Identify everyone affected by a recommendation and understand their interests and concerns | LO5 |
| | A) Determine the budget for a project | | | | |
| | B) Identify everyone affected by a recommendation and understand their interests and concerns | | | ✓ Correct | |
| | C) Create a risk register for the project | | | | |
| | D) Write the final executive summary | | | | |

*Operations note: Microsoft Forms does not auto-grade and hide correct answers from students. Configure the form so results are NOT shared with respondents. Export answers to SharePoint and calculate the score via Power Automate (compare answer to stored correct-answer key).*

---

## Section 4 — Preferences & Profile Setup
*Header text: "A few more details to get you set up."*

| Q# | Question Text | Type | Required | Notes | SharePoint Field |
|---|---|---|---|---|---|
| 23 | What name would you like on your IMPACT name tag? | TEXT-S | Yes | Can differ from legal name | Name Tag |
| 24 | Write a 2–3 sentence professional bio for the IMPACT website/directory. | TEXT-L | No | Optional; can submit later | Bio |
| 25 | Please upload a professional headshot photo. | File upload | No | JPG/PNG, max 5MB | Headshot (links to Asset Library) |
| 26 | What are your general weekly availability blocks for project work? | CHK | Yes | Mon AM / Mon PM / Tue AM / Tue PM / Wed AM / Wed PM / Thu AM / Thu PM / Fri AM / Fri PM | Availability |
| 27 | Do you have any prior consulting, internship, or relevant work experience? | YN | Yes | — | Prior Experience flag |
| 28 | If yes — briefly describe your most relevant prior experience (1–2 sentences). | TEXT-L | BRANCH (if Q27 = Yes) | — | Prior Experience Detail |

---

## Section 5 — Consent
*Header text: "Two quick consent questions before you finish."*

| Q# | Question Text | Type | Required | Options | SharePoint Field |
|---|---|---|---|---|---|
| 29 | Do you consent to IMPACT using your photo, quotes, and anonymized academic/career outcomes in program reports, the Dean's Annual Report, and promotional materials? | MC | Yes | Yes, I consent / No, please do not use my information / Yes, but only anonymized (no name or photo) | Consent to Share Story |
| 30 | I confirm that I have read and understand the IMPACT Student Expectations document linked here: [link to SOP]. | MC | Yes | Yes, I have read and understood it / I need more time — I will complete the SOP acknowledgment form (F8) separately | SOP Pre-acknowledgment |

---

## Branching Logic Summary

| Trigger | Branch |
|---|---|
| Q3 = "Other" | Show Q4 (major specification) |
| Q27 = "Yes" | Show Q28 (prior experience detail) |
| Q30 = "Yes, I have read..." | Mark SOP acknowledged in Onboarding Tracker; skip F8 |
| Q30 = "I need more time..." | Operations sends F8 separately |

---

## Power Automate: On F1 Submission

```
Trigger: F1 submitted
  → Create row in Student Roster with all field values
  → Set Training_Completed = No (default)
  → Set Pre_KnowledgeTest_Score = calculated from Q13–Q22 (via correct-answer comparison)
  → Set Pre_Confidence_Avg = avg(Q8–Q12)
  → Notify Operations team via Teams message: "[Student Name] has completed onboarding form"
  → If Q29 includes consent → set Consent_to_Share = Yes
  → If Q30 = "I need more time" → send F8 link separately
```

---

## Form Settings (Microsoft Forms configuration)

| Setting | Value |
|---|---|
| Who can fill out | Specific people in my organization (WSU account required) |
| Response receipt | Off (do not send copy to respondent) |
| Show results | Off (do not show summary to respondents) |
| Shuffle questions | Off (keep order) |
| Shuffle answers | On for Q13–Q22 (randomize answer order per respondent) |
| One response per person | Yes |
| Start date | Set per cohort |
| End date | 1 week after cohort start date |
| Confirmation message | "Thank you! Your onboarding is underway. You'll receive a welcome message from your team shortly." |
