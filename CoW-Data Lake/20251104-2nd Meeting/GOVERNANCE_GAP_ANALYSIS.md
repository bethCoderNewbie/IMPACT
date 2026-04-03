# Laserfiche Data Governance - Gap Analysis Report
## City of Wichita Data Management System

**Date:** November 5, 2025
**Analysis of:** Data Management Lists (44 Excel files)

---

## Executive Summary

Based on the analysis of 44 Excel files in the "Data Management Lists" folder, this report identifies **what information is currently available** versus **what additional information is needed** to fully answer your 10 governance questions.

### Key Findings:
- ✅ **Document taxonomy is well-defined**: 432+ document types across 22 departments
- ✅ **Retention schedules are structured**: 33 different retention periods with cutoff triggers
- ✅ **Metadata fields are identified**: 32 metadata fields for classification
- ❌ **Major gaps exist** in: access control, stakeholder roles, enforcement procedures, and adoption strategies

---

## Detailed Gap Analysis by Question

### 1️⃣ DATA CLASSIFICATION SCHEMA

#### ✅ What You HAVE:
- Document classifications by department and type
- 432 document type abbreviations with full names
- Document classes (Legal, Files, Boards, Finance, etc.)

#### ❌ What You NEED:
| Missing Information | Where to Find It |
|---------------------|------------------|
| Data classification levels (Public, Internal, Confidential, Restricted) | **City Information Security Policy** or **Data Classification Policy Document** |
| Specific definitions for each classification level | Same as above |
| Handling rules per classification level | **Information Handling Procedures Manual** |
| Access requirements per classification level | **Access Control Policy** |
| Storage requirements per classification | **IT Security Standards** |

**🎯 Action Items:**
1. Request the City's **Information Security Policy** from IT/Security team
2. Ask for the **Data Classification Standards** document
3. Interview the **Chief Information Security Officer (CISO)** or equivalent role

---

### 2️⃣ FILE NAMING & METADATA STANDARDS

#### ✅ What You HAVE:
- **32 metadata fields** identified:
  - DocClass, DocType, Abbr, Template
  - RMCutoff, RMRetention, RMSeries, SecTag, Disposition
  - Department-specific fields (District, Division, Airport Name, etc.)
- **432 document abbreviations** with standardized codes
- Department templates defined for all 22 departments

#### ❌ What You NEED:
| Missing Information | Where to Find It |
|---------------------|------------------|
| Complete file naming convention schema with examples | **Laserfiche Configuration Guide** or **System Administrator** |
| Naming logic/rules (e.g., [Dept]-[Type]-[Date]-[Description].ext) | Same as above |
| Which metadata fields are MANDATORY vs OPTIONAL | **Laserfiche Template Definitions** |
| Validation rules for metadata (formats, allowed values) | **System Configuration Documentation** |
| Default values for metadata fields | Same as above |
| Metadata inheritance rules (folder-level vs document-level) | **Laserfiche Best Practices Guide** |

**🎯 Action Items:**
1. Interview the **Laserfiche System Administrator(s)**
2. Request **Laserfiche template configuration exports**
3. Ask for **user training materials** on document uploads
4. Review **Laserfiche workflow documentation** if available

---

### 3️⃣ RECORDS COORDINATORS / DATA STEWARDS

#### ✅ What You HAVE:
- Partial user access requirements in Notes sections
- A few names mentioned (Lindsay Benacka, Jesse Koza, Rhonda Harper, Logan Walker, Mandee Greer, etc.)
- Evidence that "30 records coordinators" exist (mentioned in initial context)

#### ❌ What You NEED:
| Missing Information | Where to Find It |
|---------------------|------------------|
| Complete list of 30 records coordinators with names and contact info | **City Clerk's Office** or **Records Management Program Documentation** |
| Department assignment for each coordinator | Same as above |
| Specific responsibilities for each coordinator | **Records Coordinator Job Description** or **Charter** |
| Training requirements for coordinators | **Records Management Training Program** |
| Escalation procedures when coordinator is unavailable | **Records Management Procedures Manual** |
| Performance metrics/KPIs for coordinators | **Records Management Annual Reports** or **Performance Reviews** |

**🎯 Action Items:**
1. Request the **official list of Records Coordinators** from the City Clerk
2. Ask for the **Records Coordinator Charter** or role definition document
3. Interview 3-5 Records Coordinators to understand their actual responsibilities
4. Request **training materials** provided to new coordinators

---

### 4️⃣ STAKEHOLDER ROLES (RACI MATRIX)

#### ✅ What You HAVE:
- 22 departments identified using Laserfiche
- Evidence of departmental structure and ownership

#### ❌ What You NEED:
| Missing Information | Where to Find It |
|---------------------|------------------|
| Complete RACI matrix (Responsible, Accountable, Consulted, Informed) | **Governance Charter** or **Project Documentation** |
| IT Department roles and responsibilities | **IT Service Catalog** or **IT Governance Policy** |
| Legal Department roles and responsibilities | **Legal Department Procedures** |
| Department Head responsibilities | **City Administrative Manual** or **Department Head Policies** |
| City Clerk's role in records management | **City Charter** or **Records Management Ordinance** |
| Audit and compliance oversight roles | **Internal Audit Charter** |
| Escalation paths for governance issues | **Governance Framework Document** |

**🎯 Action Items:**
1. Interview **IT Leadership** to understand their role
2. Interview **Legal Department** representative
3. Interview **City Clerk or Records Manager**
4. Request any **Laserfiche Governance Committee** meeting minutes
5. Ask for the **Records Management Ordinance** or enabling legislation

---

### 5️⃣ RETENTION SCHEDULES

#### ✅ What You HAVE:
- **8 cutoff types** with some descriptions:
  - CO-01 File Date: Cutoff begins at file date
  - CO-02 Expiration: Cutoff begins when contract/event expires
  - CO-03 Superseded: When a document gets superseded
  - CO-04 OBS/NLU: Document is obsolete and no longer useful
  - CO-05 Completion: Cutoff begins on project completion
  - CO-07 Employee Term: Cutoff begins at employee termination

- **33 retention periods** ranging from 1 year to permanent

- **Disposition types**: destroy, permanent, retain, with specific instructions

#### ❌ What You NEED:
| Missing Information | Where to Find It |
|---------------------|------------------|
| Source of retention schedules (City Clerk's office? State law? Federal?) | **Official Records Retention Schedule** from City Clerk |
| How retention schedules are updated/maintained | **Records Management Policy** |
| Legal citations for retention requirements | **Annotated Retention Schedule** |
| Exceptions to standard retention rules | **Records Management Procedures** |
| Hold/litigation hold procedures | **Legal Hold Policy** (Legal Department) |
| How to handle documents with multiple retention requirements | **Records Management Manual** |

**🎯 Action Items:**
1. Request the **official City of Wichita Records Retention Schedule**
2. Ask if it's based on the **Kansas State Records Retention Schedule**
3. Interview City Clerk about how schedules are maintained and updated
4. Request any **retention schedule updates** from the past 5 years
5. Ask Legal Department for **litigation hold procedures**

---

### 6️⃣ RETENTION ENFORCEMENT

#### ✅ What You HAVE:
- Cutoff triggers defined (File Date, Expiration, Superseded, etc.)
- Retention periods assigned to each document type
- Disposition instructions (destroy, permanent, retain)

#### ❌ What You NEED:
| Missing Information | Where to Find It |
|---------------------|------------------|
| Is retention enforcement automated or manual? | **Laserfiche System Administrator** |
| What metadata field triggers the retention countdown? | **Laserfiche Configuration** |
| Notification system before disposition | **Laserfiche Workflow Documentation** |
| Approval workflow for disposition | **Records Disposition Procedures** |
| Audit trail for disposed records | **System Audit Logs** or **Records Destruction Certificates** |
| Recovery procedures for accidentally disposed records | **Disaster Recovery Plan** or **Backup Procedures** |
| System configuration for automated retention | **Laserfiche Records Management Configuration Guide** |

**🎯 Action Items:**
1. Interview **Laserfiche System Administrator** about automation
2. Request **Laserfiche Records Management module configuration**
3. Ask for examples of **disposition notifications** sent to users
4. Review **audit logs** for past dispositions
5. Request **Records Destruction Certificates** if they exist

---

### 7️⃣ ACCESS CONTROL MODEL

#### ✅ What You HAVE:
- Evidence of departmental boundaries (22 departments)
- Security tags referenced (though not populated in current data)
- Template-based organization suggesting access controls

#### ❌ What You NEED:
| Missing Information | Where to Find It |
|---------------------|------------------|
| Complete access control model documentation | **Laserfiche Security Configuration Guide** |
| User role definitions (e.g., Admin, Power User, Read-Only) | **Laserfiche User Role Matrix** |
| Permission levels (Read, Write, Delete, Share, etc.) | Same as above |
| How departmental boundaries enforce access | **Access Control Policy** |
| Cross-department access procedures | **Access Request Procedures** |
| Privileged access management (PAM) for sensitive data | **IT Security Policy** |
| Service account management | **IT Service Account Policy** |

**🎯 Action Items:**
1. Request **Laserfiche security group definitions** from IT
2. Ask for **access control matrix** showing who can access what
3. Review **Active Directory integration** (if applicable)
4. Interview IT about **privileged access management**
5. Request examples of **cross-department access requests**

---

### 8️⃣ SENSITIVE DATA ACCESS WORKFLOW

#### ✅ What You HAVE:
- No explicit workflow documentation found in the Excel files

#### ❌ What You NEED:
| Missing Information | Where to Find It |
|---------------------|------------------|
| Definition of 'sensitive data' in this context | **Data Classification Policy** |
| Request submission process | **Access Request Procedures** |
| Approval authority matrix | **Delegation of Authority** or **Access Approval Policy** |
| Timeframe for access request processing | **Service Level Agreement (SLA)** for IT |
| Temporary vs permanent access procedures | **Access Control Procedures** |
| Access review and recertification schedule | **Access Recertification Policy** |
| Logging and monitoring of sensitive data access | **Security Monitoring Policy** or **SIEM Configuration** |

**🎯 Action Items:**
1. Request the **Data Classification Policy** (likely defines sensitive data)
2. Ask IT for the **access request workflow** (may be in ServiceNow, etc.)
3. Interview **Information Security Officer** about monitoring
4. Request **access recertification procedures**
5. Review **audit logs** for sensitive data access

---

### 9️⃣ DATA EXPORT & SYSTEM CONNECTION

#### ✅ What You HAVE:
- No export or integration documentation found

#### ❌ What You NEED:
| Missing Information | Where to Find It |
|---------------------|------------------|
| Export capabilities and restrictions | **Laserfiche Administrator Guide** |
| API availability for system integration | **Laserfiche API Documentation** |
| Data format standards for exports | **Data Integration Standards** |
| Governance rules that apply to exported data | **Data Sharing Policy** or **Data Governance Policy** |
| Metadata preservation in exports | **Laserfiche Export Configuration** |
| Integration with future data lake or analytics platforms | **IT Strategic Plan** or **Data Architecture Documentation** |
| Export approval workflow | **Data Export Policy** |
| Audit trail for data exports | **System Audit Logs** |

**🎯 Action Items:**
1. Interview **IT leadership** about data lake plans
2. Ask **Laserfiche Administrator** about API and export capabilities
3. Request **IT Strategic Plan** or **Data Architecture Roadmap**
4. Ask about any existing **data warehouse or BI integrations**
5. Review any **vendor contracts** with Laserfiche for API access

---

### 🔟 GOVERNANCE ADOPTION CHALLENGES

#### ✅ What You HAVE:
- Notes sections showing requirements being gathered (suggests this is relatively new)
- Evidence of 22 departments with different needs
- Multiple divisions, boards, districts within departments

#### ❌ What You NEED:
| Missing Information | Where to Find It |
|---------------------|------------------|
| Historical adoption challenges (lessons learned) | **Project Retrospectives** or **Steering Committee Meeting Minutes** |
| Change management strategy | **Change Management Plan** |
| Training programs and materials | **Training Department** or **HR Learning & Development** |
| Compliance monitoring and enforcement | **Internal Audit Reports** or **Compliance Monitoring Plan** |
| User feedback mechanisms | **User Surveys** or **Feedback Forms** |
| Success metrics and adoption rates | **Project Status Reports** or **KPI Dashboards** |
| Ongoing governance improvements | **Governance Committee Meeting Minutes** |

**🎯 Action Items:**
1. Interview **Records Coordinators** about biggest challenges
2. Request **project retrospective documents** from implementation
3. Ask for **user training materials** and **adoption metrics**
4. Review **help desk tickets** related to Laserfiche (common issues)
5. Request any **user satisfaction surveys** conducted
6. Interview **Change Management lead** if there is one

---

## 📋 Summary: 10 Critical Documents to Request

| Priority | Document Type | Primary Source |
|----------|---------------|----------------|
| 🔴 HIGH | **Official Records Retention Schedule** | City Clerk's Office |
| 🔴 HIGH | **Laserfiche System Configuration Documentation** | IT Department / Laserfiche Admin |
| 🔴 HIGH | **Records Coordinator List & Responsibilities** | City Clerk's Office |
| 🔴 HIGH | **Data Classification Policy** | IT Security / CISO |
| 🟡 MEDIUM | **Access Control Policy & Procedures** | IT Department |
| 🟡 MEDIUM | **RACI Matrix / Governance Charter** | Project Management Office / Steering Committee |
| 🟡 MEDIUM | **Retention Enforcement Procedures** | City Clerk / IT |
| 🟡 MEDIUM | **Training Materials & Adoption Metrics** | Training Department / PMO |
| 🟢 LOW | **Data Export & Integration Policy** | IT Department / Enterprise Architecture |
| 🟢 LOW | **Change Management Documentation** | PMO / Organizational Change Management |

---

## 👥 Key Stakeholders to Interview

### Essential Interviews (High Priority)

1. **Laserfiche System Administrator(s)**
   - Questions: Configuration, automation, access control, export capabilities
   - Time needed: 1-2 hours

2. **City Clerk or Records Manager**
   - Questions: Retention schedules, legal basis, records coordinators, enforcement
   - Time needed: 1-2 hours

3. **Chief Information Security Officer (CISO) or IT Security Lead**
   - Questions: Data classification, access control, sensitive data handling
   - Time needed: 1 hour

### Important Interviews (Medium Priority)

4. **IT Department Leadership (CIO or Deputy)**
   - Questions: Strategic plans, data lake integration, system architecture
   - Time needed: 1 hour

5. **Legal Department Representative**
   - Questions: Legal holds, compliance, litigation procedures
   - Time needed: 45 minutes

6. **3-5 Records Coordinators from Different Departments**
   - Questions: Day-to-day challenges, training, adoption issues
   - Time needed: 30-45 minutes each

### Supplementary Interviews (Nice to Have)

7. **Department Heads (2-3 heavy users)**
   - Questions: Business value, challenges, future needs
   - Time needed: 30 minutes each

8. **Internal Audit or Compliance Representative**
   - Questions: Audit findings, compliance monitoring
   - Time needed: 45 minutes

9. **Project Manager (if Laserfiche was a recent implementation)**
   - Questions: Implementation challenges, lessons learned
   - Time needed: 1 hour

---

## 🔍 What the Excel Files Tell Us

### Strengths of Current System:

1. **Well-Structured Taxonomy**
   - 432 document types clearly defined
   - Consistent abbreviation system
   - 22 departments fully mapped

2. **Comprehensive Retention Framework**
   - 33 different retention periods
   - 8 cutoff trigger types
   - Clear disposition instructions

3. **Metadata Standards Established**
   - 32 metadata fields identified
   - Department-specific customization (districts, divisions, boards)
   - Template-based approach

4. **Department-Specific Customization**
   - Public Works (11 different divisions)
   - Finance (7 different areas)
   - Cultural Arts (divisions and boards)
   - Community Services (6 districts)

### Gaps/Concerns Observed:

1. **Inconsistencies in Data**
   - "RMCutoff" vs "RMCuttoff" (spelling variations)
   - Disposition values: "destroy" vs "Destroy" vs "Desroy" (typo)
   - "Permanent" vs "permanent"
   - Some retention periods include file names (error: "PW-D-002-Public Works Environmental Health")

2. **No Security Classification Data**
   - SecTag field exists but appears to be empty
   - No explicit classification levels defined

3. **Limited Governance Documentation**
   - Notes sections show this is still being developed
   - User access lists incomplete
   - No workflow documentation

4. **No Enforcement Evidence**
   - No indication of automation
   - No audit trail references
   - No disposition tracking

---

## 📊 Quick Reference: Information Availability Matrix

| Governance Question | Available | Partial | Missing |
|---------------------|-----------|---------|---------|
| 1. Data Classification | | | ❌ |
| 2. File Naming & Metadata | | 🟡 | |
| 3. Records Coordinators | | 🟡 | |
| 4. Stakeholder Roles (RACI) | | | ❌ |
| 5. Retention Schedules | | ✅ | |
| 6. Retention Enforcement | | 🟡 | |
| 7. Access Control Model | | 🟡 | |
| 8. Sensitive Data Workflow | | | ❌ |
| 9. Data Export & Integration | | | ❌ |
| 10. Adoption Challenges | | | ❌ |

**Legend:**
- ✅ = Substantial information available
- 🟡 = Partial information, needs supplementation
- ❌ = Little to no information available

---

## 🎯 Recommended Next Steps

### Week 1: Document Collection
1. Send document requests to City Clerk's Office (retention schedule, coordinator list)
2. Send document requests to IT Department (security policy, Laserfiche config)
3. Schedule interviews with key stakeholders

### Week 2: Primary Interviews
4. Interview Laserfiche System Administrator
5. Interview City Clerk or Records Manager
6. Interview CISO or IT Security Lead

### Week 3: Supplementary Interviews
7. Interview 3-5 Records Coordinators
8. Interview Legal Department representative
9. Interview IT Leadership

### Week 4: Analysis & Documentation
10. Consolidate all gathered information
11. Fill in gaps in governance documentation
12. Prepare comprehensive governance documentation
13. Identify any remaining gaps for follow-up

---

## 📝 Interview Question Templates

### For Laserfiche System Administrator:

**Configuration & Automation:**
- How is the Laserfiche system configured for retention management?
- Is retention enforcement automated or manual?
- What triggers the retention countdown?
- How are users notified before disposition?

**Access Control:**
- How are user roles and permissions defined?
- How do you handle cross-department access requests?
- What security groups exist in the system?

**Integration:**
- Does Laserfiche have API access enabled?
- Are there any current integrations with other systems?
- What export formats are available?

### For City Clerk / Records Manager:

**Retention Schedules:**
- What is the source of the retention schedules (state law, local ordinance)?
- How often are retention schedules reviewed and updated?
- What legal citations support these retention requirements?

**Records Coordinators:**
- Can you provide the complete list of 30 records coordinators?
- What are their official responsibilities?
- How are they trained?
- How is their performance monitored?

**Enforcement:**
- How is disposition approved?
- What happens when records need to be destroyed?
- Is there a legal hold process?

### For CISO / IT Security:

**Data Classification:**
- What data classification levels does the City use?
- How is sensitive data defined?
- What are the handling requirements for each classification level?

**Access Control:**
- What is the access control model for Laserfiche?
- How is sensitive data access monitored?
- What is the process for access recertification?

### For Records Coordinators:

**Day-to-Day Operations:**
- What are your biggest challenges with Laserfiche?
- How were you trained?
- How do you handle unusual situations?
- What would make your job easier?

**Adoption:**
- How well are people in your department using the system?
- What resistance have you encountered?
- What questions do you get most often?

---

## 🔗 Related Files to Explore

Based on this analysis, you should also check if these files exist in your data lake:

- `/CoW-Data Lake/Policies/` (if it exists)
- `/CoW-Data Lake/Documentation/` (if it exists)
- `/CoW-Data Lake/Training/` (if it exists)
- `/CoW-Data Lake/Procedures/` (if it exists)
- Any `README.md` or `GOVERNANCE.md` files
- Any Word docs (.docx) or PDFs that might contain policy information

---

**Report Generated:** November 5, 2025
**Analysis Tool:** Python with openpyxl
**Source Files:** 44 Excel files in "Data Management Lists" folder
**Total Document Types Identified:** 432+
**Departments Covered:** 22
