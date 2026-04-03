# Proposal: Data Governance Review & System Requirements
**Prepared by:** IMPACT Consulting — Barton School of Business, Wichita State University  
**Prepared for:** City of Wichita (CoW)  
**Date:** April 1, 2026  
**Version:** v1 — Draft for Client Review  

---

## 1. Executive Summary

The City of Wichita manages records across 22 departments, 30+ records coordinators, and a Laserfiche Cloud platform that holds the city's official document repository. An analysis of CoW's 45 departmental data management lists has identified 609 data quality issues and confirmed significant gaps in governance documentation — including no formal data classification policy, no access control model, and no retention enforcement automation.

IMPACT Consulting proposes a six-week engagement to deliver three outcomes in sequence:

1. A **Standards Selection Brief** — a short advisory document evaluating three applicable governance frameworks and recommending which one CoW should align to. CoW must sign off on this before Deliverables 2 and 3 are benchmarked. Without an agreed baseline, neither downstream deliverable can be completed accurately.
2. A **Data Governance Review Report** — a compliance audit of CoW's current framework benchmarked against the standard confirmed in Deliverable 1, with a 10-domain gap matrix and prioritized recommendations
3. A **System Requirements Document** — detailed functional and non-functional requirements for CoW's planned data storage and analysis environment, developed with the IT department

These deliverables will give CoW the documentation needed to demonstrate governance compliance, address audit exposure, and procure or build a data environment with confidence.

---

## 2. Problem Statement

### 2.1 Governance Framework Gaps

CoW has invested in Laserfiche Cloud and structured its 45 data management lists to define document classification and retention across 22 departments. However, the governance layer that should sit above these tools is missing or undocumented.

**Specific gaps confirmed during October–November 2025 discovery:**

| Gap | Impact |
|---|---|
| No formal data classification policy | Records cannot be consistently secured or shared |
| Security tag (`SecTag`) field is empty in all 45 files | No records have a security classification — all data is treated the same |
| No access control model or documented user roles | Cannot demonstrate who can access what, or why |
| No retention enforcement automation confirmed | Records may be disposed too early or held too long |
| No governance charter or RACI matrix | Accountability for governance decisions is unclear |
| No sensitive data handling procedures | Compliance risk for CJIS, HIPAA-adjacent, and legally privileged records |
| 609 data quality issues in the metadata foundation | Automation built on this data will produce incorrect results |

### 2.2 System Requirements Undefined

CoW has conceptually committed to modernizing its data environment but has not yet documented what that environment must do. Without a requirements document:

- IT cannot scope or plan implementation work
- Vendors cannot provide meaningful proposals
- Investment decisions cannot be evaluated objectively
- Success cannot be measured after delivery

---

## 3. Proposed Scope of Work

### 3.1 What We Will Do

**Workstream 1 — Data Governance Review**

- Review CoW's current governance framework across 10 domains (see Section 4)
- Assess three applicable governance frameworks (DAMA-DMBOK v2, NIST SP 800-188, ISO 8000) against CoW's municipal context and recommend the most appropriate alignment (see Section 4a)
- Benchmark CoW's current state against the recommended standard
- Conduct structured stakeholder interviews with 8 role groups (see Section 6)
- Produce a compliance gap matrix with evidence, risk level, and recommended owner per finding
- Deliver ranked recommendations with effort and impact ratings

**Workstream 2 — System Requirements**

- Interview IT department and relevant stakeholders to document operational needs
- Define functional requirements across 7 domains (ingestion, storage, access, retention, search, reporting, audit)
- Define non-functional requirements (uptime, security, compliance, scalability)
- Document integration requirements for Laserfiche Cloud and existing city systems
- Produce acceptance criteria suitable for vendor evaluation or internal project sign-off

### 3.2 What Is Not in Scope

- Implementing any new system or software
- Rewriting city policy or ordinance documents
- Training staff on Laserfiche or any other platform
- Recommending or procuring specific vendors
- Remediating the 609 data quality issues in the data management lists

---

## 4. The 10 Governance Domains We Will Assess

| # | Domain | Current Status |
|---|---|---|
| 1 | Data Classification Schema | No formal policy; `SecTag` field empty across all records |
| 2 | File Naming & Metadata Standards | Naming structure exists; 6 column header misspellings; no validation enforced |
| 3 | Records Coordinators / Data Stewards | 30+ coordinators identified; roles partially defined; no formal charter |
| 4 | Stakeholder Roles (RACI Matrix) | No RACI exists; accountability structure informal |
| 5 | Retention Schedules | 33 periods defined; legal citation source not confirmed |
| 6 | Retention Enforcement | Triggers defined; automation status in Laserfiche unconfirmed |
| 7 | Access Control Model | No documented access model; no user role definitions |
| 8 | Sensitive Data Access Workflow | No documented process for flagging or accessing sensitive records |
| 9 | Data Export & System Connections | No export governance; Laserfiche integration points undefined |
| 10 | Governance Adoption & Change Management | No training program; no adoption metrics; no change management plan |

---

## 4a. Standards Selection — Preliminary Evaluation Against CoW's Context

CoW has not designated a target governance standard. Based on what we know from the October 2025 kickoff and November 2025 second meeting, we have conducted a preliminary evaluation of the three candidate frameworks below. This evaluation will be validated and finalized during stakeholder interviews in Weeks 2–3, then delivered as Deliverable 1 (Standards Selection Brief) on May 16 alongside Deliverables 2 and 3.

---

### Framework Profiles

**DAMA-DMBOK v2** (Data Management Body of Knowledge, 2nd Edition)
A comprehensive data management framework covering 11 knowledge areas: Data Governance, Data Architecture, Data Modeling, Data Storage, Data Security, Data Integration, Reference and Master Data, Data Warehousing and Business Intelligence, Metadata Management, Data Quality, and Document and Content Management. It includes a Data Management Maturity (DMM) model that allows organizations to assess current state and plan incremental improvement. Widely adopted by government entities and organizations managing complex, multi-department data environments.

**NIST SP 800-188** (De-Identifying Government Datasets)
A narrowly scoped NIST publication focused specifically on techniques for de-identifying government datasets prior to public release. It does not provide a governance framework, does not address retention, access control, metadata standards, or data stewardship roles. Relevant to CoW only insofar as the Open Data Policy (AR 8.4) requires publication of public datasets. It would need to be paired with a broader framework to cover CoW's full governance needs.

**ISO 8000** (Data Quality and Master Data)
An international standard focused on data quality management and master data exchange. Directly applicable to data accuracy, completeness, consistency, and interoperability across systems. ISO 8000-61 covers data quality management processes; ISO 8000-110 covers master data exchange. Strong alignment with CoW's Master Table governance model, which is fundamentally a master data management architecture. However, ISO 8000 does not address governance structure (RACI, stewardship roles), access control, or retention policy — leaving significant gaps for CoW's needs.

---

### Peer City & Industry Benchmarking

CoW explicitly asked us to research what comparable cities are doing and what professional associations recommend. This research will be completed during Weeks 2–3 and incorporated into Deliverable 1. The following questions frame the research scope.

#### Peer Cities

CoW identified four peer cities for benchmarking: **Kansas City (MO)**, **Tulsa (OK)**, **Omaha (NE)**, and **Austin (TX)**. These cities are comparable in scale, regional context, or governance ambition. For each, we will research:

- What data governance framework (if any) they have formally adopted
- How they handle records retention enforcement across departments
- What their data storage and analytics environment looks like
- Whether they have published open data governance policies or maturity assessments

**Preliminary context known at time of proposal:**

| City | What Is Known | Research Priority |
|---|---|---|
| **Austin, TX** | Advanced open data program; Data & Technology Services department published a data governance framework; known to reference DAMA principles | High — most documented; likely confirms DAMA direction |
| **Kansas City, MO** | Smart city initiative with a data lake and analytics platform (KC Stat); data governance less publicly documented but IT governance program exists | High — closest in data lake ambition to CoW |
| **Tulsa, OK** | Oklahoma state records management program in place; city-level governance less documented | Medium — regional peer; useful for retention schedule comparison |
| **Omaha, NE** | Comparable Midwest city; limited public documentation on data governance maturity | Medium — useful as a baseline comparison if governance is early-stage |

#### Professional Associations

| Association | Relevance to CoW |
|---|---|
| **ICMA (International City/County Management Association)** | Publishes data governance guidance specifically for local government; Center for Management and Technology resources address records management, data quality, and analytics maturity. ICMA does not endorse a single framework but consistently references DAMA-aligned principles in its publications. |
| **Bloomberg Philanthropies — What Works Cities (WWC)** | Operates a certification program for city governments on data use and governance. The WWC Standard includes a Data Governance component with explicit criteria around data classification, retention policies, stewardship roles, and access control — directly mapping to CoW's 10 governance domains. Cities that achieve WWC Certification typically align their internal governance programs to WWC criteria. This is a strong candidate for CoW to consider alongside or within DAMA. |

#### Common Challenges We Will Research

CoW specifically asked how other cities have solved two operational problems that mirror their own situation:

| Challenge | What We Will Research |
|---|---|
| **Data stored on USB drives and local hard drives outside governed systems** | How peer cities detected and remediated shadow data; what policies they put in place to prohibit ungoverned storage; how they enforced migration to central repositories |
| **Lack of formal retention schedules or unenforced existing schedules** | How peer cities rebuilt retention programs from scratch or from an inconsistent baseline; what automation they used to enforce schedules; how they handled the transition period while schedules were being formalized |

These challenge-based findings will appear in the Deliverable 1 benchmarking section and will directly inform recommendations in Deliverable 2.

#### How Peer Research Affects the Standards Recommendation

If peer city research confirms that Austin, Kansas City, or ICMA-guided cities use DAMA-DMBOK v2 as their primary reference, it strengthens the preliminary recommendation. If Bloomberg What Works Cities is a certification CoW's leadership wants to pursue, the WWC Standard becomes the primary framework and DAMA serves as a supporting reference. We will present both paths in Deliverable 1 if the research surfaces this option.

---

### Evaluation Against CoW's Context

| Criterion | DAMA-DMBOK v2 | NIST SP 800-188 | ISO 8000 |
|---|---|---|---|
| **Regulatory obligation** | Not mandated, but aligns with Kansas records management statutes and AR 8.4 without conflict | Only relevant to public data release under AR 8.4; does not satisfy broader governance obligations | Not mandated; no conflict with Kansas law, but no alignment either |
| **Maturity match** | Designed for incremental adoption; DMM model explicitly supports low-maturity organizations building from scratch — fits CoW's current state | Too narrow to build a maturity program around; cannot anchor a governance improvement roadmap | Addresses data quality improvement incrementally, but covers only 2 of 10 governance domains CoW needs to close |
| **Coverage fit** | Covers all 10 governance domains under review: classification, metadata, stewardship, RACI, retention, enforcement, access control, sensitive data, integration, and adoption | Covers Domain 8 (sensitive data handling) and parts of Domain 9 (data export) only; silent on all other domains | Covers Domains 2 (metadata standards) and parts of Domain 5 (retention data quality); silent on governance structure, access, enforcement, and adoption |
| **Peer precedent** | Austin TX references DAMA principles in its published data governance framework; ICMA publications consistently reference DAMA-aligned principles; Kansas DAMA chapter exists; Bloomberg What Works Cities certification aligns closely with DAMA knowledge areas | Used by federal agencies and research institutions for public data release; not referenced in ICMA, WWC, or peer city governance programs | Common in manufacturing and enterprise; limited precedent in municipal government; not referenced by ICMA or peer cities |
| **Future roadmap** | Knowledge areas for Data Architecture, Data Warehousing, and Data Integration directly map to CoW's planned data lake environment (ingestion, storage, query, reporting layers) | No guidance on data lake architecture, system integration, or analytics environments | ISO 8000-110 (master data exchange) aligns with the Master Table model and Laserfiche integration, but does not address the broader data lake architecture |

**Scoring summary (H = High fit / M = Medium fit / L = Low fit):**

| | DAMA-DMBOK v2 | NIST SP 800-188 | ISO 8000 |
|---|---|---|---|
| Regulatory obligation | H | M (narrow) | M (neutral) |
| Maturity match | H | L | M |
| Coverage fit | H | L | M |
| Peer precedent (peer cities + ICMA + WWC) | H | L | L |
| Future roadmap | H | L | M |
| **Overall** | **Strong** | **Weak** | **Partial** |

---

### Preliminary Recommendation

Based on CoW's current state, regulatory environment, and planned data lake modernization:

**Primary framework: DAMA-DMBOK v2**
DAMA is the only framework that covers all 10 governance domains CoW needs to address, supports low-maturity organizations building incrementally, aligns with municipal government precedent, and maps directly to the data lake architecture CoW is planning. The DMM maturity model gives CoW a scoring baseline today and a structured improvement path going forward.

**Supplement with ISO 8000 for data quality and master data domains**
ISO 8000-61 (data quality management) and ISO 8000-110 (master data exchange) provide specific, implementable standards for the metadata quality issues identified (609 issues across 45 files) and for the Master Table governance model CoW has already committed to. These complement DAMA rather than replace it.

**NIST SP 800-188 as a reference only**
Retain as a reference for the specific question of how to de-identify records before public release under AR 8.4. It is not appropriate as a primary or supplementary governance framework for CoW's needs.

---

### What Could Change This Recommendation

This preliminary recommendation will be confirmed, adjusted, or overridden based on interview findings in Weeks 2–3:

| If interviews reveal... | Recommendation adjusts to... |
|---|---|
| CoW leadership wants to pursue Bloomberg What Works Cities certification | WWC Standard becomes the primary governance framework; DAMA used as the supporting implementation reference |
| Peer city research confirms Kansas City or Tulsa uses a different standard CoW wants to benchmark against | Adopt that standard to enable direct peer comparison; note gaps vs. DAMA |
| CoW receives federal funding with NIST compliance requirements | Add NIST CSF or NIST SP 800-53 as a co-primary framework alongside DAMA |
| CoW's primary near-term driver is Police Dept. CJIS compliance | Prioritize NIST SP 800-53 (security controls) alongside DAMA |
| City leadership has already committed to ISO certification | Shift to ISO 8000 as primary; supplement with DAMA governance-specific KAs |

> **Action for CoW at kickoff:** If any policy, audit requirement, grant condition, or leadership preference already points to a specific standard, share it before Week 2. It may confirm or change this preliminary recommendation and will be incorporated into Deliverable 1.

---

## 5. Deliverables

### Deliverable 1: Standards Selection Brief

**Format:** Word and PDF  
**Delivered:** May 16, 2026 (draft shared May 5 with Deliverables 2 and 3)  
**Sign-off expected:** During Week 5 client review (May 5–9)

> **Standards must be agreed internally before Week 4 drafting begins.** IMPACT will finalize the framework recommendation based on stakeholder interviews in Weeks 2–3. Deliverables 2 and 3 will be drafted against that internal recommendation. If CoW's Week 5 review results in a standard change, revisions to all three deliverables will be required and may affect the May 16 delivery date.

| Section | Description |
|---|---|
| Purpose | Why selecting a standard matters and what it unlocks for CoW |
| Framework Summaries | Plain-language description of DAMA-DMBOK v2, NIST SP 800-188, and ISO 8000 |
| Peer City Benchmarking | What Kansas City, Tulsa, Omaha, and Austin are doing; what ICMA and Bloomberg What Works Cities recommend; how peer cities solved the USB drive problem and missing retention schedules |
| Evaluation Against CoW's Context | How each framework scores across 5 criteria: regulatory obligation, maturity match, coverage fit, peer precedent, future roadmap |
| Recommendation | The recommended standard (or combination) with rationale |
| CoW Sign-Off Block | Formal acceptance field — signature, date, and any overrides noted in writing |

**Accepted when:** CoW's designated authority signs the sign-off block, either accepting the recommendation or specifying in writing which standard they choose instead.

---

### Deliverable 2: Data Governance Review Report

**Format:** Markdown (working), Word and PDF (final)  
**Draft:** May 2, 2026  
**Final:** May 16, 2026  
**Depends on:** Framework recommendation finalized internally after Week 3 interviews

| Section | Description |
|---|---|
| Executive Summary | Key findings, critical gaps, top recommendations — 1 page |
| Methodology | Review process, data sources examined, standard applied (as confirmed in Deliverable 1) |
| Current State Assessment | How CoW's governance functions today across all 10 domains |
| Compliance Gap Matrix | Domain-by-domain table benchmarked against the confirmed standard: status, evidence, risk level |
| Industry Benchmarking | Comparison to peer municipalities using the same or similar frameworks |
| Recommendations | Ranked by priority with owner, effort, and impact |
| Risk Register | Unaddressed gaps mapped to compliance, operational, and security risk |
| Appendix A | Data quality findings from 45 data management lists (609 issues) |
| Appendix B | RACI matrix — roles and responsibilities for data governance |

**Accepted when:** CoW confirms current-state accuracy; all 10 domains covered with evidence; recommendations are actionable with named owners.

---

### Deliverable 3: System Requirements Document

**Format:** Markdown (working), Word and PDF (final)  
**Draft:** May 2, 2026  
**Final:** May 16, 2026  
**Depends on:** Framework recommendation finalized internally after Week 3 interviews

| Section | Description |
|---|---|
| Business Context & Objectives | Why the current environment falls short and what the new one must achieve |
| Stakeholder Register | IT contacts, data stewards, governance owners, and their requirements |
| Functional Requirements | What the system must do — organized across 7 domains |
| Non-Functional Requirements | Performance, security, compliance, availability, scalability |
| Data Architecture Diagram | Logical diagram: ingestion → storage → access → export |
| Integration Requirements | Laserfiche Cloud connectors, existing CoW departmental systems |
| Acceptance Criteria | Pass/fail conditions for evaluating any proposed solution |
| Open Issues & Decisions Log | Outstanding decisions with owner and target date |

**Accepted when:** IT department validates requirements; all SLAs are confirmed; compliance requirements referenced in the document align with the standard confirmed in Deliverable 1; document is complete enough to share with a vendor or internal project team.

---

## 6. Approach & Methodology

### Phase 1 — Document Review (Week 1)
Analyze documents provided by CoW (see Section 7) to build the evidence base for the gap matrix. Begin preliminary assessment of which governance framework (DAMA-DMBOK v2, NIST SP 800-188, ISO 8000) best fits CoW's regulatory environment and maturity level. Standards selection is finalized during interviews in Phase 2.

### Phase 2 — Stakeholder Interviews (Weeks 2–3)
Conduct structured interviews across 8 role groups to validate document findings, surface undocumented practices, and gather system requirements.

| Stakeholder | Sessions | Duration |
|---|---|---|
| Laserfiche System Administrator | 1 | 1–2 hours |
| City Clerk / Records Manager | 1 | 1–2 hours |
| CISO / IT Security Lead | 1 | 1 hour |
| IT Department Leadership | 1 | 1 hour |
| Legal Department Representative | 1 | 45 minutes |
| Records Coordinators | 3–5 separate sessions | 30–45 min each |
| Department Heads | 2–3 separate sessions | 30 minutes each |
| Internal Audit / Compliance | 1 | 45 minutes |

### Phase 3 — Analysis & Drafting (Week 4)
Synthesize interview findings and document review into both deliverable drafts. Internal quality review before client share.

### Phase 4 — Client Review (Week 5)
Share drafts with CoW. Collect written feedback within the agreed review window.

### Phase 5 — Revisions & Final Delivery (Week 6)
Incorporate feedback and deliver final approved versions of both documents.

---

## 7. What We Need From CoW

### Required Documents — Due April 11, 2026

| # | Document | Owner | Priority |
|---|---|---|---|
| 1 | Official Records Retention Schedule (with legal citations) | City Clerk's Office | Critical |
| 2 | Laserfiche system configuration (fields, workflows, security tags) | IT Department | Critical |
| 3 | Records Coordinator list with department assignments and contacts | City Clerk's Office | Critical |
| 4 | Data Classification Policy | IT Security / CISO | Critical |
| 5 | Access Control Policy and Laserfiche procedures | IT Department | High |
| 6 | Governance Charter or RACI matrix (if any exists) | PMO / Steering Committee | High |
| 7 | Retention enforcement procedures | City Clerk / IT | High |
| 8 | Existing records management training materials | Training Department | Medium |
| 9 | Data export or system integration policy | IT Department | Medium |

### Stakeholder Availability — Weeks 2 & 3

We ask that CoW's project lead coordinate scheduling for all 8 interview sessions during the weeks of April 14–25. All sessions can be conducted via Microsoft Teams or in person.

---

## 8. Timeline

| Week | Dates | Activity |
|---|---|---|
| Week 1 | Apr 7–11 | Document collection; project setup |
| Week 2 | Apr 14–18 | Stakeholder interviews — primary sessions (City Clerk, IT, CISO) |
| Week 3 | Apr 21–25 | Stakeholder interviews — supplementary sessions; framework recommendation finalized internally |
| Week 4 | Apr 28–May 2 | Analysis, drafting of all three deliverables, internal review |
| Week 5 | May 5–9 | Client review of draft Deliverables 1, 2, and 3; CoW reviews and accepts standards recommendation |
| Week 6 | May 12–16 | Revisions and final delivery of all three deliverables |

> Timeline assumes client documents are received by April 11 and all interview sessions are scheduled by April 11. If CoW's Week 5 review results in a standard change to Deliverable 1, revisions to Deliverables 2 and 3 will be required and may affect the May 16 delivery date.

---

## 9. Team

| Role | Responsibility |
|---|---|
| Project Lead | Overall engagement management, client communication, quality assurance |
| Governance Analyst | Data governance framework review, gap matrix, recommendations |
| Systems Analyst | System requirements gathering, functional and non-functional requirements |
| Data Analyst | Data quality analysis, metadata review, Appendix A compilation |

All team members are graduate students in the MSBA or MBA program at the Barton School of Business, Wichita State University, supervised by IMPACT program faculty.

---

## 10. Engagement Terms

### Fees

This engagement is delivered under the IMPACT Consulting program. Fees are structured as follows:

| Item | Detail |
|---|---|
| Engagement fee | [To be confirmed — IMPACT program structure] |
| Included revisions | Up to 2 rounds per deliverable |
| Additional revisions | Require a signed Change Order |

### Service Commitments

| Commitment | Standard |
|---|---|
| Email response | Within 1 business day |
| Agenda delivery | 24 hours before each session |
| Draft delivery | End of Week 4 (May 2) |
| Revision turnaround | 3 business days after written feedback received |
| Finding escalation | Significant compliance risks flagged within 1 business day |
| Confidentiality | All CoW information used solely for this engagement |
| Document ownership | All final deliverables become CoW property upon sign-off |

### Assumptions

1. CoW will provide a designated project lead as primary point of contact
2. Required documents will be available by April 11
3. Interview participants will be available during Weeks 2 and 3
4. Client feedback on drafts will be provided in writing within the Week 5 review window
5. The engagement builds on prior work from October–November 2025; no re-execution of that discovery work is included

### Out-of-Scope Triggers

If any of the following arise during the engagement, a Change Order will be required before proceeding:
- Additional departments or systems beyond the 22 departments in scope
- Implementation or configuration work in Laserfiche
- Policy document drafting beyond what is defined in the deliverables
- More than 2 rounds of revisions per deliverable

---

## 11. Why IMPACT Consulting

- **Familiarity with CoW's environment** — Our team has been working with CoW since October 2025 and has already conducted the gap analysis that underpins this engagement
- **No-bias approach** — As an academic consulting program, we have no vendor relationships that could influence our recommendations
- **Direct access to faculty expertise** — All work is supervised by Barton School faculty with backgrounds in data governance, information systems, and public administration
- **Prior deliverables on record** — October and November 2025 session artifacts are documented and available as inputs, reducing re-discovery time

---

*IMPACT Consulting — Barton School of Business, Wichita State University*  
*City of Wichita Data Governance & Data Lake Engagement — April 2026*  
*Document: `02-Proposal/Draft-Proposal/20260401-CoW-Proposal-v1.md`*
