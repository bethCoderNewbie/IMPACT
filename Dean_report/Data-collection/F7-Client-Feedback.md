# F7 — Client Behavioral Feedback Form
## Microsoft Forms Specification

**Form title:** IMPACT Consulting Program — Project Feedback
**Subtitle:** Thank you for partnering with IMPACT at Wichita State University. This 5-minute survey helps us measure the value we delivered and improve the program. Your responses are used in our annual report to the Dean and Kansas legislature — they matter.
**Administered:** Within 2 weeks of project completion
**Sent by:** Operations — client-specific link (one per project)
**Recipient:** Client contact (primary point of contact for the project)
**SharePoint destination:** Master Project List — Tier 2 Operations Site (updates client score fields)
**Estimated completion time:** 4–6 minutes

---

## Section 1 — Project Identification

| Q# | Question Text | Type | Required | Notes | SharePoint Field |
|---|---|---|---|---|---|
| 1 | Your name | TEXT-S | Yes | — | Client_Contact_Name |
| 2 | Your organization | TEXT-S | Yes | Pre-filled by Operations if possible | Client_Organization |
| 3 | Which IMPACT project are you providing feedback for? | MC | Yes | [Project name — pre-populated by Operations] | Project_Name |
| 4 | Approximately when did your project work with IMPACT end? | DATE | Yes | — | Project_End_Actual_Confirm |

---

## Section 2 — Behavioral Observations (Y/N Checklist)
*Header text: "Please answer Yes or No for each statement based on your direct experience with the IMPACT team."*
*Instruction: "These are factual questions about specific behaviors — not general impressions. If you genuinely don't know, select 'Unsure'."*

| Q# | Statement | Type | Required | Options | LO | SharePoint Field |
|---|---|---|---|---|---|---|
| 5 | The team proactively updated us on project progress without our team needing to ask. | MC | Yes | Yes / No / Unsure | LO4 | Client_YN_Q1 |
| 6 | The team asked clarifying questions before starting work — they did not assume they already knew what we needed. | MC | Yes | Yes / No / Unsure | LO4 | Client_YN_Q2 |
| 7 | The team's recommendations were grounded in evidence or data — not just opinion. | MC | Yes | Yes / No / Unsure | LO4 | Client_YN_Q3 |
| 8 | Based on this experience, we would trust this team with a higher-stakes or more sensitive project. | MC | Yes | Yes / No / Unsure | LO4 | Client_YN_Q4 |
| 9 | The team respected confidentiality and professional boundaries throughout the engagement. | MC | Yes | Yes / No / Unsure | LO5 | Client_YN_Q5 |

*Score calculation (Power Automate):*
```
Yes = 1, No = 0, Unsure = 0.5
LO4_Client_YN_Score = ((Q5 + Q6 + Q7 + Q8) / 4) × 5
LO5_Client_YN_Score = (Q9 / 1) × 5
```

---

## Section 3 — Satisfaction Ratings (1–5)
*Header text: "Rate each aspect of the engagement."*

| Q# | Question Text | Type | Required | Scale | SharePoint Field |
|---|---|---|---|---|---|
| 10 | How useful were the recommendations or deliverables your team received? | RATE | Yes | 1 (Not useful) → 5 (Extremely useful) | Client_Sat_Usefulness |
| 11 | How professionally did the IMPACT team communicate throughout the engagement? | RATE | Yes | 1 (Unprofessional) → 5 (Highly professional) | Client_Sat_Communication |
| 12 | How satisfied are you overall with the IMPACT engagement? | RATE | Yes | 1 (Very dissatisfied) → 5 (Very satisfied) | Client_Sat_Overall |
| 13 | How likely are you to engage IMPACT again for a future project? | RATE | Yes | 1 (Definitely not) → 5 (Definitely yes) | Client_Reengagement_Likelihood |

*Q10 → feeds Lens A for LO4 (Client_Satisfaction_Usefulness item = primary Lens A score)*
*Q11, Q12, Q13 → feed Master Project List for Dean's report and legislative reporting*

---

## Section 4 — Qualitative Feedback
*Header text: "Your words help us improve the program and recognize outstanding student work."*

| Q# | Question Text | Type | Required | Notes | Use |
|---|---|---|---|---|---|
| 14 | What was the most valuable thing the IMPACT team delivered or contributed? | TEXT-L | Yes | Min 20 characters | Dean's Report quote; PM recognition |
| 15 | What could the team have done better? | TEXT-L | Yes | Constructive feedback for program improvement | Closed-loop improvement |
| 16 | Is there a specific student or contribution you'd like to recognize? *(Optional — name and what they did)* | TEXT-L | No | — | Individual recognition; Dean's Report |
| 17 | Would you be willing to provide a brief testimonial quote for the IMPACT program's annual report or website? | MC | Yes | Yes, use my name and organization / Yes, but please keep it anonymous / No | Testimonial_Consent |
| 18 | If yes — write your testimonial here (2–4 sentences describing the value IMPACT provided to your organization): | TEXT-L | BRANCH (if Q17 = Yes) | — | Client_Testimonial |

---

## Section 5 — Re-Engagement
*Header text: "We'd love to work with your organization again."*

| Q# | Question Text | Type | Required | Options | SharePoint Field |
|---|---|---|---|---|---|
| 19 | Would you be interested in engaging IMPACT for another project next semester? | MC | Yes | Yes — please contact us / Maybe — we'll reach out when we have a project ready / Not at this time | Reengagement_Interest |
| 20 | Is there a colleague or peer organization you'd recommend we contact about IMPACT? *(Optional)* | TEXT-S | No | — | Referral_Name |

---

## Power Automate: On F7 Submission

```
Trigger: F7 submitted
  → Match to Master Project List by Project_Name
  → Update Master Project List:
      Client_Sat_Usefulness = Q10
      Client_Sat_Communication = Q11
      Client_Sat_Overall = Q12
      Client_Reengagement_Likelihood = Q13
      Client_YN_Q1–Q5 = Q5–Q9 (mapped)
      LO4_Client_YN_Score = calculated
      LO5_Client_YN_Score = calculated
  → Recalculate LO4 Lens B for all students on this team:
      Include Client_YN_Score as a modifier to Lens B
  → If Reengagement_Interest = "Yes" → create task in Operations Planner: "Follow up with [Client] for next semester"
  → If Client_Testimonial filled → append to Success Stories / Hub for Dean's Report
  → Notify Operations: "Client feedback received for [Project Name]. Overall sat: [Q12]/5"
```

---

## Operations Workflow — Sending F7

| Step | Timing | Action |
|---|---|---|
| 1 | Project close confirmed | Operations marks project Status = Completed in Master Project List |
| 2 | Within 2 business days | Operations sends F7 link to client contact email |
| 3 | 7 days later — no response | Send one reminder email |
| 4 | 14 days after send — no response | Log Client_Feedback_Status = "No response" in Master Project List; do not chase further |
| 5 | Response received | Power Automate updates all fields automatically |

---

## Form Settings

| Setting | Value |
|---|---|
| Who can fill out | Anyone with the link (external clients do not have WSU accounts) |
| Response receipt | Optional — offer to send copy to client |
| Show results | Off |
| One response per person | Off (no login enforced for external) |
| Branding | Add IMPACT logo and Barton School logo to form header |
| Language | English only (unless client requires Spanish — flag for Operations) |
| Confirmation message | "Thank you for your feedback. It will be used to measure our program's impact and improve our work. We hope to partner with you again soon." |
