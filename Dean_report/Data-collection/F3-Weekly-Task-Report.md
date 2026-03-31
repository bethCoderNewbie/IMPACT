# F3 — Weekly Task Report
## Microsoft Forms Specification

**Form title:** IMPACT — Weekly Task Report
**Subtitle:** Submit by end of day Monday. This takes about 5 minutes. Your report is reviewed by your project manager each week.
**Administered:** Every Monday (auto-triggered by Power Automate Flow 3 at 8:00 AM)
**Sent by:** Power Automate Flow 3 (scheduled)
**Recipient:** All active students
**SharePoint destination:** Weekly Task Reports list (Tier 2 unified list — recommended per architecture plan Q7 resolution)
**Estimated completion time:** 4–6 minutes

---

## Section 1 — Identity & Week
*Header text: "Start here — takes 30 seconds."*

| Q# | Question Text | Type | Required | Options / Notes | SharePoint Field |
|---|---|---|---|---|---|
| 1 | Your full name | TEXT-S | Yes | — | Student_Name |
| 2 | Your WSU email address | TEXT-S | Yes | Used to match to Student Roster | WSU_Email |
| 3 | Your project team | MC | Yes | Alpha / Beta / Gamma / Delta / Epsilon *(update per semester)* | Team |
| 4 | Week ending date *(select the Sunday of this week)* | DATE | Yes | Auto-default to most recent Sunday; student confirms | Week_Ending_Date |

---

## Section 2 — Hours Breakdown
*Header text: "Enter your hours for this week. Be honest — this data is used to report the program's value to the state of Kansas."*
*Instruction: "Decimals are fine (e.g., 7.5 hours). If you did zero hours in a category, enter 0."*

| Q# | Question Text | Type | Required | Validation | SharePoint Field |
|---|---|---|---|---|---|
| 5 | Hours spent on **client work** this week *(direct project tasks, deliverables, client meetings, research for the client)* | NUM | Yes | 0–40; warn if >20 | Hours_Client_Work |
| 6 | Hours spent on **admin or coordination** this week *(team check-ins, internal meetings, email, organizing files, Planner updates)* | NUM | Yes | 0–15 | Hours_Admin |
| 7 | Hours spent on **training or SOP review** this week *(reading SOPs, attending program training, onboarding activities)* | NUM | Yes | 0–10 | Hours_Training |

*Validation note: If Q5 + Q6 + Q7 > 40, show warning: "Your total hours exceed 40 — please double-check your entries."*

---

## Section 3 — Deliverables & Progress
*Header text: "What did you actually produce or complete this week?"*

| Q# | Question Text | Type | Required | Notes | SharePoint Field |
|---|---|---|---|---|---|
| 8 | What did you complete or contribute to this week? *(Name the specific task, deliverable, or output. Be concrete — not "worked on project" but "completed 3-page competitive analysis section for client deck.")* | TEXT-L | Yes | Min 20 characters | Deliverable_Completed |
| 9 | What are you working on next week? *(Brief — 1–2 sentences)* | TEXT-L | Yes | — | Next_Week_Plan |
| 10 | Did you submit or contribute to a formal deliverable to the client or PM this week? | YN | Yes | Yes / No | Formal_Deliverable_Submitted |
| 11 | If yes — what was the name or description of the deliverable? | TEXT-S | BRANCH (if Q10 = Yes) | — | Deliverable_Name |

---

## Section 4 — Blockers & Flags
*Header text: "Be honest here — this is where you flag issues before they become problems."*

| Q# | Question Text | Type | Required | Options | SharePoint Field |
|---|---|---|---|---|---|
| 12 | Do you have any blockers or issues that are slowing your work down? | YN | Yes | Yes / No | Has_Blocker |
| 13 | If yes — describe the blocker briefly. What is it and who needs to resolve it? | TEXT-L | BRANCH (if Q12 = Yes) | — | Blocker_Description |
| 14 | Overall, how would you rate your team's progress on the project this week? | MC | Yes | On track — no concerns / Slightly behind but manageable / Behind — needs PM attention / On hold — waiting on client or external input | Team_Progress_Status |
| 15 | Anything else you want your PM to know this week? *(Optional)* | TEXT-L | No | — | PM_Notes |

---

## Branching Logic Summary

| Trigger | Branch |
|---|---|
| Q5 + Q6 + Q7 > 40 | Show warning: "Total hours exceed 40 — please review." (soft warning, not a block) |
| Q10 = "Yes" | Show Q11 (deliverable name) |
| Q12 = "Yes" | Show Q13 (blocker description) |

---

## Power Automate: On F3 Submission

```
Trigger: F3 submitted
  → Create row in Weekly Task Reports list (Tier 2):
      Student_Name, WSU_Email, Team, Week_Ending_Date,
      Hours_Client, Hours_Admin, Hours_Training,
      Deliverable_Completed, Next_Week_Plan,
      Formal_Deliverable_Submitted, Deliverable_Name,
      Has_Blocker, Blocker_Description, Team_Progress_Status,
      PM_Notes, Submission_Timestamp (auto)
  → Set Reviewed_By_PM = No (default)
  → If Has_Blocker = Yes → send Teams notification to PM:
      "⚠ [Student Name] reported a blocker this week: [Blocker_Description]"
  → If Team_Progress_Status = "Behind — needs PM attention" → send Teams alert to PM
```

## Power Automate: Weekly Submission Rate Check (Flow 3b)

```
Trigger: Every Tuesday 9:00 AM
  → Query Weekly Task Reports list: count submissions for current week ending date per team
  → Compare to expected submissions (active students per team)
  → For any student with no submission: send reminder email
  → If team submission rate < 80%: send Teams alert to Operations
  → Every Monday EOD: compile submission digest for Leadership
```

---

## PM Review Workflow

After Flow 3 creates rows, PM reviews each submission in SharePoint:
- Set `Reviewed_By_PM = Yes` after reading
- Set `Report_Flagged = Yes` if report is incomplete, vague, or missing key info
  - Flag reason options: Incomplete hours / Vague deliverable description / Missing next-week plan / Other

`Report_Flagged = Yes` feeds directly into **Lens A for LO1** (communication quality): a high flag rate lowers the student's LO1 behavioral score.

---

## Form Settings

| Setting | Value |
|---|---|
| Who can fill out | Specific people in my organization |
| Response receipt | Off |
| Show results | Off |
| One response per person | No *(students submit weekly — multiple submissions needed)* |
| Start date | Week 1 Monday |
| End date | Week 15 Friday |
| Recurring link | Same form link reused each week — Power Automate sends it every Monday |
| Confirmation message | "Report submitted. Your PM will review it shortly. See you next Monday!" |
