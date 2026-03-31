# IMPACT Program — Microsoft Forms Master Index
## All Data Collection Instruments

**Date:** 2026-03-29
**Owner:** Operations Team
**Platform:** Microsoft Forms (native M365, no additional cost)
**All form links to be sent from:** `barton.impact@wichita.edu` service account

---

## Forms Overview

| # | Form Name | Who Fills It | When | Feeds Into | File |
|---|---|---|---|---|---|
| F1 | Student Onboarding Form | Student | Day 1 | Student Roster (Pre-scores, info) | `F1-Student-Onboarding.md` |
| F2 | Student Exit Form | Student | Final week | Student Roster (Post-scores, career) | `F2-Student-Exit.md` |
| F3 | Weekly Task Report | Student | Every Monday | Weekly Task Reports list | `F3-Weekly-Task-Report.md` |
| F4 | PM BARS Evaluation | Project Manager | Final week | Student Roster (PM BARS scores) | `F4-PM-BARS-Evaluation.md` |
| F5 | Deliverable Quality Scorecard | Project Manager | Per deliverable | Deliverable Quality Scores list | `F5-Deliverable-Quality-Scorecard.md` |
| F6 | Peer Nomination | Student (anonymous) | Final week | Peer Nominations list | `F6-Peer-Nomination.md` |
| F7 | Client Behavioral Feedback | Client | Post-project | Master Project List (client scores) | `F7-Client-Feedback.md` |
| F8 | SOP Acknowledgment | Student | Week 1 | Onboarding Tracker | `F8-SOP-Acknowledgment.md` |

---

## Data Flow Summary

```
DAY 1
  F1 → Student Roster (Pre-confidence, Knowledge Test Pre, personal info, media consent)
  F8 → Onboarding Tracker (SOP acknowledgment)

EVERY MONDAY
  F3 → Weekly Task Reports list (hours, deliverables, blockers)

PER DELIVERABLE (ongoing)
  F5 → Deliverable Quality Scores list (Lens A for LO2)

FINAL WEEK
  F2 → Student Roster (Post-confidence, Knowledge Test Post, career outcomes)
  F4 → Student Roster (PM BARS scores — Lens B)
  F6 → Peer Nominations list (anonymous — Lens B)

POST-PROJECT (within 2 weeks of close)
  F7 → Master Project List (Client Y/N checklist — Lens B, LO4/LO5)
```

---

## SharePoint Destination Lists

| Form | SharePoint List | Site Tier |
|---|---|---|
| F1 | Student Roster | Tier 2 — Operations |
| F2 | Student Roster | Tier 2 — Operations |
| F3 | Weekly Task Reports | Tier 3 — Per Team (or unified Tier 2 list) |
| F4 | Student Roster | Tier 2 — Operations |
| F5 | Deliverable Quality Scores | Tier 2 — Operations |
| F6 | Peer Nominations | Tier 2 — Operations |
| F7 | Master Project List | Tier 2 — Operations |
| F8 | Onboarding Tracker | Tier 2 — Operations |

---

## Access Control

| Form | Who Has the Link | How Distributed |
|---|---|---|
| F1 | Student only | Power Automate Flow 2 (welcome email on HR clearance) |
| F2 | Student only | Operations sends in final week |
| F3 | Student only | Power Automate Flow 3 (weekly, every Monday 8AM) |
| F4 | PM only | Operations sends in final week — PM-specific link |
| F5 | PM only | Operations sends after each deliverable is submitted |
| F6 | Student only | Operations sends in final week — anonymous link |
| F7 | Client only | Operations sends post-project — client-specific link |
| F8 | Student only | Included in welcome email (alongside F1) |

---

## Question Type Legend (used in form specs)

| Code | Type | Microsoft Forms Equivalent |
|---|---|---|
| MC | Multiple choice (single select) | Choice → Single answer |
| CHK | Checkboxes (multi-select) | Choice → Multiple answers |
| RATE | Rating scale | Rating |
| TEXT-S | Short text | Text → Short answer |
| TEXT-L | Long text / paragraph | Text → Long answer |
| YN | Yes/No | Choice → Single answer (Yes / No) |
| NUM | Number | Text → Number |
| DATE | Date | Date |
| RANK | Ranking | Ranking |
| BRANCH | Branching logic | Show/hide based on answer |
