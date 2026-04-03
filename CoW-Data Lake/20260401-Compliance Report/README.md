# CoW Data Governance — Compliance Report & System Requirements
**Client:** City of Wichita (CoW)  
**Engagement:** IMPACT Consulting — Data Governance & System Requirements Review  
**Phase:** April 2026 — Formal Compliance Report  
**Date:** 2026-04-01  

---

## Purpose

This folder contains the two primary deliverables for the Data Governance and System Requirements Review engagement:

1. **Data Governance Review Report** — A comprehensive compliance audit of CoW's current Data Governance framework against industry standards (DAMA-DMBOK, NIST, ISO 8000), including a 10-domain gap matrix and prioritized recommendations.
2. **System Requirements Document** — Detailed functional and non-functional requirements for a revamped data storage and analysis environment ("the Data Lake"), developed in collaboration with CoW's IT department.

These deliverables draw from prior-phase artifacts produced during the October 2025 kickoff and November 2025 gap analysis sessions.

---

## Folder Structure

The folder is organized by engagement lifecycle phase — from pre-sales through project closure. Each phase folder contains both internal working documents and client-facing outputs.

```
20260401-Compliance Report/
├── README.md                                    ← This file (index and guide)
│
├── 00-Admin/                                    ← Engagement management, budget, risk, RACI
│   ├── Project-Charter.md
│   ├── RACI-Matrix.md
│   ├── Risk-Register.md
│   ├── Budget-and-Hours-Tracker.xlsx
│   └── Change-Log.md
│
├── 01-Presales/                                 ← Pre-engagement context and opportunity docs
│   ├── Client-Background-Notes.md
│   └── Initial-Inquiry-Summary.md
│
├── 02-Proposal/                                 ← Scope proposal, pricing, team credentials
│   ├── Draft-Proposal/
│   ├── Final-Proposal/
│   └── Pricing-and-Effort-Estimate.xlsx
│
├── 03-Contract/                                 ← SOW, MSA, NDA, change orders
│   ├── SOW-Draft.docx
│   ├── SOW-Signed.pdf
│   ├── NDA.pdf
│   └── Change-Orders/
│
├── 04-Kickoff/                                  ← Kickoff brief, communication plan, governance
│   ├── 20260401-Client-Kickoff-Brief.md         ← Scope, timeline, questionnaire, SLA for client
│   ├── Communication-Plan.md
│   ├── Stakeholder-Register.md
│   └── Kickoff-Meeting-Notes.md
│
├── 05-Discovery/                                ← Interviews, current state, gap analysis inputs
│   ├── Interview-Notes/
│   ├── Current-State-Assessment.md
│   ├── Gap-Analysis-Inputs/
│   └── Workshop-Outputs/
│
├── 06-Delivery/                                 ← Primary deliverables (drafts → final)
│   ├── 06a-Governance-Review/                   ← Data Governance Review Report
│   │   ├── 20260401-DG-Review-Report-v1.md
│   │   └── FINAL/
│   └── 06b-System-Requirements/                 ← System Requirements Document
│       ├── 20260401-System-Requirements-v1.md
│       └── FINAL/
│
├── 07-Supporting-Evidence/                      ← Policy docs, data exports, screenshots, references
│   ├── Data-Quality-Findings/
│   ├── Policy-References/
│   └── System-Screenshots/
│
├── 08-Presentations/                            ← Stakeholder-facing decks per review session
│
├── 09-Closure/                                  ← Sign-off, lessons learned, archival
│   ├── Client-Sign-Off.pdf
│   ├── Lessons-Learned.md
│   ├── Post-Engagement-Retrospective.md
│   └── Final-Invoice-Reference.md
│
└── _Internal/                                   ← Team-only: working notes, drafts, financials
    ├── Working-Papers/
    ├── Internal-Analysis/
    └── Team-Communications/
```

> **Client vs. Internal:** All folders except `_Internal/` may be shared with the client. The `_Internal/` folder contains working papers and draft analysis not intended for client review.

> **Upstream artifacts** from prior engagement phases (October 2025 kickoff, November 2025 gap analysis) live in the parent `CoW-Data Lake/` directory and are referenced as inputs — not copied here.

---

## Deliverable 1: Data Governance Review Report

**Output file:** `01-Governance-Review/20260401-DG-Review-Report-v1.md` (or `.docx` / `.pdf` for final)

### Recommended Document Structure

| Section | Description |
|---|---|
| **1. Executive Summary** | Key findings, critical gaps, top 3 recommendations — 1 page max |
| **2. Methodology** | Standards applied (DAMA-DMBOK v2, NIST SP 800-188, ISO 8000), review process, data sources examined |
| **3. Current State Assessment** | CoW's existing governance structure, Laserfiche alignment, retention schedules, data stewardship roles |
| **4. Compliance Gap Matrix** | 10-domain assessment table: status (Compliant / Partial / Gap), evidence, risk level |
| **5. Industry Benchmarking** | Comparison to peer municipalities and DG industry standards |
| **6. Recommendations & Prioritization** | Ranked action items with owner, effort, and impact |
| **7. Risk Register** | Unaddressed gaps mapped to compliance, operational, and security risk |
| **8. Appendix A** | Data quality findings from 45 departmental data management lists (609 issues) |
| **9. Appendix B** | RACI matrix — Data Governance roles and responsibilities |

### 10 Governance Domains to Assess (from prior gap analysis)

1. Data Classification Schema (Security Tags)
2. File Naming & Metadata Standards
3. Records Coordinators / Data Stewards
4. Stakeholder Roles (RACI Matrix)
5. Retention Schedules
6. Retention Enforcement
7. Access Control Model
8. Sensitive Data Access Workflow
9. Data Export & System Connections
10. Governance Adoption & Change Management

---

## Deliverable 2: System Requirements Document

**Output file:** `02-System-Requirements/20260401-System-Requirements-v1.md` (or `.docx` / `.pdf` for final)

### Recommended Document Structure

| Section | Description |
|---|---|
| **1. Business Context & Objectives** | Why the data environment needs to change; strategic goals and constraints |
| **2. Stakeholder Register** | IT department contacts, department data stewards, governance owners, and their roles |
| **3. Functional Requirements** | Capabilities the system must provide — organized by domain (see below) |
| **4. Non-Functional Requirements** | Performance, security, compliance, availability, scalability targets |
| **5. Data Architecture Diagram** | Logical diagram of proposed data lake layers: ingestion → storage → access → export |
| **6. Integration Requirements** | Laserfiche Cloud connectors, existing CoW departmental systems, API/ETL specs |
| **7. Acceptance Criteria** | Pass/fail conditions for each major requirement — used for UAT sign-off |
| **8. Open Issues & Decisions Log** | Outstanding architectural or policy decisions with owner and target date |

### Functional Requirements Domains

- **Data Ingestion** — Batch and event-driven ingestion from 22+ city departments
- **Data Storage** — Tiered storage strategy (hot / warm / cold); retention enforcement
- **Access Control** — Role-based access aligned to Laserfiche security tags and RACI matrix
- **Data Retention & Disposal** — Automated enforcement of retention schedules from Data Management Lists
- **Search & Discovery** — Metadata-driven discoverability across departments
- **Reporting & Analytics** — Power BI integration; self-service analytics layer
- **Audit & Compliance** — Logging, access trails, export tracking

---

## Upstream Artifacts (Inputs to Use)

| Source Document | Location | Used In |
|---|---|---|
| Governance Gap Analysis v2 | `../Gap Analysis Report/GOVERNANCE-REPORT_2026-04-01_v2.md` | Deliverable 1 — Sections 3, 4 |
| Governance Gap Analysis (detailed) | `../20251104-2nd Meeting/GOVERNANCE_GAP_ANALYSIS.md` | Deliverable 1 — Section 3 |
| On-Prem Infrastructure Overview | `../20251104-2nd Meeting/ON_PREM_DATA_INFRASTRUCTURE_OVERVIEW.md` | Deliverable 2 — Sections 1, 5 |
| Integration Framework | `../IntegrationFramework.md` | Deliverable 2 — Sections 5, 6 |
| Data Management Lists (45 files) | `../Data Management Lists/*.xlsx` | Deliverable 1 — Appendix A; Deliverable 2 — Section 3 |
| Naming & Numbering Conventions | `../Naming Conventions/Naming and Numbering Conventions.docx` | Both — standards reference |
| AR 8.4 IT Open Data Policy | `../AR 8.4 IT Open Data Policy.pdf` | Deliverable 1 — Section 2 |
| Kickoff Questions & Industry Practices | `../20251001-Kickoff/` | Deliverable 1 — Sections 2, 5 |

---

## Naming Conventions

All files in this folder follow the IMPACT project naming standard:

```
YYYYMMDD-DocumentName-vN.ext
```

Examples:
- `20260401-DG-Review-Report-v1.md`
- `20260415-System-Requirements-v2.docx`
- `20260401-Gap-Matrix-Evidence.xlsx`
- `20260401-Stakeholder-Review-Deck-v1.pptx`

Use `-FINAL` suffix on the approved version submitted to the client:
- `20260401-DG-Review-Report-FINAL.pdf`

---

## Status Tracker

### 00 — Admin
- [ ] Project Charter drafted and approved
- [ ] RACI matrix completed
- [ ] Risk register initialized
- [ ] Budget and hours tracker set up

### 01 — Pre-Sales
- [x] Client background documented (`01-Presales/Client-Background-Notes.md`)
- [x] Initial inquiry summarized (`01-Presales/Initial-Inquiry-Summary.md`)

### 02 — Proposal
- [x] Draft proposal written (`02-Proposal/Draft-Proposal/20260401-CoW-Proposal-v1.md`)
- [ ] Draft proposal reviewed and submitted to client
- [ ] Pricing and effort estimate approved

### 03 — Contract
- [ ] SOW drafted
- [ ] SOW signed by both parties
- [ ] NDA executed

### 04 — Kickoff
- [x] Client kickoff brief prepared (`04-Kickoff/20260401-Client-Kickoff-Brief.md`)
- [ ] Success metrics and acceptance criteria confirmed by client
- [ ] SLA commitments agreed and signed off
- [ ] Required documents received from client (due Apr 11)
- [ ] Stakeholder interviews scheduled
- [ ] Kickoff meeting held and notes filed

### 05 — Discovery
- [ ] Stakeholder interviews completed (all 8 sessions)
- [ ] Current state assessment drafted
- [ ] Gap analysis inputs compiled
- [ ] Workshop outputs documented

### 06 — Delivery

#### Deliverable 1: Data Governance Review Report
- [ ] Draft executive summary
- [ ] Current state assessment written (draw from 05-Discovery)
- [ ] 10-domain compliance gap matrix completed
- [ ] Industry benchmarking conducted
- [ ] Recommendations and prioritization written
- [ ] Risk register built
- [ ] Appendix A compiled (data quality findings — 609 issues)
- [ ] Appendix B compiled (RACI matrix)
- [ ] Internal review completed
- [ ] Draft shared with client (by May 2)
- [ ] Client feedback received and incorporated
- [ ] Final version approved and delivered

#### Deliverable 2: System Requirements Document
- [ ] Business context and objectives defined with IT
- [ ] Stakeholder register completed
- [ ] Functional requirements drafted (all 7 domains)
- [ ] Non-functional requirements drafted
- [ ] Data architecture diagram created
- [ ] Integration requirements documented (Laserfiche + existing systems)
- [ ] Acceptance criteria defined
- [ ] Open issues and decisions logged
- [ ] Internal review completed
- [ ] Draft shared with client (by May 2)
- [ ] IT department validation session held
- [ ] Final version approved and delivered

### 07 — Supporting Evidence
- [ ] Data quality findings exported and filed
- [ ] Policy references collected and organized
- [ ] System screenshots captured

### 08 — Presentations
- [ ] Draft review presentation prepared
- [ ] Final presentation delivered to stakeholders

### 09 — Closure
- [ ] Client sign-off received on both deliverables
- [ ] Lessons learned documented
- [ ] Post-engagement retrospective completed
- [ ] Final invoice reference filed
- [ ] Project archived
