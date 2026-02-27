# IMPACT Data Home — Constraints, Resource Gaps & Business ROI

**Date:** 2026-02-26
**Linked Plan:** `20260226-Architecture Plan.md`
**Decision Matrix:** `20260226-Automation Decision Matrix.md`

---

## Part 1: Constraints & Resolutions

---

### C1 — M365 License Tier (Verify Before Build)

**Why it matters:** Not all M365 plans include the same Power Automate capabilities. The automation flows depend on this.

| License Tier | Power Automate Included | Flow Run Limit | Premium Connectors |
|---|---|---|---|
| M365 A1 (Education free) | Yes | 750 runs/month/user | No |
| M365 A3/A5 (Education paid) | Yes | 750 runs/month/user | Some |
| Power Automate standalone | Yes | 5,000+ runs/month | Yes |

**At IMPACT scale (54 students, 4 flows):** ~300 runs/month total — within A1 limits.

**Action:** Confirm with WSU IT whether licenses are A1, A3, or Business before build starts.

---

### C2 — IT Admin Access (Critical Path Item)

**Why it matters:** SharePoint site creation, Teams provisioning, and shared mailbox OAuth configuration are controlled by central IT at WSU — not end users.

**Blockers if not resolved:**
- Cannot create the Hub Communication Site without SharePoint admin rights
- Cannot set Hub site associations without tenant-level admin
- Cannot configure shared mailbox routing for `barton.impact@wichita.edu`

**Action:** Submit IT request early. Designate one Operations or Leadership member as **Site Collection Admin** for the IMPACT SharePoint environment. IT retains tenant admin.

---

### C3 — FERPA Compliance (Scoped & Manageable)

**Context:** Since WSU HR owns all legal employment paperwork, IMPACT only stores **operational data** in the Student Roster — not academic records. This significantly reduces FERPA exposure.

**What IMPACT stores:**
- Team assignment, start/end dates, training completion — operational, not academic records
- Success stories — requires student consent (add consent checkbox to onboarding form)

**What IMPACT does NOT store:**
- GPA, transcript data, enrollment status, grades — HR/Registrar owns these

**Actions:**
- Add consent checkbox to onboarding form: *"I consent to my success story being used in program reporting"*
- Disable external sharing on the Operations Team Site
- Confirm with WSU's FERPA officer that operational HR data for student employees is not restricted

---

### C4 — System Ownership & Turnover Risk (Resolved)

**Resolution:** All Power Automate flows and SharePoint site ownership must be held by the **shared service account** (`barton.impact@wichita.edu`), not any individual student's account.

**Implementation:**
- Create all flows while logged in as `barton.impact@wichita.edu`
- Assign one permanent faculty/staff member as backup SharePoint admin
- Store all flow documentation and site structure SOPs in the Hub SOP Library (self-referential)
- Conduct a handoff review at the end of each academic year

---

### C5 — HR Paperwork Scope (Resolved)

**Resolution:** HR handles all Kansas state and university legal employment requirements. IMPACT's onboarding scope is strictly operational. See the **IMPACT Onboarding Scope** section in the Architecture Plan.

**Boundary rule:** HR makes them an employee. IMPACT makes them a functioning team member.

**Trigger:** HR confirmation email to `barton.impact@wichita.edu` → Power Automate Flow 2 begins IMPACT onboarding automatically.

---

### C6 — Credential Management (Resolved)

**Tiered approach:**

| Credential Type | Recommended Practice | Cost |
|---|---|---|
| Social media (Meta, LinkedIn, Twitter) | Native team/agency accounts — individual logins, no shared password | $0 |
| Platforms without team accounts | Restricted SharePoint List (ops-only, versioning enabled) | $0 |
| Long-term all credentials | Bitwarden Teams (encrypted vault, audit log) | ~$3/user/month |

**Immediate action:** Switch Meta and LinkedIn to Business Suite / Team access. This eliminates the highest-risk shared credentials at zero cost.

---

### C7 — SharePoint Storage Governance

**Status:** 1 TB + 10 GB/user available in M365 — no immediate risk at current scale.

**Action:** Establish naming convention and folder structure for the Asset Library on Day 1. Schedule annual archive review of outdated assets.

---

## Part 2: Resources Needed

| Resource | Status | Owner | Action |
|---|---|---|---|
| SharePoint Site Collection Admin rights | Unconfirmed | IT | Submit IT request before build |
| Shared mailbox OAuth access for Power Automate | Unconfirmed | IT | Include in same IT request |
| FERPA review sign-off | Not started | Leadership + WSU FERPA officer | Confirm operational data scope |
| Faculty/staff permanent admin backup | Not identified | Leadership decision | Assign before go-live |
| ~50 hrs build time | Estimated | Operations / MSBA students | Plan sprint schedule |
| Social media platform team access setup | Not started | Operations | Switch before credential vault is built |

---

## Part 3: Business ROI

### Assumptions (conservative — verify with Operations)

| Activity | Current Time/Week | After Automation | Saved/Week |
|---|---|---|---|
| Email sorting & routing | 2.5 hrs | 0.5 hrs | **2.0 hrs** |
| Chasing & compiling weekly reports | 1.5 hrs | 0.25 hrs | **1.25 hrs** |
| Deliverable tracking across Trello boards | 1.0 hr | 0.25 hrs | **0.75 hrs** |
| Meeting minutes collection & filing | 0.5 hrs | 0.17 hrs | **0.33 hrs** |
| Ad-hoc asset requests | 0.5 hrs | 0.0 hrs (self-serve) | **0.5 hrs** |
| Success story tracking | 0.5 hrs | 0.17 hrs | **0.33 hrs** |
| **Total weekly** | **6.5 hrs** | **1.34 hrs** | **5.16 hrs/week** |

| Activity | Current (per semester) | After Automation | Saved |
|---|---|---|---|
| IMPACT operational onboarding (~15 students × 2 hrs) | 30 hrs | 5 hrs | **25 hrs** |

> Note: Onboarding estimate revised down from 3 hrs to 2 hrs per student — HR handles the most time-intensive legal paperwork separately.

---

### Financial ROI

**Assumed labor rate:** $12/hr (WSU student worker — operations role)

| | Current State | Future State | Savings |
|---|---|---|---|
| Weekly operational labor | 6.5 hrs × $12 = **$78/week** | 1.34 hrs × $12 = **$16/week** | **$62/week** |
| Semester operational labor (16 weeks) | **$1,248** | **$256** | **$992/semester** |
| Onboarding labor/semester | 30 hrs × $12 = **$360** | 5 hrs × $12 = **$60** | **$300/semester** |
| **Annual savings (2 semesters)** | | | **~$2,584/year** |

**One-time investment:**

| Item | Cost |
|---|---|
| M365 tools | $0 (existing licenses) |
| Build labor (~50 hrs × $12/hr) | $600 |
| Training (2 hrs × 10 people × $12/hr) | $240 |
| **Total** | **$840** |

**Payback period: ~4 months**

**3-Year ROI:**
```
Net benefit = ($2,584 × 3) - $840 = $6,912
ROI = $6,912 / $840 = 823%
```

---

### Strategic ROI (Non-Financial)

| Benefit | Current State | Future State |
|---|---|---|
| **Program credibility** | Success stories scattered in emails | Searchable database — ready for grant reports and donor presentations |
| **Scalability** | Adding a team requires manual Trello, email chains, folder setup | Adding a team = 45-minute template clone |
| **Data continuity** | Knowledge lives in personal emails and individual boards | All data in centralized SharePoint — survives student turnover |
| **Client confidence** | Ad-hoc project tracking | Structured deliverable tracking with audit trail |
| **Reporting to university/funders** | Manual assembly of metrics | Export from SharePoint Lists in seconds |
| **HR boundary clarity** | Onboarding tasks mixed with legal paperwork | Clean handoff: HR clears → IMPACT activates |

---

### ROI at Scale (5 → 9 Teams)

| Metric | 5 Teams | 9 Teams | Delta |
|---|---|---|---|
| Students tracked | ~30 | ~54 | +24 |
| Weekly report automations | 5 | 9 | +4 (no extra cost) |
| Operational labor without system | 6.5 hrs/week | ~11.7 hrs/week | +5.2 hrs |
| Operational labor with system | 1.34 hrs/week | ~1.8 hrs/week | +0.46 hrs |
| **Annual savings at 9 teams** | $2,584 | **~$4,600** | +$2,016 |

System cost does not scale with team count — ROI grows as teams are added.

---

## Summary: Pre-Build Checklist

| Priority | Item | Owner | Deadline |
|---|---|---|---|
| Critical | Confirm M365 license tier | IT / Leadership | Before build starts |
| Critical | Request SharePoint admin rights + mailbox OAuth | Operations → IT | Before build starts |
| High | Switch social media to native team accounts | Operations | Before credential vault built |
| High | Designate permanent system admin (faculty/staff) | Leadership | Before go-live |
| High | FERPA review — confirm operational data scope | Leadership + FERPA officer | Before Student Roster goes live |
| Medium | Define success story consent language | Leadership | Before Flow 4 build |
| Medium | Asset Library naming convention | Operations | During Hub build |
| Medium | Document all flows in SOP Library | Operations | Before go-live |
