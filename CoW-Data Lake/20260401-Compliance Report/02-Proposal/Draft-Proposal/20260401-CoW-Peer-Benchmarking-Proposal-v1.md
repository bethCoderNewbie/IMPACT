# Proposal: Peer City & Industry Benchmarking
**Prepared by:** IMPACT Consulting — Barton School of Business, Wichita State University  
**Prepared for:** City of Wichita (CoW)  
**Date:** April 1, 2026  
**Version:** v1 — Draft for Client Review  
**Parent Engagement:** Data Governance Review & System Requirements  
**Feeds Into:** Deliverable 1 (Standards Selection Brief), Deliverable 2 (Data Governance Review Report)

---

## 1. Why This Research Exists

At the kickoff session, CoW asked a direct question: *what are cities like us actually doing?*

That question matters for three reasons:

1. **Standards selection cannot happen in a vacuum.** If we recommend DAMA-DMBOK v2 or Bloomberg What Works Cities certification as CoW's governance framework, CoW needs to know whether comparable cities have walked that path and what it looked like in practice — not just what the framework says on paper.

2. **CoW does not need to solve problems from scratch that other cities have already solved.** The specific challenges CoW faces — data stored on USB drives and local hard drives outside any governed system, and retention schedules that exist on paper but are not enforced — are not unique. Other cities have addressed them. The question is how, how long it took, and what it cost.

3. **Leadership buy-in is easier when there is precedent.** A recommendation grounded in "here is what Austin did and here is what changed" is more actionable than a recommendation grounded in a framework specification alone.

This proposal defines the scope, methodology, and outputs for the peer city and industry benchmarking research CoW requested.

---

## 2. Research Scope

### 2.1 Peer Cities

CoW identified four peer cities for benchmarking. These cities were selected because they are comparable in scale, regional proximity, or governance ambition.

| City | Population | Why Relevant |
|---|---|---|
| **Kansas City, MO** | ~510,000 | Regional peer; known smart city initiative with a data analytics platform (KC Stat); similar Midwest municipal environment |
| **Tulsa, OK** | ~410,000 | Regional peer; operates under Oklahoma state records management framework; useful for retention schedule comparison |
| **Omaha, NE** | ~490,000 | Comparable Midwest city; useful as a low-to-mid maturity baseline for governance program development |
| **Austin, TX** | ~980,000 | National leader in city data governance; Data & Technology Services department has published a data governance framework; frequently cited as a model for other cities |

For each city we will research and document:

| Research Question | Why It Matters to CoW |
|---|---|
| Has the city formally adopted a data governance framework? If so, which one? | Confirms or challenges the DAMA/WWC preliminary recommendation |
| How does the city handle records retention across departments — centralized policy, departmental autonomy, or hybrid? | CoW has 22 departments with inconsistent retention practices; peer models show what has worked |
| What is their data storage and analytics environment — cloud, on-prem, hybrid? What platforms do they use? | Informs CoW's data lake technology decision |
| Have they published a data governance maturity assessment or open data policy? | Provides a benchmark against which to position CoW's current state |
| What governance gaps did they start with, and how did they close them? | Shows the improvement trajectory CoW can expect |
| What organizational structure supports governance — is there a Chief Data Officer, a Records Management Office, or a distributed coordinator model? | Compares to CoW's City Clerk and 30+ coordinator structure |

---

### 2.2 Professional Associations

CoW asked what frameworks professional associations recommend for cities. We will research two organizations specifically named at the kickoff session.

#### International City/County Management Association (ICMA)

ICMA is the primary professional body for local government managers in the United States, with over 13,000 members across city, county, and regional governments.

| Research Question | Why It Matters to CoW |
|---|---|
| What data governance guidance does ICMA publish for local governments? | Establishes what the profession considers baseline practice |
| Does ICMA endorse or reference any specific governance framework (DAMA, ISO, NIST, or other)? | Informs standards selection |
| What does ICMA say about records management, metadata standards, and retention enforcement for municipalities? | Maps directly to CoW's 10 governance domains |
| Are there ICMA case studies of cities that have built governance programs from a low-maturity baseline? | Provides implementation precedent for CoW |

#### Bloomberg Philanthropies — What Works Cities (WWC)

Bloomberg What Works Cities is a certification program that helps cities use data and evidence effectively. WWC Certification is held by cities including Los Angeles, Atlanta, Boston, Denver, and over 100 others. The program includes a Data Governance Standard with explicit criteria.

| Research Question | Why It Matters to CoW |
|---|---|
| What are the specific Data Governance criteria in the WWC Standard? | Maps directly to CoW's gap domains — determines whether WWC is a viable primary framework |
| Which certified cities are comparable in size or region to Wichita? | Provides peer precedent for WWC adoption |
| What does it take for a city to achieve WWC Certification — timeline, resources, and organizational change? | Helps CoW assess feasibility |
| Does WWC Certification align with DAMA-DMBOK, ISO 8000, or other frameworks, or does it stand alone? | Determines whether pursuing WWC requires choosing between frameworks or allows combination |
| Has any Kansas or Midwest city pursued WWC Certification? | Establishes regional precedent |

---

### 2.3 Common Challenges

CoW specifically asked how other cities have solved two operational problems that mirror their own situation. These are the most practically valuable research questions in this engagement.

#### Challenge 1 — Data on USB Drives and Local Hard Drives

CoW's records exist in Laserfiche Cloud, in 45 Excel-based data management lists, and — to an undocumented extent — on USB drives, personal hard drives, and shared network drives outside any governed system. This is a records compliance risk and a governance gap that cannot be closed through policy alone if ungoverned copies continue to exist.

| Research Question | Output |
|---|---|
| How have peer cities detected the scope of their shadow data problem — what inventory methods did they use? | A detection methodology CoW can adapt |
| What policy instruments did they use to prohibit ungoverned storage — IT policy, AUP, HR policy, or records ordinance? | A policy template or model language CoW can reference |
| How did they handle the transition — was there an amnesty window for migrating existing shadow data, or was enforcement immediate? | A migration approach CoW can adopt or adapt |
| What technology did they use to enforce centralized storage — DLP tools, endpoint management, or purely administrative controls? | A technology options list for CoW's IT team |
| How long did it take from policy adoption to measurable compliance, and what did the change management look like? | A realistic timeline expectation for CoW leadership |

#### Challenge 2 — Missing or Unenforced Retention Schedules

CoW has 33 retention periods and 8 cutoff triggers defined in its data management lists, but the legal citation source for those schedules has not been confirmed, enforcement automation in Laserfiche is unverified, and no disposition approval workflow is documented. The retention framework exists on paper but does not function operationally.

| Research Question | Output |
|---|---|
| How have peer cities rebuilt or formalized retention schedules when starting from an inconsistent or undocumented baseline? | A remediation approach CoW can adapt |
| What is the typical source of authority for a municipal retention schedule — state law, city charter, City Clerk policy, or a combination? | Confirms or challenges how CoW should anchor its retention framework legally |
| How have cities automated retention enforcement in document management platforms — what triggers, workflows, and approval steps do they use? | A Laserfiche workflow design reference for CoW's IT team |
| How did cities handle the transition period — records filed before the governance program existed that have no retention metadata? | A legacy records remediation strategy |
| What role did the City Clerk, Legal Department, and IT play in building the retention enforcement system? | Defines the organizational model CoW needs to replicate |

---

## 3. Research Methodology

### 3.1 Primary Sources (Weeks 2–3, Concurrent with Stakeholder Interviews)

| Method | Target | Purpose |
|---|---|---|
| Published governance documents | Austin DTS, Kansas City IT, ICMA, Bloomberg WWC | Framework adoption, policy language, maturity models |
| Open data portals and city websites | All four peer cities | Published data policies, governance charters, retention schedules |
| ICMA publications and knowledge base | ICMA Center for Management and Technology | Professional guidance and case studies |
| Bloomberg WWC Standard documentation | Bloomberg Philanthropies | Certification criteria and city profiles |
| Direct outreach (if time permits) | IT or records management contacts at peer cities | Confirmation of unpublished practices |

### 3.2 Secondary Sources

| Source | Purpose |
|---|---|
| Academic and practitioner literature on municipal data governance | Supports framework evaluation with independent evidence |
| State of Kansas records management guidelines | Legal basis for CoW's retention obligations |
| National League of Cities and Government Finance Officers Association publications | Additional professional association guidance |

### 3.3 Limitations

- Peer city research relies primarily on publicly available documents. Practices not published online may not be captured unless direct outreach is successful.
- Research is conducted in Weeks 2–3 concurrently with stakeholder interviews. Depth is constrained by the 6-week engagement timeline.
- Findings reflect the state of each city's published governance program as of April 2026. Programs may have evolved since their most recent publication.

---

## 4. Output Structure

Peer city and industry benchmarking findings will appear in two places:

### In Deliverable 1 (Standards Selection Brief) — due May 16

A dedicated **Peer City Benchmarking** section presenting:
- One summary row per peer city: governance framework adopted, maturity level, key practices
- ICMA guidance summary: what the profession recommends for municipalities at CoW's stage
- Bloomberg WWC summary: certification criteria, comparable certified cities, feasibility assessment for CoW
- How the peer findings informed the standards recommendation

### In Deliverable 2 (Data Governance Review Report) — due May 16

A dedicated **How Peer Cities Solved It** callout per relevant governance domain, showing:
- The specific challenge domain (e.g., retention enforcement, shadow data)
- What at least one peer city did
- What CoW can adapt from that approach
- Estimated effort and timeline based on peer city experience

---

## 5. What We Need From CoW to Complete This Research

| Item | Purpose | Deadline |
|---|---|---|
| Confirmation of which peer cities matter most to CoW leadership | Allows us to prioritize depth of research if time is constrained | Week 1 kickoff call |
| Any existing relationships CoW has with peer city IT or records staff | Enables direct outreach for unpublished practices | Week 1 |
| CoW's awareness of whether any peer city has already been through a Laserfiche governance implementation | Directly relevant to both challenge areas | Week 1 kickoff call |
| Confirmation of whether CoW leadership has heard of or is interested in Bloomberg What Works Cities certification | Determines how much depth to give WWC research | Week 1 kickoff call |

---

## 6. Timeline

| Week | Benchmarking Activity |
|---|---|
| **Week 1** (Apr 7–11) | Confirm peer city priorities with CoW; begin document collection from public sources |
| **Week 2** (Apr 14–18) | Deep research on Austin and Kansas City; ICMA publication review; Bloomberg WWC Standard review |
| **Week 3** (Apr 21–25) | Research on Tulsa and Omaha; challenge-specific research (USB drives, retention schedules); draft benchmarking section of Deliverable 1 |
| **Week 4** (Apr 28–May 2) | Peer city "How They Solved It" callouts drafted for Deliverable 2; benchmarking section finalized for Deliverable 1 |
| **May 16** | Benchmarking findings included in Deliverable 1 (Standards Selection Brief) delivered to CoW alongside Deliverables 2 and 3 |

---

*IMPACT Consulting — Barton School of Business, Wichita State University*  
*City of Wichita Data Governance & Data Lake Engagement — April 2026*  
*Document: `02-Proposal/Draft-Proposal/20260401-CoW-Peer-Benchmarking-Proposal-v1.md`*
