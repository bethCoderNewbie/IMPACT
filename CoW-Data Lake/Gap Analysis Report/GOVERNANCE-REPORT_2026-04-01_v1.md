# Laserfiche Governance Analysis Report
**Generated:** 2026-04-01 13:28:28  
**Source:** Data Management Lists (45 Excel files)  
**Script:** governance_analysis.py

---
## Part 1 — Governance Analysis: Information Available vs Needed

### 1. Data Classification Schema

**Available in files:**
- Security Tags found: **0**
  - No explicit security tags found in the data

**Needed (gaps):**
- ❌ Data classification levels (Public, Internal, Confidential, Restricted)
- ❌ Specific definitions for each classification level
- ❌ Handling rules for each classification level
- ❌ Who can access each classification level
- ❌ Storage requirements per classification

### 2. File Naming & Metadata Standards

**Available in files:**
- Metadata fields identified: **32**
  - `Abbr`
  - `Airport Name`
  - `Awards`
  - `Classification`
  - `Code`
  - `Cultural Arts Board`
  - `Cultural Arts Division`
  - `Cutoff`
  - `Description`
  - `Disposition`
  - `District`
  - `Division`
  - `Division Coordinator - Rhonda Harper`
  - `Division Coordinator -Logan Walker`
  - `Division Coordinator -Mandee Greer`
  - `DocClass`
  - `DocType`
  - `Drop downs for: Advanced Plans; Current Plans; Historic Preservation`
  - `Long Desc`
  - `Name`
  - `Need:`
  - `RMCutoff`
  - `RMCuttoff`
  - `RMRetention`
  - `RMSeries`
  - `Retention`
  - `SecTag`
  - `Short Desc`
  - `Template`
  - `Type`
  - `abv`
  - `subfolders`
- Document abbreviations: **432**
  - `139-FUELINSP` = Part 139 Fuel Truck Inspections
  - `ACT-RP` = Activity Reporting
  - `AMI` = Asset Management Inventory
  - `AVSEC` = AVSEC Notification
  - `BR-INV` = Bridge Inventory
  - `CASE-REQ` = Documentation for Case Request
  - `CAT-EX` = Categorical Exclusions
  - `DAY-BLTN` = Daily Bulletin
  - `KEY-CTRL` = Key Control
  - `SNOW` = Snow Removal Logs
  - *… and 422 more*

**Needed (gaps):**
- ❌ Complete file naming convention schema with examples
- ❌ Naming logic/rules (e.g., [Dept]-[Type]-[Date]-[Description].ext)
- ❌ Which metadata fields are MANDATORY vs OPTIONAL
- ❌ Validation rules for metadata (formats, allowed values)
- ❌ Default values for metadata fields
- ❌ Metadata inheritance rules (folder-level vs document-level)

### 3. Records Coordinators / Data Stewards

**Available in files:**
- Partial user access requirements found in Notes sections:
  - `[AP-D-001-Airport Documents.xlsx]` List of users - LF license
  - `[AP-D-002-Airports.xlsx]` List of users - LF license
  - `[CA-D-001-Cultrual Arts Documents.xlsx]` Names of all who will need access to Laserfiche: Lindsay Benacka, Jesse Koza, Jana Erwin, Alisha Gri

**Needed (gaps):**
- ❌ Complete list of 30 records coordinators with names and contact info
- ❌ Department assignment for each coordinator
- ❌ Specific responsibilities for each coordinator
- ❌ Training requirements for coordinators
- ❌ Escalation procedures when coordinator is unavailable
- ❌ Performance metrics/KPIs for coordinators

### 4. Stakeholder Roles (RACI Matrix)

**Available in files:**
- Departments identified: Airport, COMMUNITY SERVICES, COURT, City Clerk, Council, Cultural Arts, ECO DEVO, FIRE, Finance, General
  - *… and 12 more*

**Needed (gaps):**
- ❌ Complete RACI matrix (Responsible, Accountable, Consulted, Informed)
- ❌ IT Department roles and responsibilities
- ❌ Legal Department roles and responsibilities
- ❌ Department Head responsibilities
- ❌ City Clerk's role in records management
- ❌ Audit and compliance oversight roles
- ❌ Escalation paths for governance issues

### 5. Retention Schedules

**Available in files:**
- Cutoff types: **8**
  - `CO-01`
  - `CO-01 File Date`
  - `CO-02`
  - `CO-02 Expiration`
  - `CO-03 Superseded`: When a document gets superseded.
  - `CO-04 OBS/NLU`
  - `CO-05 Completion`: Cutoff Begins on Project completion
  - `CO-07 Employee Term`
- Retention periods: **33**
  - `01 year`
  - `02 years`
  - `03 years`
  - `04 years`
  - `05 Years`
  - `05 years`
  - `06 years`
  - `07 years`
  - `08 Years`
  - `08 years`
  - `1 year`
  - `10 years`
  - `10 years unless an issue is in litigation`
  - `15 years`
  - `15 years until bonds pay out`
  - `2 years`
  - `20 years`
  - `3 years`
  - `30 years`
  - `5 years`
  - `5 years or until all statute of limitations have expired, whichever is longer`
  - `5 years until expired or cancelled`
  - `7 years`
  - `As long as LOC is outstanding`
  - `As long as the assessment is outstanding`
  - `PW-D-002-Public Works Environmental Health`
  - `Permanent`
  - `life of contract plus 5 years  (minimum of 15 years)`
  - `life of contract plus 5 years (minimum of 15 years)`
  - `permanent`
  - `program or policy term, inactive 15 years`
  - `until death`
  - `until paid`
- Disposition types:
  - `Desroy`
  - `Destroy`
  - `Destroy 5 years after all litigations, audits resolved`
  - `Permanent`
  - `Permanent 1 copy`
  - `Retain 1 perm copy`
  - `destroy`
  - `destroy 10 years past bond maturity or 25 years from date of bond sold`
  - `destroy 3 years after contract ends`
  - `destroy 3 years after end of employment`
  - `destroy 3 years after grant is closed`
  - `destroy after 5 years`
  - `destroy; retain 1 bond of each series permanently`
  - `permanent`
  - `retain`
  - `retain 3 copies permanently`
  - `until death`
  - `until paid`
- RM Series:

**Needed (gaps):**
- ❌ Source of retention schedules (City Clerk's office? State law? Federal?)
- ❌ How retention schedules are updated/maintained
- ❌ Legal citations for retention requirements
- ❌ Exceptions to standard retention rules
- ❌ Hold/litigation hold procedures
- ❌ How to handle documents with multiple retention requirements

### 6. Retention Enforcement

**Available in files:** Cutoff triggers defined (File Date, Expiration, Superseded, etc.)

**Needed (gaps):**
- ❌ Is retention enforcement automated or manual?
- ❌ What metadata field triggers the retention countdown?
- ❌ Notification system before disposition
- ❌ Approval workflow for disposition
- ❌ Audit trail for disposed records
- ❌ Recovery procedures for accidentally disposed records
- ❌ System configuration for automated retention

### 7. Access Control Model

**Available in files:** Security tags referenced; departmental boundaries implied by templates

**Needed (gaps):**
- ❌ Complete access control model documentation
- ❌ User role definitions (e.g., Admin, Power User, Read-Only)
- ❌ Permission levels (Read, Write, Delete, Share, etc.)
- ❌ How departmental boundaries enforce access
- ❌ Cross-department access procedures
- ❌ Privileged access management (PAM) for sensitive data
- ❌ Service account management

### 8. Sensitive Data Access Workflow

**Available in files:** No explicit workflow documentation found

**Needed (gaps):**
- ❌ Definition of 'sensitive data' in this context
- ❌ Request submission process
- ❌ Approval authority matrix
- ❌ Timeframe for access request processing
- ❌ Temporary vs permanent access procedures
- ❌ Access review and recertification schedule
- ❌ Logging and monitoring of sensitive data access

### 9. Data Export & System Connection

**Available in files:** No export or integration documentation found

**Needed (gaps):**
- ❌ Export capabilities and restrictions
- ❌ API availability for system integration
- ❌ Data format standards for exports
- ❌ Governance rules that apply to exported data
- ❌ Metadata preservation in exports
- ❌ Integration with future data lake or analytics platforms
- ❌ Export approval workflow
- ❌ Audit trail for data exports

### 10. Governance Adoption Challenges

**Available in files:** Notes sections show requirements being gathered; 22 departments with different needs

**Needed (gaps):**
- ❌ Historical adoption challenges (lessons learned)
- ❌ Change management strategy
- ❌ Training programs and materials
- ❌ Compliance monitoring and enforcement
- ❌ User feedback mechanisms
- ❌ Success metrics and adoption rates
- ❌ Ongoing governance improvements

---
## Part 2 — Validation Report: Naming Conventions & Data Quality

> Cross-referenced against `GOVERNANCE_GAP_ANALYSIS.md`

### File Naming Convention
Expected pattern: `DEPT-D-###-Description.xlsx`

| Result | Count |
|--------|-------|
| ✅ Conforming | 45 |
| ❌ Non-conforming | 0 |

### Department Code Validation
Source: `GE-D-001-Department Abbreviations CODES.xlsx`

**Known codes (17):** `1`, `10`, `11`, `12`, `13`, `14`, `15`, `16`, `19`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`

**Unrecognised dept codes in filenames:**
- `AP-D-001-Airport Documents.xlsx` — code `AP` not in GE-D-001
- `AP-D-002-Airports.xlsx` — code `AP` not in GE-D-001
- `CA-D-001-Cultrual Arts Documents.xlsx` — code `CA` not in GE-D-001
- `CA-D-002-Cultrual Arts Divisions.xlsx` — code `CA` not in GE-D-001
- `CA-D-003-Cultrual Arts Boards.xlsx` — code `CA` not in GE-D-001
- `CC-D-001-City Council Awards Department.xlsx` — code `CC` not in GE-D-001
- `CC-D-001-City Council Documents.xlsx` — code `CC` not in GE-D-001
- `CK-D-001-City Clerk Documents.xlsx` — code `CK` not in GE-D-001
- `CS-D-001-Office of Community Services District.xlsx` — code `CS` not in GE-D-001
- `CS-D-001-Office of Community Services Documents.xlsx` — code `CS` not in GE-D-001
- `ED-D-001-Economic Development Bond Type.xlsx` — code `ED` not in GE-D-001
- `ED-D-001-Economic Development Documents.xlsx` — code `ED` not in GE-D-001
- `FD-D-001-Fire Department Documents.xlsx` — code `FD` not in GE-D-001
- `FD-D-001-Fire Department Subfolders.xlsx` — code `FD` not in GE-D-001
- `FN-D-001-Finance Controllers.xlsx` — code `FN` not in GE-D-001
- `FN-D-002-Finance Debt Management.xlsx` — code `FN` not in GE-D-001
- `FN-D-003-Finance Express.xlsx` — code `FN` not in GE-D-001
- `FN-D-004-Finance Pension.xlsx` — code `FN` not in GE-D-001
- `FN-D-005-Finance Purchasing.xlsx` — code `FN` not in GE-D-001
- `FN-D-006-Finance Risk Management.xlsx` — code `FN` not in GE-D-001
- `FN-D-007-Finance Treasury Express.xlsx` — code `FN` not in GE-D-001
- `HC-D-001-Housing and Community Services Documents.xlsx` — code `HC` not in GE-D-001
- `HR-D-001-HR Documents.xlsx` — code `HR` not in GE-D-001
- `IT-D-001-IT Documents.xlsx` — code `IT` not in GE-D-001
- `LB-D-001-Library Documents.xlsx` — code `LB` not in GE-D-001
- `LW-D-001-Law Department Documents.xlsx` — code `LW` not in GE-D-001
- `MC-D-001-Municiple Court Documents.xlsx` — code `MC` not in GE-D-001
- `MP-D-001-MAPC Divisions.xlsx` — code `MP` not in GE-D-001
- `MP-D-001-MAPC Documents.xlsx` — code `MP` not in GE-D-001
- `PD-D-001-Police Department Documents.xlsx` — code `PD` not in GE-D-001
- `PM-D-001-Property Management Documents.xlsx` — code `PM` not in GE-D-001
- `PR-D-001-Park and Recreation Documents.xlsx` — code `PR` not in GE-D-001
- `PW-D-001-Public Works Engineering.xlsx` — code `PW` not in GE-D-001
- `PW-D-002-Public Works Environmental Health.xlsx` — code `PW` not in GE-D-001
- `PW-D-003-Public Works Admin.xlsx` — code `PW` not in GE-D-001
- `PW-D-004-Public Works Fleet Maintenance.xlsx` — code `PW` not in GE-D-001
- `PW-D-005-Public Works Stormwater.xlsx` — code `PW` not in GE-D-001
- `PW-D-006-Public Works Facilities Maintenance.xlsx` — code `PW` not in GE-D-001
- `PW-D-007-Public Works Streets.xlsx` — code `PW` not in GE-D-001
- `PW-D-008-Public Works Sewer Maintenance.xlsx` — code `PW` not in GE-D-001
- `PW-D-009-Public Works Sewer Treatment.xlsx` — code `PW` not in GE-D-001
- `PW-D-010-Public Works Water Production.xlsx` — code `PW` not in GE-D-001
- `PW-D-011-Public Works Water Distribution.xlsx` — code `PW` not in GE-D-001
- `TR-D-001-Transportation Department Documents.xlsx` — code `TR` not in GE-D-001

### Data Quality Issues

#### Misspelled Column Headers — 6 issue(s)
| File | Sheet | Found | Expected |
|------|-------|-------|----------|
| `CA-D-001-Cultrual Arts Documents.xlsx` | `Arts and Culture - Ready` | `RMCuttoff` | `RMCutoff` |
| `CC-D-001-City Council Documents.xlsx` | `City Council - Ready` | `RMCuttoff` | `RMCutoff` |
| `FD-D-001-Fire Department Documents.xlsx` | `Fire - Ready` | `RMCuttoff` | `RMCutoff` |
| `HC-D-001-Housing and Community Services Documents.xlsx` | `Housing - Ready` | `RMCuttoff` | `RMCutoff` |
| `HR-D-001-HR Documents.xlsx` | `Human Resources - Ready` | `RMCuttoff` | `RMCutoff` |
| `LW-D-001-Law Department Documents.xlsx` | `Law - Ready` | `RMCuttoff` | `RMCutoff` |

#### Disposition Value Issues (case / typos) — 298 issue(s)
| File | Sheet | Row | Value | Issue |
|------|-------|-----|-------|-------|
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 10 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 15 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 18 | `Permanent` | case inconsistency (expected 'permanent') |
| `FD-D-001-Fire Department Documents.xlsx` | `Fire - Ready` | 7 | `Destroy` | case inconsistency (expected 'destroy') |
| `HR-D-001-HR Documents.xlsx` | `Human Resources - Ready` | 4 | `Permanent` | case inconsistency (expected 'permanent') |
| `HR-D-001-HR Documents.xlsx` | `Human Resources - Ready` | 19 | `Permanent` | case inconsistency (expected 'permanent') |
| `HR-D-001-HR Documents.xlsx` | `Human Resources - Ready` | 20 | `Permanent` | case inconsistency (expected 'permanent') |
| `HR-D-001-HR Documents.xlsx` | `Human Resources - Ready` | 22 | `Permanent` | case inconsistency (expected 'permanent') |
| `HR-D-001-HR Documents.xlsx` | `Human Resources - Ready` | 30 | `Permanent` | case inconsistency (expected 'permanent') |
| `HR-D-001-HR Documents.xlsx` | `Human Resources - Ready` | 34 | `Permanent` | case inconsistency (expected 'permanent') |
| `MP-D-001-MAPC Documents.xlsx` | `MAPC - Ready` | 2 | `Permanent` | case inconsistency (expected 'permanent') |
| `MP-D-001-MAPC Documents.xlsx` | `MAPC - Ready` | 3 | `Permanent` | case inconsistency (expected 'permanent') |
| `MP-D-001-MAPC Documents.xlsx` | `MAPC - Ready` | 4 | `Permanent` | case inconsistency (expected 'permanent') |
| `MP-D-001-MAPC Documents.xlsx` | `MAPC - Ready` | 5 | `Permanent` | case inconsistency (expected 'permanent') |
| `MP-D-001-MAPC Documents.xlsx` | `MAPC - Ready` | 6 | `Permanent` | case inconsistency (expected 'permanent') |
| `MP-D-001-MAPC Documents.xlsx` | `MAPC - Ready` | 7 | `Destroy` | case inconsistency (expected 'destroy') |
| `MP-D-001-MAPC Documents.xlsx` | `MAPC - Ready` | 8 | `Permanent` | case inconsistency (expected 'permanent') |
| `MP-D-001-MAPC Documents.xlsx` | `MAPC - Ready` | 9 | `Permanent` | case inconsistency (expected 'permanent') |
| `MP-D-001-MAPC Documents.xlsx` | `MAPC - Ready` | 10 | `Permanent` | case inconsistency (expected 'permanent') |
| `MP-D-001-MAPC Documents.xlsx` | `MAPC - Ready` | 11 | `Permanent` | case inconsistency (expected 'permanent') |
*… and 278 more rows*

#### Retention Case Inconsistencies — 260 issue(s)
| File | Sheet | Row | Value | Issue |
|------|-------|-----|-------|-------|
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 3 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 5 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 6 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 7 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 8 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 9 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 10 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 11 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 13 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 15 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 16 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 17 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 18 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 20 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 21 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 23 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 26 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 27 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 28 | `Permanent` | case inconsistency (expected 'permanent') |
| `AP-D-001-Airport Documents.xlsx` | `Airport - Ready` | 30 | `Permanent` | case inconsistency (expected 'permanent') |
*… and 240 more rows*

#### Retention Fields Containing Filenames (data entry error) — 1 issue(s)
| File | Sheet | Row | Value |
|------|-------|-----|-------|
| `PW-D-002-Public Works Environmental Health.xlsx` | `PW-D-002-Public Works Environme` | 22 | `PW-D-002-Public Works Environmental Health` |

---
## Summary

| Category | Issues |
|----------|--------|
| Non-conforming filenames | 0 |
| Unknown dept codes | 44 |
| Misspelled headers | 6 |
| Disposition value issues | 298 |
| Retention case issues | 260 |
| Retention/filename mix-ups | 1 |
| **TOTAL** | **609** |
