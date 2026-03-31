# IMPACT Data Home — M365 Architecture Plan

**Date:** 2026-02-26
**Constraint:** Microsoft Office 365 licenses only
**Current Scale:** 5 teams × 5–6 students (~25–30 students)
**Target Scale:** 9 teams × 5–6 students (~45–54 students)

---

## Guiding Principles

- **Zero custom code** — use only native M365 tools (low maintenance, no IT debt)
- **Template-first** — adding a 6th, 7th, 8th team = duplicate a template, not rebuild
- **Least privilege** — students see only their team; leadership sees everything
- **Single entry point** — one SharePoint Hub, everything links back to it

---

## Tier Structure (3 Tiers)

```
┌────────────────────────────────────────────────────────┐
│              TIER 1: IMPACT HUB SITE                   │
│         (SharePoint Communication Site)                │
│  - SOPs  - Announcements  - Assets  - Success Stories  │
└───────────────────┬────────────────────────────────────┘
                    │ Hub Association
        ┌───────────┴───────────┐
        ▼                       ▼
┌───────────────┐     ┌─────────────────────────────────┐
│  TIER 2:      │     │         TIER 3:                 │
│  OPERATIONS   │     │    PROJECT TEAM SITES (x5→x9)   │
│  TEAM SITE    │     │  ┌──────────┐  ┌──────────┐     │
│               │     │  │ Team 1   │  │ Team 2   │ ... │
│ - Roster      │     │  │ Site     │  │ Site     │     │
│ - Onboarding  │     │  └──────────┘  └──────────┘     │
│ - Inbox log   │     └─────────────────────────────────┘
│ - Master list │
└───────────────┘
```

---

## Hub Incorporation Workflow

To incorporate your existing separate Microsoft Teams into the IMPACT architecture, follow this three-step process:

1.  **The "Parent" (The Hub Site):** Create (or have IT create) one SharePoint Communication Site called "IMPACT Hub." This is a clean, webpage-style site for your SOPs, news, and branding.
https://learn.microsoft.com/en-us/sharepoint/create-hub-site
https://learn.microsoft.com/en-us/sharepoint/sharepoint-admin-role

2.  **The "Registration" (The Connection):** In the SharePoint Admin Center, IT must "Register" that IMPACT Hub site as an official Hub Site. This makes it the "Parent" of the organization.
3.  **The "Association" (Linking the Projects):** You (or IT) then go to the settings of each existing Project Team Site and "Associate" them with the IMPACT Hub.

### What happens after they are incorporated?

Once your project sites are "Associated" with the Hub, four things happen automatically:

*   **Shared Navigation:** The top navigation bar from your IMPACT Hub will appear at the top of every Project Team Site. Students can jump from their project file folder back to the "SOPs" or "Success Stories" on the Hub with one click.
*   **Search Roll-up:** If you search for a document on the IMPACT Hub, Microsoft will search through all associated project sites at once (only showing the user files they already have permission to see).
*   **News Aggregation:** If a Team Lead posts a "News" update on their specific Project Site, that headline can automatically "roll up" and appear on the main IMPACT Hub homepage for Leadership to see.
*   **Shared Branding:** If you change the logo or colors on the IMPACT Hub, all your project sites will automatically update to match, ensuring a professional, unified look.

**Summary of the Workflow:**
*   **Step 1:** Create the "IMPACT Hub" (Tier 1).
*   **Step 2:** IT registers it as a Hub.
*   **Step 3:** IT/Ops "Associate" your current separate Teams to that Hub.
*   **Result:** You have a unified network where students stay in their private project silos, but everything is visually and functionally connected to the central IMPACT organization.

---

## Tier 1: IMPACT Hub (Communication Site)

**Purpose:** Public-facing org layer. All members can read; leadership writes.

| Library / List | Tool | Contents |
|---|---|---|
| SOP Library | SharePoint Doc Library | Onboarding guides, process docs |
| Asset Library | SharePoint Doc Library | Headshots, logos, social media branding |
| Success Stories | SharePoint List | Student name, outcome, date, team |
| Announcements | SharePoint News | Leadership posts, program updates |
| Credential Vault | SharePoint List (restricted) | Non-social-media shared credentials only (ops-only access, versioning on) |

> **Credential note:** Social media accounts should use native team/agency features (Meta Business Suite, LinkedIn Team access) so no shared password exists. The SharePoint List covers only credentials for platforms that do not support team logins. All other shared credentials should migrate to Bitwarden Teams long-term if budget allows.

---

## Tier 2: Operations Team Site

**Purpose:** Internal ops/leadership only. Handles intake, student data, and coordination.

| Component | Tool | Purpose |
|---|---|---|
| Student Roster | SharePoint List | Major, grad date, training completed, team |
| Onboarding Tracker | SharePoint List | IMPACT operational onboarding status, steps completed |
| Email Inbox Log | SharePoint List (auto-populated) | All emails to `barton.impact@wichita.edu` logged via Power Automate |
| Master Project List | SharePoint List | All active projects, team assignments, status |
| Meeting Minutes | SharePoint Doc Library | Organized by `Year > Month > Team` |

---

## Tier 3: Project Team Sites (Template Pattern)

**Each team gets one Microsoft Teams team.** Teams uses SharePoint as its file backend automatically.

```
IMPACT - [Project Name] - [Semester] [Year]
├── General channel         ← Announcements, pinned SOP links, Hub link
├── Project Deliverables    ← Weekly task reports, files
├── Meeting Notes           ← Minutes per sprint/week
└── Planner (tab)           ← Replaces Trello (Kanban board)
```

**Naming convention:** `IMPACT - [Client/Project Name] - [Semester] [Year]`
Example: `IMPACT - Heartland Credit Union - Spring 2026`

**Scaling rule:** To add Team 6–9, clone the Team template. Takes ~45 minutes per team with the process below.

---

## SharePoint List Schemas

All lists are built in SharePoint. Fields marked **[R]** are required for operational or legislative reporting. Fields marked **[AACSB]** are required for accreditation assurance of learning.

---

### List 1: Student Roster
**Location:** Tier 2 — Operations Team Site
**Purpose:** Single source of truth for all student employee data across all teams.

| Field Name | Type | Values / Format | Required | Reporting Use |
|---|---|---|---|---|
| Student Name | Person (M365) | Auto-resolved from WSU account | Yes | All reports |
| WSU Email | Text | @shockers.wichita.edu | Yes | Automation trigger |
| Major | Choice | Accounting, Finance, MIS, Marketing, Management, Economics, Other | Yes **[R]** | Majors represented metric |
| Minor | Text | Free text | No | Supplemental |
| Expected Graduation Date | Date | MM/YYYY | Yes **[R]** | Graduation pipeline metric |
| Team Assignment | Lookup → Master Project List | Project name | Yes | Team utilization |
| Semester Cohort | Choice | Spring 2026, Fall 2026, ... | Yes | Semester grouping |
| HR Clearance Date | Date | Date HR confirmation received | Yes | Onboarding time start |
| IMPACT Start Date | Date | Date of first project contribution | Yes **[R]** | Onboarding time = Start − HR Clearance |
| Status | Choice | Active, Completed, Departed | Yes **[R]** | Student retention rate |
| Training Completed | Yes/No | Default: No | Yes **[R]** | Training completion rate |
| Training Completion Date | Date | Set by Flow 5 when Training Completed is changed to Yes (SharePoint cannot detect a column value change and set a date field natively) | Yes | Time-to-ready metric |
| Pre-Assessment Score | Number (1–5) | From onboarding self-assessment form | Yes **[AACSB]** | Skill delta |
| Post-Assessment Score | Number (1–5) | From exit self-assessment form | Yes **[AACSB]** | Skill delta |
| PM Evaluation Score | Number (1–5) | Entered by Project Manager at semester end | Yes **[AACSB]** | Learning outcome achievement |
| Consent to Share Story | Yes/No | Collected on onboarding form | Yes **[R]** | FERPA compliance gate |
| Notes | Multi-line text | Internal ops use only | No | — |

---

### List 2: Master Project List
**Location:** Tier 2 — Operations Team Site
**Purpose:** Tracks all client engagements and project delivery for business partnership reporting.

| Field Name | Type | Values / Format | Required | Reporting Use |
|---|---|---|---|---|
| Project Name | Text | Client + brief descriptor | Yes | All project reports |
| Client Organization | Text | Full legal name | Yes **[R]** | Business partners count |
| Client Contact Name | Text | Primary relationship owner | Yes | CRM |
| Client Contact Email | Text | For automated follow-up | Yes | Flow 1 routing |
| Kansas-Based | Yes/No | Default: Yes | Yes **[R]** | Kansas partner % (legislative) |
| Industry Sector | Choice | Healthcare, Finance, Nonprofit, Retail, Manufacturing, Education, Government, Other | Yes **[R]** | Sectors represented |
| Repeat Client | Yes/No | Manual entry — ops marks Yes when re-engagement is confirmed (SharePoint calculated columns cannot query other list rows; a Power Automate flow can automate this if priority warrants) | Yes **[R]** | Partner retention rate |
| First Engagement Date | Date | Date of first project kickoff with this client | Yes **[R]** | New vs. returning partner |
| Project Start Date | Date | | Yes | Timeline tracking |
| Project End Date (Planned) | Date | | Yes **[R]** | On-time delivery baseline |
| Project End Date (Actual) | Date | | Yes **[R]** | On-time delivery rate |
| Status | Choice | Active, Completed, On Hold, Cancelled | Yes **[R]** | Projects delivered count |
| Assigned Team | Lookup → Teams | Teams team name | Yes | Team → project mapping |
| Client Satisfaction Score | Number (1–5) | From client feedback form (post-project) | Yes **[R]** | Client satisfaction metric |
| NDA Required | Yes/No | Default: No | Yes | Confidentiality controls |
| Estimated Value Delivered ($) | Number | Entered manually by PM at project close: sum of Hours — Client Work from team task reports × agreed rate proxy (currently estimated at $50–$75/hour). Cross-list aggregation is not supported by SharePoint calculated columns. | Yes **[R]** | Legislative value metric |
| Notes | Multi-line text | Internal use | No | — |

---

### List 3: Weekly Task Reports
**Location:** Tier 3 — Each Project Team Site (one list per team)
**Purpose:** Captures per-student weekly hours and deliverables. Feeds applied learning hour totals and value-delivered calculations.

| Field Name | Type | Values / Format | Required | Reporting Use |
|---|---|---|---|---|
| Student Name | Person (M365) | Auto-resolved | Yes | Per-student hours |
| Week Ending Date | Date | Auto-set to Sunday of current week | Yes | Submission timeliness |
| Hours — Client Work | Number | Decimal allowed (e.g., 7.5) | Yes **[R]** | Applied learning hours; value delivered |
| Hours — Admin / Coordination | Number | Decimal allowed | Yes **[R]** | Operational overhead ratio |
| Hours — Training | Number | Decimal allowed | Yes **[AACSB]** | Training investment tracking |
| Deliverable Completed This Week | Multi-line text | Free text description | Yes **[R]** | Deliverable tracking |
| Blockers / Issues | Multi-line text | Free text | No | PM visibility |
| Submission Timestamp | Date/Time | Auto-set on form submit | Yes **[R]** | Submission rate metric |
| Reviewed by PM | Yes/No | PM marks after review | Yes | Quality gate |

> **Routing note:** Flow 3 sends one form link but responses must route to the correct team's list. A single shared form has no native mechanism to target 5–9 separate team-specific lists. See Open Question Q7 for the three routing architecture options. Decision required before Flow 3 is built.

---

### List 4: Onboarding Tracker
**Location:** Tier 2 — Operations Team Site
**Purpose:** Tracks the status of each student's IMPACT operational onboarding from HR clearance through first contribution.

| Field Name | Type | Values / Format | Required | Reporting Use |
|---|---|---|---|---|
| Student Name | Lookup → Student Roster | | Yes | Cross-reference |
| HR Clearance Received | Yes/No | Set by Flow 1 on email match | Yes | Flow 2 trigger |
| Welcome Email Sent | Yes/No | Auto-set by Flow 2 | Yes | Audit trail |
| Onboarding Form Submitted | Yes/No | Auto-set when Forms response received | Yes | Step tracking |
| Access Provisioned | Yes/No | Set manually by Operations | Yes | Access gate |
| SOP Training Assigned | Yes/No | Set by Operations | Yes | Training gate |
| Training Completed | Yes/No | Linked to Student Roster field | Yes | Completion tracking |
| Onboarding Complete | Yes/No | Set by Flow 5 when all prerequisite fields = Yes (SharePoint cannot evaluate multiple columns and flip a computed field natively) | Yes **[R]** | Onboarding time metric |
| Days to Complete | Calculated | = Onboarding Complete Date − HR Clearance Date | Yes **[R]** | Onboarding speed metric |
| Notes | Multi-line text | Internal | No | — |

---

### List 5: Success Stories
**Location:** Tier 1 — IMPACT Hub Site
**Purpose:** Documents student outcomes for legislative reporting, donor engagement, and program evaluation.

| Field Name | Type | Values / Format | Required | Reporting Use |
|---|---|---|---|---|
| Student Name | Text | (Not linked — FERPA: consent required first) | Yes | Story attribution |
| Consent Given | Yes/No | Must = Yes — FERPA gate (view filter alone is insufficient; see enforcement note below) | Yes **[R]** | FERPA gate |
| Graduation Date | Date | MM/YYYY | Yes **[R]** | Post-graduation timeline |
| Outcome Type | Choice | Internship, Full-Time Job, Graduate School, Other | Yes **[R]** | Categorized outcomes |
| Employer / Institution | Text | | Yes **[R]** | Industry tracking |
| Role / Position | Text | | Yes | Detail |
| Date of Outcome | Date | | Yes **[R]** | Time from IMPACT to placement |
| IMPACT Team / Project | Lookup → Master Project List | | Yes **[R]** | Attribution to specific engagement |
| Quote / Story | Multi-line text | Student-provided quote | No | Marketing, donor use |
| Submitted By | Person (M365) | Student or PM | Yes | Audit trail |

> **FERPA enforcement note:** A SharePoint list view filter on `Consent = Yes` is not sufficient — any user with Read access can query the list API and see all rows including those with `Consent = No`. FERPA requires access control at the item level. See Open Question Q6 for options. Decision required before Hub site is built.

---

### List 6: Email Inbox Log
**Location:** Tier 2 — Operations Team Site
**Purpose:** Auto-populated by Flow 1. Provides a searchable audit trail of all inbound communications.

| Field Name | Type | Values / Format | Required | Reporting Use |
|---|---|---|---|---|
| Received Date/Time | Date/Time | Auto-set by Flow 1 | Yes | Audit trail |
| Sender | Text | Auto-set from email From field | Yes | CRM |
| Subject | Text | Auto-set | Yes | Routing reference |
| Category | Choice | Student Application, Client Request, HR Clearance, General, Other | Yes | Triage tracking |
| Routed To | Choice | Onboarding Tracker, Master Project List, Unrouted | Yes | Flow accountability |
| Handled | Yes/No | Set manually after follow-up | Yes | Open item tracking |
| Notes | Multi-line text | Operations notes | No | — |

---

## Team Provisioning Process

Each new team requires two parties: **IT** and **Operations**. Scope is divided as follows.

### IT Responsibilities (requires IT ticket per new team)

- Create the M365 Group and Teams team from the approved IMPACT template
- Associate the team's SharePoint site to the IMPACT Hub
- Grant shared mailbox OAuth access to Power Automate service account (`barton.impact@wichita.edu`)
- Confirm external sharing is **disabled** on the new team site

### Operations Responsibilities (~45 min per new team)

1. Submit IT ticket using the standard provisioning request form
2. Once IT confirms — name the team using the naming convention above
3. Copy the Planner board from the template team into the new team
4. Create the team's entry in the Master Project List (Operations Site)
5. Add team members to the M365 Group (permissions auto-inherit)
6. Pin the SOP Library link and Hub link to the General channel
7. Send team welcome message with onboarding form link

### What Operations Does NOT Own

- Creating new SharePoint site collections from scratch — IT owns that
- Modifying Power Automate flows — flows are List-based and require no change per new team
- Managing individual file-level permissions — M365 Group inheritance handles it

---

## IMPACT Onboarding Scope

**Boundary:** WSU HR owns all Kansas state and university legal employment requirements. IMPACT onboarding begins **after** HR confirms the student is cleared to start. That HR confirmation email to `barton.impact@wichita.edu` is the trigger for the IMPACT onboarding flow.

**Rule:** HR makes them an employee. IMPACT makes them a functioning team member.

| Stage | What IMPACT Covers | Tool |
|---|---|---|
| Pre-start | Send welcome email with self-assessment form link | Power Automate (triggered by HR confirmation email) |
| Day 1 — Self-Assessment | Skills, availability, preferred work style, prior experience | Microsoft Forms |
| Day 1 — Preferences | Name tag info, headshot submission, bio for website | Microsoft Forms |
| Day 1 — Access | Add to Teams team, SharePoint, Planner | Operations (manual or Power Automate) |
| Week 1 — Training | Assign SOP reading list, track completion | SharePoint List checklist |
| Week 1 — Introduction | Structured intro to project team and PM | Teams meeting (manual) |
| Ongoing | Training completion log, weekly report submissions | SharePoint Lists |

### What IMPACT Explicitly Does NOT Own

- I-9 verification
- Tax withholding forms (W-4)
- Employment contract / offer letter
- Background checks
- Payroll setup

---

## Automation Flows (Power Automate — all native, no cost)

> All flows must be owned by the **shared service account** (`barton.impact@wichita.edu`), not a personal account. This prevents flows from breaking when a student worker graduates or leaves.

### Flow 1: Email Intake Router

```
Trigger: Email arrives at barton.impact@wichita.edu
  ├── If subject contains "application" or "student" → log to Onboarding Tracker list
  ├── If subject contains "client" or "project" → log to Master Project List
  ├── If subject contains "HR cleared" or "start date" → trigger Flow 2 (onboarding)
  └── All emails → append to Email Inbox Log list
```

### Flow 2: IMPACT Operational Onboarding

```
Trigger: HR confirmation email arrives (keyword match in Flow 1)
  → Send welcome email with Microsoft Forms link (self-assessment + preferences)
  → Create row in Student Roster (SharePoint List)
  → Notify Operations team via Teams message
  → [Manual step] Operations adds student to correct team's M365 Group
```

### Flow 3: Weekly Task Report

```
Trigger: Scheduled — every Monday 8:00 AM
  → Send Microsoft Forms link to all active student emails
  → Form responses auto-append to team's Deliverables List
  → Leadership gets a digest email summary (via Power Automate)
```

> **Routing gap:** A single shared form cannot route responses to 5–9 separate team-specific lists without knowing which team the student belongs to. See Open Question Q7 — this must be resolved before Flow 3 is designed.

### Flow 4: Success Story Capture

```
Trigger: Microsoft Form submitted (by student or PM)
  → Append to Success Stories list on Hub site
  → Post to Leadership Teams channel for visibility
```

### Flow 5: Field State Automation

```
Trigger: Student Roster item updated — Training Completed changed to Yes, Training Completion Date is blank
  → Set Training Completion Date = current date

Trigger: Onboarding Tracker item updated — all prerequisite fields = Yes, Onboarding Complete = No
  → Set Onboarding Complete = Yes
  → Set Onboarding Complete Date = current date (enables Days to Complete calculated column)
```

---

## Permissions Model

| Role | Hub Site | Operations Site | Own Team Site | Other Team Sites |
|---|---|---|---|---|
| Student | Read | No access | Read + Write | No access |
| Project Manager | Read + Write | Read | Full control | No access |
| Operations | Read + Write | Full control | Read | Read |
| Leadership | Full control | Full control | Full control | Full control |

**Implementation:** Use M365 Groups tied to each Teams team — permissions inherit automatically. No manual user management per file.

---

## Scalability Checklist (5 → 9 Teams)

- [ ] Submit IT provisioning ticket for new team
- [ ] IT creates M365 Group, Teams team, and associates SharePoint site to Hub
- [ ] Operations copies Planner template board
- [ ] Operations adds team entry to Master Project List
- [ ] Operations adds team members to M365 Group (permissions auto-apply)
- [ ] Power Automate flows auto-include new team (List-based triggers — no flow changes needed)

No structural changes needed — the architecture absorbs new teams by design.

---

## Build Order (Recommended)

| Step | Component | Why First |
|---|---|---|
| 1 | Hub Communication Site | Foundation everything links to |
| 2 | Operations Team Site + Student Roster List | Core data layer |
| 3 | One Team site as template | Validate before replicating |
| 4 | Power Automate: Email Intake Router (Flow 1) | Highest immediate value, triggers Flow 2 |
| 5 | IMPACT Onboarding Form + Flow 2 | Replaces most painful manual work |
| 6 | Weekly Report Form + Flow 3 | Replaces Trello/manual tracking |
| 7 | Success Story Form + Flow 4 | Enables impact reporting |
| 8 | Replicate Team template × 4 | Scale out to all 5 current teams |
| 9 | Replicate Team template × 4 more | Scale to 9 teams when ready |

---

## Pre-Build Verification Checklist

Confirm all items with WSU IT, WSU HR, and IMPACT Leadership before starting the Build Order. A "No" or "Unknown" on any item requires a plan adjustment before that component is built.

### 1. IT Infrastructure (WSU IT)
| # | Verification Item | Owner | Verified? |
|---|---|---|---|
| V1 | `barton.impact@wichita.edu` has a Power Automate license (confirm no "seeded" plan limits) | WSU IT | [ ] |
| V2 | `barton.impact@wichita.edu` has **Full Access** (not just Send As) on the shared mailbox | WSU IT | [ ] |
| V3 | WSU IT will grant OAuth consent for the Power Automate → Exchange and SharePoint connectors | WSU IT | [ ] |
| V4 | WSU IT will register the IMPACT Hub as a hub site and associate 9+ team SharePoint sites | WSU IT | [ ] |
| V5 | Confirm WSU tenant plan supports 9+ SharePoint hub site associations | WSU IT | [ ] |
| V6 | Student `@shockers.wichita.edu` accounts include Teams, Planner, SharePoint, and Forms access | WSU IT | [ ] |
| V7 | Planner board copy (within Teams) works as expected on the current WSU tenant | WSU IT / Ops | [ ] |
| V8 | Confirm WSU IT policy for disabling **External Sharing** on Tier 3 team sites | WSU IT | [ ] |
| V9 | Verify no MFA or Conditional Access policies block the headless service account (`barton.impact`) | WSU IT | [ ] |

### 2. Data & Process (Operations)
| # | Verification Item | Owner | Verified? |
|---|---|---|---|
| V10 | Obtain one real WSU HR clearance email — confirm subject/keywords for Flow 1 logic | WSU HR / Ops | [ ] |
| V11 | Identify the "Source of Truth" file for the initial Student Roster migration | Operations | [ ] |
| V12 | Confirm legacy data volume fits "Minor History" assumption (<1GB total) | Operations | [ ] |

### 3. Policy & Strategy (Leadership)
| # | Verification Item | Owner | Verified? |
|---|---|---|---|
| V13 | Approve the **48-hour Migration Freeze** window for the initial transition | Leadership | [ ] |
| V14 | Approve the **$50–$75/hour market rate** proxy for "Value Delivered" reporting | Leadership | [ ] |
| V15 | Identify the Faculty Lead for **AACSB Learning Outcome** sign-off (ref: List 1) | Leadership | [ ] |

---

## Open Questions

| # | Question | Status |
|---|---|---|
| Q1 | **Provisioning Ownership** — Who creates the sites? | **Resolved** — IT creates sites; Operations configures. |
| Q2 | **HR Scope** — Is Microsoft Forms sufficient for legal paperwork? | **Resolved** — No. HR handles legal; IMPACT handles operational onboarding. |
| Q3 | **Password Vault** — Long-term credential strategy? | **Resolved** — Social media: native; others: SharePoint (short) / Bitwarden (long). |
| Q4 | **Flow Ownership** — Who owns Power Automate when staff rolls off? | **Resolved** — `barton.impact@wichita.edu` service account. |
| Q5 | **Confidentiality** — How to handle client NDA data on team sites? | **Open** — Options: (a) Power Automate folder permissions; (b) Private Channels. |
| Q6 | **FERPA** — How to enforce Consent=Yes on Success Stories? | **Open** — A view filter is insufficient. Item-level permissions required via Flow 4. |
| Q7 | **Weekly Routing** — How to route one Form to 9 separate lists? | **Open** — Options: (a) 1 Form per team; (b) Dropdown + Flow branching; (c) Unified Tier 2 list. |
| Q8 | **Hub Capacity** — Does WSU IT support the IMPACT Hub registration? | **Open** — Ref V4, V5. Confirm before Step 1. |
| Q9 | **Student Licensing** — Do students have full Teams/Planner/Forms access? | **Open** — Ref V6. Confirm before assuming Planner functionality. |
| Q10 | **Trigger Logic** — What is the exact subject line of HR clearance emails? | **Open** — Ref V10. Needed for Flow 1/2 reliability. |
| Q11 | **Market Rate** — Is the $50-$75/hr proxy approved for legislative reporting? | **Open** — Ref V14. Required for Master Project List value field. |
| Q12 | **AACSB Lead** — Who signs off on the skill delta metrics? | **Open** — Ref V15. Required for List 1 data validation. |
