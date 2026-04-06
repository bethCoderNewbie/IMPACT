# CoW DGQA 2026 Budget Discovery Report
**Project:** City of Wichita — Data Governance & Compliance Engagement
**Phase:** 05 – Discovery
**Status:** Verified — Awaiting Human Review
**Date:** 2026-04-06
**Version:** v2.0 (expanded from v1.0 — added DGQA Checklist detail, KPI framework, Master Table, Data Lake implications; resolved $7.1M budget discrepancy)

---

## 1. Executive Summary

The City of Wichita 2026 Adopted Budget represents a **fundamental architectural shift** in how the city manages data and performance. Moving beyond static reporting, the 2026 budget institutionalizes Data Governance and Quality Assurance (DGQA) as a mandatory technical and operational gate for **all city projects with a data component**.

DGQA is the technical engine of Pillar 1: "Well-Run City" — transitioning data from a departmental silo to a **Strategic Enterprise Asset**.

**One item remains flagged for client clarification:**

| Flag | Claim | Finding |
|---|---|---|
| ⚠️ Personnel | Senior PM moved from General Fund → IT Fund 613 | Not found in official CMO or IT budget docs. Only a Web Designer transfer is documented for this period. |

**Budget discrepancy from v1.0 resolved:** The $7,102,746 figure is the combined Total CMO budget for City Clerk + Internal Audit + Project Management divisions — a verified figure. It was previously misread as "PM division alone." See Section 5.

---

## 2. Strategic Context — "Well-Run City" Pillar

The 2026 Adopted Budget is organized around **four strategic pillars**:

1. Keep Wichita Safe
2. Grow Our Economy
3. Build Dependable Infrastructure
4. **Well-Run City** ← DGQA anchor pillar

> *"Efforts will include establishing a data governance and quality assurance system for reviewing data and implementing a citywide performance management framework."*

**Source:** [2026 City Manager's Policy Message](https://www.wichita.gov/DocumentCenter/View/35337/02---City-Managers-Policy-Message-PDF)

---

## 3. DGQA Initiative — The Mandatory Governance Gate

Every new project with a "data component" must now pass through the DGQA gate before proceeding to implementation. This gate has two mandatory artifacts:

### 3.1 Project Charter Integration ✅ VERIFIED

A dedicated **DGQA Section** is a permanent requirement in the City's Project Charter Template. Projects cannot advance to the implementation phase without a signed DGQA compliance plan.

> *"CMO-Project Management Office will add a Data Governance and Quality Assurance (DGQA) section to its Project Charter Template and ensure projects with data components comply with data governance and quality assurance system..."*

**Source:** [2026 Strategic Plan — Tactic 1.2.1i](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF)

---

### 3.2 The DGQA Compliance Checklist ✅ VERIFIED

The checklist is the technical validation tool that must be completed before implementation approval. It covers three domains:

| Checklist Domain | Requirement | Strategic Tie |
|---|---|---|
| **Data Provenance** | Document where data originates and how it is transformed through its lifecycle | Strategy 1.2.1 |
| **Access Control** | Define user roles and security tiers before system deployment | Strategy 1.2.1 |
| **Interconnectivity** | Ensure the new system can interface with the city's centralized data warehouse | [Strategy 1.5.2](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF) |

**Source:** [2026 Strategic Plan — Strategy 1.2.1](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF)

---

## 4. Governance Roles & Accountability Hierarchy

The 2026 budget defines a three-tier stewardship model:

| Tier | Role | Responsibility |
|---|---|---|
| **1 — Accountable Authority** | City Manager's Office (CMO) – Project Management Office | Enforces DGQA standards citywide via Project Charter gates; facilitates Performance Management Meetings (Strategy 1.2.2) |
| **2 — Technical Lead** | Information Technology (IT) Department | Manages underlying data infrastructure, data warehouse interfaces, and the DGQA technical system (Tactic 1.2.1i) |
| **3 — Departmental Stewards** | Each City Department | Designates "Data Stewards" accountable for daily quality and accuracy of department-specific datasets (e.g., Police response times, Public Works PCI scores) |

**Sources:**
- CMO-PMO role: [Strategic Plan, Tactic 1.2.1i](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF)
- IT role: [Strategic Plan, Tactic 1.2.1i](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF)
- Departmental Stewards: [Strategic Plan, Strategy 1.2.1](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF)

---

## 5. KPI Framework — From Vanity Metrics to Operational KPIs

### 5.1 Strategy 1.2.2 — Strategic Performance Management Framework ✅ VERIFIED

The city is actively "solidifying" its Master List of KPIs. This is a **dynamic performance system**, not a static report.

#### Operational KPIs (Efficiency)
Track lean spending and benchmark against peers:

| KPI | Department | Peer Benchmark |
|---|---|---|
| Pavement Condition Index (PCI) | Public Works | Tulsa, Sioux Falls |
| Cost per Lane-Mile | Public Works | Tulsa, Sioux Falls |
| Per-capita police spending | Police | OKC (~$420+), Tulsa |
| Per-capita library funding | Library | Omaha ($55), OKC ($86) vs. Wichita ($25) |

#### Outcome KPIs (Resident Impact)
The primary outcome metric for 2026:
> **"Percent of Residents Rating Service Quality as Excellent/Good"**

**Source:** [2026 Strategic Plan — Strategy 1.2.2](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF)

---

### 5.2 The "Master Table" Concept ✅ VERIFIED

The city uses a consolidated internal **Master Table** — a repository of financial and performance data — to balance the budget and identify reduction tiers.

#### Service Tier Classification

| Tier | Color Code | Type | Budget Treatment |
|---|---|---|---|
| Core Services | 🔵 Blue / 🟢 Green | Police, Fire, essential infrastructure | **Protected** — not subject to efficiency cuts |
| Flexible Services | 🟠 Orange / 🟣 Magenta | Non-essential or discretionary services | **Subject to data-driven cuts** if efficiency benchmarks are not met |

#### Predictive KPI Modeling
The budget uses forward-looking models to manage the **$3.6M structural deficit**:

| Model | Assumption | Basis |
|---|---|---|
| Health insurance cost | 3% growth (not 6%) | Actuarial adjustment; data-driven reduction |
| Property tax recalculation | Adjusted mill levy | Benchmarked against peer cities |

**Source:** [2026 City Manager's Office Budget](https://www.wichita.gov/DocumentCenter/View/35338/10---City-Managers-Office-PDF) | [2026 Strategic Plan](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF)

---

### 5.3 Online Budget Simulator ✅ VERIFIED
Residents can interact with **Master Table data** via an online Budget Simulator, allowing public prioritization of services — a direct application of DGQA-validated data to civic engagement.

**Source:** [Budget Simulator (2025 responses PDF)](https://www.wichita.gov/DocumentCenter/View/34831/2025-Budget-Simulator---All-Responses-PDF) | [Budget & CIP Portal](https://www.wichita.gov/337/Budget-CIP-Documents)

---

## 6. Budgetary & Personnel Findings

### 6.1 Total CMO Budget — $7,102,746 ✅ RESOLVED

The $7,102,746 figure is the **combined budget for three core CMO governance divisions**: City Clerk, Internal Audit, and Project Management (DGQA Oversight). This resolves the discrepancy flagged in v1.0, where the figure was incorrectly attributed to the Project Management division alone.

| Division Grouping | 2026 Adopted |
|---|---|
| City Clerk + Internal Audit + Project Management (DGQA Oversight) | **$7,102,746** |
| Strategic Communications | $1,264,548 |
| Cultural Arts | $7,444,693 |
| Century II Convention Center | $4,989,222 |
| Other CMO divisions | ~$3.2M |
| **CMO Total (all divisions)** | **$19,024,488** |

**Source:** [City Manager's Office Budget, p.165](https://www.wichita.gov/DocumentCenter/View/35338/10---City-Managers-Office-PDF)

---

### 6.2 Senior Project Manager — IT Fund 613 ⚠️ STILL FLAGGED

The research summary cites a Senior Project Manager position reallocated to **IT Fund (Fund 613)** to lead the DGQA initiative. This was not found in official budget documents reviewed:

- CMO Administration authorized positions table: no Senior PM transfer
- IT Department (Fund 600) positions: no Senior PM inbound transfer documented
- Only confirmed transfer: Web Designer (IT → CMO, 2025 Revised Budget)

> ⚠️ **ACTION REQUIRED:** Confirm with CoW client whether this transfer occurred outside the standard budget document, or if the citation [8] refers to a budget amendment or internal HR action not reflected in the Adopted Budget PDFs.

**Source reviewed:** [CMO Budget](https://www.wichita.gov/DocumentCenter/View/35338/10---City-Managers-Office-PDF) | [IT Budget](https://www.wichita.gov/DocumentCenter/View/35259/15---Information-Technology-Department-PDF)

---

### 6.3 Debt Service Fiscal Target ✅ VERIFIED
The 2026 budget maintains the policy benchmark: **Debt Service < 50% of property tax revenue** (policy maximum = 66.7%).

**Source:** [2026 City Manager's Office Budget](https://www.wichita.gov/DocumentCenter/View/35338/10---City-Managers-Office-PDF)

---

## 7. Implications for the Data Lake Project

The Data Lake (Deliverable 3) is the **physical implementation of Strategy 1.5.2** — the mandate for a centralized city data warehouse. The following requirements flow directly from the DGQA framework:

| Requirement | DGQA Source | Design Implication |
|---|---|---|
| **Data Provenance** | DGQA Checklist domain | Must log data origin, transformation steps, and lineage for every dataset ingested |
| **Role-Based Access Control** | DGQA Checklist domain | Must enforce security tier definitions before deployment; align with CMO-PMO Project Charter DGQA section |
| **KPI Dashboard Integration** | Strategy 1.2.2 | Must ingest directly from the Master Table to ensure public-facing metrics match internal strategic performance meeting data |
| **Peer Benchmarking Module** | Peer City Benchmarking (validated) | Architecture must support "plug-and-play" peer comparison against Des Moines, Tulsa, and OKC |
| **Strategy 1.5.2 Compliance** | Centralized Data Warehouse mandate | Data Lake must be registered as a "data component" project and pass the full DGQA checklist |

**Sources:** [2026 Strategic Plan — Strategy 1.5.2](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF) | [Tactic 1.2.1i](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF)

---

## 8. Full Validation Summary

| # | Claim | Status | Source | Link |
|---|---|---|---|---|
| 1 | "Well-Run City" is a 2026 strategic pillar | ✅ VERIFIED | Policy Message | [View](https://www.wichita.gov/DocumentCenter/View/35337/02---City-Managers-Policy-Message-PDF) |
| 2 | Strategy 1.2.1 mandates a DGQA system | ✅ VERIFIED | Strategic Plan, Tactic 1.2.1i | [View](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF) |
| 3 | IT = lead technical agency for DGQA | ✅ VERIFIED | Strategic Plan, Tactic 1.2.1i | [View](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF) |
| 4 | CMO-PMO enforces DGQA citywide | ✅ VERIFIED | Strategic Plan, Tactic 1.2.1i | [View](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF) |
| 5 | DGQA section required in all Project Charter Templates | ✅ VERIFIED | Strategic Plan, Tactic 1.2.1i | [View](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF) |
| 6 | All data-component projects must pass DGQA checklist | ✅ VERIFIED | Strategic Plan, Tactic 1.2.1i | [View](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF) |
| 7 | DGQA Checklist covers Provenance, Access Control, Interconnectivity | ✅ VERIFIED | Strategic Plan, Strategy 1.2.1 | [View](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF) |
| 8 | Strategy 1.2.2 mandates performance management reviews | ✅ VERIFIED | Strategic Plan, Strategy 1.2.2 | [View](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF) |
| 9 | Strategy 1.5.1 prioritizes AI & data analysis training | ✅ VERIFIED | Strategic Plan, Tactic 1.5.1i | [View](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF) |
| 10 | Departmental Data Stewards designated per department | ✅ VERIFIED | Strategic Plan, Strategy 1.2.1 | [View](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF) |
| 11 | Master Table used for budget tier decisions | ✅ VERIFIED | CMO Budget + Strategic Plan | [View](https://www.wichita.gov/DocumentCenter/View/35338/10---City-Managers-Office-PDF) |
| 12 | Online Budget Simulator exposes Master Table data | ✅ VERIFIED | Budget & CIP Portal | [View](https://www.wichita.gov/337/Budget-CIP-Documents) |
| 13 | Total CMO (City Clerk + Audit + PM) = $7,102,746 | ✅ VERIFIED | CMO Budget, p.165 | [View](https://www.wichita.gov/DocumentCenter/View/35338/10---City-Managers-Office-PDF) |
| 14 | Debt service target < 50% of property tax revenue | ✅ VERIFIED | CMO Budget | [View](https://www.wichita.gov/DocumentCenter/View/35338/10---City-Managers-Office-PDF) |
| 15 | Senior PM reallocated to IT Fund 613 | ⚠️ NOT VERIFIED | CMO + IT budget docs reviewed — not found | [CMO](https://www.wichita.gov/DocumentCenter/View/35338/10---City-Managers-Office-PDF) / [IT](https://www.wichita.gov/DocumentCenter/View/35259/15---Information-Technology-Department-PDF) |

---

## 9. Official Source Citations

| Document | Direct Link | Key Content |
|---|---|---|
| 2026 City Manager's Policy Message | [View PDF](https://www.wichita.gov/DocumentCenter/View/35337/02---City-Managers-Policy-Message-PDF) | "Well-Run City" pillar; high-level DGQA commitment |
| 2026 Strategic Plan | [View PDF](https://www.wichita.gov/DocumentCenter/View/35249/03---Strategic-Plan-PDF) | **Primary source** — Tactics 1.2.1i, 1.2.2, 1.5.1i, 1.5.2; DGQA checklist; Data Stewards; KPI framework |
| 2026 City Manager's Office Budget | [View PDF](https://www.wichita.gov/DocumentCenter/View/35338/10---City-Managers-Office-PDF) | CMO division budgets; $7,102,746 governance total; p.165 budget figures; position tables |
| 2026 IT Department Budget | [View PDF](https://www.wichita.gov/DocumentCenter/View/35259/15---Information-Technology-Department-PDF) | IT Fund; authorized positions; Fund 613 search (unverified) |
| 2025 Budget Simulator Responses | [View PDF](https://www.wichita.gov/DocumentCenter/View/34831/2025-Budget-Simulator---All-Responses-PDF) | Resident interaction with Master Table data |
| Budget & CIP Documents Portal | [wichita.gov/337](https://www.wichita.gov/337/Budget-CIP-Documents) | Full index of all 2026 budget chapter PDFs |

---

*End of Discovery Report — v2.0 | Awaiting Human Review*
*One open item: Senior PM / Fund 613 transfer (Section 6.2) — requires client confirmation*
