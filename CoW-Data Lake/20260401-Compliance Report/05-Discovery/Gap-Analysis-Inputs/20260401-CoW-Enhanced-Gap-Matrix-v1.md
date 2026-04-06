# Enhanced Compliance Gap Matrix
**Prepared by:** IMPACT Consulting — Barton School of Business, Wichita State University
**Prepared for:** City of Wichita (CoW) — Internal Working Document
**Date:** April 6, 2026
**Version:** v1
**Feeds into:** Deliverable 2 — Data Governance Review Report (Compliance Gap Matrix section)

> **How to use this document:** This is the primary input for Deliverable 2's Compliance Gap Matrix. Each domain has seven fields: current state, risk severity, evidence citation, regulatory obligation, peer benchmark status, recommended owner, and open interview questions. Risk severity ratings are preliminary — confirm or adjust based on Week 2–3 stakeholder interviews, particularly with the CISO, City Clerk, and Laserfiche System Admin.

---

## Section 1: Summary — Risk by Domain

| # | Domain | Risk Severity | One-Line Status |
|---|---|---|---|
| 1 | Data Classification Schema | 🔴 **Critical** | SecTag field exists in all 45 files; zero records classified |
| 2 | File Naming & Metadata Standards | 🟠 **High** | 609 data quality issues; 45 are blocking for automation |
| 3 | Records Coordinators / Data Stewards | 🟡 **Medium** | 30+ coordinators identified; no formal charter or authority |
| 4 | Stakeholder Roles (RACI Matrix) | 🟡 **Medium** | No RACI exists; accountability is entirely informal |
| 5 | Retention Schedules | 🟠 **High** | 33 periods defined; legal citation source not confirmed |
| 6 | Retention Enforcement | 🔴 **Critical** | Laserfiche not configured to enforce; automation status unconfirmed |
| 7 | Access Control Model | 🔴 **Critical** | No documented model; no user roles defined; audit exposure |
| 8 | Sensitive Data Access Workflow | 🔴 **Critical** | No CJIS or HIPAA-adjacent procedures; Police and Community Services records unprotected |
| 9 | Data Export & System Connections | 🟠 **High** | No export governance; data lake integration undefined |
| 10 | Governance Adoption & Change Management | 🟢 **Low** | No training program; maturity gap, not immediate compliance risk |

**Critical domains (4):** 1, 6, 7, 8 — must be addressed before Laserfiche automation can be safely configured or a data lake designed.
**High domains (3):** 2, 5, 9 — carry legal exposure or will block implementation if unresolved.
**Medium/Low domains (3):** 3, 4, 10 — important for long-term governance maturity; not blocking immediate compliance.

---

## Section 2: Enhanced 10-Domain Gap Matrix

Column guide:
- **Current State** — what exists today, drawn from the 45 Excel data management lists and client-provided documents
- **Risk Severity** — Critical / High / Medium / Low, with rationale
- **Evidence** — specific file and field citation from GOVERNANCE-REPORT_2026-04-01_v2.md and team briefing
- **Regulatory Obligation** — the statute, federal policy, or city policy that makes this gap a compliance matter
- **Peer Status** — status from Benchmarking Report v2 Section 4 (Tulsa / Kansas City / Austin)
- **Recommended Owner** — the CoW role responsible for remediation
- **Open Interview Questions** — what must be confirmed in Week 2–3 sessions

---

### Domain 1 — Data Classification Schema

**Current State:** The `SecTag` metadata field exists as a defined column in all 45 data management files. Zero rows have a value populated. No formal data classification policy exists. No classification levels (Public, Internal, Sensitive, Protected) are defined anywhere in the client-provided documentation.

**Risk Severity:** 🔴 **Critical**
All records are treated identically regardless of sensitivity. The Police Department (CJIS), Community Services (HIPAA-adjacent), and Legal (privilege) all share the same access treatment as public documents. Without classification, no security differentiation is possible — any user with access to Laserfiche can reach any record.

**Evidence:**
- `Data Management Lists/*.xlsx` — `SecTag` column present in all 45 files; zero rows populated across any file (GOVERNANCE-REPORT_2026-04-01_v2.md, Part 1, Section 1: "Security Tags found: 0")
- `COW Data Governance and Retention Policy - Laserfiche Alignment Notes.docx` — references classification intent but defines no classification levels (Team Briefing, "What Is Missing or Broken," row 1)

**Regulatory Obligation:**
- **CJIS Security Policy (FBI)** — requires designation and protection of Criminal Justice Information; classification is the prerequisite for access control segregation
- **HIPAA Privacy Rule (45 CFR §164.514)** — requires designation of Protected Health Information; classification is the prerequisite for PHI handling procedures
- **AR 8.4 (CoW Open Data Policy)** — requires distinguishing public-releasable data from internal/sensitive data before publication; classification is the prerequisite

**Peer Status (Benchmarking Report v2, Section 4):**
- Tulsa: **Explicit Policy** — COP 1400 (Feb 2026), 4-tier schema (Public / Internal / Sensitive / Protected)
- Kansas City: **Explicit Policy** — 2025 Charter, 4-tier schema (Public / Private / Sensitive / Confidential)
- Austin: **Partial** — contract-level Public / Non-Public only; no standalone policy

**Recommended Owner:** CISO / IT Security Lead (classification policy author); City Clerk (records classification authority); IT Department (SecTag field population in Laserfiche)

**Open Interview Questions (Week 2 — CISO session):**
1. Has CoW ever operated under a classification policy, even informally? Any previous draft?
2. Is the Police Department currently managing CJIS records in Laserfiche, or in a separate system?
3. Who currently has authority to designate a record as sensitive or protected?
4. Has AR 8.4 ever been used to exclude records from open data publication — and on what basis?

---

### Domain 2 — File Naming & Metadata Standards

**Current State:** 32 metadata fields defined across the 45 data management files. 432 document type abbreviations catalogued. File naming follows the `DEPT-D-###-Description.xlsx` convention — all 45 files conform. However, 609 data quality issues exist in the metadata values (see Section 4 for severity breakdown). No validation rules are enforced at data entry; no mandatory vs. optional field designation exists.

**Risk Severity:** 🟠 **High**
45 of the 609 issues are blocking — they will cause Laserfiche automation to fail or route records incorrectly. The remaining 558 are cosmetic but will compound without validation enforcement. The Austin precedent (2023 data reliability incident — multiple departments publishing conflicting information) is a direct analogue: CoW's 609 issues are the same category of problem, and unresolved they will produce incorrect automated outputs.

**Evidence:**
- `Data Management Lists/*.xlsx` — 32 column headers identified; 6 files contain `RMCuttoff` misspelling instead of `RMCutoff`; 44 files contain department codes not in `GE-D-001-Department Abbreviations CODES.xlsx`; 298 disposition and 260 retention case inconsistencies; 1 retention/filename data entry error in `PW-D-002-Public Works Environmental Health.xlsx` row 22 (GOVERNANCE-REPORT_2026-04-01_v2.md, Part 2, all subsections)

**Regulatory Obligation:**
- **K.S.A. 45-403** (government records as public property) — records must be identifiable and retrievable to be considered managed; poor metadata makes records un-producible under KORA (Kansas Open Records Act)
- No Kansas statute mandates a specific metadata schema, but discoverability is implied by public records law

**Peer Status (Benchmarking Report v2, Section 4):**
- Tulsa: **Principles Stated** — Data Provenance Policy requires metadata documented before CDR ingestion; no enumerated field schema published
- Kansas City: **Principles Stated** — Data Service Standard Principle 5 requires "clear, descriptive metadata"; open standards mandate
- Austin: **Partial** — BLDS standard for permits only; no citywide schema

*Note: CoW's 32-field model is more specific than any peer's published metadata schema. The gap is not field definition — it is validation enforcement and data quality.*

**Recommended Owner:** City Clerk / Records Manager (metadata policy authority); IT Department (validation configuration in Laserfiche); Records Coordinators (data entry quality)

**Open Interview Questions (Week 2 — City Clerk session):**
1. Are the 44 unrecognized department codes a known issue? Is GE-D-001 the authoritative code list?
2. Is there a formal naming convention document beyond what exists in the Excel files?
3. Which metadata fields are considered mandatory before a record enters Laserfiche?
4. What happens today when a record is entered with incorrect or missing metadata — is there any review?

---

### Domain 3 — Records Coordinators / Data Stewards

**Current State:** 30+ records coordinators identified across 22 departments. Names found in Notes sections of multiple Excel files (Lindsay Benacka, Jesse Koza, Jana Erwin, Rhonda Harper, and others). No formal coordinator charter exists. No complete roster with all coordinator names, department assignments, and contact information has been provided. No defined responsibilities beyond informal coordination.

**Risk Severity:** 🟡 **Medium**
Operations continue informally. Coordinators exist and are engaged — the gap is authority and accountability, not presence. Risk escalates to High if retention enforcement or classification policy is implemented without a formal stewardship structure to operate it.

**Evidence:**
- `Data Management Lists/AP-D-001-Airport Documents.xlsx`, `AP-D-002-Airports.xlsx`, `CA-D-001-Cultural Arts Documents.xlsx` — coordinator names appear in Notes sections (GOVERNANCE-REPORT_2026-04-01_v2.md, Part 1, Section 3)
- Complete roster not provided; coordinator roles not defined in any client document (Team Briefing, "What Is Missing or Broken," not listed — absence of record)

**Regulatory Obligation:**
- **K.S.A. 12-120 / 12-121** — minimum retention requirements for city records imply designated records management responsibility
- City Clerk's statutory records management authority (Kansas City Clerk statute) implies a stewardship structure must exist beneath the Clerk's office

**Peer Status (Benchmarking Report v2, Section 4):**
- Tulsa: **Explicit Policy** — EO 2019-08 defines 4-role structure (Data Manager, DGC Members, Data Stewards, Data Users); 2-day review SLA; formal ethical code for Data Manager
- Kansas City: **Explicit Policy** — CDO by City Code 2-2133; named 6-member Governance Committee; Data Owners and Data Stewards defined
- Austin: **Partial** — Open Data Liaisons (one per dept) + Records Custodians under City Clerk; no formal charter

**Recommended Owner:** City Clerk / Records Manager (charter authority); CISO (security responsibilities within stewardship model)

**Open Interview Questions (Week 2 — City Clerk session; Week 3 — Records Coordinator sessions):**
1. Can the City Clerk's office provide a complete coordinator roster with department assignments and contact information?
2. What are coordinators currently responsible for — and what are they NOT responsible for?
3. Has any coordinator received formal training? Is there a training program?
4. Who do coordinators escalate to when they encounter a records issue they cannot resolve?

---

### Domain 4 — Stakeholder Roles (RACI Matrix)

**Current State:** No RACI matrix or governance charter exists. 22 departments identified from data management file prefixes. IT, Legal, City Clerk, and department head roles are known but accountability for specific governance decisions (who approves a retention exception? who authorizes cross-department data access?) is undocumented.

**Risk Severity:** 🟡 **Medium**
Governance decisions are currently made informally without documented accountability. Risk escalates to High once classification policy and retention enforcement are implemented — those systems require someone to be accountable for decisions; informal accountability will not survive an audit.

**Evidence:**
- All 4 client-provided documents: absent from all (Team Briefing, "What Is Missing or Broken," row 5: "No RACI matrix or governance charter — Absent from all 4 client-provided documents")
- 22 department codes confirmed across data management file prefixes (GOVERNANCE-REPORT_2026-04-01_v2.md, Part 1, Section 4)

**Regulatory Obligation:**
- No Kansas statute directly mandates a RACI matrix
- **CJIS Security Policy** requires a designated Agency Security Officer (ASO) — this is a specific named accountability that constitutes a partial RACI requirement
- Bloomberg WWC Gold certification (Kansas City path) required a formal cross-departmental governance committee — relevant if CoW pursues certification

**Peer Status (Benchmarking Report v2, Section 4):**
- Tulsa: **Principles Stated** — governance manual creates functional RACI (Data Steward: Responsible; Data Manager: Accountable; DGC Members: Consulted; Data Users: Informed); no document labeled RACI
- Kansas City: **Principles Stated** — roles defined in charter; no document labeled RACI
- Austin: **Not Found**
- *No peer city has published a document explicitly labeled "RACI." CoW creating one would be more explicit than any peer.*

**Recommended Owner:** City Manager's Office or PMO (governance charter authority); City Clerk (records management accountability); CISO (security role assignments)

**Open Interview Questions (Week 2 — IT Leadership, CISO sessions):**
1. Who currently makes the decision to grant cross-departmental access to records?
2. Who has authority to approve a retention exception or a legal hold?
3. Is there a designated Agency Security Officer (ASO) for CJIS purposes?
4. Who would sign off on CoW's data governance policy — City Manager, Mayor, or City Council?

---

### Domain 5 — Retention Schedules

**Current State:** 33 retention periods defined across the 45 data management files (ranging from 1 year to permanent). 8 cutoff trigger types defined (File Date, Expiration, Superseded, OBS/NLU, Completion, Employee Termination, and others). Legal citation source for the retention periods has not been confirmed — it is unknown whether these periods were derived from K.S.A. minimums, KSHS guidance, or internal CoW decisions.

**Risk Severity:** 🟠 **High**
33 periods are defined — this is a real asset. The risk is legal defensibility: if CoW cannot cite the statute or authority that justified each retention period, it cannot defend a destruction decision in litigation or an audit. One retention period contains a filename instead of a period value (PW-D-002, row 22 — data entry error).

**Evidence:**
- `Data Management Lists/*.xlsx` — `RMRetention` column across all 45 files; 33 distinct period values enumerated (GOVERNANCE-REPORT_2026-04-01_v2.md, Part 1, Section 5, full list)
- `RMCutoff` column: 8 distinct cutoff types (CO-01 through CO-07, plus CO-01 File Date and CO-02 Expiration variants)
- No legal citation column exists in any data management file; no supporting retention schedule document provided (Team Briefing, "What Is Missing or Broken": "Retention enforcement not automated" and "Source of retention schedules not confirmed")

**Regulatory Obligation:**
- **K.S.A. 45-403** — government records are public property; destruction is prohibited except as permitted under approved retention schedules
- **K.S.A. 12-120 / 12-121** — minimum retention periods for specific city record types
- **KSHS guidance** — Kansas Historical Society provides advisory retention schedules for Kansas municipalities; advisory (not mandatory) but the standard reference for CoW's City Attorney to confirm against

**Peer Status (Benchmarking Report v2, Section 4):**
- Tulsa: **Explicit Policy** — Oklahoma Title 67 Records Management Act; Oklahoma Dept. of Libraries provides schedules
- Kansas City: **Explicit Policy** — Missouri General Records Retention Schedule (state-mandated)
- Austin: **Explicit Policy** — Texas State Library Local Government Retention Schedules; City Clerk oversight
- *All three peer cities use their state's official records retention schedule as the legal basis. CoW should confirm whether its 33 periods are sourced from KSHS guidance and K.S.A. minimums.*

**Recommended Owner:** City Clerk / Records Manager (retention schedule authority); City Attorney (legal citation confirmation and hold procedures)

**Open Interview Questions (Week 2 — City Clerk session; Legal Dept. session):**
1. What is the source of the 33 retention periods — were they developed internally, derived from KSHS guidance, or from K.S.A. minimums?
2. Has the City Attorney reviewed and approved the retention schedule?
3. Is there a formal process for updating retention periods when Kansas law changes?
4. How are litigation holds currently managed — what is the process when the City Attorney flags a case?
5. How are records with multiple retention requirements handled (e.g., a record that falls under both a 5-year and a 10-year schedule)?

---

### Domain 6 — Retention Enforcement

**Current State:** Cutoff triggers are defined in the data management files (8 trigger types). The `Laserfiche Alignment Notes` document describes a desired retention enforcement workflow but confirms it is not yet active. Automation status in Laserfiche has not been verified with IT. No disposition approval workflow is documented. No audit trail for disposed records has been confirmed.

**Risk Severity:** 🔴 **Critical**
Laserfiche is capable of automated retention enforcement natively — but is not configured to do so. Without enforcement, two failure modes exist simultaneously: records may be disposed too early (K.S.A. 45-403 violation; litigation risk) or held indefinitely beyond their schedule (storage cost; privacy risk; potential KORA over-disclosure if retained records are later requested). This is not a planning gap — it is an active operational risk.

**Evidence:**
- `COW Data Governance and Retention Policy - Laserfiche Alignment Notes.docx` — "Laserfiche Cloud capable of enforcement (not yet configured to do so)" (Team Briefing, "What They Have," row 5)
- `Data Management Lists/*.xlsx` — `RMCutoff` and `RMRetention` fields present; values populated across most records; Laserfiche RM module configuration status unknown

**Regulatory Obligation:**
- **K.S.A. 45-403** — destruction of government records is prohibited except under approved retention schedules; failure to enforce schedules creates both early-disposal violations and over-retention risk
- **K.S.A. 12-120 / 12-121** — minimum retention requirements for city records; unenforced schedules mean compliance with these minimums cannot be verified

**Peer Status (Benchmarking Report v2, Section 4):**
- Tulsa: **Principles Stated** — Oklahoma mandate exists; automated enforcement not documented publicly
- Kansas City: **Principles Stated** — Missouri state schedules mandated; no published enforcement automation documentation
- Austin: **Partial** — Records Custodians enforce manually; no evidence of automation
- *No peer city has published Laserfiche-specific retention automation documentation. Rochester, NY (non-peer) implemented Laserfiche workflow automation and achieved ~50% reduction in records processing time — the closest published technical reference.*

**Recommended Owner:** City Clerk / Records Manager (schedule authority and disposition approval); Laserfiche System Admin (platform configuration); IT Department (RM module enablement)

**Open Interview Questions (Week 2 — Laserfiche System Admin session; City Clerk session):**
1. Is the Laserfiche Records Management module enabled in CoW's current deployment?
2. Are the `RMRetention` and `RMCutoff` fields from the Excel files mapped to Laserfiche metadata fields?
3. Who currently approves record disposition — is there any approval workflow, even manual?
4. Has any record ever been formally disposed of through Laserfiche? If so, is there an audit log?
5. What happens when a record reaches its retention trigger today — does anything alert anyone?

---

### Domain 7 — Access Control Model

**Current State:** No documented access control model exists. No user role definitions (Admin, Power User, Read-Only, etc.) have been provided. Departmental folder structure exists in Laserfiche, implying some access boundary, but the boundary is not defined in any policy document. No cross-department access procedures exist. No privileged access management for sensitive records.

**Risk Severity:** 🔴 **Critical**
This is the most audit-visible gap. Any external audit (CJIS, internal audit, or future accreditation) will require CoW to demonstrate who can access what records and why. Without a documented model, CoW cannot answer that question. Additionally, without access controls, the SecTag classification field (Domain 1) cannot function — classification without access enforcement is cosmetic.

**Evidence:**
- All 4 client-provided documents: absent from all (Team Briefing, "What Is Missing or Broken," row 4: "No access control model or user role definitions — Absent from all 4 client-provided documents; not referenced in AR 8.4 or Laserfiche Alignment Notes")
- `Data Management Lists/*.xlsx` — partial user access requirements noted in Notes sections for Airport and Cultural Arts (GOVERNANCE-REPORT_2026-04-01_v2.md, Part 1, Section 3 — user lists in Notes, not in a formal model)

**Regulatory Obligation:**
- **CJIS Security Policy Section 5** — access control requirements for criminal justice information; requires documented user accounts, role-based access, and minimum necessary access principle
- **HIPAA Security Rule 45 CFR §164.312(a)(1)** — technical safeguards require unique user identification, emergency access procedures, and automatic logoff
- **K.S.A. 45-221** (KORA exemptions) — CoW must be able to segregate exempt records from public-releasable records; access control is the mechanism

**Peer Status (Benchmarking Report v2, Section 4):**
- Tulsa: **Explicit Policy** — COP 1200 + EO 2019-08; 3-tier Active Directory hierarchy (Classification / Department / Application folders); request → Steward → IT → AD group; annual audit by IT Security
- Kansas City: **Principles Stated** — 2025 Charter mandates access controls and user role definition; technical model not published
- Austin: **Partial** — encryption requirements in contracts; internal model not published

**Recommended Owner:** CISO / IT Security Lead (access control policy and enforcement); Laserfiche System Admin (security group configuration); IT Department (Active Directory or equivalent group management)

**Open Interview Questions (Week 2 — CISO session; Laserfiche System Admin session):**
1. How are Laserfiche user accounts currently provisioned — is there a process for adding or removing users?
2. Are there any security groups or folder-level permissions configured in Laserfiche today?
3. What happens when an employee leaves the organization — is their Laserfiche access revoked?
4. Does the Police Department have separate Laserfiche access controls for CJIS-relevant records, or do they use the same access model as other departments?
5. Is there any audit log of who accesses which records in Laserfiche?

---

### Domain 8 — Sensitive Data Access Workflow

**Current State:** No documented workflow exists for requesting, approving, or auditing access to sensitive records. No definition of "sensitive data" in CoW's context. No procedures for CJIS (Police Department criminal justice information) or HIPAA-adjacent (Community Services, Housing) records. No temporary vs. permanent access distinction. No access recertification schedule.

**Risk Severity:** 🔴 **Critical**
This is CoW's highest regulatory exposure. CJIS and HIPAA are federal-level requirements with specific procedural mandates. The absence of any workflow means Police Dept. records (CJIS-covered) and Community Services records (potentially PHI-adjacent) are being stored and accessed without any differentiation from general public documents.

**Evidence:**
- "No explicit workflow documentation found" (GOVERNANCE-REPORT_2026-04-01_v2.md, Part 1, Section 8)
- Team Briefing, "What Is Missing or Broken," row 6: "No sensitive data handling procedures — Absent from all 4 client-provided documents; AR 8.4 covers public data only; no sensitivity handling procedures present. Exposure on CJIS (Police), HIPAA-adjacent (Community Services)"

**Regulatory Obligation — CJIS (Police Department):**
- **FBI CJIS Security Policy v5.9** requires all of the following, none of which CoW has documented:
  - Designated Agency Security Officer (ASO) responsible for CJIS compliance
  - Personnel security screening before access to Criminal Justice Information (CJI)
  - User authentication with minimum complexity requirements
  - Physical security controls for systems that process CJI
  - Audit logging of all CJI access events
  - Incident response procedures for unauthorized CJI access
- **Risk:** FBI CJIS compliance audits are conducted by the Kansas Bureau of Investigation (KBI). Non-compliance can result in suspended access to NCIC and state criminal justice databases — a critical operational impact for the Police Department.

**Regulatory Obligation — HIPAA-Adjacent (Community Services, Housing):**
- Community Services and Housing may hold records containing individually identifiable health information (IIHI) related to housing assistance, social service benefits, or case management programs
- Whether these records are covered PHI under HIPAA depends on whether CoW qualifies as a covered entity or business associate for any specific federal program (e.g., HUD CDBG, HOME, or ESG programs that involve health screening)
- **CoW currently has:** No documented process for identifying whether a record contains health information; no de-identification procedure; no handling distinction between general community services records and health-related records
- **Risk:** If CoW receives federal health program funding with HIPAA business associate obligations, current handling may constitute a HIPAA violation. At minimum, the absence of a workflow means CoW cannot demonstrate compliance if audited.

**Peer Status (Benchmarking Report v2, Section 4):**
- Tulsa: **Explicit Policy** — COP 1400; Sensitive tier: Director/Designee approval required; Protected tier (CJI/PHI): Legal Dept. + DGSC Chair approval; "used only when no alternative exists" as default restriction
- Kansas City: **Partial** — HIPAA/law enforcement records acknowledged as Confidential tier; no published access workflow
- Austin: **Not Found**
- *Tulsa's COP 1400 is the only published city-level sensitive data workflow across all four peer cities. It is the direct reference template for CoW's policy development.*

**Recommended Owner:** CISO / IT Security Lead (CJIS ASO designation and security procedures); City Attorney (HIPAA business associate analysis and privileged records); IT Department (audit logging configuration in Laserfiche)

**Open Interview Questions (Week 2 — CISO session; Legal Dept. session):**
1. Is there a designated Agency Security Officer (ASO) for CJIS purposes? If so, who?
2. Are Police Department records currently stored in Laserfiche, or in a separate CJIS-compliant system?
3. Has the City Attorney conducted a HIPAA business associate analysis for Community Services or Housing programs?
4. Is there any current process — even informal — for flagging a record as sensitive before it is stored?
5. Has CoW ever received a CJIS audit? If so, what findings were issued?

---

### Domain 9 — Data Export & System Connections

**Current State:** No export governance policy exists. No documented API or integration connections between Laserfiche and other city systems. No data export approval workflow. No metadata preservation requirements for exports. The planned data lake environment (subject of Deliverable 3) has no defined integration with Laserfiche or data governance requirements. AR 8.4 (Open Data Policy) requires public data publication but defines no technical export standards or audit trail.

**Risk Severity:** 🟠 **High**
This domain becomes Critical the moment the data lake project begins. Every design decision for ingestion, storage, and access in the data lake depends on export governance from Laserfiche. Without a defined export policy, the data lake will import records without classification, retention context, or provenance — importing the governance gaps, not solving them.

**Evidence:**
- "No export or integration documentation found" (GOVERNANCE-REPORT_2026-04-01_v2.md, Part 1, Section 9)
- `AR 8.4 IT Open Data Policy.pdf` — covers public data publication; does not define export governance for internal or sensitive data
- `COW Data Governance and Retention Policy - Laserfiche Alignment Notes.docx` — integration framework described conceptually; no technical integration specifications documented

**Regulatory Obligation:**
- **AR 8.4 (CoW Open Data Policy)** — public data publication obligations; requires a mechanism to distinguish publishable from non-publishable data at export
- **CJIS Security Policy** — explicitly prohibits unauthorized export of Criminal Justice Information; any data lake integration touching Police Dept. records requires CJIS authorization
- **K.S.A. 45-403 / KORA** — exported records remain public property and subject to public records law; export does not remove records management obligations

**Peer Status (Benchmarking Report v2, Section 4):**
- Tulsa: **Explicit Policy** — Pre-purchase data sovereignty questionnaire (4 questions: analytics need, integration, city ownership, raw data download); automated ETL provenance logging from source to CDR
- Kansas City: **Principles Stated** — Data Service Standard open standards mandate; Open Data KC portal as sharing hub
- Austin: **Not Found**

**Recommended Owner:** IT Department / CIO (integration architecture and data sovereignty); Laserfiche System Admin (export configuration); CISO (CJIS export authorization); City Clerk (records management obligations for exported records)

**Open Interview Questions (Week 2 — IT Leadership session; Laserfiche System Admin session):**
1. Can Laserfiche currently export records with their metadata intact — does a bulk export preserve RMRetention, RMCutoff, and SecTag values?
2. Are there any existing API connections between Laserfiche and other CoW systems (finance, HR, permitting)?
3. Who currently has authority to authorize a data export from Laserfiche?
4. For the planned data lake: does CoW own all data generated by vendors in that environment, and can CoW download raw data at any time?
5. What is the process for publishing records to the Open Data portal under AR 8.4 — how is the public/non-public distinction made today?

---

### Domain 10 — Governance Adoption & Change Management

**Current State:** No formal training program exists for records coordinators, department staff, or Laserfiche users. No adoption metrics have been defined. No change management plan has been documented. The 22-department scope and 30+ coordinators represent a significant change management challenge for any governance program rollout.

**Risk Severity:** 🟢 **Low**
This is a maturity gap, not an immediate compliance risk. The absence of a training program does not create legal exposure today. However, it is the single most important enabler for all other domains — classification policy, retention enforcement, and access control all require staff to understand and follow them. Without adoption infrastructure, governance policies will exist on paper only.

**Evidence:**
- All 4 client-provided documents: absent from all (inference from absence; no training materials provided at kickoff or November meeting)
- Team Briefing, "What We Need From CoW" section: "Existing records management training materials — Training Department (Medium priority, due April 11)"
- GOVERNANCE-REPORT_2026-04-01_v2.md, Part 1, Section 10: lists change management strategy, training programs, compliance monitoring, user feedback mechanisms, and success metrics as all needed

**Regulatory Obligation:**
- No Kansas statute mandates a training program
- **Bloomberg WWC Certification** — "Data Workforce Culture and Trainings" is a WWC practice area criterion; training program is required for Silver certification
- **CJIS Security Policy** — requires security awareness training for anyone with access to CJI; this is a mandatory training requirement for the Police Department component of Domain 10

**Peer Status (Benchmarking Report v2, Section 4):**
- Tulsa: **Explicit Policy** — Urban Data Pioneers program (7+ cohorts; 70% reduction in 911 calls from repeat utilizers documented); mandatory training for classification authority delegation; Data Quality self-service workflow
- Kansas City: **Principles Stated** — CDO mandated to develop training; Bloomberg Gold external accountability
- Austin: **Not Found**

**Recommended Owner:** City Clerk / Records Manager (records-specific training); CISO (CJIS security awareness training); IT Department (Laserfiche user training); PMO or City Manager's Office (enterprise change management)

**Open Interview Questions (Week 3 — Records Coordinator sessions; Dept. Head sessions):**
1. Have records coordinators received any training on Laserfiche or records management since the system was deployed?
2. Are department heads aware of the governance gaps identified in this review — or is this news to them?
3. Has CoW used a change management approach for any prior system rollout (e.g., Laserfiche initial deployment)?
4. What communications channels reach all 22 department coordinators simultaneously?

---

## Section 3: Data Quality Issue Severity Breakdown

The 609 issues from `GOVERNANCE-REPORT_2026-04-01_v2.md` are not equal in operational impact. Three tiers:

### Tier 1 — Blocking Issues (45 total)
*Will cause Laserfiche automation to fail or route records incorrectly. Must be resolved before any automation is configured.*

| Issue Type | Count | Affected Files | Operational Consequence |
|---|---|---|---|
| Unrecognized department codes | 44 | All files with dept codes AP, CA, CC, CK, CS, ED, FD, FN, HC, HR, IT, LB, LW, MC, MP, PD, PM, PR, PW, TR | Laserfiche folder routing and security group assignment use dept codes; records will land in wrong containers or fail to route |
| Retention field contains filename (data entry error) | 1 | `PW-D-002-Public Works Environmental Health.xlsx`, Sheet `PW-D-002-Public Works Environme`, row 22 | Retention period for this record is `PW-D-002-Public Works Environmental Health` (a filename string); automation will fail to parse a retention period; record will not be subject to retention enforcement |

**Action required before automation:** The 44 unrecognized department codes need to be reconciled — either the master code list (`GE-D-001`) is out of date and needs to be updated to include the actual in-use codes (AP, CA, CC, etc.), or the files need to be corrected to match the master. This is a decision for the City Clerk and IT, not IMPACT. The PW-D-002 data entry error needs correction by the Public Works records coordinator.

### Tier 2 — Structural Issues (6 total)
*Will cause field mapping failures when any system reads column names. Must be corrected before Laserfiche import or any data pipeline is built.*

| Issue Type | Count | Affected Files | Operational Consequence |
|---|---|---|---|
| Misspelled column header (`RMCuttoff` instead of `RMCutoff`) | 6 | `CA-D-001`, `CC-D-001-City Council Documents`, `FD-D-001`, `HC-D-001`, `HR-D-001`, `LW-D-001` | Any system that reads column names to map retention cutoff data (Laserfiche import, data lake ETL) will fail to find the field; affected records will have no retention cutoff trigger |

**Action required before import:** The 6 files need their column header corrected from `RMCuttoff` to `RMCutoff`. This is a simple find-and-replace in each Excel file; it can be done by the respective department coordinators.

### Tier 3 — Cosmetic / Normalization Issues (558 total)
*Functionally equivalent values; do not affect system operation but indicate absence of validation. Bulk-resolvable via a normalization script.*

| Issue Type | Count | Pattern | Operational Consequence |
|---|---|---|---|
| Disposition value case inconsistencies | 298 | `Permanent` / `permanent`, `Destroy` / `destroy` | Values are functionally equivalent; a case-insensitive comparison or normalization script resolves all 298 |
| Retention value case inconsistencies | 260 | `Permanent` / `permanent` | Same pattern as above; all 260 are resolvable by normalization |

**Note for Deliverable 2:** Remediating these 558 issues is out of scope for this engagement. However, the absence of validation enforcement that allowed 558 inconsistencies to accumulate is a governance gap — Domain 2 must include a recommendation to implement Laserfiche field validation rules that prevent future inconsistencies at data entry.

**Total verification:** 44 + 1 + 6 + 298 + 260 = **609 ✓**

---

## Section 4: Laserfiche Configuration Gap Sub-Analysis

The Laserfiche Alignment Notes confirm: *"Laserfiche Cloud capable of enforcement (not yet configured to do so)."* This is a distinct gap type from "policy missing" — the platform is deployed and capable, but its governance features are dormant. For each domain with a Laserfiche-specific configuration gap:

| Domain | Laserfiche Capability (Native) | Current Configuration Status | What Must Happen First | IT Interview Confirmation Needed |
|---|---|---|---|---|
| **1 — Classification** | `SecTag` metadata field exists on every record | Field present; zero values populated across all 45 files and all Laserfiche records | Classification policy (tiers + definitions) must be adopted and published | Confirm: Can SecTag values be bulk-populated for existing records? What is the mechanism? |
| **5–6 — Retention** | Records Management module: monitors record aging, tracks retention periods, generates disposition alerts, routes through approval workflow, holds records for legal review, produces audit logs | `RMRetention` and `RMCutoff` fields defined in Excel; Laserfiche RM module configuration status unknown | Retention schedule must be legally confirmed (K.S.A. citations); RM module must be enabled; field mapping from Excel to Laserfiche metadata must be verified | Confirm: Is the RM module enabled? Are `RMRetention` and `RMCutoff` mapped to Laserfiche metadata fields? Has any retention workflow ever been triggered? |
| **7 — Access Control** | Folder-level and document-level security groups; role-based permissions; user group management | Departmental folder structure exists; security group assignments unknown; no access model documented | Access control model (roles, permissions, group definitions) must be designed and approved | Confirm: Are any security groups currently defined in Laserfiche? How are new users provisioned? Is there a process for access removal? |
| **8 — Sensitive Data Workflow** | Laserfiche Forms — configurable approval routing workflows; can route access requests through a defined approval chain with audit logging | No approval workflow exists in Laserfiche | Sensitive data workflow policy must be defined (who approves, at what tier, with what documentation) | Confirm: Is Laserfiche Forms enabled in CoW's deployment? Has any approval workflow ever been built? |
| **2 — Validation** | Field validation rules; dropdown/controlled vocabulary enforcement at data entry | No validation rules are configured; all field values are free-text | Mandatory field list and allowed value sets must be defined | Confirm: Can Laserfiche enforce mandatory field completion at document check-in? Can it validate against a controlled vocabulary list? |

**Key insight for Deliverable 3 (System Requirements):** The data lake system requirements must account for this configuration gap. If Laserfiche's governance features are not activated before the data lake ingests records, the data lake will receive unclassified, unenforced, ungoverned records — and the governance gap moves upstream into the data lake rather than being resolved.

---

## Section 5: CJIS and HIPAA-Adjacent Risk Detail (Domain 8 Expansion)

### CJIS — Police Department

**What CJIS requires (FBI CJIS Security Policy v5.9, applicable sections):**

| Requirement | Policy Section | CoW Current Status |
|---|---|---|
| Designated Agency Security Officer (ASO) | Section 3 | Not documented — no ASO identified in any client document |
| Personnel security screening before CJI access | Section 5.12 | Not documented — no screening procedure in client documents |
| User authentication (minimum complexity + multi-factor for remote access) | Section 5.6 | Unknown — Laserfiche authentication configuration not reviewed |
| Physical security for CJI-processing systems | Section 5.9 | Unknown — no physical security assessment conducted |
| Audit logging of all CJI access | Section 5.4.2 | Not confirmed — Laserfiche audit log configuration unknown |
| Incident response for unauthorized CJI access | Section 5.3.5 | Not documented — no incident response procedure in client documents |
| Security awareness training | Section 5.2.1.1 | Not documented — no training program in any client document |

**Audit risk:** CJIS compliance is audited by the Kansas Bureau of Investigation (KBI). Non-compliance findings can result in:
- Suspended or revoked access to NCIC (National Crime Information Center)
- Suspended access to Kansas criminal justice information systems
- Mandatory remediation with re-audit within 30–90 days

**Interview priority:** Confirm whether Police Dept. records are in Laserfiche or a separate CJIS-compliant system. If they are in Laserfiche, CJIS Section 5 requirements apply to the entire Laserfiche deployment.

---

### HIPAA-Adjacent — Community Services and Housing

**What triggers HIPAA applicability:**
HIPAA applies when a CoW department is a "covered entity" (provides health care or health insurance) or a "business associate" (handles PHI on behalf of a covered entity). The following programs may create HIPAA obligations:
- HUD Community Development Block Grant (CDBG) programs involving health-related services
- HUD HOME Investment Partnerships with housing counseling that includes health screening
- HUD Emergency Solutions Grants (ESG) involving homeless services with health assessments
- Any program where CoW partners with a health care provider and handles patient-identifiable information

**CoW currently has:**
- No documented analysis of whether any Community Services or Housing program triggers HIPAA business associate status
- No documented procedure for identifying health-related information within records
- No de-identification procedure (relevant to AR 8.4 open data publication if any records contain IIHI)
- No handling distinction in Laserfiche between general community services records and records that may contain health information

**Risk calibration:** This is a "may apply" risk, not a confirmed violation. The City Attorney must assess each federal program individually to determine if HIPAA applies. The gap is that this assessment has not been done — and without it, CoW cannot know whether it is compliant or not.

**Interview priority (Legal Dept. session, Week 3):**
1. Has the City Attorney conducted a HIPAA business associate analysis for Community Services or Housing?
2. Does CoW receive any federal health program funding that involves individually identifiable health information?
3. Are there any records in Community Services or Housing that contain health screening data, treatment information, or medical history?

---

## Section 6: Open Questions Master List for Stakeholder Interviews

Compiled from all 10 domains. Organized by interview session.

### City Clerk / Records Manager (Week 2)
1. What is the source of the 33 retention periods in the data management files?
2. Has the City Attorney reviewed and approved the retention schedule?
3. Is there a process for updating retention periods when Kansas law changes?
4. How are litigation holds currently managed?
5. How are records with multiple retention requirements handled?
6. What are records coordinators currently responsible for — and what are they NOT responsible for?
7. Has any coordinator received formal training?
8. Who do coordinators escalate to when they encounter a governance issue they cannot resolve?
9. Are the 44 unrecognized department codes a known issue? Is GE-D-001 the authoritative code list?
10. Which metadata fields are considered mandatory before a record enters Laserfiche?

### CISO / IT Security Lead (Week 2)
1. Has CoW ever operated under a data classification policy, even informally?
2. Is there a designated Agency Security Officer (ASO) for CJIS purposes?
3. Are Police Department records in Laserfiche, or in a separate CJIS-compliant system?
4. Who currently has authority to designate a record as sensitive or protected?
5. Has AR 8.4 ever been used to exclude records from open data publication — and on what basis?
6. Who currently makes the decision to grant cross-departmental access to records?
7. How are Laserfiche user accounts currently provisioned?
8. Are there any security groups or folder-level permissions configured in Laserfiche today?
9. Does the Police Department have separate Laserfiche access controls for CJIS-relevant records?
10. Has CoW ever received a CJIS audit? What findings were issued?

### Laserfiche System Admin (Week 2)
1. Is the Laserfiche Records Management module enabled in CoW's current deployment?
2. Are the `RMRetention` and `RMCutoff` fields from the Excel files mapped to Laserfiche metadata fields?
3. Has any retention workflow ever been triggered?
4. Can SecTag values be bulk-populated for existing records?
5. Are any security groups currently defined in Laserfiche?
6. Is Laserfiche Forms enabled?
7. Can Laserfiche enforce mandatory field completion at document check-in?
8. Is there an audit log of who accesses which records?
9. Can Laserfiche export records with all metadata fields intact?
10. Are there any existing API connections between Laserfiche and other CoW systems?

### IT Leadership / CIO (Week 2)
1. Who currently has authority to authorize a data export from Laserfiche?
2. For the planned data lake: does CoW own all data generated by vendors in that environment?
3. Can CoW download all raw data from any vendor system at any time?
4. What is the process for publishing records to the Open Data portal under AR 8.4?
5. Who would sign off on CoW's governance policy — City Manager, Mayor, or City Council?

### Legal Department (Week 3)
1. Has the City Attorney conducted a HIPAA business associate analysis for Community Services or Housing programs?
2. Does CoW receive any federal health program funding that involves individually identifiable health information?
3. Are there any records in Community Services or Housing that contain health screening or medical information?
4. Who has authority to approve a retention exception or a legal hold?

### Records Coordinators (Week 3 — 3–5 sessions)
1. Have you received any training on Laserfiche or records management?
2. Do staff in your department save city records to local hard drives or USB drives?
3. Are there shared network folders outside Laserfiche used for active file storage?
4. Estimate the volume of records outside Laserfiche: under 100 / 100–1,000 / over 1,000 files?
5. Do you know who to contact if you have a question about whether a record is sensitive or public?
6. Have you ever been asked to flag a record as confidential or restricted?

### Department Heads (Week 3 — 2–3 sessions)
1. Are you aware of the governance gaps identified in this review?
2. Has your department received any guidance on data classification or records retention?
3. What would be the most disruptive change to your department's workflows if governance policies were enforced?

---

*IMPACT Consulting — Barton School of Business, Wichita State University*
*City of Wichita Data Governance & Data Lake Engagement — April 2026*
*Document: `05-Discovery/Gap-Analysis-Inputs/20260401-CoW-Enhanced-Gap-Matrix-v1.md`*
*Classification: Internal working document — feeds into Deliverable 2*
