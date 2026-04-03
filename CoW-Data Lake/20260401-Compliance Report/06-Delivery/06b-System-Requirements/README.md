# 06b — System Requirements Document

**Deliverable:** Detailed functional and non-functional requirements for CoW's new data storage and analysis environment  
**Draft Due:** May 2, 2026  
**Final Due:** May 16, 2026  
**Developed With:** CoW IT Department  

---

## Files

| File | Description |
|---|---|
| `20260401-System-Requirements-v1.md` | Working draft — update in place, increment version on each client share |
| `FINAL/` | Approved, signed-off version only — nothing goes here until IT validation and client acceptance |

---

## Document Outline

| Section | Input Source |
|---|---|
| 1. Business Context & Objectives | `04-Kickoff/` + IT Department interviews |
| 2. Stakeholder Register | `04-Kickoff/Stakeholder-Register.md` |
| 3. Functional Requirements | `05-Discovery/Interview-Notes/` + IT sessions |
| 4. Non-Functional Requirements | SLA definitions from kickoff brief |
| 5. Data Architecture Diagram | `../20251104-2nd Meeting/ON_PREM_DATA_INFRASTRUCTURE_OVERVIEW.md` |
| 6. Integration Requirements | `../IntegrationFramework.md` + IT interviews |
| 7. Acceptance Criteria | Confirmed at kickoff — see `04-Kickoff/20260401-Client-Kickoff-Brief.md` |
| 8. Open Issues & Decisions Log | Maintained throughout discovery and delivery |

---

## Functional Requirements Domains

| Domain | Description |
|---|---|
| Data Ingestion | Batch and event-driven ingestion from 22+ departments |
| Data Storage | Tiered strategy (hot / warm / cold) with retention enforcement |
| Access Control | Role-based access aligned to Laserfiche security tags and RACI |
| Data Retention & Disposal | Automated enforcement of retention schedules |
| Search & Discovery | Metadata-driven discoverability across departments |
| Reporting & Analytics | Power BI integration and self-service analytics layer |
| Audit & Compliance | Logging, access trails, and export tracking |

---

## Acceptance Criteria

- [ ] IT department confirms functional requirements reflect actual operational needs
- [ ] All SLA values in the document approved by appropriate CoW authority
- [ ] Document is complete enough to share with a vendor or internal IT project team
- [ ] Open Issues log reviewed — all blocking decisions resolved or formally deferred
- [ ] Final version approved in writing by CoW IT lead and project lead
