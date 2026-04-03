# Team Briefing: CoW Engagement
**For:** IMPACT Consulting Team (Internal Only)  
**Date:** April 1, 2026  
**Do not share with client**

---

## 1. Client Snapshot

**City of Wichita (CoW)**: 22 departments, 30+ records coordinators, primary platform is **Laserfiche Cloud** backed by 45 Excel data management lists. The City Clerk holds records management authority. IT owns the platform.

### What They Have

| Finding | Source (`01-Presales/Provided by CoW/`) | Date Provided |
|---|---|---|
| 432+ document types catalogued across all departments | `Data Management Lists/*.xlsx` (45 client-provided Excel files) | Oct 1, 2025 (kickoff) |
| 33 retention periods and 8 cutoff triggers defined | `Data Management Lists/*.xlsx` (RMRetention and RMCutoff columns across all 45 files) | Oct 1, 2025 (kickoff) |
| 32 metadata fields specified (DocClass, DocType, RMCutoff, RMRetention, SecTag, etc.) | `Data Management Lists/*.xlsx` (column headers across all 45 files) | Oct 1, 2025 (kickoff) |
| 45 Excel data management lists across 22 departments | `Data Management Lists/` folder (45 files, dept codes AP through TR) | Oct 1, 2025 (kickoff) |
| Laserfiche Cloud capable of enforcement (**not yet configured to do so**) | `COW Data Governance and Retention Policy - Laserfiche Alignment Notes.docx` | Oct 1, 2025 (kickoff) |

### What Is Missing or Broken

| Gap | Source (`01-Presales/Provided by CoW/`) | Risk |
|---|---|---|
| No data classification policy | Absent from all 4 client-provided documents; `COW Data Governance and Retention Policy - Laserfiche Alignment Notes.docx` references classification intent but defines no levels | Records can't be consistently secured or shared |
| `SecTag` field empty in all 45 files | `Data Management Lists/*.xlsx` (SecTag column present in every file; zero rows populated across all 45 files) | Zero records have a security classification |
| Retention enforcement not automated | `COW Data Governance and Retention Policy - Laserfiche Alignment Notes.docx` (describes desired workflow but no evidence of active automation in Laserfiche) | Records may be destroyed early or held too long |
| No access control model or user role definitions | Absent from all 4 client-provided documents; not referenced in `AR 8.4 IT Open Data Policy.pdf` or Laserfiche Alignment Notes | Can't demonstrate who accesses what, or why |
| No RACI matrix or governance charter | Absent from all 4 client-provided documents; no governance structure document provided | Accountability for governance decisions is informal |
| No sensitive data handling procedures | Absent from all 4 client-provided documents; `AR 8.4` covers public data only; no sensitivity handling procedures present | Exposure on CJIS (Police), HIPAA-adjacent (Community Services) |

### Data Quality Issues (609 Total Across 45 Files)

| Issue | Count |
|---|---|
| Unrecognized department codes | 44 |
| Misspelled column headers (`RMCuttoff`) | 6 |
| Disposition value case inconsistencies | 298 |
| Retention value case inconsistencies | 260 |
| Data entry errors | 1 |

> **Note for team:** Remediating these 609 issues is **out of scope**. We document them in Appendix A of the governance report; we do not fix them.

### Key Stakeholders to Build Relationships With

| Who | Why They Matter |
|---|---|
| City Clerk / Records Manager | Policy authority; sign-off on retention findings in Deliverable 2 |
| Laserfiche System Admin | Platform owner; critical for Deliverable 3 system requirements |
| CISO / IT Security Lead | Must answer standards questions (Q16, Q17) to unlock Deliverable 1; owns classification and access policy |
| IT Leadership (CIO) | Infrastructure decisions; gate for Deliverable 3; confirm who has authority to sign off on standards selection during Week 5 review |
| Legal Department | Litigation holds, CJIS, compliance edge cases — informs standards selection |
| Records Coordinators (Lindsay Benacka, Jesse Koza, Jana Erwin, Rhonda Harper, others) | Day-to-day operations; best source of ground truth for gap evidence |

### Regulatory Context to Keep in Mind
- **AR 8.4**: City's Open Data Policy (public records publication)
- **Kansas State Records Law**: likely legal basis for retention periods (not yet confirmed by City Clerk; flag this in interviews)
- **CJIS**: applies to Police Department records
- **HIPAA-adjacent**: Community Services and Housing may hold health-related records

---

## 2. How We Got Here

CoW came to IMPACT in **October 2025** with two asks: audit their governance framework and define requirements for a new data environment. We completed the Oct 2025 kickoff session. This April engagement covers both the **gap analysis and deliverable phase**.

### What CoW Explicitly Asked For
1. *"Conduct a comprehensive review of the CoW's Data Governance framework to ensure alignment with industry standards."*
2. *"Analyze system requirements for a revamped data storage and analysis environment in collaboration with CoW's IT department."*

### What We Knew vs. Didn't Know at First Contact

| Known | Source (`01-Presales/Provided by CoW/`) | Unknown (still needs confirming) |
|---|---|---|
| 22 departments, Laserfiche Cloud in use | `Data Management Lists/*.xlsx` (22 distinct dept code prefixes AP→TR); Laserfiche confirmed in `COW Data Governance and Retention Policy - Laserfiche Alignment Notes.docx` | Whether any classification policy existed |
| 45 Excel data management lists | `Data Management Lists/` folder (45 files handed over at kickoff Oct 1, 2025) | Laserfiche active modules and workflow config |
| City Clerk holds records authority | `COW Data Governance and Retention Policy - Laserfiche Alignment Notes.docx` (records management governance section) | Whether retention is automated or manual |
| 30+ coordinators exist | `Data Management Lists/*.xlsx` (coordinator names appear across multiple Excel files: Lindsay Benacka, Jesse Koza, Jana Erwin, Rhonda Harper, others) | Complete coordinator roster with contacts |
| Open Data Policy (AR 8.4) in place | `AR 8.4 IT Open Data Policy.pdf` (provided at kickoff Oct 1, 2025) | CoW's preferred tech direction for the new environment |

### What the November 2025 2nd Meeting Surfaced
- `SecTag` field exists everywhere but is **completely empty**; nobody flagged this before
- Governance documentation is **almost entirely absent** as formal written policy
- The integration framework (Master Table model) is conceptually agreed but **not yet built**
- Public Works (11 divisions) and Finance (7 subdivisions) are significantly more complex than anticipated

---

## 3. Our Scope & Deliverables

### What We Are Doing
- **Standards selection** (Deliverable 1): evaluate DAMA-DMBOK v2, NIST SP 800-188, ISO 8000 against CoW's context; produce a recommendation brief; get client sign-off before drafting begins
- **Governance review** across 10 domains (Deliverable 2): classification, metadata, records coordinators, RACI, retention schedules, retention enforcement, access control, sensitive data workflows, data export, and adoption
- **System requirements gathering** with IT (Deliverable 3): functional requirements (7 domains), non-functional requirements, integration specs, acceptance criteria

### What We Are NOT Doing
Implementing anything. Rewriting policy. Training staff. Recommending vendors. Fixing the 609 data quality issues.

### Three Deliverables — Delivered in Sequence

**Deliverable 1: Standards Selection Brief** — draft shared May 5; final due May 16
Short advisory document evaluating DAMA-DMBOK v2, NIST SP 800-188, and ISO 8000 against CoW's regulatory context, maturity, and future roadmap. Includes a recommendation with rationale and a formal sign-off block. CoW reviews and accepts in writing during Week 5.

> **Internal note:** CoW has not told us which standard to use. We cannot assume one. We must finalize our framework recommendation internally before Week 4 drafting begins. Deliverables 2 and 3 are drafted against that internal recommendation. If CoW overrides our recommendation during Week 5 review, all three deliverables will require revision.

**Deliverable 2: Data Governance Review Report** — draft June 2; final June 16; depends on Deliverable 1
Gap matrix benchmarked against the confirmed standard. Includes current state, 10-domain analysis with evidence and risk levels, benchmarking, ranked recommendations, risk register, and appendices (609 data quality issues + RACI matrix).

**Deliverable 3: System Requirements Document** — draft July 2; final July 16; depends on Deliverable 2
Functional and non-functional requirements for the new data environment. Covers ingestion, storage, access, retention, search, reporting, and audit. Compliance requirements aligned to the confirmed standard. Includes Laserfiche integration specs, architecture diagram, acceptance criteria, and open issues log.

> One critical path dependency: documents by Apr 11. If CoW's Week 5 review results in a standard change, revisions to all three deliverables will be required. Flag immediately; do not absorb the delay silently.

---

*IMPACT Consulting | Internal Use Only | Do not distribute*
