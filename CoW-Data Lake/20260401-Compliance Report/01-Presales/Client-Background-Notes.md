# Client Background Notes
**Client:** City of Wichita (CoW)  
**Compiled:** 2026-04-01  
**Source:** October–November 2025 kickoff and gap analysis sessions  

---

## Who They Are

The City of Wichita is a municipal government serving approximately 400,000 residents in Sedgwick County, Kansas. City operations span **22 departments** managing a wide range of public services — from utilities and public safety to cultural programs and court administration.

Records management and governance responsibilities are distributed across **30+ departmental Records Coordinators** who report to the City Clerk's Office. The City Clerk serves as the central authority for official records retention policy and compliance oversight.

---

## Their Current Technology Stack

| System | Role | Status |
|---|---|---|
| **Laserfiche Cloud** | Primary document management and records retention platform | Active |
| **Excel Data Management Lists** | 45 files across 22 departments defining document classification, retention, and metadata | Active — quality issues present |
| **On-Premises Infrastructure** | Existing city data center (capacity and specs not yet assessed) | Under evaluation |
| **Power BI** | Reporting and analytics layer (referenced in dashboard planning docs) | Active |

CoW is evaluating a **modernized data lake environment** to replace or supplement the current fragmented Excel-based system. Technology options under consideration include MinIO (storage), Apache Spark (processing), Trino or ClickHouse (query), and Kubernetes (orchestration).

---

## Their 22 Departments

| Code | Department | Notes |
|---|---|---|
| AP | Airport | |
| CA | Cultural Arts | Has board and division subdivisions |
| CC | City Council | Includes Awards subdivision |
| CK | City Clerk | Records Management oversight authority |
| CS | Community Services | 6 districts |
| ED | Economic Development | |
| FD | Fire Department | |
| FN | Finance | 7 subdivisions (Controllers, Debt Management, Express, Pension, Purchasing, Risk Management, Treasury Express) |
| GE | General | Cross-departmental codes |
| HC | Housing & Community Services | |
| HR | Human Resources | |
| IT | Information Technology | Laserfiche system owner |
| LB | Library | |
| LW | Law Department | Legal holds and compliance oversight |
| MC | Municipal Court | |
| MP | MAPC / Management | |
| PD | Police Department | CJIS compliance implications |
| PM | Property Management | |
| PR | Parks & Recreation | |
| PW | Public Works | 11 divisions: Engineering, Environmental Health, Admin, Fleet, Stormwater, Facilities, Streets, Sewer Maintenance, Sewer Treatment, Water Production, Water Distribution |
| TR | Transportation | |

---

## Their Data Governance Situation

### What They Have

- **432+ document types** catalogued and named across all departments
- **32 metadata fields** defined in their data management lists, including classification (`DocClass`, `DocType`), retention (`RMCutoff`, `RMRetention`, `RMSeries`), and security (`SecTag`)
- **33 retention periods** covering standard durations (1–30 years, Permanent) and event-based triggers (project completion, employee termination, bond maturity)
- **8 cutoff trigger types** — CO-01 through CO-07 — defining when a retention clock starts
- A **Laserfiche Cloud** platform capable of enforcing retention and classification workflows if properly configured

### What Is Missing or Broken

| Gap Area | Detail |
|---|---|
| Data Classification Policy | No formal document defining sensitivity levels (Public, Internal, Confidential, Restricted) |
| Security Tags | `SecTag` field exists in all 45 files but is **empty across all records** |
| Retention Enforcement | Cutoff triggers are defined, but whether automation is active in Laserfiche is unconfirmed |
| Access Control | No documented access control model, user roles, or access request procedures |
| Sensitive Data Workflow | No documented process for flagging, accessing, or disposing of sensitive records |
| Data Export Policy | No governance around how records are exported or integrated with other systems |
| Metadata Validation | No validation rules enforced — free-text entry allows data quality issues to accumulate |
| Governance Charter / RACI | No formal document defining who owns governance decisions |

### Data Quality Issues Found (609 total across 45 files)

| Issue Type | Count |
|---|---|
| Unrecognized department codes | 44 |
| Misspelled column headers (`RMCuttoff` vs `RMCutoff`) | 6 |
| Disposition value case inconsistencies | 298 |
| Retention value case inconsistencies | 260 |
| Data entry errors (filename in retention field) | 1 |

---

## Key Stakeholders

| Role | Department | Priority |
|---|---|---|
| City Clerk / Records Manager | City Clerk's Office | Critical — policy authority |
| Laserfiche System Administrator | IT Department | Critical — platform owner |
| CISO / IT Security Lead | IT Department | Critical — classification and access policy |
| IT Department Leadership (CIO) | IT Department | High — infrastructure decisions |
| Legal Department Representative | Law Department | High — litigation holds, CJIS |
| Records Coordinators (30+) | All departments | High — operational stewards |
| City Auditor / Compliance Rep | Internal Audit | Medium — compliance oversight |
| Department Heads | Selected departments | Medium — user requirements |

### Named Coordinators (partial list identified)

- Lindsay Benacka
- Jesse Koza
- Jana Erwin
- Rhonda Harper (Division Coordinator)
- Logan Walker (Division Coordinator)
- Mandee Greer (Division Coordinator)

Full coordinator list not yet provided — requested as part of this engagement.

---

## Regulatory and Policy Context

| Reference | Relevance |
|---|---|
| **AR 8.4 — IT Open Data Policy** | Governs public data publication and access |
| **Kansas State Records Retention Schedule** | Likely legal basis for retention periods — not yet confirmed by City Clerk |
| **City Charter** | Authority for records management program |
| **CJIS (FBI)** | Applies to Police Department records |
| **HIPAA** | May apply to health-related records in Community Services and Housing |

---

## Prior Engagement History

| Date | Activity | Output |
|---|---|---|
| Oct 1, 2025 | Kickoff meeting | Discovery questions, industry practices doc, current state overview |
| Nov 4–5, 2025 | Gap analysis session | 10-domain gap analysis report, on-prem infrastructure overview |
| Apr 1, 2026 | Compliance report phase begins | This engagement |

All prior artifacts are stored in `../20251001-Kickoff/` and `../20251104-2nd Meeting/` in the parent `CoW-Data Lake/` directory.

---

## Key Decision Already Made

CoW has committed to a **Master Table governance model** where:

1. Each department owns and maintains a classification/retention table
2. Laserfiche forms auto-populate metadata fields (`Abbr`, `RMCutoff`, `RMRetention`, `RMSeries`, `ExpReq`, `SecTag`) from that table
3. Laserfiche workflows enforce retention schedules and classification rules
4. The CDO and City Clerk monitor compliance via Laserfiche audit reports
5. The City Auditor runs stewardship audits using metadata logs and workflow histories

This architecture is documented in `../IntegrationFramework.md`.
