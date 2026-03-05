# **SOP 01: SharePoint Governance & File Management**
**Owner:** IMPACT Operations Team  
**Scope:** All Leadership, Team Leads, and Students  
**Location:** Tier 1 (IMPACT Hub) - Standard Operating Procedures
**Effective Date:** 2026-03-02

### **1. The 3-Tier Access Matrix**
To maintain security and reduce "file noise," all users must adhere to the following access levels:

| Tier | Site Type | Primary Use | Access (Read/Write) |
| :--- | :--- | :--- | :--- |
| **Tier 1: Hub** | Communication | SOPs, Media, Archives | **Read:** Everyone / **Write:** Ops & Leadership |
| **Tier 2: Ops** | Team Site | Roster, Finance, Tracking | **Read/Write:** Leadership & Ops Only |
| **Tier 3: Project** | Teams-Integrated | Project Deliverables, Notes | **Read/Write:** Specific Team Members + Leadership |

### **2. Mandatory File Naming Convention**
To ensure files are searchable across the Wichita State M365 tenant, all files must follow this format:
`YYYYMMDD-ProjectName-FileDescription-vX.extension`

*   **Date:** Always use `YYYYMMDD` (e.g., `20260302`) for chronological sorting.
*   **Project Name:** Use a consistent short name (e.g., `Cessna`, `Gulfstream`).
*   **Description:** Clear, concise title (e.g., `WeeklyStatus`, `FinalReport`).
*   **Version:** Use `v1`, `v2`, etc. Do **not** use "FINAL" or "LATEST" in the filename; SharePoint’s version history handles the "latest" version automatically.
*   **Separator:** Use hyphens (`-`) only. Avoid spaces or underscores for better web compatibility.

> **Example:** `20260302-Gulfstream-ProjectTimeline-v2.xlsx`

### **3. Tier 3 (Project Site) Folder Template**
Every new Project Team Site must be provisioned with the following five top-level folders:
1.  **01_External_Deliverables:** Finalized work sent to clients/stakeholders.
2.  **02_Internal_Working_Files:** Drafts, research, and collaborative documents.
3.  **03_Meeting_Notes:** Agendas and minutes for all syncs.
4.  **04_Reference_Materials:** Client-provided data, research papers, or branding.
5.  **05_Archive:** Obsolete drafts or completed project phases.

### **4. Data Retention & The "Archive Trigger"**
*   **Active Status:** Files remain in Tier 3 (Project Site) for the duration of the semester/project.
*   **The Trigger:** Within **14 days** of project completion, the Team Lead must move all files in `01_External_Deliverables` and the `Master Project Record` to the **Legacy Archive** in Tier 1.
*   **Deletion:** Working files in Folder `02` that are not required for "Success Stories" should be deleted 30 days after project close-out to save tenant space.

### **5. Security & Sharing Rules**
*   **External Sharing:** All external sharing (sending files to people outside `@wichita.edu` or `@shockers.wichita.edu`) must be initiated via the `barton.impact@wichita.edu` account or approved by the Operations Team.
*   **Wichita State Licensing:** All students must use their `@shockers.wichita.edu` accounts. Personal OneDrive or personal emails are **strictly prohibited** for any project deliverables.
