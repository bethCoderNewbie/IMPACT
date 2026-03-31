# Follow-Up Meeting Note
**Meeting:** IMPACT Data Home – Discussion Debrief
**Date:** 2026-03-05
**Based on:** Discussion Memo dated 2026-03-02

---

## 1. Why We Are Doing This (The Problem)

**In plain words:**
IMPACT's files, student records, and project work live in too many separate places — personal email, Trello, individual OneDrive folders, and Teams. No one person can see everything at once, and when someone leaves, data goes with them.

**The fix in one sentence:** Build one central "home base" on SharePoint so all teams use the same system, the same rules, and the same files.

---

## 2. Two Options for the Structure

We have two valid ways to build this. The difference comes down to one step: whether IT registers an official "Hub" site at the top.

### Option A — 3-Tier with Hub (Original Plan)

| Level | Name | Who Uses It | What It Holds |
|---|---|---|---|
| **Level 1** | IMPACT Hub | Everyone reads; Ops/Leadership edits | SOPs, branding, announcements, success stories |
| **Level 2** | Operations Site | Leadership & Ops only | Student rosters, finance, onboarding files |
| **Level 3** | Project Team Sites (one per team) | Each team + Leadership | Project files, tasks, meeting notes |

- All three levels are connected automatically by Microsoft.
- Students can navigate, search, and see updates across all sites in one click.
- **Blocker:** IT must register the Hub site at a tenant level. This cannot be done by Ops.

### Option B — 2-Tier without Hub (Recommended to Start)

| Level | Name | Who Uses It | What It Holds |
|---|---|---|---|
| **Level 1** | IMPACT Communication Site | Everyone reads; Ops/Leadership edits | SOPs, branding, announcements, success stories |
| **Level 2** | Operations Site + Project Team Sites | Ops/Leadership; each team | Same as Option A — just not auto-connected |

- Ops creates Level 1 with no IT needed (see Open Question 1 below).
- Each project team site is created by IT — same process as Option A, one ticket per team.
- Level 1 links to each team site manually (a list of links on the homepage).
- **No Hub registration required** — the one hard IT blocker is removed.

---

## 3. Side-by-Side Comparison

| Factor | 3-Tier with Hub | 2-Tier without Hub |
|---|---|---|
| Works at 5 teams (now) | Yes | Yes |
| Works at 9 teams (near-term) | Yes | Yes — manageable |
| Works beyond 15 teams | Best option | Gets harder to manage |
| Requires IT to register Hub | **Yes — hard blocker** | **No — removed** |
| Requires IT per new team site | Yes | Yes — same |
| Planner per team | Works | Works |
| SharePoint Lists per team | Works | Works |
| All 5 automation flows | All work | All work |
| Students navigate between sites | One click | Bookmark or manual link |
| Search across all sites at once | Yes — built in | No — search each site separately |
| News from teams rolls up | Yes — automatic | No — weekly Teams post substitute |
| Logo/color changes everywhere | One change, all sites update | Must update each site manually |

**Verdict:** 2-Tier works fine at current and near-term scale. The only losses are navigation comfort and auto-aggregation — manageable at 5–9 teams. When teams grow past 10 or IT relationship is established, migrate to 3-Tier.

---

## 4. Limitations of the 2-Tier Structure

These are real trade-offs — not blockers, but the team should know them before deciding.

| Limitation | What It Means in Practice | How We Work Around It |
|---|---|---|
| No automatic navigation bar | Students must bookmark the SOPs site or use a manual link | Ops adds a clearly labeled links section on the Level 1 homepage |
| No cross-site search | Leadership cannot search all project files from one place | Each team site must be searched separately |
| No automatic news roll-up | Team Lead updates stay on their team site only | Weekly Teams channel post covers this |
| Manual branding updates | Changing the logo requires editing each site individually | Low effort at 5–9 sites; only a problem beyond ~15 |
| No "Version A" private channels | Using private channels inside one Team breaks Planner and List automation | Use separate Team Sites per project (Version B) — this is already the plan |

---

## 5. Critical Open Questions for IT

These must be answered before we start building. They are yes/no questions — no major work on IT's side.

| # | Question for IT | Why It Blocks Us |
|---|---|---|
| **1** | Is self-service site creation enabled in the WSU tenant? Can Ops create a Communication Site without filing a ticket? | If no, Ops cannot build Level 1 — the main "no IT needed" claim for 2-Tier breaks |
| **2** | Is M365 Group creation restricted? Can only IT create new Teams, or can Ops do it? | Determines whether the one-ticket-per-team process is required or optional |
| **3** | Will IT grant "Send As" on `barton.impact@wichita.edu` to Power Automate? This is a one-time setup. | All automated weekly report emails depend on this. Without it, Flow 3 cannot send from the shared mailbox |
| **4** | Can student accounts (`@shockers.wichita.edu`) use Teams, Planner, SharePoint, and Forms — or are they web-only? | If students are limited, the Planner tab (Trello replacement) and Forms (weekly report) may not work on their devices |
| **5** | What is IT's expected turnaround time to create one project Team Site after a ticket is filed? | Determines the build sequence — Ops cannot set up Lists, Planner, or automation until the site exists |

> **Note on the shared mailbox password:** Ops holds the password for `barton.impact@wichita.edu`. That allows logging in and sending email manually — but it does NOT give admin rights. IT must separately authorize the account to connect to Power Automate at a system level. Having the mailbox password is like having a key to a P.O. box — it lets you send letters, but it does not let you wire up the automatic mail sorter in the back room.

---

## 6. What Happens Next (Action Items)

| What | Who | Done When |
|---|---|---|
| Answer the 5 IT open questions above | Leadership + IT Admin | Before any build starts |
| Choose between 3-Tier and 2-Tier (recommend 2-Tier to start) | Leadership | After IT answers questions 1–2 |
| Confirm `barton.impact@wichita.edu` Send As grant (Q3) | IT | One-time, before automation setup |
| Write core SOPs (file naming, project lifecycle, communication) | Ops & Team Leads | V1.0 draft complete |
| Build a standard weekly report template | Team Leads | One shared template agreed upon |
| Move active files into the new sites | Operations Team | Priority files migrated |

---

## What Is NOT in Scope

- No automation flows until Level 1 site exists and IT questions are answered
- No new tools outside existing Microsoft 365 licenses
- No backend IT configuration beyond M365 setup

---

**Prepared by:** Operations
**Next check-in:** After IT answers Open Questions 1–5
