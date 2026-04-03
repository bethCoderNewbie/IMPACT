# Initial Inquiry Summary
**Client:** City of Wichita (CoW)  
**First Contact:** October 1, 2025  
**Engagement Confirmed:** October 2025  
**Compiled:** 2026-04-01  

---

## How This Engagement Began

The City of Wichita approached the IMPACT Consulting program at Wichita State University's Barton School of Business seeking outside expertise on two interconnected problems:

1. **Their data governance framework was undocumented and inconsistently applied** — CoW had 45 Excel-based data management lists defining document classification and retention rules, but no formal policy documents, no enforcement automation, and significant data quality issues in the lists themselves.

2. **They wanted to modernize how they store and analyze city data** — CoW recognized that the current environment (Laserfiche + fragmented Excel files) was not positioned to support the city's growing analytics needs, and they needed a clear requirements picture before evaluating any new system or vendor.

---

## What CoW Asked For

CoW's initial ask organized into two workstreams:

### Workstream 1 — Data Governance Review
> *"Conduct a comprehensive review of the CoW's Data Governance framework to ensure alignment with industry standards."*

Specifically, they wanted to understand:
- Whether their current governance practices meet recognized standards (DAMA-DMBOK, NIST, ISO 8000)
- Where the gaps are across their 10 identified governance domains
- What they need to do, in what order, and who should own each action

### Workstream 2 — System Requirements for a New Data Environment
> *"Analyze system requirements for a revamped data storage and analysis environment in collaboration with CoW's IT department."*

Specifically, they needed:
- A structured requirements document usable by their IT team and potential vendors
- Functional and non-functional requirements covering ingestion, storage, access, retention, and reporting
- Integration requirements connecting the new environment to Laserfiche and existing city systems

---

## What Was Known at First Contact

| Known | Unknown |
|---|---|
| 22 departments with records management responsibilities | Whether any formal data classification policy existed |
| 45 Excel data management lists in use | Laserfiche configuration details (active modules, workflows, security setup) |
| Laserfiche Cloud is the primary document platform | Whether retention enforcement was automated or manual |
| City Clerk's Office holds records management authority | Complete list of Records Coordinators and their contact information |
| 30+ departmental Records Coordinators exist | Current data volumes and growth rate in Laserfiche |
| Open Data Policy (AR 8.4) is in place | Preferred technology direction for the new data environment |
| CoW operates across a wide regulatory landscape (CJIS, HIPAA possible) | Budget or infrastructure constraints for new system |

---

## What Was Agreed at Kickoff (October 1, 2025)

1. IMPACT would conduct a two-phased review — governance framework first, system requirements second
2. CoW would provide access to their 45 data management lists for analysis
3. CoW would make key stakeholders available for interviews (City Clerk, IT, CISO, Records Coordinators, Legal)
4. Deliverables would be two formal documents: a Data Governance Review Report and a System Requirements Document
5. The engagement would build on prior work from CoW's internal Laserfiche project rather than starting from scratch

---

## What the October–November 2025 Sessions Revealed

The kickoff and gap analysis sessions confirmed the initial inquiry and surfaced additional complexity:

- **The data quality problem was larger than expected** — analysis of the 45 Excel files found 609 data quality issues including misspelled field names, case inconsistencies, and unrecognized department codes
- **Security tagging was entirely absent** — the `SecTag` metadata field exists in every file but had never been populated, meaning no records had any security classification
- **Governance documentation was almost entirely missing** — no access control policy, no data classification policy, no RACI matrix, no retention enforcement procedures existed as formal documents
- **The integration framework had been conceptually designed but not implemented** — CoW had a clear vision of how their Laserfiche Master Table model should work, but implementation had not begun
- **Public Works and Finance were notably complex** — Public Works alone had 11 divisions and Finance had 7, creating significant scope for metadata standardization work

---

## Why This Engagement Matters to CoW

- **Compliance risk:** Without documented governance, CoW cannot demonstrate compliance in an audit
- **Operational risk:** Manual, inconsistent retention practices create exposure to records being destroyed too early or held too long
- **Strategic risk:** Without clear system requirements, any new data environment investment could fail to meet actual needs
- **Efficiency opportunity:** Automating retention enforcement and metadata validation in Laserfiche would reduce manual effort across 30+ coordinators

---

## Engagement Entry Point

This engagement formally enters its deliverable phase on **April 1, 2026**, building on the discovery work completed in October–November 2025. The full engagement timeline runs from April 7 through May 16, 2026.

Prior phase artifacts:
- `../20251001-Kickoff/` — October 2025 discovery documents
- `../20251104-2nd Meeting/` — November 2025 gap analysis and infrastructure overview
- `../Gap Analysis Report/GOVERNANCE-REPORT_2026-04-01_v2.md` — synthesized 10-domain gap analysis
