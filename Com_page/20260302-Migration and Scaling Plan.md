# IMPACT — Migration & Scaling Plan

**Date:** 2026-03-02
**Assumption:** Historical project data is minor and serves primarily as reference material.
**Goal:** Establish a "Least Complex" M365 architecture that scales from 5 to 9+ teams without manual overhead.

---

## 1. The 3-Tier "Impact Data Home" Architecture

To keep complexity low, we will use a **Hub-and-Spoke** model native to SharePoint:

### Tier 1: The IMPACT Hub (Communication Site)
*   **Purpose:** The central landing page and public-facing storage.
*   **Contents:** SOP Library, Media Assets (Headshots/Logos), Success Stories, and the **Legacy Data Archive**.
*   **Access:** Read access for all students; Write access for Operations/Leadership.

### Tier 2: Operations Site (Team Site)
*   **Purpose:** Secure management of program-wide data.
*   **Contents:** Student Roster, Master Project List, Financials, and Onboarding Trackers.
*   **Access:** Private to Leadership and Operations.

### Tier 3: Project Team Sites (Teams-Integrated)
*   **Purpose:** Day-to-day execution for student teams.
*   **Contents:** Deliverables, Meeting Minutes, Client Documentation.
*   **Access:** Restricted to specific team members + Leadership.

---

## 2. Migration Plan for Historical Project Data

Given that the history is minor, we will avoid complex tagging and instead use a **"Clean Slate"** approach:

### Step 1: Identify the "Truth" (Day 0)
*   Identify the most recent versions of administrative files (Rosters/Evaluations) currently split between Teams and OneDrive.
*   Designate these as the starting point for the Tier 2 Operations Site.

### Step 2: The Legacy Archive
*   Create a folder in the Tier 1 Hub named `00_Archive_Legacy_Data`.
*   Move all minor historical files from personal drives and old OneDrives here.
*   **Trello Export:** Export all Trello boards to PDF/CSV and place them in this archive. Close Trello boards immediately after.

### Step 3: Active Migration (In-Progress Only)
*   Only move "Active" files into the new Tier 3 sites.
*   If a project is finished, it goes to the `00_Archive_Legacy_Data` folder.

---

## 3. Scalability & Organization Rules

*   **Zero-Manual Permissions:** Use Microsoft 365 Groups. Permissions are inherited at the site level. Adding a student to a Team automatically gives them access to their SharePoint files.
*   **Template Folder Structure:** Every Project Site *must* use this structure:
    *   `01_Client_Materials`
    *   `02_Internal_Working_Files`
    *   `03_Final_Deliverables`
    *   `04_Meeting_Notes`
*   **Unified Naming Convention:** All files moved into the new system must follow: `YYYYMMDD_ProjectName_Description_vX`.

---

## 4. Immediate Next Actions

1.  **Audit (48hrs):** Operations team to identify the "Truth" administrative files.
2.  **Hub Setup:** IT/Operations to register the IMPACT Hub Site.
3.  **Migration Wave 1:** Move "Active" project files from Teams into the new Tier 3 sites.
4.  **Migration Wave 2:** Bulk move all other data into the Tier 1 Legacy Archive.

\n\n---\n\n

👋 **New to Desktop Commander?** Try these prompts to explore what it can do:

**1.** Organize my Downloads folder  
**2.** Explain a codebase or repository  
**3.** Create organized knowledge base  
**4.** Analyze a data file (CSV, JSON, etc)  
**5.** Check system health and resources

*Just say the number (1-5) to start!*

\n\n---\n\n