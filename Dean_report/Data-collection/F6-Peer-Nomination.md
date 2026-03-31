# F6 — Peer Nomination Form
## Microsoft Forms Specification

**Form title:** IMPACT — Peer Recognition
**Subtitle:** Recognize a teammate who made a difference this semester. Your responses are completely anonymous — we cannot see who nominated whom. This takes about 3 minutes.
**Administered:** Final week of semester (Week 14–15)
**Sent by:** Operations — anonymous link (no WSU login required)
**Recipient:** Active students only (Operations sends link via team channel or email)
**SharePoint destination:** Peer Nominations list — Tier 2 Operations Site
**Estimated completion time:** 3–4 minutes
**Anonymity:** Strictly enforced — no respondent identity stored. Nomination counts only.

---

## Important Design Notes

> **Anonymity in Microsoft Forms:** Configure this form with "Anyone can respond" (no sign-in required) OR "Anonymous responses" if the tenant supports it. Do NOT require WSU login — that stores a respondent identity. The form link should be distributed only to the team channel so that only team members have access, even though it is technically unauthenticated.

> **One submission per student:** Without authentication, Microsoft Forms cannot enforce 1 response per person. Mitigate by: (a) sending the link only via a private Teams channel students cannot forward, (b) instructing students clearly, and (c) monitoring for anomalous nomination counts.

---

## Section 1 — Team Identification
*Header text: "Which team are you on? We need this to make sure nominations are counted within the right group."*

| Q# | Question Text | Type | Required | Options | SharePoint Field |
|---|---|---|---|---|---|
| 1 | Which IMPACT project team are you on? | MC | Yes | Alpha / Beta / Gamma / Delta / Epsilon | Nominator_Team |

*Note: This is NOT stored with respondent identity. It is used only to ensure nominations are scored within the correct team.*

---

## Section 2 — Nomination Questions
*Header text: "For each question below, select ONE teammate who best matches the description. You cannot nominate yourself. If it's a tie, pick the person who comes to mind first."*
*Instruction: "These are not rankings — just recognitions. There is no wrong answer."*

| Q# | Question Text | Type | Required | Options | LO Mapped | SharePoint Field |
|---|---|---|---|---|---|---|
| 2 | **Communication & Analysis:** Which teammate most clearly explained a complex business idea or concept to you or the team this semester? | MC | Yes | [Teammate names from this team — pre-populated by Operations per team] | LO1 + LO2 | Nominee_Q1 |
| 3 | **Reliability & Professionalism:** Which teammate was the most consistent, reliable, and professional throughout the entire semester? | MC | Yes | [Teammate names] | LO3 | Nominee_Q2 |
| 4 | **Applied Knowledge:** Which teammate did the best job connecting what they learned in their courses to the client's real problem? | MC | Yes | [Teammate names] | LO4 | Nominee_Q3 |

*Note for Operations: The teammate list for each team must be pre-loaded into the form as a separate form variant per team (Form A = Alpha names, Form B = Beta names, etc.), OR use a branching structure: Q1 answer drives which name options appear in Q2–Q4.*

---

## Section 3 — Optional Recognition Note
*Header text: "If you'd like, leave an anonymous note recognizing someone on your team. This may be shared (anonymously) with the student in the Dean's Report."*

| Q# | Question Text | Type | Required | Notes | Use |
|---|---|---|---|---|---|
| 5 | Is there anything specific you'd like to recognize about a teammate this semester? *(Optional — completely anonymous)* | TEXT-L | No | — | Dean's Report quotes; PM coaching notes |

---

## Scoring Calculation (Power Automate)

```
For each nomination question (Q2, Q3, Q4):
  Count nominations received per student within their team
  Max possible nominations = team size - 1 (e.g., 5 on a 6-person team)
  Normalized_Score = (nominations_received / max_possible) × 5

Peer_Nomination_LO1_LO2 = Normalized score from Q2
Peer_Nomination_LO3     = Normalized score from Q3
Peer_Nomination_LO4     = Normalized score from Q4

Store in Peer Nominations list: Student_Name, Team, Nom_Q1_Count, Nom_Q2_Count, Nom_Q3_Count,
                                  Norm_Score_Q1, Norm_Score_Q2, Norm_Score_Q3
```

---

## Power Automate: On F6 Submission

```
Trigger: F6 submitted
  → Do NOT log respondent identity
  → Increment nomination count for each named student:
      Peer_Nominations list → find row for [Nominee_Q1, Team] → Nom_Q1_Count += 1
      Peer_Nominations list → find row for [Nominee_Q2, Team] → Nom_Q2_Count += 1
      Peer_Nominations list → find row for [Nominee_Q3, Team] → Nom_Q3_Count += 1
  → Recalculate normalized scores after each submission

After all F6 submissions are closed (end of Week 15):
  → Freeze nomination counts
  → Calculate final Normalized_Score for each student
  → Update Student Roster: Peer_Nom_Score_LO1LO2, Peer_Nom_Score_LO3, Peer_Nom_Score_LO4
```

---

## Handling Ties and Edge Cases

| Scenario | Handling |
|---|---|
| Two students tied in nomination count | Both receive the same normalized score — no tie-breaking needed |
| Student receives 0 nominations | Score = 0 (counts as a data point, not excluded) |
| Team has only 2 members | Nomination max = 1; normalized score is binary (0 or 5) — flag for faculty review |
| Anomalous submission count (>5 submissions for a 6-person team) | Flag for Operations review; exclude excess submissions from scoring |

---

## Distribution Logistics

| Step | Action | Owner |
|---|---|---|
| 1 | Operations creates 5 form variants (one per team, with that team's names) | Operations |
| 2 | Each variant is sent only to the corresponding team's private Teams channel | Operations |
| 3 | Operations posts: "Complete the anonymous peer recognition form by [date]. Link only works once — please don't share it outside the team." | Operations |
| 4 | Reminder sent if submission count < team size - 1 (some non-response is expected) | Operations |
| 5 | Form closed after Week 15 deadline | Operations |

---

## Form Settings

| Setting | Value |
|---|---|
| Who can fill out | Anyone with the link (anonymous — no sign-in) |
| Response receipt | Off |
| Show results | Off — **critical for anonymity** |
| One response per person | Cannot enforce (anonymous) — manage via distribution control |
| Confirmation message | "Your recognition has been submitted anonymously. Thank you for helping us recognize great teammates." |
