# F5 — Deliverable Quality Scorecard
## Microsoft Forms Specification

**Form title:** IMPACT — Deliverable Quality Review
**Subtitle:** Complete one scorecard each time you review a student's deliverable. This is a quick 2-minute checklist — not a narrative review. It generates the Lens A score for Analytical Thinking (LO2).
**Administered:** Each time a deliverable is submitted by a student for PM review (ongoing throughout semester)
**Sent by:** Operations — PM-only link (standing link; PM opens whenever needed)
**Recipient:** Project Manager only
**SharePoint destination:** Deliverable Quality Scores list — Tier 2 Operations Site
**Estimated completion time:** 2–3 minutes per deliverable

---

## Section 1 — Deliverable Identity

| Q# | Question Text | Type | Required | Notes | SharePoint Field |
|---|---|---|---|---|---|
| 1 | Your name (Project Manager) | TEXT-S | Yes | — | PM_Name |
| 2 | Project team | MC | Yes | Alpha / Beta / Gamma / Delta / Epsilon | Team |
| 3 | Student being evaluated | MC | Yes | [Student names on this team] | Student_Name |
| 4 | Deliverable name or description | TEXT-S | Yes | e.g., "Week 6 Competitive Analysis" or "Final Client Presentation Deck" | Deliverable_Name |
| 5 | Date you reviewed this deliverable | DATE | Yes | Auto-defaults to today | Review_Date |
| 6 | What type of deliverable is this? | MC | Yes | Written report / Slide presentation / Data analysis / Research memo / Client email / Other | Deliverable_Type |
| 7 | Semester week this deliverable was submitted | MC | Yes | Week 1 / Week 2 / ... / Week 15 | Submission_Week |

---

## Section 2 — Quality Checklist (5 Items)
*Header text: "Check each item that this deliverable meets. If you are unsure about an item, do not check it."*

| Q# | Quality Standard | Type | Required | Notes | SharePoint Field |
|---|---|---|---|---|---|
| 8 | **Executive summary or overview section is present.** *(For emails or short memos: an opening paragraph that states the purpose and key conclusion counts.)* | YN | Yes | Yes = present / No = missing | Checklist_Q1 |
| 9 | **At least one recommendation is supported by data, research, or a named business framework.** *(A recommendation without evidence does not count. "We recommend X because Y data shows Z" does count.)* | YN | Yes | — | Checklist_Q2 |
| 10 | **Action items specify a responsible owner AND a date.** *(If the deliverable has no action items, select "N/A — no action items in this deliverable type".)* | MC | Yes | Yes / No / N/A — no action items | Checklist_Q3 |
| 11 | **Formatting meets professional standard.** *(No visible spelling errors, consistent fonts, clean layout. Not perfect — professional standard.)* | YN | Yes | — | Checklist_Q4 |
| 12 | **The deliverable answers the client's stated question or scope of work.** *(Does it do what it was supposed to do? If you asked for a competitive analysis and this is a competitive analysis, Yes.)* | YN | Yes | — | Checklist_Q5 |

---

## Section 3 — Additional Notes
*Header text: "Optional — for PM records only. Not shared with students unless you choose to."*

| Q# | Question Text | Type | Required | Notes | SharePoint Field |
|---|---|---|---|---|---|
| 13 | Was this deliverable returned for revision before this review? | MC | No | Yes — major revision requested / Yes — minor edits only / No — first submission accepted | Revision_History |
| 14 | Any notes on this deliverable for your own records? | TEXT-L | No | — | PM_Notes |

---

## Score Calculation (Power Automate)

```
Deliverable_Score = 0

For each Yes in Q8–Q12:
  Add 1 to Deliverable_Score

If Q10 = "N/A — no action items":
  Score = (Deliverable_Score / 4) × 5   ← denominator is 4, not 5
Else:
  Score = (Deliverable_Score / 5) × 5

Student LO2 Lens A Score = AVERAGE of all Deliverable_Score values for that student this semester
```

---

## Power Automate: On F5 Submission

```
Trigger: F5 submitted
  → Create row in Deliverable Quality Scores list:
      PM_Name, Team, Student_Name, Deliverable_Name, Review_Date,
      Deliverable_Type, Submission_Week,
      Checklist_Q1–Q5, Revision_History, PM_Notes,
      Deliverable_Score (calculated)
  → Recalculate Student's LO2_LensA_Score in Student Roster:
      = AVERAGE of all Deliverable_Score rows for this student
  → If Revision_History = "Yes — major revision" → flag for LO1 Lens A (report flag rate)
```

---

## When to Submit F5

| Trigger | Action |
|---|---|
| Student submits a deliverable to the PM for review | PM opens F5 standing link and completes within 48 hours |
| Weekly task report mentions "formal deliverable submitted" | PM cross-references and submits F5 if not already done |
| End of semester | PM confirms all deliverables from the semester have been scored |

**Minimum expected submissions per student per semester:** 3–5 (varies by project scope)

---

## Form Settings

| Setting | Value |
|---|---|
| Who can fill out | Specific people in my organization (PM only) |
| Response receipt | Off |
| Show results | Off |
| One response per person | No *(PM submits once per deliverable — multiple needed)* |
| Standing link | Yes — same link used all semester |
| Confirmation message | "Scorecard submitted. The student's LO2 score has been updated." |
