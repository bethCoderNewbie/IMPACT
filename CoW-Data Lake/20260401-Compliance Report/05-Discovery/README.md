# 05 — Discovery

**Purpose:** All research, interview outputs, and analysis inputs gathered from the client during the engagement. This folder feeds directly into the deliverables in `06-Delivery/`.

---

## Subfolders

| Folder | Contents |
|---|---|
| `Interview-Notes/` | Notes from each stakeholder session — one file per interview |
| `Gap-Analysis-Inputs/` | Raw data and evidence used to populate the compliance gap matrix |
| `Workshop-Outputs/` | Whiteboards, decisions, and action items from collaborative sessions |

## Other Files

| File | Description |
|---|---|
| `Current-State-Assessment.md` | Synthesized picture of CoW's governance and infrastructure as it exists today — drawn from interviews, document review, and prior gap analysis |

---

## Interview Notes — File Format

Each interview note file should follow this structure:

```
# Interview: [Stakeholder Name] — [Role]
Date: YYYY-MM-DD
Duration: X minutes
Interviewer(s): [Name(s)]

## Key Responses
[Question-by-question summary]

## Key Findings
[Bullet list of notable gaps, confirmations, or surprises]

## Action Items
| Item | Owner | Due |
|---|---|---|
```

**Naming:** `YYYYMMDD-Interview-[Role].md`
Example: `20260414-Interview-CityClerk.md`

---

## Gap Analysis Inputs — What to Collect

Pull from the following upstream sources (all in parent `CoW-Data Lake/` directory):

| Source | Location | Feeds Into |
|---|---|---|
| Governance Gap Analysis v2 | `../Gap Analysis Report/GOVERNANCE-REPORT_2026-04-01_v2.md` | Current State Assessment, Gap Matrix |
| Governance Gap Analysis (detail) | `../20251104-2nd Meeting/GOVERNANCE_GAP_ANALYSIS.md` | Current State Assessment |
| Data Management Lists (45 files) | `../Data Management Lists/*.xlsx` | Gap Matrix Appendix A |
| On-Prem Infrastructure Overview | `../20251104-2nd Meeting/ON_PREM_DATA_INFRASTRUCTURE_OVERVIEW.md` | System Requirements context |

---

## Definition of Done for This Phase

- [ ] All 8 stakeholder interview sessions completed and notes filed
- [ ] Current state assessment written and internally reviewed
- [ ] Gap analysis inputs organized and cross-referenced
- [ ] Workshop outputs documented
