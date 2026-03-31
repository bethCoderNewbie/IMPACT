# F8 — SOP Acknowledgment Form
## Microsoft Forms Specification

**Form title:** IMPACT Program — Week 1 Training Acknowledgment
**Subtitle:** Before you start your project work, confirm that you've read each SOP below. This takes about 2 minutes once you've completed the readings. Completing this form by the end of Week 2 is required for your IMPACT record.
**Administered:** Week 1 (must be completed by end of Week 2)
**Sent by:** Operations — included in welcome email alongside F1, OR sent separately if F1 Q30 = "I need more time"
**Recipient:** Student only
**SharePoint destination:** Onboarding Tracker — Tier 2 Operations Site
**Estimated completion time:** 2 minutes (after readings are completed)

---

## Before Filling Out This Form

*Students must read each SOP before checking the acknowledgment. Links to each SOP are provided in-form.*

**SOPs to read (pre-populate links before sending):**
1. IMPACT Student Expectations & Code of Conduct — [SharePoint link]
2. Client Confidentiality & Data Handling Policy — [SharePoint link]
3. Weekly Task Report Submission Guide — [SharePoint link]
4. Deliverable Standards & Formatting Guide — [SharePoint link]
5. Communication Protocol (PM, client, IMPACT leadership) — [SharePoint link]

---

## Section 1 — Identity

| Q# | Question Text | Type | Required | Notes | SharePoint Field |
|---|---|---|---|---|---|
| 1 | Your full name | TEXT-S | Yes | Must match Student Roster | Student_Name |
| 2 | Your WSU email address | TEXT-S | Yes | Lookup key | WSU_Email |
| 3 | Your IMPACT project team | MC | Yes | Alpha / Beta / Gamma / Delta / Epsilon | Team |

---

## Section 2 — SOP Acknowledgments

*Header text: "For each SOP, confirm that you have read it. If you have not read it yet, please read it before checking the box."*

| Q# | Acknowledgment Statement | Type | Required | SharePoint Field |
|---|---|---|---|---|
| 4 | I have read the **IMPACT Student Expectations & Code of Conduct** and I understand the behavioral standards expected of me as an IMPACT student. | MC | Yes | SOP_Ack_Expectations |
| 5 | I have read the **Client Confidentiality & Data Handling Policy** and I understand my obligations to protect client information. | MC | Yes | SOP_Ack_Confidentiality |
| 6 | I have read the **Weekly Task Report Submission Guide** and I understand the format, deadline (Monday EOD), and submission process. | MC | Yes | SOP_Ack_WeeklyReport |
| 7 | I have read the **Deliverable Standards & Formatting Guide** and I understand the quality expectations for all deliverables submitted to my PM or client. | MC | Yes | SOP_Ack_Deliverables |
| 8 | I have read the **Communication Protocol** and I understand how and when to communicate with my PM, the client, and IMPACT leadership. | MC | Yes | SOP_Ack_Communication |

*Each question options: "Yes, I have read and understood this SOP" / "I have questions about this SOP — please contact me"*

*If any Q4–Q8 = "I have questions": Operations is automatically notified via Teams message.*

---

## Section 3 — Commitment Statement

| Q# | Question Text | Type | Required | Options | SharePoint Field |
|---|---|---|---|---|---|
| 9 | I understand that my participation in IMPACT is subject to these policies, and that violations may result in removal from the program. | MC | Yes | I understand and agree / I have concerns I'd like to discuss with Operations | Commitment_Agreement |
| 10 | Today's date *(your digital acknowledgment date)* | DATE | Yes | Auto-defaults to today | SOP_Acknowledgment_Date |

---

## Power Automate: On F8 Submission

```
Trigger: F8 submitted
  → Match student by WSU_Email → find row in Onboarding Tracker
  → Update Onboarding Tracker:
      SOP_Training_Assigned = Yes (if not already)
      Training_Completed = Yes
      Training_Completion_Date = today (Q10)
  → Update Student Roster: Training_Completed = Yes
  → Check Onboarding Tracker: if all prerequisite fields = Yes →
      Set Onboarding_Complete = Yes
      Set Onboarding_Complete_Date = today
  → Notify Operations: "[Student Name] completed SOP training on [date]"
  → If any Q4–Q8 = "I have questions" → Teams alert to Operations: "Student has SOP questions"
  → If Q9 = "I have concerns" → Teams alert to Operations for follow-up
```

---

## Reminder Workflow

```
Trigger: Each Monday during Week 1 and Week 2
  → Check Onboarding Tracker: which students have Training_Completed = No?
  → For each: send reminder email with F8 link
  → If still incomplete by end of Week 2 → Operations flagged; PM notified
```

---

## Form Settings

| Setting | Value |
|---|---|
| Who can fill out | Specific people in my organization |
| Response receipt | Optional — send copy to student as their record |
| Show results | Off |
| One response per person | Yes *(one acknowledgment per student per semester)* |
| Start date | Week 1 Monday |
| End date | Week 2 Friday |
| Confirmation message | "Your SOP acknowledgment has been recorded. You're cleared to start your project work. Welcome to IMPACT!" |

---

## Operations Notes

- F8 is the trigger for setting `Training_Completed = Yes` in the Student Roster, which feeds **Lens A for LO5** (SOP completion = one of three behaviors in the Ethics BARS).
- If a student never completes F8, their LO5_LensA_Score is automatically reduced (SOP completion behavior = No).
- Archive completed F8 responses each semester in `Hub SOP Library > AOL Records > [Semester] > SOP Acknowledgments`.
