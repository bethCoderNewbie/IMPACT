# Follow-Up Meeting Note
**Meeting:** IMPACT Data Home – Discussion Debrief
**Date:** 2026-03-05
**Based on:** Discussion Memo dated 2026-03-02

---

## How to Read This Note
Each section below covers **one distinct topic** with no overlap. Together, they cover everything discussed.

---

## 1. Why We Are Doing This (The Problem)

**In plain words:**
IMPACT's files, student records, and project work live in too many separate places — personal email, Trello, individual OneDrive folders, and Teams. No one person can see everything at once, and when someone leaves, data goes with them.

**The fix in one sentence:** Build one central "home base" on SharePoint so all teams use the same system, the same rules, and the same files.

---

## 2. What We Are Building (The Solution)

**In plain words:**
A three-level filing system called "Hub-and-Spoke":

| Level | Name | Who Uses It | What It Holds |
|---|---|---|---|
| **Level 1 (Top)** | IMPACT Hub | Everyone can read; only Ops/Leadership can edit | SOPs, branding, announcements, success stories |
| **Level 2 (Middle)** | Operations Site | Leadership & Ops only | Student rosters, finance, onboarding files |
| **Level 3 (Bottom)** | Project Team Sites (5 → 9+) | Each team + Leadership | Project deliverables, meeting notes, task files |

Think of Level 1 as the front desk of a building — everyone sees it. Levels 2 and 3 are back offices with key-card access.

---

## 3. What the System Does Automatically (The Benefits)

**In plain words — four things happen for free once the sites are connected:**

- **One navigation bar** — Students can jump from their project files to the main SOPs page in one click.
- **One search** — Searching on the Hub finds files across all team sites at once (only files you're allowed to see).
- **News rolls up** — When a Team Lead posts an update, Leadership sees it on the Hub homepage automatically.
- **One brand** — Change the logo once at the top; all team sites update instantly.

---

## 4. What We Still Need to Decide (Open Questions)

**In plain words — four decisions are blocking progress:**

| Decision | Who Decides | The Simple Question |
|---|---|---|
| Hub site approval | Leadership + IT Admin | Will IT be asked to register the official IMPACT Hub site? |
| Permanent email owner | Leadership | Is `barton.impact@wichita.edu` the forever owner of all automation, no matter who leaves? |
| Student license check | Leadership + IT Admin | Can student (`@shockers.wichita.edu`) accounts fully use Teams, Planner, SharePoint, and Forms — or are they limited to web-only? |
| Old project data | Leadership | Do we treat old files as non-critical and simply move them to an "Archive" folder? |
| **Who builds and runs the system** | Leadership + IT Admin | See breakdown below. |

### Who Is Responsible — IT or Operations?

Before we can move forward, we need to agree on who owns each task and what IT needs to hand over if Operations takes the lead.

| Task | Who Does It? | If Operations Takes Over — What Do We Need from IT? |
|---|---|---|
| Create new SharePoint sites and Teams | IT (by default) | A step-by-step guide + a one-time admin permission grant so Ops can create sites without filing a ticket each time |
| Connect team sites to the IMPACT Hub | IT (by default) | Hub admin access for at least one Ops member, or a standing IT agreement to process connection requests within 24–48 hrs |
| Set up the shared mailbox (`barton.impact@wichita.edu`) for automation | IT only | IT must grant the mailbox OAuth access to Power Automate — Ops cannot do this without admin rights |
| Ongoing site maintenance (adding members, adjusting permissions) | Operations (preferred) | IT to assign Ops a "Site Collection Admin" role so day-to-day changes don't require IT tickets |

**The key question for Leadership:** Should Operations be empowered to manage the system independently after the initial setup, or will all changes go through IT? The answer determines what admin rights IT needs to permanently hand over.

> **Note on the shared mailbox password:** Ops currently holds the password for `barton.impact@wichita.edu`. This allows Ops to log in and send emails — but it does NOT give admin rights. IT still needs to separately grant the account permission to connect to Power Automate and SharePoint at a system level. Think of it this way: having the key to a mailbox lets you send and receive letters, but it does not make you the building manager who can rewire the electricity or add new rooms.

---

## 5. Who Needs to Do What Next (Action Items)

**In plain words — four workstreams, each with a clear owner:**

| What | Who | Done When |
|---|---|---|
| Approve the 3-level structure and folder names | Leadership & Ops | Formal sign-off received |
| Write the core SOPs (file naming, project lifecycle, communication) | Ops & Team Leads | V1.0 draft complete |
| Build a standard weekly report template for all teams | Team Leads | One shared template agreed upon |
| Move active files into the new Level 2 and Level 3 sites | Operations Team | Priority files migrated |

---

## What Is NOT in Scope (To Avoid Confusion)

- No backend IT configuration beyond the M365 setup
- No automated workflows (Categories B & C) until Level 1 infrastructure is done
- No new tools outside the existing Microsoft 365 licenses

---

**Prepared by:** Operations
**Next check-in:** After Leadership decision on Hub authorization and student license verification
