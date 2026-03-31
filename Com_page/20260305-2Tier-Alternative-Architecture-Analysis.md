# 2-Tier Alternative Architecture Analysis
**Date:** 2026-03-05
**Purpose:** Evaluate a Hub-free 2-tier SharePoint structure that removes IT dependency for initial setup.
**Context:** Alternative to the 3-Tier Hub-and-Spoke model proposed in the Discussion Memo (2026-03-02).

---

## The Core Problem This Solves

The 3-Tier architecture requires IT to register the IMPACT Hub at the tenant level — a step that cannot be delegated. The 2-Tier alternative removes this blocker entirely. Ops can build and launch the full system independently.

---

## Two Versions of 2-Tier — Important Distinction

After cross-referencing the Architecture Plan, there are two ways to build a 2-Tier structure. They are not equal.

| Version | Structure | Verdict |
|---|---|---|
| **Version A** *(original proposal)* | Communication Site + One Teams Group with private channels per project | **Do not use** — breaks Planner, SharePoint Lists, and Flow 3 |
| **Version B** *(recommended)* | Communication Site (no Hub) + Separate Team Sites per project, same as current Tier 3 | **Use this** — only loses the 4 Hub features; everything else works |

---

## Version A — Why It Breaks (Private Channels)

```
┌─────────────────────────────────────────────────────┐
│         TIER 1: IMPACT Communication Site           │
│       (Any M365 user can create this — no IT)       │
│  - SOPs  - Announcements  - Assets  - Success Stories│
│  - Manual links to each Team Site on the home page  │
└─────────────────────────────────────────────────────┘
          ↕ Manual links (no auto-connection)
┌─────────────────────────────────────────────────────┐
│         TIER 2: One Teams Group                     │
│     with Private Channels per Project Team          │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐            │
│  │ Ops Ch.  │ │ Team 1   │ │ Team 2   │  ...        │
│  │(restricted)│ │ Channel  │ │ Channel  │            │
│  └──────────┘ └──────────┘ └──────────┘            │
│  Document libraries only — no SharePoint Lists      │
└─────────────────────────────────────────────────────┘
```

Private channels break three critical components of the Architecture Plan:

| What Breaks | Why |
|---|---|
| **Planner tab per team** | Microsoft does not support Planner inside private channels — Trello replacement fails |
| **SharePoint Lists per team** | Private channel SharePoint sites have severe integration limitations — Planner, connectors, and key app tabs (Tasks, Forms) are unsupported per Microsoft docs; SharePoint Lists as an automation target are unreliable in this context, making List 3 (Weekly Task Reports) unviable |
| **Flow 3 weekly report routing** | With no reliable team-specific SharePoint Lists (see above), Flow 3 has no valid destination to write responses to |

**Conclusion: Version A cannot support the Architecture Plan as designed.**

---

## Version B — Recommended 2-Tier Structure

```
┌─────────────────────────────────────────────────────┐
│         TIER 1: IMPACT Communication Site           │
│       (Any M365 user can create this — no IT)       │
│  - SOPs  - Announcements  - Assets  - Success Stories│
│  - Manual links to each Team Site on the home page  │
└─────────────────────────────────────────────────────┘
          ↕ Manual links (no auto-connection)
        ┌──────────────┬──────────────────────────────┐
        ▼              ▼                              ▼
┌──────────────┐ ┌──────────┐  ┌──────────┐
│  Operations  │ │ Team 1   │  │ Team 2   │  ...
│  Team Site   │ │ Team Site│  │ Team Site│
│  (Ops only)  │ │(full SP) │  │(full SP) │
└──────────────┘ └──────────┘  └──────────┘
  Separate site    Each is a full Teams team with SharePoint
  no private ch.   Lists, Planner, and automation intact
```

**How it works:**
- Tier 1 is a Communication Site — Ops creates with no IT
- Operations data lives in a separate standalone Team Site — Ops creates with no IT
- Each project team is a full Microsoft Teams team with its own SharePoint site — **same as the original Architecture Plan Tier 3, IT still creates these**
- Hub registration step is simply skipped — everything else proceeds unchanged
- Tier 1 home page holds manual links to each team site

---

## What Version B Loses (Hub Features Only)

| Feature Lost | What It Means in Practice | Severity at 5–9 Teams |
|---|---|---|
| Automatic navigation bar | Students need a bookmark or manual link to reach the SOPs page | Medium |
| Cross-site search roll-up | Leadership must search each site separately | Medium |
| News aggregation | Team Lead updates don't roll up — weekly Teams post is the substitute | Low |
| Shared branding propagation | Logo/color changes require manual update per site | Very low |

---

## Scale Assessment

| Factor | 3-Tier with Hub | 2-Tier Version B | Verdict |
|---|---|---|---|
| Current scale (5 teams) | Best | Works fine | 2-Tier B is sufficient |
| Target scale (9 teams) | Best | Still manageable | 2-Tier B still works |
| Beyond 15 teams | Best | Gets messy | 3-Tier wins |
| Hub registration IT dependency | Required | **Removed** | 2-Tier B wins |
| IT still needed per new team | Yes | **Yes — unchanged** | Same |
| Planner per team | Works | Works | Same |
| SharePoint Lists per team | Works | Works | Same |
| Automation flows (1–5) | All work | **All work** | Same |
| Student navigation experience | Seamless | Requires bookmarks | 3-Tier wins |

---

## Recommendation

Use **Version B**. It removes the only hard IT blocker (Hub registration) while keeping every automation, every SharePoint List, and every Planner board from the Architecture Plan intact.

The only things lost are the 4 Hub features — all manageable at 5–9 team scale with minor manual workarounds.

| Phase | Architecture | Trigger to Move Up |
|---|---|---|
| Now (5 teams) | 2-Tier Version B — skip Hub registration | — |
| Near-term (9 teams) | 2-Tier Version B — still manageable | — |
| Future (10+ teams) | Migrate to 3-Tier Hub-and-Spoke | When manual navigation/search becomes a real pain point OR IT relationship is established |

---

## What Ops Needs to Build the 2-Tier Version B System

| Action | Who | IT Required? |
|---|---|---|
| Create the Tier 1 Communication Site | Ops | No — *assumes self-service site creation is enabled in WSU tenant; verify by attempting creation or confirming with IT* |
| Create the standalone Operations Team Site | Ops | No — *same assumption as above* |
| Create each project Teams team (M365 Group) | IT | **Yes — same as original plan, one ticket per team** |
| Set up SharePoint Lists per team site | Ops | No — after IT creates the team |
| Set up Planner tab per team | Ops | No — after IT creates the team |
| Add students to their respective teams | Ops | No |
| Set up Power Automate flows via Send As | Ops | No |
| Grant Ops "Send As" on `barton.impact@wichita.edu` | IT | **Yes — one-time only** |
| ~~Register IMPACT Hub~~ | ~~IT~~ | **Removed — no longer needed** |

The only IT dependency removed compared to the original plan is Hub registration. Everything else is unchanged.

---

## Open Questions — Require Confirmation Before Build

| # | Question | Why It Matters | How to Confirm |
|---|---|---|---|
| 1 | Is self-service site creation enabled in the WSU M365 tenant? | If disabled, Ops cannot create the Tier 1 Communication Site or the Operations Team Site without IT — the "no IT" claim for those steps breaks | Ops attempts to create a Communication Site at `wichita.sharepoint.com`; if blocked, escalate to IT |
| 2 | Is M365 Group creation restricted at WSU (i.e., can only IT create new Teams)? | The plan already assumes IT creates each project team — but if the restriction applies to Ops too, this must be made explicit in the IT request process | IT confirms current group-creation policy; if restricted, the one-ticket-per-team process in the plan is correct and sufficient |
| 3 | Has IT confirmed the one-time "Send As" grant on `barton.impact@wichita.edu`? | Flow 3 (weekly report routing) depends on this — without it, automated emails cannot send from the shared mailbox | IT confirms or schedules the Send As permission grant |
| 4 | Is there a timeline for when IT can provision the first project team site? | The build sequence requires at least one team site to exist before Ops can test Planner, Lists, and automation | Schedule a specific IT ticket with target date |