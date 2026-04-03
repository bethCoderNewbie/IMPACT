# Peer City & Industry Benchmarking Research Report
**Prepared by:** IMPACT Consulting — Barton School of Business, Wichita State University
**Prepared for:** City of Wichita (CoW)
**Date:** April 2, 2026
**Version:** v1 — Based on Publicly Available Sources as of April 2026
**Feeds Into:** Deliverable 1 (Standards Selection Brief) · Deliverable 2 (Data Governance Review Report)

---

> **Disclaimer:** This report is based on publicly available information gathered as of April 2026. It does not represent the official positions of any city government, professional association, or certification body cited. Findings have not been independently verified through direct contact with peer city staff. Where information could not be located in public sources, this is stated explicitly rather than inferred or assumed.

---

## Executive Summary

At the kickoff session, the City of Wichita asked: *what are cities like us actually doing?*

We researched four peer cities and two professional organizations to answer that question. Here is what we found:

- **Tulsa, OK is the most directly relevant peer for Wichita.** Tulsa is a similar-sized Midwest city that built its governance program from scratch, used an executive order to formalize policy, and earned Bloomberg's Silver certification. Its model is small, practical, and adaptable.
- **Kansas City, MO shows what a more mature program looks like.** It has a formal Data Governance Charter, a dedicated governance team, and Bloomberg Gold Certification. It took them roughly a decade to get there from a standing start.
- **No Kansas city has done this yet.** As of April 2026, no municipality in Kansas holds Bloomberg What Works Cities Certification. Wichita has an opportunity to be the first.
- **Wichita's two core problems — shadow data and unenforced retention — have known solutions.** The tools and legal authorities needed already exist. What is missing is the policy framework and workflow configuration to put them to work.

---

## Section 1: Peer City Findings

### At a Glance

| City | Governance Framework | Retention Model | Key Platform | Governance Structure | Bloomberg WWC Status |
|---|---|---|---|---|---|
| **Austin, TX** | Custom (Open Government Directive, 2013) | Hybrid — City Clerk oversight + departmental custodians | Tyler/Socrata; Austin Technology Services | No CDO; Enterprise Open Data Platform Team + per-dept liaisons | Not found in public sources |
| **Kansas City, MO** | Custom Data Governance Charter (2014, updated 2015) | State-mandated (Missouri Local Records Board schedules) | AWS + on-premises | Former CDO (2015–2021); now DataKC + Governance Committee | Gold |
| **Tulsa, OK** | Formal governance policy via Executive Order (Dec 2015) | Oklahoma Title 67 Records Management Act | Central Data Repository + ArcGIS Open Data | OPSI office (Finance Dept); Data Analytics Manager | Silver |
| **Omaha, NE** | None found in public sources | Nebraska SOS schedules only; no city-specific policy | DOTComm shared IT + DOGIS (GIS only) | No CDO; no formal governance office identified | Not certified |

---

### Austin, Texas

Austin published its Open Government Directive in August 2013, making it one of the earlier cities to formally commit to data governance in writing. Rather than adopting a national framework like DAMA or NIST, Austin built its own approach and has updated it continuously since.

**How retention works:** Austin uses a hybrid model. The City Clerk's Office sets centralized policy and compliance oversight. Individual departments are responsible for managing their own records under those rules, guided by the Texas State Library's Local Government Retention Schedules. Each department has a designated Records Custodian.

**How governance is organized:** Austin does not have a city-level Chief Data Officer. Instead, governance is distributed through an Enterprise Open Data Platform Team (within Austin Technology Services) and Open Data Liaisons assigned to each department. This is a coordinator model rather than a centralized one.

**Problem they solved:** In 2023, Austin publicly acknowledged widespread data reliability issues — different departments publishing conflicting and outdated information. They responded by upgrading to a new Enterprise Data Platform through Tyler Technologies. The lesson: data quality problems that are allowed to compound across departments eventually require a costly system-wide fix.

**What CoW can take from Austin:** Departmental accountability works when it is backed by clear central policy. Austin's Open Data Liaison model — one designated person per department — is a practical starting structure that does not require a large central team.

*Sources: Austin Open Government Directive (opendatapolicyhub.sunlightfoundation.com/collection/austin-tx-2013-08-26/); Austin Technology Services (austintexas.gov/department/information-technology); Austin Open Data Portal (data.austintexas.gov); Austin data reliability issues (communityimpact.com, July 2023)*

---

### Kansas City, Missouri

Kansas City has one of the most developed data governance programs among comparable Midwest cities. It started with an Open Data ordinance in 2014, updated it in 2015 after collaborating with the Sunlight Foundation, and published a formal Data Governance Charter that is still publicly available today.

**How retention works:** Kansas City follows the Missouri General Records Retention Schedule, published by the Missouri Secretary of State's Records Management Division. This is a state-mandated baseline that all Missouri local governments are expected to follow.

**How governance is organized:** Kansas City appointed its first Chief Data Officer in May 2015. After that CDO departed in 2021, governance shifted to a committee model. Today, the DataKC program sits within the City Manager's Office and coordinates a cross-departmental Governance Committee. The KC Stat program — a public-facing performance dashboard running since 2011 — provides accountability for citywide priorities.

**Bloomberg certification:** Kansas City holds Gold Certification from Bloomberg's What Works Cities program. The certification was earned in large part by formalizing its governance commitment in writing (the Data Governance Charter) and building a comprehensive data inventory across departments.

**What CoW can take from Kansas City:** A written governance charter is not just paperwork — it is what made Gold certification possible. Kansas City's committee model (DataKC + cross-dept Governance Committee) is a realistic structure for a city without a dedicated CDO budget.

*Sources: Data Governance Charter (data.kcmo.org/dataset/Data-Governance-Charter/fuiv-g28p); Open Data Policy (opendatapolicyhub.sunlightfoundation.com); DataKC Program (kcmo.gov); Kansas City on AWS (aws.amazon.com/solutions/case-studies/kansas-city/); Missouri SOS Records Management (sos.mo.gov/records/recmgmt)*

---

### Tulsa, Oklahoma

Tulsa is the most directly adaptable model for Wichita. It is a similar-sized Midwest city (population ~410,000) that built a formal data governance program from a low starting point and achieved Bloomberg Silver Certification — without requiring a large budget or a new department.

**How governance was built:** The city created the Office of Performance, Strategy and Innovation (OPSI) within the Finance Department in 2019. A Data Analytics Manager chairs the Data Governance Committee. The data governance policy was enacted by Executive Order on December 21, 2015 — before OPSI existed — which gave the program formal authority from the start.

**How retention works:** Tulsa follows the Oklahoma Records Management Act (Title 67, Oklahoma Statutes), which requires local governments to manage records using the state's General Records Disposition Schedules. The Oklahoma Department of Libraries provides the schedules and guidance.

**What they built:** Tulsa created a Central Data Repository accessible to city employees and residents for data requests. The city also runs an Urban Data Pioneers program — cross-functional teams of city staff and residents who use city data to solve civic problems. Results include a 70% reduction in 911 calls from repeat utilizers and a 63% improvement in fine payment compliance through targeted outreach.

**Bloomberg certification:** Tulsa holds Silver Certification. The path to Silver took a formal policy, a governance committee, and a central data repository — none of which required a large team.

**What CoW can take from Tulsa:** An executive order or resolution formalizing governance authority is the critical first step. A small, dedicated team with a clear charter (the OPSI model) can do more than a large, uncoordinated effort. The Central Data Repository concept is directly relevant to CoW's scattered-data problem.

*Sources: City of Tulsa OPSI (cityoftulsa.org/government/performance-strategy-and-innovation/); Tulsa WWC Silver Certification (cityoftulsa.org); Tulsa Urban Data Pioneers Report (cityoftulsa.org/media/17025); What Works Cities — Tulsa Profile (whatworkscities.bloomberg.org/cities/tulsa-oklahoma-usa/); Oklahoma Title 67 (oksenate.gov); Oklahoma Records Management (oklahoma.gov/libraries/archives-and-records)*

---

### Omaha, Nebraska

Omaha is included as a cautionary comparison — a peer-sized Midwest city that has not built a formal data governance program, and whose history shows what happens when that work is deferred.

**What exists today:** Omaha does not have a published municipal data governance policy or a designated Chief Data Officer. Its formal records management relies entirely on the Nebraska Secretary of State's retention schedules for local governments. IT services are shared with Douglas County through DOTComm, a joint interlocal agreement. The city manages GIS data through DOGIS (the Douglas-Omaha GIS office) — that is the most structured data governance function publicly documented.

**Historical record:** A 1982 University of Nebraska assessment of Omaha's data systems found they were "neither coordinated nor comprehensive" and lacked "clear policy direction." There is no public evidence that this situation has fundamentally changed in the decades since.

**What CoW can take from Omaha:** The risk of inaction is well documented here. Without a governance policy and executive sponsorship, data fragmentation compounds over time. Shared IT infrastructure (like DOTComm) provides economies of scale but does not substitute for governance policy.

*Sources: Nebraska SOS Records Management (sos.nebraska.gov/records-management-division); DOGIS Open Data Portal (data.dogis.org); DOTComm Services (dotcomm.org); Historical Omaha data assessment, UNO (digitalcommons.unomaha.edu/cparpubarchives/153/)*

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

**Useful resources from ICMA:**
- *Using Data to Improve Local Government Decision Making* — includes case studies from small and mid-size cities
- *Five Ways to Become a Data-Driven Local Government* — practical starting checklist
- Local Gov Data free webinar series — accessible training for staff at no cost

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

**What the 43 criteria cover:** Open data practices, data governance structures, performance analytics, data inventory completeness, low-cost evaluation capacity, results-driven contracting, and transparent public accountability. The criteria do not align to DAMA, ISO 8000, or NIST — WWC is its own standalone standard.

**Which cities comparable to Wichita are certified:**
- **Kansas City, MO** (~490,000) — Gold Certification
- **Tulsa, OK** (~410,000) — Silver Certification
- **Denver, CO** (~700,000) — Certified
- **Phoenix, AZ** (~1.6M) — Platinum Certification

As of April 2026, **no Kansas city holds WWC Certification.** Wichita would be the first.

**How long does it take?** The only published specific example is Norfolk, Virginia, which achieved Silver after approximately one year of focused effort. Bloomberg does not publish a standard timeline. The evidence suggests Silver is achievable for a city that formalizes governance, builds a data inventory, and establishes cross-departmental coordination — the same foundations Tulsa and Kansas City built.

**What would CoW need to pursue Silver?**
- A written governance policy (ordinance or executive order)
- A data inventory across departments
- Cross-departmental governance coordination (committee or designated leads)
- An open data portal or equivalent transparency mechanism
- Performance analytics capability tied to city priorities

**What this means for CoW:** Bloomberg WWC Silver is a realistic near-term goal. Kansas City's path to Gold and Tulsa's Silver certification both show this is achievable for mid-size Midwest cities. Starting with Silver also does not require choosing WWC over other frameworks — the criteria overlap substantially with what DAMA and NIST recommend.

*Sources: WWC Assessment (whatworkscities.bloomberg.org/assessment/); Bloomberg Philanthropies WWC overview (bloomberg.org); WWC Cities Directory (whatworkscities.bloomberg.org/cities/); GovEx About (govex.jhu.edu/about/); Norfolk WWC Certification (norfolk.gov/5131/What-Works-Cities-Certification); StateScoop — Cities Certified (statescoop.com)*

---

## Section 3: How Peer Cities Solved CoW's Two Core Problems

### Problem 1 — Data Stored Outside Governed Systems (USB Drives, Local Hard Drives)

CoW has records stored in Laserfiche Cloud and in 45 Excel-based department lists — but also, to an unknown extent, on USB drives, personal hard drives, and shared network folders outside any governed system. This is not unique to Wichita. Other cities and organizations have addressed it.

**Why it matters:**
Industry data shows that 1 in 3 data breaches involve "shadow data" — records that exist outside governed systems. The average cost of a breach involving shadow data is $4.88 million (Cyberhaven, 2026). For a public agency, the risk is also legal: records that exist outside governed systems cannot be subject to retention enforcement, cannot be produced in litigation, and may violate public records law.

**How other cities and organizations have addressed it:**

Step 1 — **Audit the scope.** Before writing policy, organizations inventory what shadow data exists and where. This can be done manually (department surveys) or through IT tools that scan network drives and endpoints.

Step 2 — **Publish a removable media policy.** A formal policy establishes that USB drives and local hard drives are not authorized storage for city records. The policy specifies approved tools, defines what "city records" means, and sets consequences for non-compliance.

Step 3 — **Deploy monitoring before enforcement.** Organizations that succeed typically monitor usage first (logging what data moves where) before blocking. This builds a picture of actual behavior and makes the policy defensible.

Step 4 — **Move to technical enforcement.** Once monitoring is in place, technical controls are activated: device whitelisting (only approved USB devices work), endpoint management policies, and Data Loss Prevention (DLP) tools that prevent unauthorized file transfers.

**Technology options:**
- **Microsoft Purview Endpoint DLP** — The most practical option for CoW given its existing Microsoft 365 environment. Integrates with Windows, enforces policies across devices, logs all file movement activity. Documentation: learn.microsoft.com/en-us/purview/endpoint-dlp-learn-about
- **CrowdStrike DLP** — Enterprise-grade endpoint protection with DLP capabilities
- **ManageEngine Endpoint DLP Plus** — Mid-market option with strong policy management

**Timeline:** Organizations deploying modern DLP tools typically see tangible compliance improvement within 12–18 months for smaller organizations, 6–12 months for larger ones.

**What was not found:** No public case studies documenting a specific city's amnesty window or migration timeline from shadow data to governed storage. If CoW wants to understand whether an amnesty period is appropriate, direct outreach to peer city IT staff (scheduled for Week 1) is the best path.

**Note for CoW:** Technical controls alone do not work — employees find workarounds. Policy alone does not work — without enforcement, non-compliance continues. Both are required, implemented in the sequence above.

*Sources: Concentric.ai Shadow Data Guide 2026 (concentric.ai/shadow-data-the-threat-you-dont-know-about-but-should/); OPSWAT Removable Media Policy (opswat.com/blog/removable-media-policy-guidelines-best-practices/); CrowdStrike DLP Best Practices (crowdstrike.com); Microsoft Purview Endpoint DLP (learn.microsoft.com/en-us/purview/endpoint-dlp-learn-about); Nightfall AI DLP Guide (nightfall.ai)*

---

### Problem 2 — Retention Schedules That Are Defined But Not Enforced

CoW has 33 retention periods and 8 cutoff triggers defined in its data management lists, but the legal authority behind those periods has not been confirmed, enforcement automation in Laserfiche has not been verified, and no disposition approval workflow is documented.

**The legal foundation CoW should use:**

Kansas statutes establish the legal basis for municipal records management:
- **K.S.A. 45-403** — Government records are public property; destruction is prohibited except as permitted under approved retention schedules
- **K.S.A. 45-404** — State Records Board duties; county and state agency requirements
- **K.S.A. 12-120 and K.S.A. 12-121** — Minimum retention requirements specific to city records

The Kansas Historical Society (KSHS) provides guidance to Kansas municipalities, including sample retention schedules. KSHS maintains a sample schedule from Wichita itself, which confirms the framework already exists in public record. However, KSHS guidance is **advisory for municipalities**, not mandatory (state agencies and counties have stricter requirements). This means CoW has flexibility — and responsibility — to formalize its own schedules through a council resolution or ordinance.

**How to go from inconsistent to enforced — the remediation path:**

1. **Inventory records by type and location.** Before assigning retention periods, document what records exist across all 22 departments and where they are stored (Laserfiche, Excel lists, email, shared drives).

2. **Classify into functional categories.** Group records by function (financial, personnel, permits, correspondence, etc.) using the KSHS local government retention guidance as a reference.

3. **Assign retention periods.** Map each category to K.S.A. minimums and KSHS sample schedules. Where no statutory minimum exists, the KSHS schedule provides a reasonable default.

4. **Formalize via council resolution.** Retention schedules for Kansas municipalities must be formally approved by the city council (or equivalent governing body) and recorded in official meeting minutes. This is the step that creates legal authority.

5. **Configure Laserfiche automation.** Once schedules are formalized, Laserfiche can enforce them automatically.

**What Laserfiche can do natively (already included in the platform):**
- Monitor record aging and track retention periods automatically
- Generate alerts to department managers and records staff as disposition dates approach
- Route records through a disposition approval workflow without manual tracking
- Hold records for legal review if flagged by the City Attorney
- Produce audit logs of all disposition actions for compliance verification

CoW does not need to purchase additional software. The capability already exists in Laserfiche — it requires configuration, not a new system.

**The approval chain that peer cities use:**

> Department Head confirms records are ready for disposition
> → City Clerk verifies the applicable retention schedule minimum has been met
> → City Attorney confirms no legal hold is active (litigation, FOIA, audit)
> → City Clerk authorizes destruction or transfer to archives
> → Records manager documents the disposition with date and method

**Legal holds:** When a record is subject to pending litigation, a public records request, or an audit, the City Attorney's Office should initiate a hold that suspends the retention schedule. Laserfiche supports this natively.

**How to handle records that predate the governance program:** Legacy records — files created before any retention schedule was in force — should be inventoried, assessed for historical value, and either transferred to KSHS (if of enduring historical value) or destroyed under a one-time disposition authorization approved by the City Attorney. This is a standard remediation step that does not require reinventing the process.

**Case study — Rochester, New York:** Rochester processes 4,000+ public records (FOIL) requests per year using Laserfiche. After implementing Laserfiche workflow automation for records management, processing time dropped by approximately 50%. Rochester is a mid-size city (population ~210,000) using the same platform CoW already has.

*Sources: Kansas Revised Statutes Chapter 45 (ksrevisor.gov/statutes/ksa_ch45.html); KSHS Municipal Records Management (kansashistory.gov/p/municipal-government-records-management/11346); KSHS Local Records Management Manual (kansashistory.gov/p/local-records-management-manual/11342); Laserfiche Retention Schedules Documentation (doc.laserfiche.com); Laserfiche Government Solutions (laserfiche.com/solutions/government/); Laserfiche — City of Rochester Case Study (laserfiche.com/casestudy/city-of-rochester-ny/)*

---

## Section 4: What This Means for Wichita

**The governance program CoW needs already has a proven model.** Tulsa built it with a small team, an executive order, and a formal policy document. Kansas City shows what a more mature version looks like with a governance charter and committee structure. Neither city started with everything in place — both built incrementally.

**CoW has a head start that neither Tulsa nor Kansas City had:** Laserfiche is already deployed. The retention periods are already defined (if not enforced). A records management structure exists through the City Clerk. The problem is not absence of tools — it is the absence of policy authority and workflow configuration to make existing tools work as designed.

**On Bloomberg What Works Cities:** No Kansas city holds this certification. The criteria Kansas City and Tulsa met to earn their certifications are the same foundations CoW's governance program needs to build regardless of whether certification is pursued. Pursuing certification provides an external benchmark, peer support from GovEx, and public accountability — all of which help sustain governance programs through leadership changes.

**Recommended next steps based on peer findings:**
1. Confirm which peer city models are most relevant to CoW leadership (Tulsa's OPSI model vs. Kansas City's committee model)
2. Identify whether CoW has existing relationships with IT or records staff at any of the four peer cities — direct outreach will add context not available in public documents
3. Confirm whether CoW leadership is interested in Bloomberg WWC Certification — this determines how much depth to give WWC research in subsequent weeks
4. Begin inventory of records stored outside Laserfiche (shadow data scope assessment)

---

## Section 5: Disclaimer & Assumptions

This report is based on publicly available information gathered as of April 2026. It does not represent the official positions of any city government, professional association, or certification body cited. Findings have not been independently verified through direct contact with peer city staff.

**Assumptions:**
- Peer city governance programs are assumed to reflect their most recently published documentation. Programs may have evolved since publication.
- Bloomberg WWC certification criteria are based on the 2022 revised standard. Bloomberg Philanthropies may update criteria at any time.
- Kansas statutory citations (K.S.A. 12-120/121, K.S.A. 45-403/404) reflect currently published statutes. CoW should confirm applicability to its specific record types with its City Attorney before taking action.
- Laserfiche capabilities described reflect current platform documentation. Actual capabilities in CoW's deployed environment require verification with CoW's IT team.
- No direct outreach to peer city staff was completed for this draft. Outreach is scheduled for Week 1 per the approved proposal and will supplement these findings.
- Shadow data scope within CoW has not been independently assessed. Risk figures cited (1 in 3 breaches; $4.88M average cost) are from industry sources and may not reflect CoW's specific situation.
- ICMA does not endorse specific frameworks. References to ICMA guidance reflect published materials, not a formal ICMA recommendation for CoW.
- Where no case study was found in public sources (e.g., municipal amnesty windows for shadow data migration), this is stated explicitly. No inference has been substituted for missing evidence.

---

## Sources & Citations

**Austin, TX**
- Open Government Directive (2013): https://opendatapolicyhub.sunlightfoundation.com/collection/austin-tx-2013-08-26/
- Austin Technology Services: https://www.austintexas.gov/department/information-technology
- Austin Information Security Office: https://www.austintexas.gov/department/information-security-office-0
- Austin Open Data Portal: https://data.austintexas.gov/
- Austin data reliability issues (2023): https://communityimpact.com/austin/central-austin/city-county/2023/07/26/austin-seeks-solutions-to-widespread-public-data-reliability-issues/
- Texas State Library Local Records Retention Schedules: https://www.tsl.texas.gov/slrm/localretention

**Kansas City, MO**
- Data Governance Charter: https://data.kcmo.org/dataset/Data-Governance-Charter/fuiv-g28p
- Open Data Policy (2014): https://opendatapolicyhub.sunlightfoundation.com/collection/kansas-city-mo-2014-06-19/
- Open Data Policy (2015 update): https://opendatapolicyhub.sunlightfoundation.com/collection/kansas-city-mo-2015-10-08/
- DataKC Program: https://www.kcmo.gov/city-hall/departments/city-manager-s-office/datakc
- Kansas City CDO departure: https://statescoop.com/kansas-city-chief-data-officer-eric-roche-pearland-texas/
- Kansas City on AWS: https://aws.amazon.com/solutions/case-studies/kansas-city/
- Missouri Records Management (Secretary of State): https://www.sos.mo.gov/records/recmgmt
- Missouri General Records Retention Schedule: https://www.sos.mo.gov/cmsimages/localrecords/general.pdf
- Open Data KC Portal: https://data.kcmo.org/

**Tulsa, OK**
- City of Tulsa OPSI: https://www.cityoftulsa.org/government/performance-strategy-and-innovation/
- Tulsa What Works Cities Silver Certification: https://www.cityoftulsa.org/press-room/city-of-tulsa-receives-national-recognition-silver-what-works-cities-certification-for-excellence-in-data-driven-local-government/
- Tulsa Urban Data Pioneers Report: https://www.cityoftulsa.org/media/17025/urban_data_pioneers_optimizing_open_data-9-2021.pdf
- Tulsa WWC Medium Case Study: https://medium.com/what-works-cities-certification/tulsa-scales-up-data-first-innovation-452bd28b6470
- Tulsa Open Data Portal: https://gis2-cityoftulsa.opendata.arcgis.com/
- Oklahoma Title 67 Records Management Act: https://oksenate.gov/sites/default/files/2019-12/os67.pdf
- Oklahoma State Records Management: https://oklahoma.gov/libraries/archives-and-records/records-management.html
- Oklahoma General Records Disposition Schedule: https://oklahoma.gov/libraries/grds-state-agencies.html
- What Works Cities — Tulsa Profile: https://whatworkscities.bloomberg.org/cities/tulsa-oklahoma-usa/

**Omaha, NE**
- Nebraska SOS Records Management Division: https://sos.nebraska.gov/records-management-division
- Nebraska SOS Retention Schedules for Local Government: https://sos.nebraska.gov/records-management/records-retention-schedules-local-govt
- DOGIS Open Data Portal: https://data.dogis.org/
- DOTComm Services: https://www.dotcomm.org/
- UNO Digital Governance Lab: https://www.unomaha.edu/college-of-public-affairs-and-community-service/public-administration/research-centers/digital-governance-and-analytics-lab/index.php
- Historical Omaha data assessment (1982): https://digitalcommons.unomaha.edu/cparpubarchives/153/

**ICMA**
- Using Data to Improve Local Government Decision Making: https://icma.org/articles/article/using-data-improve-local-government-decision-making
- Five Ways to Become a Data-Driven Local Government: https://icma.org/blog-posts/five-ways-become-data-driven-local-government
- Local Gov Data Free Webinar Series: https://icma.org/local-gov-data-free-webinar-series
- ICMA Technology Management Institute: https://icma.org/technology-management-institute
- MetroLab Network Data Governance Guide: https://metrolabnetwork.org/datagovernance-guide/

**Bloomberg What Works Cities**
- WWC Assessment and Criteria: https://whatworkscities.bloomberg.org/assessment/
- Bloomberg Philanthropies — WWC Overview: https://www.bloomberg.org/government-innovation/strengthening-city-data-to-improve-lives/what-works-cities/
- WWC Cities Directory: https://whatworkscities.bloomberg.org/cities/
- GovEx (Johns Hopkins): https://govex.jhu.edu/about/
- Norfolk, VA WWC Certification: https://www.norfolk.gov/5131/What-Works-Cities-Certification
- StateScoop — 7 Cities Certified: https://statescoop.com/what-works-cities-certifies-seven-new-cities-for-good-data-practices/
- Results for America — WWC Portal: https://results4america.org/tools/what-works-cities-certification-assessment-portal/

**Shadow Data & DLP Tools**
- Concentric.ai — Shadow Data Guide 2026: https://concentric.ai/shadow-data-the-threat-you-dont-know-about-but-should/
- OPSWAT Removable Media Policy Best Practices: https://www.opswat.com/blog/removable-media-policy-guidelines-best-practices/
- CurrentWare Removable Media Policy Template: https://www.currentware.com/blog/removable-media-policy-template/
- CrowdStrike DLP Best Practices: https://www.crowdstrike.com/en-us/cybersecurity-101/data-protection/dlp-best-practices/
- Microsoft Purview Endpoint DLP: https://learn.microsoft.com/en-us/purview/endpoint-dlp-learn-about
- Nightfall AI — DLP Policies Guide: https://www.nightfall.ai/blog/data-loss-prevention-dlp-policies-guide-and-policy-template

**Kansas Records Law & KSHS**
- Kansas Revised Statutes Chapter 45: https://ksrevisor.gov/statutes/ksa_ch45.html
- KSHS Municipal Government Records Management: https://www.kansashistory.gov/p/municipal-government-records-management/11346
- KSHS Local Records Management Manual: https://www.kansashistory.gov/p/local-records-management-manual/11342
- KSHS Records Management and the Law: https://www.kansashistory.gov/p/records-management-and-the-law/11348
- KSHS State Records Retention Schedules: https://www.kansashistory.gov/p/state-records-retention-schedules/11366

**Laserfiche & Retention Automation**
- Laserfiche Retention Schedules Documentation: https://doc.laserfiche.com/laserfiche.documentation/11/administration/en-us/Subsystems/LFAdmin/Content/RecordsManagement/Retention_Schedule.htm
- Laserfiche — What Is Records Retention: https://www.laserfiche.com/resources/blog/what-is-records-retention/
- Laserfiche Government Solutions: https://www.laserfiche.com/solutions/government/
- Laserfiche Case Study — City of Rochester, NY: https://www.laserfiche.com/casestudy/city-of-rochester-ny/

**Frameworks Referenced**
- DAMA DMBOK: https://dama.org/learning-resources/dama-data-management-body-of-knowledge-dmbok/
- NIST Data Governance and Management Profile: https://www.nist.gov/privacy-framework/new-projects/data-governance-and-management-profile

---

*IMPACT Consulting — Barton School of Business, Wichita State University*
*City of Wichita Data Governance & Data Lake Engagement — April 2026*
*Document: `02-Proposal/Final-Proposal/20260401-CoW-Peer-Benchmarking-Research-Report-v1.md`*
