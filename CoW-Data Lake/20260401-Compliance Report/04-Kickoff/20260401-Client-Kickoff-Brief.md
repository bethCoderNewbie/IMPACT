# Project Kickoff Brief
**Project:** Data Governance Review & Data Environment System Requirements  
**Client:** City of Wichita (CoW)  
**Consulting Team:** IMPACT — Barton School of Business, Wichita State University  
**Date:** April 1, 2026  
**Location:** `04-Kickoff/20260401-Client-Kickoff-Brief.md`  

---

## What This Project Is About

The City of Wichita manages records across 22 departments using Laserfiche Cloud and a set of departmental data management lists. As CoW prepares to modernize its data storage and analysis environment, this project will do two things:

1. **Review your current Data Governance framework** — We will audit how data is classified, retained, accessed, and governed today, compare it against industry standards, and give you a clear picture of where you stand and what needs to change.

2. **Define requirements for your new data environment** — Working with your IT department, we will document exactly what the new data storage and analysis system needs to do — so CoW can evaluate solutions and vendors with confidence.

---

## Scope of Work

### What We Will Do

| Area | Description |
|---|---|
| Data Classification Review | Assess how data types are labeled and secured across departments |
| Metadata & File Naming Standards | Evaluate consistency and gaps in how files are named and tagged |
| Records Coordinator Assessment | Review roles, responsibilities, and gaps for the 30+ records coordinators |
| Retention Schedule Compliance | Verify that retention schedules align with legal requirements and are being enforced |
| Access Control Review | Assess who can access what, and whether access procedures are documented |
| Sensitive Data Handling | Review workflows for flagging, accessing, and disposing of sensitive records |
| System Integration Mapping | Document how data flows between Laserfiche and other CoW systems |
| System Requirements Gathering | Interview IT and stakeholders to define requirements for the new data environment |

### What Is Not in Scope

- Implementing any new system or software
- Rewriting city policy documents
- Training staff on Laserfiche or any other platform
- Procuring or recommending specific vendors

---

## Deliverables

You will receive three documents. They are delivered in sequence — the first must be approved before the second and third can be completed.

### Deliverable 1: Standards Selection Brief
**Delivered:** May 16, 2026 | **Draft shared for review:** May 5, 2026

This is a short advisory document that answers one question: **which data governance standard should CoW align to?**

Without an agreed standard, the gap analysis in Deliverable 2 has no baseline — it cannot tell you whether a gap is critical or minor, or what "good" looks like for your organization. This step ensures the rest of the work is grounded in a framework that actually fits CoW.

We will evaluate three frameworks and recommend the best fit:

| Framework | Best For |
|---|---|
| **DAMA-DMBOK v2** | Organizations building a broad data management program across classification, quality, retention, and architecture |
| **NIST SP 800-188** | Organizations where the primary driver is government data security, privacy, and de-identification |
| **ISO 8000** | Organizations where the primary driver is data accuracy, consistency, and cross-system interoperability |

> **Your input matters here.** If CoW has ever been required by a city policy, state mandate, audit finding, or grant condition to align with a specific standard, tell us at the kickoff call. It may simplify or eliminate this step entirely. See questions 16 and 17 in the questionnaire section below.

All three deliverables are shared simultaneously in Week 5 for your review. Deliverables 2 and 3 are drafted against our internal framework recommendation from Week 3. **If you select a different standard during your Week 5 review, revisions to all three deliverables will be required and may affect the May 16 delivery date.** You may accept our recommendation, select a different standard, or specify a combination — any choice is valid, but it must be confirmed in writing during the review window.

---

### Deliverable 2: Data Governance Review Report
**Delivered:** May 16, 2026 | **Draft shared:** May 5, 2026

A plain-language compliance report that covers:
- Where CoW's governance practices stand today
- Gaps identified across 10 governance domains, benchmarked against the standard confirmed in Deliverable 1
- Ranked recommendations with risk levels and suggested owners

### Deliverable 3: System Requirements Document
**Delivered:** May 16, 2026 | **Draft shared:** May 5, 2026

A technical specification document that covers:
- What the new data environment must do (functional requirements)
- Performance, security, and compliance constraints aligned to the confirmed standard
- Integration needs with Laserfiche and existing CoW systems
- Acceptance criteria CoW can use to evaluate any proposed solution

---

## Timeline

| Week | Activity |
|---|---|
| **Week 1** (Apr 7–11) | Document collection — client provides required materials (see list below) |
| **Week 2** (Apr 14–18) | Stakeholder interviews — primary sessions (City Clerk, IT, CISO) |
| **Week 3** (Apr 21–25) | Stakeholder interviews — supplementary sessions; framework recommendation finalized internally |
| **Week 4** (Apr 28–May 2) | Analysis, drafting, and internal review of all three deliverables |
| **Week 5** (May 5–9) | Client review of draft Deliverables 1, 2, and 3 — feedback window |
| **Week 6** (May 12–16) | Revisions and final delivery of all three deliverables |

> **Note:** All three deliverables are delivered together on May 16. Deliverables 2 and 3 are drafted against our framework recommendation from Week 3. If you select a different standard during your Week 5 review, revisions to all three deliverables may affect the May 16 delivery date. We will notify you immediately if this risk materializes.

---

## What We Need From You

### Required Documents — Please Provide by April 11

These are essential inputs. Without them, the review cannot be completed.

| # | Document | Who Owns It | Priority |
|---|---|---|---|
| 1 | Official Records Retention Schedule (with legal citations) | City Clerk's Office | Critical |
| 2 | Laserfiche system configuration documentation (fields, workflows, security tags) | IT Department | Critical |
| 3 | Records Coordinator list with department assignments and contact information | City Clerk's Office | Critical |
| 4 | Data Classification Policy (defining sensitivity/security levels) | IT Security / CISO | Critical |
| 5 | Access Control Policy and procedures for Laserfiche | IT Department | High |
| 6 | Governance Charter or RACI matrix (if one exists) | PMO or Steering Committee | High |
| 7 | Retention enforcement procedures (how disposals are triggered and approved) | City Clerk / IT | High |
| 8 | Any existing training materials for records management | Training Department | Medium |
| 9 | Data export or system integration policy | IT Department | Medium |

---

## Questionnaire — Questions for Your Team

The following questions will be discussed in stakeholder interviews, but we are sharing them in advance so your team can prepare. Written responses are welcome if preferred.

### For the City Clerk / Records Manager

1. What is the official source of truth for retention schedules — is it the data management lists, a separate policy document, or both?
2. Are retention periods currently enforced automatically in Laserfiche, or is this a manual process?
3. How are records coordinators selected and trained for each department?
4. When a record reaches its retention end date, what is the approval process before it is disposed of?
5. Has CoW ever had a records-related audit finding or compliance issue? If so, what was it?

### For the IT Department / Laserfiche Administrator

6. Which Laserfiche modules are currently active (Forms, Workflow, Records Management, etc.)?
7. How are the SecTag (security tag) fields assigned — manually, automatically, or not at all?
8. What other city systems currently connect to or exchange data with Laserfiche?
9. What is the current data volume in Laserfiche, and what is the expected growth rate?
10. Does CoW have a preferred technology direction for the new data environment (cloud, on-premises, hybrid)?
11. What are the most critical performance requirements for the new system (query speed, uptime, concurrent users)?

### For the CISO / IT Security Lead

12. Are there defined data classification levels for CoW data (e.g., Public, Internal, Confidential, Restricted)?
13. Is there an access recertification process — meaning, are user access rights reviewed periodically?
14. How are access requests to sensitive records currently submitted and approved?
15. What is the maximum acceptable downtime for the data environment (for SLA definition)?
16. Has CoW ever been required — by a city policy, state mandate, audit finding, or grant condition — to align with a specific data governance standard such as NIST, ISO, or DAMA? If yes, which one and what was the requirement?
17. Is there a preference from city leadership or IT leadership on which governance framework CoW should target going forward?

### For Records Coordinators (per department)

18. Do you follow a written SOP for uploading documents to Laserfiche?
19. How confident are you that documents in your department are filed in the correct document class and type?
20. Have you received training on the retention schedule for your department?
21. Do you know who to contact if you have a question about a document classification decision?

### For Legal / Compliance

22. Are there any records categories subject to litigation hold or legal discovery requirements?
23. Are there state or federal regulations beyond standard records law that apply to specific departments (e.g., HIPAA for health-related records, CJIS for police)?

---

## Service Level Agreements (SLAs) — Items CoW Must Define

The following SLAs need to be formally established as part of this engagement. We will capture your responses in the System Requirements Document.

| SLA Item | Question for CoW |
|---|---|
| **System Uptime** | What is the minimum acceptable availability for the data environment (e.g., 99.5% uptime)? |
| **Access Request Response Time** | When a user requests access to a restricted record, how quickly must it be approved or denied? |
| **Retention Disposition Notification** | How far in advance should a records coordinator be notified before a record reaches its disposal date? |
| **Disposition Approval Turnaround** | Once notified, how many business days does a coordinator have to approve or hold a record before it is disposed? |
| **Data Recovery / Backup Window** | If data is accidentally deleted or corrupted, what is the maximum acceptable recovery time (RTO) and data loss window (RPO)? |
| **Audit Report Frequency** | How often should governance compliance audit reports be generated and reviewed (monthly, quarterly)? |
| **Access Recertification Cycle** | How frequently should user access rights be reviewed and revalidated (e.g., annually, semi-annually)? |
| **Incident Response Time** | If a data breach or unauthorized access is detected, what is the required escalation and response time? |

---

## Stakeholder Interviews — Scheduling Request

Please help us schedule the following sessions during Weeks 2–3. All interviews are conducted via Teams or in person.

| Stakeholder | Duration | Preferred Window |
|---|---|---|
| Laserfiche System Administrator | 1–2 hours | Week 2 |
| City Clerk or Records Manager | 1–2 hours | Week 2 |
| CISO / IT Security Lead | 1 hour | Week 2 |
| IT Department Leadership | 1 hour | Week 2 |
| Legal Department Representative | 45 minutes | Week 3 |
| 3–5 Records Coordinators (separate sessions) | 30–45 min each | Week 3 |
| 2–3 Department Heads | 30 minutes each | Week 3 |
| Internal Audit / Compliance Representative | 45 minutes | Week 3 |

---

## Success Metrics — What Does "Done Well" Look Like?

Before we begin, we need to align on what a successful outcome means to CoW. Please discuss the following with your team and share your answers at the kickoff call.

### For the Standards Selection Brief (Deliverable 1)

| # | Question | Why It Matters |
|---|---|---|
| 1 | Has CoW been directed — by policy, audit, grant, or leadership — to align with any specific governance standard? | If yes, Deliverable 1 may be simplified to a confirmation rather than a recommendation |
| 2 | Who in CoW has the authority to approve the standards selection during the Week 5 review? | We need to know this before Week 2 so there is no ambiguity when reviewing Deliverable 1 |
| 3 | If our recommendation surprises you — if it is a standard you have not heard of or did not expect — what would it take for you to trust it? | Helps us calibrate how much evidence and rationale to include in the brief |

### For the Data Governance Review Report

| # | Question | Why It Matters |
|---|---|---|
| 4 | Which of the 10 governance domains matters most to CoW right now? | Helps us prioritize depth of analysis and recommendations |
| 5 | Is the primary audience for this report executive leadership, IT, or both? | Shapes the level of technical detail and tone |
| 6 | What would make you confident enough in the report to act on its recommendations? | Defines the evidence standard we need to meet |
| 7 | Are there any known compliance concerns or audit findings you already need addressed? | Ensures the report directly speaks to existing pressure points |
| 8 | Would you consider this report successful if it identified the top 5 gaps with clear, actionable owners? Or do you need a more comprehensive remediation roadmap? | Sets the right scope for recommendations |

### For the System Requirements Document

| # | Question | Why It Matters |
|---|---|---|
| 9 | Who will use this document — an internal IT team building the system, or vendors bidding on the work? | Determines the format and level of detail required |
| 10 | Does CoW already have a preferred solution or vendor in mind, or is this document meant to be vendor-neutral? | Avoids writing requirements that favor a pre-selected tool |
| 11 | What is the minimum the new system must do for CoW to consider this engagement a success? | Defines the "must-have" baseline separate from "nice-to-have" |
| 12 | Will CoW conduct a formal User Acceptance Test (UAT) before signing off on any new system? | Determines how prescriptive the acceptance criteria section needs to be |
| 13 | Are there budget or infrastructure constraints we should factor into the requirements? | Prevents producing requirements that cannot be met in practice |

### Acceptance Criteria for Our Deliverables

The table below defines what CoW should formally sign off on before we close the engagement. Please confirm or revise these criteria at the kickoff call.

| Deliverable | Acceptance Criterion | Sign-off Deadline |
|---|---|---|
| **Deliverable 1: Standards Selection Brief** | CoW's designated authority signs the sign-off block, either accepting the recommendation or specifying in writing which standard they choose instead | May 9 (during review week) |
| Deliverable 2: Data Governance Review Report | CoW stakeholders confirm the current-state assessment accurately reflects their environment | May 9 (during review week) |
| Deliverable 2: Data Governance Review Report | The gap matrix covers all 10 governance domains with evidence cited for each finding | May 9 |
| Deliverable 2: Data Governance Review Report | Recommendations are specific enough that CoW can assign an owner and begin acting without further clarification | May 9 |
| Deliverable 3: System Requirements Document | IT department confirms that functional requirements reflect actual operational needs | May 9 |
| Deliverable 3: System Requirements Document | All SLA items in the document have been reviewed and approved by the appropriate CoW authority | May 9 |
| Deliverable 3: System Requirements Document | The document is complete enough to share with a vendor or internal IT team as a project brief | May 9 |

> **Action for CoW:** Please identify now who has the authority to approve the standards selection during the Week 5 review (May 5–9). All three deliverables are reviewed simultaneously — having the right decision-maker available that week is critical to meeting the May 16 delivery date.

---

## What CoW Can Expect From Us — Consulting Team SLA

These are our commitments to you for the duration of this engagement.

| Commitment | Standard |
|---|---|
| **Email response time** | We will respond to all client emails within 1 business day |
| **Meeting preparation** | We will send an agenda at least 24 hours before each scheduled session |
| **Draft delivery** | Draft deliverables will be shared no later than the start of Week 5 (May 5) |
| **Revision turnaround** | We will incorporate client feedback and return a revised draft within 3 business days of receiving written comments |
| **Revision rounds** | This engagement includes up to 2 rounds of revisions per deliverable. Additional rounds require mutual agreement |
| **Finding escalation** | If we identify a significant compliance risk during the review, we will notify the primary client contact within 1 business day — we will not wait for the final report |
| **Confidentiality** | All documents, data, and information shared by CoW will be used solely for this engagement and will not be shared outside the IMPACT consulting team |
| **Document ownership** | All final deliverables become the property of the City of Wichita upon sign-off |
| **Point of contact availability** | Our team lead is available Monday–Friday, 9am–5pm CST. Contact: [Consulting Team Lead Name] — [email] |

> **Note:** All three deliverables are delivered on May 16. If CoW's feedback on any draft is received after the agreed review window (Week 5), or if the standards selection results in framework revisions, final delivery may shift accordingly. We will communicate any timeline impact immediately.

---

## Questions Before We Begin?

Please reach out to the consulting team lead before the Week 1 kickoff call if you have any questions about this brief, the document request list, or the interview scheduling process.

We look forward to working with you.

---

*Prepared by IMPACT Consulting — Barton School of Business, Wichita State University*  
*City of Wichita Data Governance & Data Lake Engagement — April 2026*
