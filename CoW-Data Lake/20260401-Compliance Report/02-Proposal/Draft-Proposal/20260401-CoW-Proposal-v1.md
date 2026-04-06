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

| Gap | Impact | Risk |
|---|---|---|
| No formal data classification policy | Records cannot be consistently secured or shared | 🔴 Critical |
| `SecTag` field empty in all 45 files — zero records classified | No security differentiation possible; all records treated identically regardless of sensitivity | 🔴 Critical |
| No access control model or documented user roles | Cannot demonstrate who can access what, or why; audit exposure | 🔴 Critical |
| No retention enforcement automation confirmed | Records may be disposed too early (K.S.A. violation) or held indefinitely | 🔴 Critical |
| No sensitive data handling procedures | CJIS compliance risk (Police Dept.); HIPAA-adjacent risk (Community Services, Housing); no Agency Security Officer designated | 🔴 Critical |
| No governance charter or RACI matrix | Accountability for governance decisions is unclear | 🟡 Medium |
| 609 data quality issues in the metadata foundation — 45 are blocking | 45 issues will cause Laserfiche automation to fail or misroute records; 558 are cosmetic but indicate absent validation | 🟠 High |

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

> **Enhanced gap matrix available:** A full compliance gap matrix with risk severity ratings, evidence citations, regulatory obligations, peer benchmark status, recommended owners, and stakeholder interview questions has been developed as an input document for Deliverable 2. See `05-Discovery/Gap-Analysis-Inputs/20260401-CoW-Enhanced-Gap-Matrix-v1.md`.

| # | Domain | Current Status | Risk Severity |
|---|---|---|---|
| 1 | Data Classification Schema | No formal policy; `SecTag` field empty across all 45 files — zero records classified | 🔴 Critical |
| 2 | File Naming & Metadata Standards | Naming structure exists; 609 data quality issues (45 blocking automation); no validation enforced | 🟠 High |
| 3 | Records Coordinators / Data Stewards | 30+ coordinators identified; roles partially defined; no formal charter | 🟡 Medium |
| 4 | Stakeholder Roles (RACI Matrix) | No RACI exists; accountability structure informal | 🟡 Medium |
| 5 | Retention Schedules | 33 periods defined; legal citation source not confirmed against K.S.A. 12-120/121 | 🟠 High |
| 6 | Retention Enforcement | Triggers defined; Laserfiche RM module configuration unconfirmed; no disposition approval workflow | 🔴 Critical |
| 7 | Access Control Model | No documented model; no user role definitions; no security groups confirmed in Laserfiche | 🔴 Critical |
| 8 | Sensitive Data Access Workflow | No CJIS or HIPAA-adjacent procedures; no ASO designated; Police and Community Services records unprotected | 🔴 Critical |
| 9 | Data Export & System Connections | No export governance; data lake integration requirements undefined | 🟠 High |
| 10 | Governance Adoption & Change Management | No training program; no adoption metrics; no change management plan | 🟢 Low |

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

CoW explicitly asked us to research what comparable cities are doing and what professional associations recommend. A preliminary benchmarking research report (v2, April 2, 2026) has been completed and incorporated into this section. Direct outreach to peer city staff is scheduled for Week 1 to supplement published-source findings. Final benchmarking results will be incorporated into Deliverable 1.

#### Peer Cities

CoW's official peer city list (sourced from the city budget book, confirmed at the April 2026 client meeting) includes: **Kansas City (MO)**, **Tulsa (OK)**, **Omaha (NE)**, **Austin (TX)**, **Des Moines (IA)**, and **Denver (CO)**. Fort Worth, TX was also noted as a city used for grants system comparisons. The initial benchmarking research (v2, April 2, 2026) covered Austin, Kansas City, Tulsa, and Omaha. Des Moines and Denver will be researched during Week 1 direct outreach and incorporated into Deliverable 1. For each city, we will research:

- What data governance framework (if any) they have formally adopted
- How they handle records retention enforcement across departments
- What their data storage and analytics environment looks like
- Whether they have published open data governance policies or maturity assessments

**Preliminary context known at time of proposal:**

| City | What Is Known | Research Priority |
|---|---|---|
| **Austin, TX** | Custom governance framework built on 2013 Open Government Directive and Texas statutes (TPIA, Texas HB 149/TRAIGA); two-tier classification (Public / Non-Public) in contract terms only; no standalone data classification policy; no CDO; Open Data Liaisons model (one designated per department) | High — most documented; confirms that all peer cities built custom frameworks rather than adopting a named standard |
| **Kansas City, MO** | 2025 Data Governance Charter (July 1, 2025) + UK GDS-adapted Data Service Standard (Oct 2025); CDO role formalized in City Code Section 2-2133; 4-tier classification (Public / Private / Sensitive / Confidential); named 6-member Governance Committee; Data Owners + Data Stewards defined; Bloomberg Gold Certification | High — most mature committee structure and classification model among peers; charter and committee structure directly adaptable for CoW |
| **Tulsa, OK** | Series of executive orders (2015–2019) + COP 1400 (Feb 26, 2026); 4-tier classification (Public / Internal / Sensitive / Protected) with explicit approval chains for sensitive and protected records; 4-role stewardship model; 3-tier Active Directory access control; Urban Data Pioneers adoption program; Bloomberg Silver Certification | High — 7 of 10 governance domains have explicit published policy; single most reusable peer governance model for CoW |
| **Omaha, NE** | No formal governance program found; no CDO; IT services shared via DOTComm; included as cautionary baseline — governance fragmentation documented since 1982 | Medium — documents the cost of inaction; not a reusable governance model |
| **Des Moines, IA** | On CoW's official budget book peer list; governance program unknown — research scheduled for Week 1 | High — official peer; Iowa Code Chapter 304 provides state records baseline; city-level program TBD |
| **Denver, CO** | On CoW's official budget book peer list; governance program unknown — research scheduled for Week 1 | High — official peer; Colorado CRS Title 24 Art. 80 provides state records baseline; city-level program TBD |

#### Professional Associations

| Association | Relevance to CoW |
|---|---|
| **ICMA (International City/County Management Association)** | Publishes data governance guidance specifically for local government; Center for Management and Technology resources address records management, data quality, and analytics maturity. ICMA does not endorse a single framework but consistently references DAMA-aligned principles in its publications. |
| **Bloomberg Philanthropies — What Works Cities (WWC)** | Operates a certification program for city governments on data use and governance. The WWC Standard includes a Data Governance component with explicit criteria around data classification, retention policies, stewardship roles, and access control — directly mapping to CoW's 10 governance domains. CoW was a past WWC participant; per the April 2026 client meeting, staff were assigned to complete re-enrollment. No Kansas city holds WWC Certification — if CoW pursues and earns it, it would be the first. Kansas City (Gold) and Tulsa (Silver) demonstrate this is achievable for mid-size Midwest cities. |

#### Common Challenges We Will Research

CoW specifically asked how other cities have solved two operational problems that mirror their own situation:

| Challenge | What We Will Research |
|---|---|
| **Data stored on USB drives and local hard drives outside governed systems** | How peer cities detected and remediated shadow data; what policies they put in place to prohibit ungoverned storage; how they enforced migration to central repositories |
| **Lack of formal retention schedules or unenforced existing schedules** | How peer cities rebuilt retention programs from scratch or from an inconsistent baseline; what automation they used to enforce schedules; how they handled the transition period while schedules were being formalized |

These challenge-based findings will appear in the Deliverable 1 benchmarking section and will directly inform recommendations in Deliverable 2.

#### How Peer Research Affects the Standards Recommendation

Peer research (completed April 2, 2026) found that none of the four peer cities formally adopt DAMA. Austin, Kansas City, and Tulsa each built custom governance frameworks; DAMA knowledge areas are consistent with — but not cited in — those frameworks. This finding reframes rather than undermines the DAMA recommendation: CoW should enact governance authority through an executive order or resolution (as all peers did) and use DAMA as the internal implementation guide to ensure comprehensive coverage. If Bloomberg What Works Cities is a certification CoW's leadership wants to pursue, WWC criteria become the primary external benchmark and DAMA serves as the supporting implementation reference. We will present both paths in Deliverable 1.

---

### Evaluation Against CoW's Context

| Criterion | DAMA-DMBOK v2 | NIST SP 800-188 | ISO 8000 |
|---|---|---|---|
| **Regulatory obligation** | Not mandated, but aligns with Kansas records management statutes and AR 8.4 without conflict | Only relevant to public data release under AR 8.4; does not satisfy broader governance obligations | Not mandated; no conflict with Kansas law, but no alignment either |
| **Maturity match** | Designed for incremental adoption; DMM model explicitly supports low-maturity organizations building from scratch — fits CoW's current state | Too narrow to build a maturity program around; cannot anchor a governance improvement roadmap | Addresses data quality improvement incrementally, but covers only 2 of 10 governance domains CoW needs to close |
| **Coverage fit** | Covers all 10 governance domains under review: classification, metadata, stewardship, RACI, retention, enforcement, access control, sensitive data, integration, and adoption | Covers Domain 8 (sensitive data handling) and parts of Domain 9 (data export) only; silent on all other domains | Covers Domains 2 (metadata standards) and parts of Domain 5 (retention data quality); silent on governance structure, access, enforcement, and adoption |
| **Peer precedent** | No peer city formally adopts DAMA. All four peers built custom governance frameworks (executive orders, charters) without referencing DAMA as a parent standard. However, the governance structures they independently developed — four-tier classification, stewardship roles, metadata requirements, access control — are fully consistent with DAMA knowledge areas. DAMA is the implementation guide that ensures CoW doesn't leave governance domains undocumented that peer cities have also left undocumented. ICMA does not endorse a specific framework. Bloomberg WWC criteria overlap substantially with DAMA but do not require DAMA adoption | Used by federal agencies and research institutions for public data release; not referenced in ICMA, WWC, or peer city governance programs | Common in manufacturing and enterprise; limited precedent in municipal government; not referenced by ICMA or peer cities |
| **Future roadmap** | Knowledge areas for Data Architecture, Data Warehousing, and Data Integration directly map to CoW's planned data lake environment (ingestion, storage, query, reporting layers) | No guidance on data lake architecture, system integration, or analytics environments | ISO 8000-110 (master data exchange) aligns with the Master Table model and Laserfiche integration, but does not address the broader data lake architecture |

**Scoring summary (H = High fit / M = Medium fit / L = Low fit):**

| | DAMA-DMBOK v2 | NIST SP 800-188 | ISO 8000 |
|---|---|---|---|
| Regulatory obligation | H | M (narrow) | M (neutral) |
| Maturity match | H | L | M |
| Coverage fit | H | L | M |
| Peer precedent (peer cities + ICMA + WWC) | M | L | L |
| Future roadmap | H | L | M |
| **Overall** | **Strong** | **Weak** | **Partial** |

---

### Preliminary Recommendation

Based on CoW's current state, regulatory environment, and planned data lake modernization:

**Primary framework: DAMA-DMBOK v2 — as implementation guide for a custom governance policy**
DAMA is the only framework that covers all 10 governance domains CoW needs to address, supports low-maturity organizations building incrementally, and maps directly to the data lake architecture CoW is planning. No peer city formally adopted DAMA as their primary standard — Austin, Kansas City, and Tulsa each built custom governance policies through executive orders and charters, then implemented those policies in their systems. CoW should follow the same pattern: enact governance authority through an executive order or resolution, using Tulsa's COP 1400 and Kansas City's 2025 Governance Charter as direct policy references, with DAMA-DMBOK v2 as the internal implementation guide that ensures comprehensive domain coverage. The DMM maturity model gives CoW a scoring baseline today and a structured improvement path going forward.

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
| Peer city research confirms Kansas City or Tulsa uses a different standard CoW wants to benchmark against | **Peer research is complete (April 2, 2026).** Neither Kansas City nor Tulsa formally adopted a named standard — both built custom frameworks. This finding confirms the DAMA-as-implementation-guide approach and does not require a change to the recommendation |
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
