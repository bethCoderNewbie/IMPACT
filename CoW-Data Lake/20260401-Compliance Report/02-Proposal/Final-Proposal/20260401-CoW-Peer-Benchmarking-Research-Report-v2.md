# Peer City & Industry Benchmarking Research Report
**Prepared by:** IMPACT Consulting — Barton School of Business, Wichita State University
**Prepared for:** City of Wichita (CoW)
**Date:** April 2, 2026
**Version:** v2 — Expanded to all 10 governance domains; framework confirmation corrected; cross-city comparison matrices added
**Feeds Into:** Deliverable 1 (Standards Selection Brief) · Deliverable 2 (Data Governance Review Report)

---

> **Disclaimer:** This report is based on publicly available information gathered as of April 2026. It does not represent the official positions of any city government, professional association, or certification body cited. Findings have not been independently verified through direct contact with peer city staff. Where information could not be located in public sources, this is stated explicitly rather than inferred or assumed. **Direct outreach to peer city staff is scheduled for Week 1 of the engagement; findings from that outreach will supplement this document in a subsequent version.**

---

> **What Changed from v1 to v2:** Six primary source documents published after v1's research window — Tulsa COP 1400 (February 26, 2026), Tulsa Data Governance Manual, Tulsa Enterprise IT Security Policy Manual (March 2025), Tulsa EO 2019-08, Kansas City 2025 Data Governance Charter (July 1, 2025), and Kansas City Data Service Standard (October 7, 2025) — were retrieved and incorporated. v2 adds domain-specific findings for all 10 governance domains, corrects the DAMA attribution for Austin, and adds two new sections: a Domain-by-Domain Peer Benchmarking Matrix (Section 4) and a Cross-City Comparison — What CoW Can Directly Borrow (Section 5).

---

## Executive Summary

At the kickoff session, the City of Wichita asked: *what are cities like us actually doing?*

We researched four peer cities and two professional organizations across all 10 governance domains CoW is being assessed on. Here is what the updated research found:

**Tulsa is the most complete governance model for Wichita — across all 10 domains, not just retention.** In February 2026, Tulsa published COP 1400, a four-tier data classification policy covering Public, Internal, Sensitive, and Protected data. It defines an explicit approval chain for sensitive and protected data access that mirrors exactly what CoW needs for CJIS and HIPAA-adjacent records. Combined with Tulsa's 2019 Data Governance Manual and its four-role stewardship structure, Tulsa has solved — in published, replicable policy documents — nearly every governance gap CoW faces.

**Kansas City's 2025 Charter supersedes the 2014 version.** Kansas City published a new Citywide Data Governance Charter on July 1, 2025, which formalizes a CDO role derived from City Code, names six Governance Committee members, and defines a four-tier data classification schema. A companion Data Service Standard (October 2025, adapted from the UK Government Digital Service framework) establishes metadata requirements and open standards mandates. These are materially more useful for CoW than the 2014/2015 charter cited in v1.

**None of the four peer cities formally adopt DAMA-DMBOK v2.** This is the most significant correction from v1. Austin builds on its 2013 Open Government Directive and Texas statutes. Kansas City uses a custom charter plus a UK GDS-adapted Data Service Standard. Tulsa uses a series of executive orders. Omaha has no formal program. If CoW adopts DAMA, it would be differentiated from all four peers. The peer evidence supports a custom-framework approach — policy enacted through executive order, using DAMA as an internal implementation guide rather than as a formal external standard.

**No published RACI matrix exists at any peer city.** RACI development is not a gap unique to Wichita — it is a gap across all four peer cities. Tulsa and Kansas City define governance roles clearly in policy; neither labels those definitions a "RACI."

**Wichita's opportunity is unchanged:** No Kansas city holds Bloomberg What Works Cities Certification. Wichita can be the first.

---

## Section 1: Peer City Findings

### At a Glance

| City | Governance Framework | Classification Schema | Stewardship Structure | Retention Model | Key Platform | Bloomberg WWC |
|---|---|---|---|---|---|---|
| **Austin, TX** | Custom (Open Government Directive, 2013) | Contract-only: Public / Non-Public | Open Data Liaisons (per dept) + Records Custodians | Hybrid — City Clerk oversight + dept custodians | Tyler/Socrata; Austin Technology Services | Not found in public sources |
| **Kansas City, MO** | Custom charter (2014, updated July 2025) + UK GDS-adapted Data Service Standard (Oct 2025) | 4-tier: Public / Private / Sensitive / Confidential | CDO (City Code 2-2133) + named Governance Committee (6 members) + Data Owners + Data Stewards | Missouri General Records Retention Schedule (state-mandated) | AWS + on-premises; Open Data KC portal | Gold |
| **Tulsa, OK** | Custom executive orders (2015, 2018, 2019) + COP 1400 (2026) | 4-tier: Public / Internal / Sensitive / Protected | Data Manager (OPSI) + DGC Members (one per dept) + Data Stewards + Data Users | Oklahoma Title 67 Records Management Act | Central Data Repository + ArcGIS Open Data | Silver |
| **Omaha, NE** | None found | None found | No CDO; no formal governance office | Nebraska SOS schedules only | DOTComm shared IT + DOGIS (GIS only) | Not certified |
| **Des Moines, IA** | Pending research | Pending research | Pending research | Iowa Code Chapter 304 (state records management) | Pending research | Pending research |
| **Denver, CO** | Pending research | Pending research | Pending research | Colorado statutes (CRS Title 24, Art. 80) | Pending research | Pending research |

> **Scope update — April 2026 client meeting:** CoW confirmed its official peer city list comes from the city budget book. Des Moines, Iowa and Denver, Colorado are on that official list and were not included in the original v2 research scope. Fort Worth, Texas was also mentioned as a possible peer (used for grants system comparisons). Research on Des Moines and Denver is scheduled for Week 1 direct outreach. Findings will be incorporated into a v3 update prior to Deliverable 1 drafting.

---

### Austin, Texas

Austin published its Open Government Directive in August 2013, making it one of the earlier cities to formally commit to data governance in writing. Rather than adopting a national framework like DAMA or NIST, Austin built a custom approach grounded in its Open Government Directive and Texas statutes (TPIA, Texas Business & Commerce Code Chapter 521, and Texas HB 149/TRAIGA effective January 2026).

**Data classification:** Austin does not have a standalone citywide data classification policy. Its most explicit classification language appears in Standard Terms and Conditions for city contracts (updated 2025), which defines a two-tier operational distinction:
- **Public** — releasable data
- **Non-Public Data** — "data typically considered internal and used for city business or mission needs; all information is considered Non-Public unless specifically designated otherwise"

Non-public data must be encrypted at rest and in transit under contract terms. Austin Technology Services confirmed in December 2025 that its Information Security Policy is being updated, but no published update was found as of April 2026.

**How retention works:** Austin uses a hybrid model. The City Clerk's Office sets centralized policy and compliance oversight. Individual departments are responsible for managing their own records under those rules, guided by the Texas State Library's Local Government Retention Schedules. Each department has a designated Records Custodian.

**How governance is organized:** Austin does not have a city-level Chief Data Officer. Governance is distributed through an Enterprise Open Data Platform Team (within Austin Technology Services) and Open Data Liaisons assigned to each department. This is a coordinator model rather than a centralized one.

**Metadata standards:** Austin's open data portal (data.austintexas.gov) uses a structured field set (Department, Publication Stage, Audience, Type, Category, timestamps). For permit data specifically, Austin has adopted the BLDS (Building & Land Development Specification), a national open standard for permit datasets — demonstrating domain-specific metadata commitment. No citywide metadata schema has been published.

**Problem they solved:** In 2023, Austin publicly acknowledged widespread data reliability issues — different departments publishing conflicting and outdated information. They responded by upgrading to a new Enterprise Data Platform through Tyler Technologies. The lesson: data quality problems that compound across departments eventually require a costly system-wide fix.

**Framework:** Austin does not formally adopt DAMA-DMBOK v2. Earlier project documentation stated Austin "references DAMA principles" — this was not confirmed in primary source documents. Austin's governance framework is custom-built around its Open Government Directive and Texas statutes.

**What CoW can take from Austin:** Departmental accountability works when backed by clear central policy. The Open Data Liaison model — one designated person per department — is a practical starting structure. The 2023 data reliability incident is a direct precedent for CoW's current 609-issue metadata problem: unresolved quality issues will compound and eventually require expensive remediation.

*Sources: Austin Open Government Directive (opendatapolicyhub.sunlightfoundation.com/collection/austin-tx-2013-08-26/); Austin Technology Services (austintexas.gov/department/information-technology); Austin Open Data Portal (data.austintexas.gov); Austin Standard Contract Terms (services.austintexas.gov/edims/document.cfm?id=469093); Austin data reliability issues (communityimpact.com, July 2023)*

---

### Kansas City, Missouri

Kansas City has one of the most developed data governance programs among comparable Midwest cities. It started with an Open Data ordinance in 2014, updated it in 2015, and has continued evolving. The most significant update — a new Citywide Data Governance Charter effective July 1, 2025 — was not captured in v1 of this report. It materially changes what CoW can learn from Kansas City.

**Data classification (2025 charter — new):** Kansas City's 2025 Charter defines four data information types:

| Type | Description | Sensitivity |
|---|---|---|
| Public | Freely available: news releases, meeting minutes, financial reports | None |
| Private | Individual info not critical to government ops: resident names, phone numbers, voter registration | Low |
| Sensitive | Moderate consequences if exposed: aggregate public health data, employee salaries, accident reports with identifiable individuals | Medium |
| Confidential | Severe consequences if exposed: crime data, pending legislation, law enforcement investigations, HIPAA/PHI individual-level health data | High |

This four-tier model is directly comparable to Tulsa's and provides a practical reference for CoW's Domain 1 gap.

**How governance is organized (2025 charter):** Kansas City's CDO role is now formally derived from City Code Section 2-2133 — it is not just a job title, it is a statutory position. The CDO is responsible for: developing the governance framework; ensuring compliance citywide; coordinating between departments; managing data risk; maintaining data quality; and providing training. The 2025 Governance Committee includes:

| Department | Representative | Title |
|---|---|---|
| City Manager's Office | LaDonna McCullough | Chief Equity Officer |
| City Manager's Office | Andrew Ngui | Chief Digital Officer |
| DataKC/Neighborhoods | Alec Sithole | Chief Data Officer |
| Health Department | Alex Francisco | Chief Science Officer |
| IT/General Services | Michael Newhouse | CTO & CISO |
| Law Department | Matthew Gigliotti | City Attorney |

Below the committee: **Data Owners** (department/agency leaders; accountable for accuracy and protection of their department's data) and **Data Stewards** (department reps; day-to-day quality, security, and compliance; maintain data inventories; represent department in citywide governance activities).

**Data Service Standard (October 2025 — new):** Kansas City published a 16-principle Data Service Standard adapted from the UK Government Digital Service (GDS) framework. Relevant principles for CoW:
- Principle 5: Ensure "clear, descriptive metadata for datasets"
- Principle 11: Identify and address security threats; process user data securely; test for vulnerabilities regularly
- Principle 13: Choose tools that allow flexibility and legacy system integration
- Principle 14: All new source code and data must be published openly; retain intellectual property for government-funded work
- Principle 15: Use and contribute to open standards; avoid vendor lock-in

**How retention works:** Kansas City follows the Missouri General Records Retention Schedule, published by the Missouri Secretary of State's Records Management Division. This is state-mandated baseline for all Missouri local governments.

**Framework:** Kansas City does not formally adopt DAMA-DMBOK v2. Its governance framework is custom: the Data Governance Charter governs structure and accountability; the Data Service Standard (adapted from UK GDS) governs open data and service practices. Neither document references DAMA, ISO 8000, or NIST as the parent framework.

**Bloomberg certification:** Kansas City holds Gold Certification. Earning Gold required: a written governance charter, a cross-departmental governance committee, a comprehensive data inventory, and the CDO role established by ordinance.

**What CoW can take from Kansas City:** The 2025 charter's four-tier classification model is directly adaptable. The committee structure — CDO + cross-department Governance Committee with defined Data Owners and Data Stewards — is the most realistic structural model for a city without a large budget for a new department. The Data Service Standard provides a principled metadata and open standards framework that complements whatever primary governance standard CoW adopts.

*Sources: Data Governance Charter 2025 (data.kcmo.org/download/fuiv-g28p/application%2Fpdf); Data Service Standard Oct 2025 (data.kcmo.org/download/8z2m-bfwe/application%2Fpdf); Open Data Policy (opendatapolicyhub.sunlightfoundation.com); DataKC Program (kcmo.gov); Kansas City on AWS (aws.amazon.com/solutions/case-studies/kansas-city/); Missouri SOS Records Management (sos.mo.gov/records/recmgmt)*

---

### Tulsa, Oklahoma

Tulsa is the most directly adaptable model for Wichita — and the most fully documented. v1 covered Tulsa's OPSI structure and Bloomberg Silver certification. v2 adds three additional primary documents (COP 1400, EO 2019-08, and the Data Governance Manual) that provide Tulsa's explicit policies across nearly every governance domain CoW is being assessed on. The City of Tulsa's governance program is built through a series of executive orders and corporate operating policies enacted between 2015 and 2026, not through adoption of a named external framework.

**How governance was built (timeline):**
- **December 21, 2015** — Executive Order establishes the city's data governance commitment (EO 2015-XX, later superseded)
- **February 14, 2018** — EO 2018-03 establishes three-tier data disclosure framework (Public, Sensitive, Protected) and five-level Impact Risk scale
- **2019** — Office of Performance, Strategy and Innovation (OPSI) created within the Finance Department
- **December 1, 2019** — EO 2019-08 establishes comprehensive data governance policy with four formal roles
- **February 26, 2026** — COP 1400 replaces EO 2018-03; updates to four-tier classification, adds Internal tier, formalizes DGSC oversight

**Domain 1 — Data Classification (COP 1400, 2026):**

Four disclosure tiers:

| Tier | Description | Sharing Rule |
|---|---|---|
| Public | No protection required; freely shareable inside and outside city | No approval required |
| Internal | Business/financial/personnel data not under legal protection: draft budgets, HR communications, vendor evaluations, in-progress grant applications | Not shared outside originating department without approval |
| Sensitive | Emergency management, public safety, infrastructure data, PII | Director or Director's Designee must approve sharing outside department; DGSC approval required for external sharing |
| Protected | Legally mandated safeguards: PHI (NIST SP 800-66 Rev 1), CJI (FBI CJIS Security Policy), state evidentiary privilege | Legal Department AND DGSC (and/or Chair) must approve; "used only when no alternative exists" |

Default classification: **Public**, unless specifically classified otherwise. Classifying Authority chain: Mayor → Department Directors → delegated Data Stewards (delegation requires written documentation and mandatory training). Data Governance Steering Committee (DGSC) provides uniform guidance, resolves disputes, and approves any sharing of Protected data outside the organization.

**Domain 2 — File Naming & Metadata (Data Governance Manual, 2019):**

The Data Provenance Policy requires that before any dataset is added to the Central Data Repository, it must be: classified by disclosure tier, organized within the appropriate folder structure, and have its metadata documented through the Data Governance Review Process. An automated ETL process saves a log of all changes between the source system and the repository, creating a full provenance chain. No specific metadata field schema was found in public documents; the requirement is that metadata be documented, not how many fields or which fields.

**Domain 3 — Records Coordinators / Stewardship (EO 2019-08 + Data Governance Manual):**

Four formal governance roles:

| Role | Location | Authority | Key Responsibilities |
|---|---|---|---|
| Data Manager | OPSI, Finance Dept | Chairs Data Governance Committee; all-city data access; subject to published ethical code | Sets citywide data vision; manages governance policy; maintains SLAs between departments; final decision authority on escalated data requests |
| Data Governance Committee Member | One per department (max) | Reviews and votes on data requests within 2 business days; operates via automated workflow | Approves or denies data requests within their department's domain |
| Data Steward | Department-level | Department's data point of contact | Sets departmental expectations for classification, analytics, provenance, quality; 2-day review window on requests before escalation |
| Data User | Any staff or resident | Consumer of city data | Submits data requests through formal channel |

**Domain 4 — Stakeholder Roles / RACI:**

No document is labeled "RACI," but the governance manual creates a functional responsibility assignment: Data Steward is Responsible (initial 2-day review); Data Manager is Accountable (escalation, final decision); DGC Members are Consulted (majority vote determines approval); Data Users are Informed. Classification authority delegation is documented in writing and requires training completion. Tulsa's practice demonstrates that explicit role definitions in a governance manual function equivalently to a RACI even without using that label.

**Domain 5–6 — Retention Schedules & Enforcement:**

Tulsa follows the Oklahoma Records Management Act (Title 67, Oklahoma Statutes), which requires local governments to manage records using the state's General Records Disposition Schedules. The Oklahoma Department of Libraries provides the schedules and guidance. (Same structure as v1 — retained here for completeness.)

**Domain 7 — Access Control (Data Governance Manual + COP 1200 IT Security Policy, March 2025):**

Tulsa uses a three-tier Active Directory hierarchy for all governed data:
1. **Data Classification Folder** — three top-level folders (Public, Sensitive, Protected), each with its own independent AD security group
2. **Department Folder** — datasets broken out by owning department within the classification tier
3. **Application Folder** — each application has its own folder and security group; datasets labeled by unique identifier

Access request process: Employee submits request to supervisor and their department Data Steward → approved request forwarded to IT → IT adds user to the correct AD group. AD group memberships are periodically reviewed and audited by IT Security.

The Enterprise IT Security Policy Manual (COP 1200, Version 2024.5, March 2025) governs all access modes (on-premises, remote, and cloud). The CIO has overall security responsibility. The IT Security Manager produces implementation guidelines. A Technology Security Committee operates under the Technology Governance Board's authority. Annual audit cycle.

**Domain 8 — Sensitive Data Access Workflow (COP 1400, 2026):**

COP 1400 establishes explicit approval workflows by classification tier:
- **Sensitive data:** Department Director or designated Director's Designee must approve use outside the originating department; DGSC must approve any external sharing
- **Protected data (CJI, PHI, legally privileged):** Legal Department AND the DGSC Chair (or full DGSC) must approve any sharing outside the organization; Protected data is "used only when no alternative exists"
- **Technical segregation:** Sensitive and Protected data are held in separate AD folders from Public data; the classification tier physically determines the access group

This is the only published city-level sensitive data workflow found in all four peer cities. It directly addresses CoW's need for CJIS (Police Department) and HIPAA-adjacent (Community Services, Housing) record handling.

**Domain 9 — Data Export & System Connections (Data Governance Manual, 2019):**

The Data Integration Policy requires that before purchasing any new software application, the following data sovereignty questions must be formally answered:
- Will the data generated by this application be needed for analytics?
- Will the database integrate with city systems?
- Will the city own the data?
- Can the city download all raw data? How frequently?

This pre-purchase governance gate is a direct control over vendor lock-in and data export rights. The Data Provenance Policy's automated ETL requirement also creates an auditable chain from source systems to the Central Data Repository.

**Domain 10 — Governance Adoption & Change Management:**

**Urban Data Pioneers** is Tulsa's primary adoption program — cross-functional teams of city staff and community volunteers who use city data to solve civic problems. At least seven cohorts have been organized. Published outcomes: 70% reduction in 911 calls from repeat utilizers; 63% improvement in fine payment compliance through targeted outreach. The program is recognized as a national model by Cities of Service (Johns Hopkins University). The program's mission statement emphasizes building a "learning culture" around data stewardship.

**Mandatory training for classification authority:** Under COP 1400, no employee may be delegated classification authority without completing required training. This creates an automatic link between governance responsibility and demonstrated competency.

**Data Analytics Self-Service Policy:** Dashboards must be validated against "known good reports" before publishing. Data quality issues are submitted via form to the Governance Committee and routed to the responsible department's Data Steward.

**Bloomberg certification:** Tulsa holds Silver Certification. The path to Silver required: a formal governance policy (executive order), a governance committee, and a Central Data Repository — none of which required a large team.

**What CoW can take from Tulsa:** Tulsa's COP 1400 four-tier classification model is the single most directly reusable document in this entire research report. It addresses Domain 1 (classification), Domain 8 (sensitive data workflow), and portions of Domain 7 (access control) in a single policy that CoW could adapt with moderate legal and IT review. The four-role stewardship structure (Data Manager, DGC Members, Data Stewards, Data Users) maps cleanly onto CoW's existing structure: a governance manager, 22 department representatives, 30+ records coordinators, and city staff.

*Sources: COP 1400 Data Classification Policy (cityoftulsa.org/media/30101/1400-cop-data-classification-final-eff-02252026.pdf); EO 2018-03 (cityoftulsa.org/media/6655/2018-03.pdf); EO 2019-08 (cityoftulsa.org/media/11918/2019-08.pdf); Data Governance Manual (cityoftulsa.org/media/11876/data-governance-manual.pdf); Enterprise IT Security Policy Manual COP 1200 (cityoftulsa.org/media/27549/cop-1200-enterprise-it-security-policy-manual-032025.pdf); Urban Data Pioneers Mission (cityoftulsa.org/media/7026/udpmission.pdf); Cities of Service Urban Data Pioneers (citiesofservice.jhu.edu/resource/urban-data-pioneers-tulsa/); Tulsa WWC Silver Certification (cityoftulsa.org); Oklahoma Title 67 (oksenate.gov); Oklahoma Records Management (oklahoma.gov/libraries/archives-and-records)*

---

### Omaha, Nebraska

> **Baseline comparison — cautionary context**
>
> Omaha is included as a peer-sized Midwest city that has not built a formal governance program. It did not appear in research for any of the 10 governance domains. No published governance policy, no CDO, no formal retention program beyond Nebraska SOS state schedules. IT services are shared with Douglas County via DOTComm. The most structured governance function documented is DOGIS — limited to geospatial data only. A 1982 University of Nebraska assessment found Omaha's data systems "neither coordinated nor comprehensive" and lacking "clear policy direction." There is no public evidence this has fundamentally changed.
>
> **What CoW can take from Omaha:** The risk of inaction compounds over decades without governance policy and executive sponsorship. Shared infrastructure provides economies of scale but does not substitute for governance authority.
>
> *Sources: Nebraska SOS Records Management (sos.nebraska.gov/records-management-division); DOGIS Open Data Portal (data.dogis.org); DOTComm Services (dotcomm.org); Historical Omaha data assessment, UNO (digitalcommons.unomaha.edu/cparpubarchives/153/)*

---

## Section 2: Professional Association Findings

### International City/County Management Association (ICMA)

ICMA is the primary professional body for local government managers in the United States, with over 13,000 members. It publishes guidance on becoming a data-driven local government but does not endorse or mandate a specific governance framework such as DAMA, NIST, or ISO.

**What ICMA recommends for cities at CoW's stage:**
- Develop a written data governance policy
- Identify an executive sponsor (City Manager or equivalent) to champion the effort
- Involve the staff who actually work with the data — not just IT and leadership
- Start with performance management: define what you want to measure, ensure data quality, and use findings for decisions

**What ICMA does not provide:** ICMA does not publish dedicated records management or metadata standards for municipalities. Its guidance is strongest on organizational change, executive sponsorship, and performance measurement — not on technical retention enforcement or document management configuration.

**What this means for CoW:** ICMA validates the importance of executive sponsorship and written policy as the essential starting conditions. Its materials are useful for building internal understanding and the case for governance investment, but they do not provide a technical framework.

*Sources: ICMA publications (icma.org/articles/article/using-data-improve-local-government-decision-making); ICMA webinars (icma.org/local-gov-data-free-webinar-series); ICMA Technology Management Institute (icma.org/technology-management-institute)*

---

### Bloomberg Philanthropies — What Works Cities (WWC) Certification

Bloomberg's What Works Cities program is a certification that helps cities demonstrate they use data effectively. It is operated in partnership with Results for America and supported by the Bloomberg Center for Government Excellence (GovEx) at Johns Hopkins University.

**How certification works:**
- Cities complete a self-assessment against 43 criteria organized into 8 practice areas
- Scoring: Silver = 51–67% of criteria met; Gold = 68–84%; Platinum = 85%+
- Cities receive a customized roadmap identifying strengths and gaps
- GovEx provides coaching, technical assistance, and implementation support

**Domain mapping — Which of CoW's 10 governance domains align to WWC practice areas:**

| CoW Governance Domain | WWC Practice Area | Relevant Criterion |
|---|---|---|
| Domain 1: Data Classification Schema | Data Management | "Protecting Data Privacy and Confidentiality" |
| Domain 2: File Naming & Metadata Standards | Data Management | "Maintaining a Comprehensive Data Inventory"; "Improving Data Quality"; "Data Service Standard" |
| Domain 3: Records Coordinators / Data Stewards | Leadership and Capacity | "Data Leadership"; "Data Workforce Culture and Trainings" |
| Domain 4: Stakeholder Roles / RACI | Leadership and Capacity + Data Management | "Executive Commitment to Data-Informed Government"; "Implementing Data Strategy and Governance" |
| Domain 5: Retention Schedules | Data Management | "Implementing Data Strategy and Governance" |
| Domain 6: Retention Enforcement | Data Management | "Improving Data Quality"; "Implementing Data Strategy and Governance" |
| Domain 7: Access Control Model | Data Management | "Managing Data Security" |
| Domain 8: Sensitive Data Workflow | Data Management | "Protecting Data Privacy and Confidentiality" |
| Domain 9: Data Export & System Connections | Open Data | "Open Data Policy"; "Open Data Portal"; "User Guidance for Open and Shared Data" |
| Domain 10: Governance Adoption & Change Management | Leadership and Capacity | "Data Workforce Culture and Trainings"; "Data Leadership"; "Executive Commitment" |

**Note:** Bloomberg does not publish scoring rubrics for individual criteria. The criterion names and practice areas are publicly available; what earns a point on each criterion is only disclosed to cities completing the formal assessment through the Results for America portal.

**What would CoW need to pursue Silver?**
- A written governance policy (ordinance or executive order)
- A data inventory across departments
- Cross-departmental governance coordination (committee or designated leads)
- An open data portal or equivalent transparency mechanism
- Performance analytics capability tied to city priorities

**As of April 2026, no Kansas city holds WWC Certification.** CoW has prior engagement with the WWC program — it was a past participant and, per the April 2026 client meeting, staff were just assigned to complete re-enrollment. If re-enrollment is completed, CoW would be positioned to immediately pursue formal certification assessment. No Kansas city holds WWC Certification, so Wichita would be the first. Kansas City's path to Gold and Tulsa's Silver both show this is achievable for mid-size Midwest cities without a large budget or new department.

*Sources: WWC Assessment (whatworkscities.bloomberg.org/assessment/); Bloomberg Philanthropies WWC overview (bloomberg.org); WWC Cities Directory (whatworkscities.bloomberg.org/cities/); GovEx About (govex.jhu.edu/about/); Norfolk WWC Certification (norfolk.gov/5131/What-Works-Cities-Certification)*

---

## Section 3: How Peer Cities Solved CoW's Two Core Problems

### Problem 1 — Data Stored Outside Governed Systems (USB Drives, Local Hard Drives)

CoW has records stored in Laserfiche Cloud and in 45 Excel-based department lists — but also, to an unknown extent, on USB drives, personal hard drives, and shared network folders outside any governed system.

**Why it matters:**
Industry data shows that 1 in 3 data breaches involve "shadow data" — records outside governed systems. The average cost of a breach involving shadow data is $4.88 million (Cyberhaven, 2026). For a public agency, the risk is also legal: records outside governed systems cannot be subject to retention enforcement, cannot be produced in litigation, and may violate public records law.

> *Scope note: The figures above reflect enterprise-wide industry data across all sectors and organization sizes. No equivalent published benchmark exists specifically for mid-size municipal governments. They are cited to establish order-of-magnitude risk. CoW's actual exposure depends on the scope of ungoverned storage — which has not yet been assessed. See Section 7, Recommended Next Step 4 for the proposed shadow data survey.*

**How peer cities address this:**

**Tulsa's approach** — The Data Provenance Policy requires that any data used for decision-making be accessed through the Central Data Repository. Before data enters the repository, it must be classified and have its metadata documented. The procurement gate (Data Integration Policy) prevents future ungoverned data pockets by requiring data sovereignty answers before any new software purchase. These two controls — inflow governance and procurement gate — work together: existing ungoverned data gets pulled into the CDR; future shadow data is prevented at procurement.

**The general remediation sequence (from industry research):**

Step 1 — **Audit the scope.** Inventory what shadow data exists and where — manually (department surveys) or through IT tools scanning network drives and endpoints.

Step 2 — **Publish a removable media policy.** Establishes that USB drives and local hard drives are not authorized storage for city records. Defines approved tools and consequences for non-compliance.

Step 3 — **Deploy monitoring before enforcement.** Log what data moves where before blocking. Builds a picture of actual behavior and makes subsequent policy enforcement defensible.

Step 4 — **Move to technical enforcement.** Device whitelisting, endpoint management policies, and Data Loss Prevention (DLP) tools.

**Technology options:**
- **Microsoft Purview Endpoint DLP** — Most practical for CoW given existing Microsoft 365 environment. Integrates with Windows, enforces policies across devices, logs all file movement activity. (learn.microsoft.com/en-us/purview/endpoint-dlp-learn-about)
- **CrowdStrike DLP** — Enterprise-grade endpoint protection with DLP capabilities
- **ManageEngine Endpoint DLP Plus** — Mid-market option with strong policy management

**Note:** No public case studies documenting a specific city's amnesty window or migration timeline from shadow data to governed storage were found. Direct outreach to peer city IT staff (scheduled for Week 1) is the best path for that information.

*Sources: Concentric.ai Shadow Data Guide 2026 (concentric.ai/shadow-data-the-threat-you-dont-know-about-but-should/); OPSWAT Removable Media Policy (opswat.com/blog/removable-media-policy-guidelines-best-practices/); Microsoft Purview Endpoint DLP (learn.microsoft.com/en-us/purview/endpoint-dlp-learn-about)*

---

### Problem 2 — Retention Schedules That Are Defined But Not Enforced

CoW has 33 retention periods and 8 cutoff triggers defined in its data management lists, but the legal authority behind those periods has not been confirmed, enforcement automation in Laserfiche has not been verified, and no disposition approval workflow is documented.

**The legal foundation CoW should use:**

Kansas statutes establish the legal basis for municipal records management:
- **K.S.A. 45-403** — Government records are public property; destruction is prohibited except as permitted under approved retention schedules
- **K.S.A. 45-404** — State Records Board duties; county and state agency requirements
- **K.S.A. 12-120 and K.S.A. 12-121** — Minimum retention requirements specific to city records

The Kansas Historical Society (KSHS) provides advisory guidance to Kansas municipalities. KSHS guidance is advisory for municipalities (not mandatory, unlike state agencies and counties), which means CoW has flexibility — and responsibility — to formalize its own schedules through a council resolution or ordinance.

**The approval chain that peer cities use:**

> Department Head confirms records are ready for disposition
> → City Clerk verifies the applicable retention schedule minimum has been met
> → City Attorney confirms no legal hold is active (litigation, FOIA, audit)
> → City Clerk authorizes destruction or transfer to archives
> → Records manager documents the disposition with date and method

**What Laserfiche can do natively:**
- Monitor record aging and track retention periods automatically
- Generate alerts to department managers and records staff as disposition dates approach
- Route records through a disposition approval workflow without manual tracking
- Hold records for legal review if flagged by the City Attorney
- Produce audit logs of all disposition actions for compliance verification

**Case study — Rochester, New York:** Rochester processes 4,000+ public records (FOIL) requests per year using Laserfiche. After implementing Laserfiche workflow automation for records management, processing time dropped by approximately 50%. Rochester is a mid-size city (~210,000) using the same platform CoW already has.

*Sources: Kansas Revised Statutes Chapter 45 (ksrevisor.gov/statutes/ksa_ch45.html); KSHS Municipal Records Management (kansashistory.gov/p/municipal-government-records-management/11346); Laserfiche Retention Schedules Documentation (doc.laserfiche.com); Laserfiche — City of Rochester Case Study (laserfiche.com/casestudy/city-of-rochester-ny/)*

---

## Section 4: Domain-by-Domain Peer Benchmarking Matrix

**Status codes:** `Explicit Policy` = formal published policy or procedure found · `Principles Stated` = principles or commitments documented, no formal procedure · `Partial` = evidence found for part of the domain · `Not Found` = no public evidence located · `Not Applicable` = domain not relevant to this peer's structure

| # | Governance Domain | CoW Current State | Austin TX | Kansas City MO | Tulsa OK | Omaha NE |
|---|---|---|---|---|---|---|
| 1 | **Data Classification Schema** | SecTag field exists but is empty across all 45 files; no classification tiers defined | Partial — contract-level Public/Non-Public distinction; no standalone policy | Explicit Policy — 4-tier: Public / Private / Sensitive / Confidential (2025 Charter) | Explicit Policy — 4-tier: Public / Internal / Sensitive / Protected (COP 1400, 2026) | Not Found |
| 2 | **File Naming & Metadata Standards** | 32 fields defined; 432 document type abbreviations; 609 data quality issues; no validation enforced | Partial — BLDS for permits; observable portal metadata; no citywide schema | Principles Stated — Data Service Standard requires clear descriptive metadata; open standards mandate | Principles Stated — Data Provenance Policy requires metadata documented before CDR ingestion | Not Found |
| 3 | **Records Coordinators / Data Stewards** | 30+ coordinators identified; roles partially defined; no formal charter | Partial — Open Data Liaisons (one per dept) + Records Custodians (City Clerk) | Explicit Policy — CDO (City Code 2-2133); named Governance Committee (6 members); Data Owners + Data Stewards defined | Explicit Policy — 4-role structure: Data Manager, DGC Members (one per dept), Data Stewards (dept-level), Data Users | Not Found |
| 4 | **Stakeholder Roles (RACI Matrix)** | No RACI; accountability informal | Not Found | Principles Stated — Roles defined in charter; no document labeled RACI | Principles Stated — Functional RACI implied in governance manual; no document labeled RACI | Not Found |
| 5 | **Retention Schedules** | 33 periods defined; legal citation source not confirmed | Explicit Policy — Texas State Library schedules; City Clerk oversight | Explicit Policy — Missouri General Records Retention Schedule (state-mandated) | Explicit Policy — Oklahoma Title 67 Records Management Act | Partial — Nebraska SOS schedules only; no city-specific policy |
| 6 | **Retention Enforcement** | Triggers defined; automation status in Laserfiche unconfirmed; no disposition workflow documented | Partial — Records Custodians enforce; no evidence of automation | Principles Stated — State schedules mandated; no published enforcement automation documentation | Principles Stated — Oklahoma Dept. of Libraries provides schedules; automated enforcement not documented | Not Found |
| 7 | **Access Control Model** | No documented access model; no user role definitions | Partial — Encryption requirements in contracts; internal model not published | Principles Stated — Charter mandates access controls and user role definition; technical model not published | Explicit Policy — 3-tier AD hierarchy (Classification / Department / Application folders); request → Steward → IT → AD group; annual audit | Not Found |
| 8 | **Sensitive Data Access Workflow** | No documented process; no CJIS or HIPAA handling procedures | Not Found | Partial — HIPAA/law enforcement records acknowledged as Confidential; no published access workflow | Explicit Policy — Sensitive: Director/Designee approval; Protected (CJI/PHI): Legal Dept + DGSC Chair approval; "used only when no alternative exists" | Not Found |
| 9 | **Data Export & System Connections** | No export governance; integration requirements with data lake undefined | Not Found | Principles Stated — Open standards mandate (Data Service Standard); Open Data KC portal as central sharing hub | Explicit Policy — Pre-purchase data sovereignty gate; automated ETL provenance logging | Not Found |
| 10 | **Governance Adoption & Change Management** | No training program; no adoption metrics; no change management plan | Not Found | Principles Stated — CDO mandated to develop training; Bloomberg Gold external accountability | Explicit Policy — Urban Data Pioneers program (7+ cohorts; published outcomes); mandatory training for classification delegation; Data Quality self-service workflow | Not Found |

**Summary by peer:**

| City | Explicit Policy domains | Principles Stated domains | Not Found domains |
|---|---|---|---|
| **Tulsa** | 1, 3, 5, 7, 8, 9, 10 | 2, 4, 6 | — |
| **Kansas City** | 1, 3, 5 | 2, 4, 6, 7, 9, 10 | 8 |
| **Austin** | 5 | 2 | 1, 3, 4, 6, 7, 8, 9, 10 |
| **Omaha** | — | 5 (partial) | 1, 2, 3, 4, 6, 7, 8, 9, 10 |

**Takeaway:** Tulsa has explicit, published policy covering 7 of 10 governance domains. Kansas City has explicit policy for 3 of 10 but principles and commitments for 6 of 10. Austin is documented only for retention. Omaha is not documented for any domain.

> **Research gap — Des Moines, IA and Denver, CO:** Both cities are on CoW's official budget book peer list (confirmed at April 2026 client meeting) and are not included in the matrix above. They will be researched during Week 1 direct outreach and added in a v3 update. Iowa Code Chapter 304 and Colorado CRS Title 24 Article 80 provide the state-level records management baseline for each; city-level governance programs are unknown at this time.

---

## Section 5: Cross-City Comparison — What CoW Can Directly Borrow

For each governance domain, this section identifies which peer city's approach is the most directly reusable for CoW and notes any adaptation needed before use.

| # | Domain | Best Peer Model | What to Borrow | Adaptation Needed |
|---|---|---|---|---|
| 1 | Data Classification | **Tulsa COP 1400** | Four-tier schema (Public/Internal/Sensitive/Protected); Mayor → Director → Steward delegation chain; DGSC approval workflow for Protected data | Replace OPSI/Finance references with CoW's governance structure; confirm CJIS and HIPAA definitions with City Attorney |
| 2 | File Naming & Metadata | **Kansas City Data Service Standard** | Principles 5 and 15 — metadata requirements and open standards mandate; adopt as CoW's stated metadata commitment | Supplement with enumerated metadata field schema (CoW's 32-field model is more specific than KC's approach; formalizing existing fields is the gap) |
| 3 | Records Coordinators | **Tulsa EO 2019-08** | 4-role structure; Data Manager role definition; 2-day review SLA; ethical code for Data Manager | Map Tulsa's roles to CoW's existing structure: OPSI equivalent → governance manager TBD; 22 department DGC members → 22 records coordinators; dept Data Stewards → 30+ existing coordinators |
| 4 | Stakeholder Roles / RACI | **Tulsa governance manual** | Use Tulsa's role definitions and workflow to construct CoW's RACI explicitly — Tulsa demonstrates the functional RACI; CoW formalizes it as a named document | No direct peer RACI exists to copy; CoW will be creating a governance artifact that is more explicit than any peer |
| 5 | Retention Schedules | **Kansas City** (state schedule structure) | Model of formalizing state-mandated schedules through council resolution; approval chain | CoW's analog is KSHS advisory schedules + K.S.A. minimums → formalize via council resolution (same pattern as KC's Missouri schedule adoption) |
| 6 | Retention Enforcement | **Tulsa** (general model) | Oklahoma mandate structure provides a model; Laserfiche's native capabilities are the implementation path | No peer has published Laserfiche-specific retention automation documentation; Rochester NY case study (non-peer) is the closest reference |
| 7 | Access Control | **Tulsa AD hierarchy** | 3-tier folder structure (Classification / Department / Application); request workflow; annual audit cycle | Translate from Tulsa's Central Data Repository to CoW's Laserfiche Cloud; confirm AD integration with IT |
| 8 | Sensitive Data Workflow | **Tulsa COP 1400** | Sensitive tier: Director/Designee approval; Protected tier: Legal + DGSC approval; "used only when no alternative exists" as default restriction | Replace DGSC references with CoW's equivalent governance body; confirm CJIS policy requirements with Police Department |
| 9 | Data Export | **Tulsa Data Integration Policy** | Pre-purchase data sovereignty questionnaire (4 questions); ETL provenance logging requirement | Adapt pre-purchase gate to CoW's IT procurement process; ETL logging is a data lake architecture requirement for Deliverable 3 |
| 10 | Adoption & Change Management | **Tulsa Urban Data Pioneers** | Cross-functional team model with community involvement; mandatory training tied to classification delegation | Start smaller — a pilot cohort aligned with one high-visibility governance initiative; adoption metrics to define before program launches |

---

### Technical Architecture Notes for the Data Lake Implementation Team

The table above focuses on governance policy. This section translates Domains 7 and 9 into storage-tier specifics relevant to CoW's Deliverable 3 (System Requirements Document).

#### Domain 7 — Access Control: How Tulsa Maps Classification to Storage

Tulsa's 3-tier Active Directory hierarchy is not just an organizational chart — it is a direct physical storage mapping:

| Classification Tier | Storage Location | Access Group | Who Can Request |
|---|---|---|---|
| Public | Open CDR folder; also surfaced to ArcGIS Open Data portal | No approval required | Any staff or resident |
| Sensitive | Department-restricted CDR folder; **not** surfaced to public portal | Department AD group; request → Steward → IT → group assignment | Department staff with Steward approval |
| Protected | Application-level CDR folder; completely isolated from public-facing systems | Application-specific AD group; Legal + DGSC Chair approval required | Named individuals only; documented approval required |

**ArcGIS Open Data portal serves only Public-classified datasets.** No Sensitive or Protected data surfaces to the portal regardless of user role. The classification tier physically determines whether a dataset can appear in any outward-facing system.

**AD group memberships are audited annually** by IT Security under COP 1200. The audit cycle is the enforcement mechanism — not just the access request workflow.

**CoW translation for Laserfiche Cloud:** Laserfiche security groups can mirror this structure directly. The `SecTag` classification field (currently empty across all 45 data management files) is the trigger: once populated, it drives which Laserfiche security group a record belongs to. The classification policy (Tulsa COP 1400 adapted) must be in place before the security group structure can be configured — policy before platform configuration.

#### Domain 7 — Access Control: Kansas City's AWS / On-Premises Split

Kansas City's infrastructure split follows an implicit classification-driven storage routing pattern:

- **AWS (cloud)** hosts the analytics layer and the Open Data KC portal — public-facing, Public and Private-tier data
- **On-premises** hosts law enforcement records and HIPAA-adjacent data — Confidential tier

The 2025 Governance Charter mandates access controls and user role definitions but does not publish the technical implementation details. The AWS/on-premises architecture suggests CoW should plan for a similar split in its data lake:

> **Implication for Deliverable 3:** CoW's System Requirements Document should specify which classification tiers are eligible for cloud storage vs. must remain on-premises (or in a dedicated Laserfiche repository with no external connectivity). This decision should be made in consultation with IT and the City Attorney before the data lake architecture is finalized.

*Confirm the technical implementation details with Kansas City IT staff during Week 1 outreach — the charter describes the policy intent; the actual routing logic is not publicly documented.*

#### Domain 9 — Data Export: Tulsa's ETL Provenance Chain as a Data Lake Requirement

Tulsa's Data Provenance Policy requires an automated ETL log for every data transfer from source system to Central Data Repository. This creates a queryable provenance chain: source system → staging → governed repository. Combined with the pre-purchase data sovereignty gate, two controls work together:

1. **Inflow governance:** Every new dataset entering the CDR is classified, metadata-documented, and ETL-logged before it is accessible
2. **Procurement gate:** Before any new software purchase, four data sovereignty questions are answered in writing — preventing future shadow data at the point of vendor selection

**CoW translation for the data lake ingestion layer (Deliverable 3):** The ingestion layer design should require:
- A classification tag assigned at intake (not retroactively)
- An ETL log entry recording source system, transfer timestamp, approving steward, and destination storage tier
- A procurement checklist embedded in CoW's existing IT purchasing process, adapted from Tulsa's four-question model: (1) Will data from this application be needed for analytics? (2) Will it integrate with city systems? (3) Will CoW own the data? (4) Can CoW download all raw data, and how frequently?

---

## Section 6: Framework Confirmation & Implications for CoW

### What the Research Found

| Peer City | Framework Formally Adopted? | Actual Approach |
|---|---|---|
| **Austin, TX** | No named framework | Custom: 2013 Open Government Directive + Texas statutes (TPIA, TBC Chapter 521, Texas TRAIGA 2026). v1 stated Austin "references DAMA principles" — this was not confirmed in primary source documents. The Texas DIR publishes a Data Management Framework Guide that references DAMA, but that is a state-level document; Austin has not formally adopted it. |
| **Kansas City, MO** | No named framework | Custom: Data Governance Charter (July 2025) + UK GDS-adapted Data Service Standard (Oct 2025). Neither document references DAMA, ISO 8000, or NIST as a parent framework. |
| **Tulsa, OK** | No named framework | Custom: Series of executive orders (EO 2015, EO 2018-03, EO 2019-08) + corporate operating policies (COP 1200, COP 1400). NIST is cited in COP 1400 for definitions of PHI and CJI only — not as a governance framework. |
| **Omaha, NE** | No framework found | No governance program documented. |
| **Bloomberg WWC** | No named framework | WWC is its own standalone standard. Its 43 criteria do not align to DAMA, ISO 8000, or NIST. |

### What This Means for CoW

**If CoW formally adopts DAMA-DMBOK v2, it will be differentiated from all four peer cities.** This is not a reason not to adopt it — it is context for how to present the decision.

The peer evidence actually **supports the DAMA recommendation**, but for a different reason than peer precedent: all four peer cities built custom governance frameworks through executive orders and policy documents, then implemented those frameworks in their systems. DAMA-DMBOK v2 is the implementation guide that tells CoW *how* to build each piece of that custom framework. Tulsa built its four-tier classification without referencing DAMA, but the four-tier model they arrived at is fully consistent with DAMA's Data Security knowledge area. Kansas City's Data Service Standard principles align with DAMA's Data Quality and Metadata knowledge areas.

**The practical framing for Deliverable 1 and Deliverable 2:** CoW is building a custom governance policy (like all four peer cities did), using DAMA-DMBOK v2 as the internal implementation guide and quality standard. DAMA ensures CoW doesn't miss governance areas that peer cities have left undocumented. Bloomberg WWC provides the external accountability framework and certification path. These are complementary, not competing.

**If CoW leadership wants to pursue Bloomberg WWC Certification:** WWC Silver is achievable without formally adopting DAMA. Tulsa earned Silver with a custom framework; Kansas City earned Gold with a custom framework. The criteria overlap substantially with what DAMA recommends, but WWC certification does not require DAMA. If certification is the primary goal, WWC criteria become the benchmark; DAMA becomes the supporting implementation reference.

---

## Section 7: What This Means for Wichita

**CoW has more head start than any of the peer cities had at a comparable stage.** Tulsa started with an executive order and no existing platform. Kansas City started with an ordinance and had to build governance committee structure from scratch. CoW starts with Laserfiche already deployed, 33 retention periods already defined, 30+ records coordinators already identified, and a Master Table governance model already conceptually approved. The problem is not absence of tools or personnel — it is absence of policy authority and workflow configuration to make existing assets work as designed.

**On the framework question:** No peer city adopted DAMA formally. All four built custom frameworks. CoW should follow the same pattern — enact governance authority through an executive order or resolution, using the policy structures developed by Tulsa and Kansas City as direct reference models, with DAMA as the implementation guide that ensures comprehensive coverage.

**On data classification:** Both Tulsa and Kansas City independently arrived at a four-tier classification model (Public / [Internal] / Sensitive / [Protected or Confidential]). CoW's SecTag field already exists in all 45 data management files — it just has no values. Filling that field begins with adopting a classification policy. Tulsa's COP 1400 is the closest published template to what CoW needs.

**On the stewardship structure:** Tulsa's four-role model maps directly onto CoW's existing personnel. The 30+ records coordinators could become Data Stewards with a formal charter. One coordinator or governance manager from the City Clerk's office could fill the Data Manager role. The RACI CoW needs to create is not a new invention — it is a formalization of responsibilities that already informally exist.

**On Bloomberg What Works Cities:** No Kansas city holds this certification. CoW has prior engagement with the WWC program and staff were assigned to complete re-enrollment at the April 2026 meeting — CoW is not starting from scratch. The foundations Tulsa and Kansas City built to earn their certifications are the same foundations CoW's governance program needs regardless of whether formal certification is pursued. Re-enrollment and assessment provide an external benchmark, peer support from GovEx, and public accountability.

**Recommended next steps based on peer findings:**
1. **Complete Des Moines and Denver research** — Both are on CoW's official budget book peer list and were not in the original research scope. Week 1 direct outreach should include these two cities. Key questions: what governance framework (if any), how is records retention handled, what platforms are in use, and do they hold Bloomberg WWC Certification
2. Confirm whether CoW leadership wants to pursue Bloomberg WWC Certification — re-enrollment is already in progress; confirm whether the goal is participation only or formal certification assessment
3. Review Tulsa COP 1400 (February 2026) with CoW's City Attorney as a direct classification policy reference
4. Review Kansas City's 2025 Governance Charter as a committee structure reference
5. **Begin shadow data scope assessment** — Before deploying technical DLP controls (see Section 3, Problem 1), establish CoW's actual exposure with a targeted survey of department Records Coordinators. Three questions are sufficient for a Week 1 baseline:
   - (a) Do staff in your department routinely save city records to local hard drives or USB drives?
   - (b) Are there shared network folders outside Laserfiche used for active file storage?
   - (c) Estimate the volume: under 100 files / 100–1,000 files / over 1,000 files.
   
   This survey can be completed alongside document collection in Week 1. Results feed directly into the risk register in Deliverable 2 and the non-functional security requirements in Deliverable 3. If the survey reveals significant shadow data volume, a technical IT scan (Microsoft Purview Endpoint DLP or equivalent) should be scoped as a follow-on activity before any data lake ingestion design is finalized.
6. Identify which of CoW's 30+ records coordinators would serve as department Data Stewards under a formal governance charter

---

## Section 8: Disclaimer & Assumptions

This report is based on publicly available information gathered as of April 2026. It does not represent the official positions of any city government, professional association, or certification body cited. Findings have not been independently verified through direct contact with peer city staff.

**Direct outreach to peer city staff is scheduled for Week 1 of the engagement.** Findings from that outreach will supplement this report. Where this document says "Not Found," that means not found in publicly available sources — not that the practice does not exist.

**Assumptions:**
- Peer city governance programs are assumed to reflect their most recently published documentation. Programs may have evolved since publication. Six documents cited in this report (Tulsa COP 1400, Tulsa IT Security Policy COP 1200, Kansas City 2025 Charter, Kansas City Data Service Standard) were effective or updated in the past 12 months — they are the most current sources available.
- Bloomberg WWC certification criteria are based on the 2022 revised standard. Bloomberg Philanthropies may update criteria at any time. WWC scoring rubrics for individual criteria are not publicly available and were not used in this analysis.
- Kansas statutory citations (K.S.A. 12-120/121, K.S.A. 45-403/404) reflect currently published statutes. CoW should confirm applicability to its specific record types with its City Attorney before taking action.
- Laserfiche capabilities described reflect current platform documentation. Actual capabilities in CoW's deployed environment require verification with CoW's IT team.
- Shadow data scope within CoW has not been independently assessed. Risk figures cited (1 in 3 breaches; $4.88M average cost) are from industry sources and may not reflect CoW's specific situation.
- ICMA does not endorse specific frameworks. References to ICMA guidance reflect published materials, not a formal ICMA recommendation for CoW.
- The v1 report stated that Austin TX "references DAMA principles in its published data governance framework." This statement was not confirmed in primary source documents and has been corrected in v2. Austin's framework is custom, built on its 2013 Open Government Directive and Texas statutes.
- No peer city formally adopts DAMA-DMBOK v2. This finding is based on review of published policy documents; direct outreach may surface internal DAMA usage not documented publicly.

---

## Sources & Citations

**Austin, TX**
- Open Government Directive (2013): https://opendatapolicyhub.sunlightfoundation.com/collection/austin-tx-2013-08-26/
- Austin Technology Services: https://www.austintexas.gov/department/information-technology
- Austin Standard Contract Terms (2025): https://services.austintexas.gov/edims/document.cfm?id=469093
- Austin AI Governance Memo (Dec 2025): https://services.austintexas.gov/edims/document.cfm?id=464924
- Austin Open Data Portal: https://data.austintexas.gov/
- Austin data reliability issues (2023): https://communityimpact.com/austin/central-austin/city-county/2023/07/26/austin-seeks-solutions-to-widespread-public-data-reliability-issues/
- Texas State Library Local Records Retention Schedules: https://www.tsl.texas.gov/slrm/localretention

**Kansas City, MO**
- Data Governance Charter 2025 (July 1, 2025): https://data.kcmo.org/download/fuiv-g28p/application%2Fpdf
- Citywide Data Service Standard (October 7, 2025): https://data.kcmo.org/download/8z2m-bfwe/application%2Fpdf
- Open Data Policy (2014): https://opendatapolicyhub.sunlightfoundation.com/collection/kansas-city-mo-2014-06-19/
- Open Data Policy (2015 update): https://opendatapolicyhub.sunlightfoundation.com/collection/kansas-city-mo-2015-10-08/
- DataKC Program: https://www.kcmo.gov/city-hall/departments/city-manager-s-office/datakc
- Kansas City CDO departure: https://statescoop.com/kansas-city-chief-data-officer-eric-roche-pearland-texas/
- Kansas City on AWS: https://aws.amazon.com/solutions/case-studies/kansas-city/
- Missouri Records Management (Secretary of State): https://www.sos.mo.gov/records/recmgmt
- Missouri General Records Retention Schedule: https://www.sos.mo.gov/cmsimages/localrecords/general.pdf
- Open Data KC Portal: https://data.kcmo.org/

**Tulsa, OK**
- COP 1400 Data Classification Policy (eff. Feb 26, 2026): https://www.cityoftulsa.org/media/30101/1400-cop-data-classification-final-eff-02252026.pdf
- EO 2018-03 Data Classification: https://www.cityoftulsa.org/media/6655/2018-03.pdf
- EO 2019-08 Data Governance Policy (Dec 1, 2019): https://www.cityoftulsa.org/media/11918/2019-08.pdf
- Data Governance Manual (2019): https://www.cityoftulsa.org/media/11876/data-governance-manual.pdf
- Enterprise IT Security Policy Manual COP 1200 (Version 2024.5, March 2025): https://www.cityoftulsa.org/media/27549/cop-1200-enterprise-it-security-policy-manual-032025.pdf
- Urban Data Pioneers Mission Statement: https://www.cityoftulsa.org/media/7026/udpmission.pdf
- Urban Data Pioneers Report: https://www.cityoftulsa.org/media/17025/urban_data_pioneers_optimizing_open_data-9-2021.pdf
- Cities of Service — Urban Data Pioneers: https://citiesofservice.jhu.edu/resource/urban-data-pioneers-tulsa/
- City of Tulsa OPSI: https://www.cityoftulsa.org/government/performance-strategy-and-innovation/
- Tulsa What Works Cities Silver Certification: https://www.cityoftulsa.org/press-room/city-of-tulsa-receives-national-recognition-silver-what-works-cities-certification-for-excellence-in-data-driven-local-government/
- Tulsa Open Data Portal: https://gis2-cityoftulsa.opendata.arcgis.com/
- Oklahoma Title 67 Records Management Act: https://oksenate.gov/sites/default/files/2019-12/os67.pdf
- Oklahoma State Records Management: https://oklahoma.gov/libraries/archives-and-records/records-management.html
- What Works Cities — Tulsa Profile: https://whatworkscities.bloomberg.org/cities/tulsa-oklahoma-usa/

**Omaha, NE**
- Nebraska SOS Records Management Division: https://sos.nebraska.gov/records-management-division
- Nebraska SOS Retention Schedules for Local Government: https://sos.nebraska.gov/records-management/records-retention-schedules-local-govt
- DOGIS Open Data Portal: https://data.dogis.org/
- DOTComm Services: https://www.dotcomm.org/
- Historical Omaha data assessment (1982): https://digitalcommons.unomaha.edu/cparpubarchives/153/

**ICMA**
- Using Data to Improve Local Government Decision Making: https://icma.org/articles/article/using-data-improve-local-government-decision-making
- Five Ways to Become a Data-Driven Local Government: https://icma.org/blog-posts/five-ways-become-data-driven-local-government
- Local Gov Data Free Webinar Series: https://icma.org/local-gov-data-free-webinar-series
- ICMA Technology Management Institute: https://icma.org/technology-management-institute

**Bloomberg What Works Cities**
- WWC Assessment and Criteria: https://whatworkscities.bloomberg.org/assessment/
- Bloomberg Philanthropies — WWC Overview: https://www.bloomberg.org/government-innovation/strengthening-city-data-to-improve-lives/what-works-cities/
- WWC Cities Directory: https://whatworkscities.bloomberg.org/cities/
- GovEx (Johns Hopkins): https://govex.jhu.edu/about/
- Norfolk, VA WWC Certification: https://www.norfolk.gov/5131/What-Works-Cities-Certification
- StateScoop — 7 Cities Certified: https://statescoop.com/what-works-cities-certifies-seven-new-cities-for-good-data-practices/

**Shadow Data & DLP Tools**
- Concentric.ai — Shadow Data Guide 2026: https://concentric.ai/shadow-data-the-threat-you-dont-know-about-but-should/
- OPSWAT Removable Media Policy Best Practices: https://www.opswat.com/blog/removable-media-policy-guidelines-best-practices/
- Microsoft Purview Endpoint DLP: https://learn.microsoft.com/en-us/purview/endpoint-dlp-learn-about
- CrowdStrike DLP Best Practices: https://www.crowdstrike.com/en-us/cybersecurity-101/data-protection/dlp-best-practices/

**Kansas Records Law & KSHS**
- Kansas Revised Statutes Chapter 45: https://ksrevisor.gov/statutes/ksa_ch45.html
- KSHS Municipal Government Records Management: https://www.kansashistory.gov/p/municipal-government-records-management/11346
- KSHS Local Records Management Manual: https://www.kansashistory.gov/p/local-records-management-manual/11342
- KSHS Records Management and the Law: https://www.kansashistory.gov/p/records-management-and-the-law/11348

**Laserfiche & Retention Automation**
- Laserfiche Retention Schedules Documentation: https://doc.laserfiche.com/laserfiche.documentation/11/administration/en-us/Subsystems/LFAdmin/Content/RecordsManagement/Retention_Schedule.htm
- Laserfiche Government Solutions: https://www.laserfiche.com/solutions/government/
- Laserfiche Case Study — City of Rochester, NY: https://www.laserfiche.com/casestudy/city-of-rochester-ny/

**Frameworks Referenced**
- DAMA DMBOK: https://dama.org/learning-resources/dama-data-management-body-of-knowledge-dmbok/
- NIST Data Governance and Management Profile: https://www.nist.gov/privacy-framework/new-projects/data-governance-and-management-profile

---

*IMPACT Consulting — Barton School of Business, Wichita State University*
*City of Wichita Data Governance & Data Lake Engagement — April 2026*
*Document: `02-Proposal/Final-Proposal/20260401-CoW-Peer-Benchmarking-Research-Report-v2.md`*
