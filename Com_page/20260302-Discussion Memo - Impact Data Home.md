**TO:** IMPACT Leadership & Operations Teams
**DATE:** 2026-03-02
**SUBJECT:** Discussion Memo: Finalizing the "Impact Data Home" & Operational Roadmap

### 1. Meeting Objective
**Goal:** To align on the transition from manual, disparate systems to a centralized Microsoft 365 environment and define the priorities for onboarding automation.

**Non-Goal:** We are not discussing technical backend configuration beyond the immediate M365 implementation.

### 2. Executive Summary & Context
*   **The Situation:** IMPACT currently relies on disparate systems like Trello and personal emails to track project work and student data. We have established a unified email address (`barton.impact@wichita.edu`) as a first step toward centralization.
*   **The Complication:** Manual onboarding and fragmented project tracking make it difficult to capture student metrics (majors, graduation dates) and "success stories" consistently. We are limited by our current Microsoft Office 365 licenses and need a solution that fits this constraint.
*   **The Core Question:** How do we structure the "Impact Data Home" on SharePoint to effectively automate communications, tracking, and onboarding?
    *   **Category A: Infrastructure & Asset Management**
    *   [DEFERRED] **Category B: Automated Workflows & Digitized Onboarding**
    *   [DEFERRED] **Category C: Project Tracking & Student Impact Metrics**
    *Discussion deferred until Category A infrastructure is finalized.*

### 3. Breakdown of the Category A: Infrastructure & Asset Management

*   **Context:** The team plans to build a centralized SharePoint "home base" for SOPs, media/marketing assets (headshots, branding).
*   **Standardization Goal:** Transition from team-specific "silos" to a Core Operational SOP Suite (File Naming, Project Lifecycle, Communication) to ensure scalability from 5 to 9+ teams.
*   **Current State:** Files, SOPs, and project data are currently scattered across personal drives, individual OneDrives, Microsoft Teams, and Trello boards. Administrative files (rosters, evaluations) are in an "Operations" folder split between Teams and OneDrive. Media assets are being consolidated into a shared Teams folder for website development access.
*   **Assumption:** Historical project data is minor and serves primarily as reference material.


### 4. Proposed 3-Tier "Impact Data Home" Architecture

To maintain security and reduce "file noise," all users must adhere to the following access levels:

| Tier | Site Type | Primary Use | Access (Read/Write) |
| :--- | :--- | :--- | :--- |
| **Tier 1: Hub** | Communication | SOPs, Media, Archives | **Read:** Everyone / **Write:** Ops & Leadership |
| **Tier 2: Ops** | Team Site | Roster, Finance, Tracking | **Read/Write:** Leadership & Ops Only |
| **Tier 3: Project** | Teams-Integrated | Project Deliverables, Notes | **Read/Write:** Specific Team Members + Leadership |

#### **Summary Architecture Table (Product Specifications)**

| Tier | Microsoft Product | SharePoint Site Template | Hub Association |
| :--- | :--- | :--- | :--- |
| **Tier 1** | SharePoint Online | **Communication Site** | **Hub Parent** |
| **Tier 2** | SharePoint + Lists | **Team Site (No Group)** | Associated to Hub |
| **Tier 3** | Teams + SharePoint | **Team Site (Group-Connected)** | Associated to Hub |

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
### What happens after they are incorporated?

Once the project sites are "Associated" with the Hub, four things happen automatically:

*   **Shared Navigation:** The top navigation bar from the IMPACT Hub will appear at the top of every Project Team Site. Students can jump from their project file folder back to the "SOPs" or "Success Stories" on the Hub with one click.
*   **Search Roll-up:** If you search for a document on the IMPACT Hub, Microsoft will search through all associated project sites at once (only showing the user files they already have permission to see).
*   **News Aggregation:** If a Team Lead posts a "News" update on their specific Project Site, that headline can automatically "roll up" and appear on the main IMPACT Hub homepage for Leadership to see.
*   **Shared Branding:** If you change the logo or colors on the IMPACT Hub, all the project sites will automatically update to match, ensuring a professional, unified look.

---
####  **Critical Questions for Leadership Decision:**
*   **Hub Site Authorization:** Will Leadership officially authorize the request for IT to register the "IMPACT Hub" site to enable centralized governance across all 9+ teams?
*   **System Continuity:** Is Leadership committed to the `barton.impact@wichita.edu` service account as the permanent owner of all IMPACT automation and data, regardless of staff/student turnover?

### 4. Required Input from Attendees
| Topic / Question / Input | Target Audience | Purpose / Clear Understanding |
| :--- | :--- | :--- |
| **SOP/Template Audit** | Team Leads | Submit current "best-practice" templates (meeting notes, task lists) for consolidation into IMPACT V1.0 standards. |
| **Operations Source of Truth** | Operations Team | Identify primary owners of current Teams/OneDrive folders to verify the final "source of truth" for rosters and evaluations. |
| **M365 Hub Capacity** | Leadership / IT Admin | Verify tenant capacity and necessary administrative permissions to register the "IMPACT Hub" and successfully associate 9+ dedicated team sites. |
| **Student License Access** | Leadership / IT Admin | Verify if student accounts (`@shockers.wichita.edu`) possess adequate licensing (e.g., beyond "Web Only" or "E1") forpossess adequate licensing (e.g., beyond "Web Only" or "E1") for full access Teams, Planner, SharePoint Online, and Microsoft Forms? |
| **3-Tier Architecture Approval** | Leadership Team | Review and provide formal approval for the "Hub-and-Spoke" model for all project data storage. |
| **Historical project data** | Leadership Team | Confirm historical project data is non-critical. The "Impact Data Home" will be built from scratch to ensure clean standards, with legacy files bulk-moved to a single "Archive" folder in Tier 1.|



### 5. Proposed Next Steps (Post-Discussion)
| Action Item | Primary Owner | Desired Outcome |
| :--- | :--- | :--- |
| **Site Structure Finalization** | Leadership & Ops | Approve on the 3-Tier "Hub-and-Spoke" architecture and folder naming conventions. |
| **Core Operational SOP Suite** | Ops & Team Leads | Drafting of V1.0 standardized procedures (File Naming, Project Lifecycle, Communication). |
| **Weekly Task Reporting** | Team Leads | Standardized template for project reporting to ensure consistent visibility across teams. |
| **Initial Migration Wave** | Operations Team | Migration of prioritized "Active" files to Tier 2 and Tier 3 sites as identified by Team Leads. |
