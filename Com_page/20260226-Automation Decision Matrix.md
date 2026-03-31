# IMPACT — Automation Decision Matrix

**Date:** 2026-02-26
**Linked Plan:** `20260226-Architecture Plan.md`
**Purpose:** Determine which processes should be automated, kept manual, or deferred. Fill in the blank cells with the team's answers before making build decisions.

---

## How to Use This Matrix

1. **Fill in columns** for each process row with the team's honest answers
2. **Score each row** using the scoring guide below
3. **Use the decision rule** to assign automation priority

### Scoring Guide

| Column | How to Score |
|---|---|
| Frequency | Daily=4, Weekly=3, Monthly=2, Ad-hoc=1 |
| Volume/Occurrence | 10+=3, 3–9=2, 1–2=1 |
| Rule-Based? | Fully=3, Mostly=2, Partially=1, No=0 |
| Clear Trigger? | Yes=2, Sometimes=1, No=0 |
| Hours/Week (manual) | 3+=3, 1–3=2, <1=1 |
| Error Risk if Manual | High=3, Medium=2, Low=1 |
| Consequence of Error | High=3, Medium=2, Low=1 |
| Sensitive Data? | Yes=-2, No=0 (penalty — sensitive data needs human review) |
| Human Judgment Needed? | Always=-3, Sometimes=-1, Never=0 (penalty) |

**Total Score → Decision:**
- **14–18:** Automate now — high value, low risk
- **9–13:** Automate with human review step — moderate complexity
- **5–8:** Partial automation or template assist — not fully automatable
- **0–4:** Keep manual — requires judgment or is too infrequent to justify

---

## Section 1: Operations

| Process | Frequency | Volume/ Occurrence | Rule-Based? | Clear Trigger? | Hours/Week (manual) | Error Risk | Consequence of Error | Sensitive Data? | Human Judgment Needed? | **Score** | **Decision** |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Incoming email triage (barton.impact@wichita.edu) | | | | | | | | | | | |
| Route email to correct SharePoint list | | | | | | | | | | | |
| Weekly task report collection — send form | | | | | | | | | | | |
| Weekly task report — aggregate responses | | | | | | | | | | | |
| Meeting minutes filing to SharePoint | | | | | | | | | | | |
| SOP update notification to all teams | | | | | | | | | | | |
| Asset request fulfillment (headshots, logos) | | | | | | | | | | | |
| Scheduling onboarding kickoff meetings | | | | | | | | | | | |
| New team provisioning checklist | | | | | | | | | | | |
| Annual archive review of outdated assets | | | | | | | | | | | |

---

## Section 2: CRM (Client-Facing)

| Process | Frequency | Volume/ Occurrence | Rule-Based? | Clear Trigger? | Hours/Week (manual) | Error Risk | Consequence of Error | Sensitive Data? | Human Judgment Needed? | **Score** | **Decision** |
|---|---|---|---|---|---|---|---|---|---|---|---|
| New client/project request intake from email or website | | | | | | | | | | | |
| Log new project to Master Project List | | | | | | | | | | | |
| Project status update communication to clients | | | | | | | | | | | |
| Follow-up reminder when client hasn't responded | | | | | | | | | | | |
| Project completion notification to client | | | | | | | | | | | |
| Client satisfaction / feedback collection | | | | | | | | | | | |
| Tracking active vs. past clients | | | | | | | | | | | |
| NDA / confidentiality flag on client project files | | | | | | | | | | | |

---

## Section 3: Student Management

| Process | Frequency | Volume/ Occurrence | Rule-Based? | Clear Trigger? | Hours/Week (manual) | Error Risk | Consequence of Error | Sensitive Data? | Human Judgment Needed? | **Score** | **Decision** |
|---|---|---|---|---|---|---|---|---|---|---|---|
| New student application intake | | | | | | | | | | | |
| Onboarding form send (post-HR clearance) | | | | | | | | | | | |
| Student Roster row creation | | | | | | | | | | | |
| Team assignment (matching student to project) | | | | | | | | | | | |
| M365 Group access provisioning | | | | | | | | | | | |
| Training assignment and SOP reading list | | | | | | | | | | | |
| Training completion tracking and reminders | | | | | | | | | | | |
| Weekly deliverable submission acknowledgment | | | | | | | | | | | |
| Success story capture (internship/job placement) | | | | | | | | | | | |
| Student offboarding (graduation or departure) | | | | | | | | | | | |
| Semester-end performance/engagement summary | | | | | | | | | | | |

---

## Section 4: Leadership & Reporting

| Process | Frequency | Volume/ Occurrence | Rule-Based? | Clear Trigger? | Hours/Week (manual) | Error Risk | Consequence of Error | Sensitive Data? | Human Judgment Needed? | **Score** | **Decision** |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Weekly digest of all team deliverables to leadership | | | | | | | | | | | |
| Program impact report (success stories, metrics) | | | | | | | | | | | |
| Student headcount and roster summary | | | | | | | | | | | |
| Cross-team progress dashboard refresh | | | | | | | | | | | |
| Grant/donor reporting data pull | | | | | | | | | | | |

---

## Pre-Filled Reference Rows (From Architecture Plan — Already Decided)

These processes have already been evaluated and included in the Architecture Plan. Shown here for completeness.

| Process | Score (Est.) | Decision | Flow |
|---|---|---|---|
| Incoming email triage | 15 | **Automate now** | Flow 1 |
| IMPACT onboarding form send (post-HR) | 14 | **Automate now** | Flow 2 |
| Student Roster row creation | 14 | **Automate now** | Flow 2 |
| Weekly task report — send form | 16 | **Automate now** | Flow 3 |
| Weekly task report — aggregate responses | 15 | **Automate now** | Flow 3 |
| Success story capture | 13 | **Automate with review** | Flow 4 |
| Team assignment (student → project) | 2 | **Keep manual** — requires judgment about fit, availability, client sensitivity | None |
| I-9 / tax / HR legal paperwork | N/A | **Out of scope** — WSU HR owns | None |

---

## Decision Summary (Fill In After Scoring)

| Priority | Process | Flow / Tool | Owner |
|---|---|---|---|
| Automate now | | | |
| Automate now | | | |
| Automate with review | | | |
| Partial / Template | | | |
| Keep manual | | | |
| Keep manual | | | |
| Out of scope | | | |

---

## The 17 Diagnostic Questions (Reference)

Use these when a process score is borderline or the team disagrees.

**Volume & Frequency**
1. How often does this happen? (Daily / Weekly / Per semester / Ad-hoc)
2. How many records or people are involved each time?
3. Does the volume grow linearly as teams are added?

**Rule Clarity**
4. Can you write the process as a clear if/then rule with no exceptions?
5. Is the input always the same format, or does it vary by person/team?
6. Are there edge cases that require human judgment to resolve?

**Current Pain**
7. How many hours per week does this take manually today?
8. Who currently does it — a specific person, or whoever is available?
9. What happens when that person is out or graduates?

**Error & Risk**
10. How often does the manual process produce errors or dropped items?
11. What is the consequence if the automated version gets it wrong? (Low / Medium / High)
12. Does this process involve sensitive data (student records, client info, financials)?

**Technical Readiness**
13. Is the input data already in a digital, structured format (form, email, list row)?
14. Is there a clear, identifiable trigger event (email arrives, form submitted, date reached)?
15. Does the output go to a predictable destination (a list, a folder, a specific person)?

**Human Dependency**
16. Does someone need to approve or review before the next step happens?
17. Does it require a relationship or contextual judgment (e.g., which team to assign a student to)?
