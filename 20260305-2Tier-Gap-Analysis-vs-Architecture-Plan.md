# 2-Tier Gap Analysis vs. Original Architecture Plan
**Date:** 2026-03-05
**Reference:** `20260226-Architecture Plan.md` vs. `20260305-2Tier-Alternative-Architecture-Analysis.md`
**Purpose:** Identify exactly what the 2-Tier alternative cannot do compared to the original 3-Tier plan.

---

## Critical Finding: Two Different Versions of "2-Tier"

Before listing gaps, there is an important distinction. The proposed 2-Tier uses **private channels inside one Teams group**. But the original Tier 3 uses **separate Teams teams** (each with their own full SharePoint site). These are very different things — and the gap depends entirely on which version of 2-Tier is chosen.

| Version | Structure | Impact |
|---|---|---|
| **2-Tier Version A** *(current proposal)* | Communication Site + One Teams Group with private channels per project | Large gaps — loses Planner, SharePoint Lists, and automation routing |
| **2-Tier Version B** *(alternative)* | Communication Site (no Hub) + Separate Team Sites per project (same as Tier 3, just not Hub-registered) | Small gaps — only loses the 4 Hub features |

The analysis below covers **both versions** so Leadership can choose.

---

## Gap 1 — Planner Tab (CRITICAL for Version A)

**What the plan requires:**
> Each team gets a Planner tab inside their Teams team — replacing Trello.
> `Architecture Plan.md:108` — `└── Planner (tab) ← Replaces Trello (Kanban board)`

**What 2-Tier Version A cannot do:**
Microsoft does not support Planner tabs inside private channels. Private channels have limited app support — Planner is explicitly excluded.

**Impact:** The entire Trello replacement strategy breaks. Teams would need to stay on Trello or use a manual alternative.

**Version B:** Not affected — separate Teams teams fully support Planner tabs.

---

## Gap 2 — SharePoint Lists in Team Sites (CRITICAL for Version A)

**What the plan requires:**
> List 3 (Weekly Task Reports) lives inside each project team's SharePoint site — one list per team.
> `Architecture Plan.md:177` — `Location: Tier 3 — Each Project Team Site`

**What 2-Tier Version A cannot do:**
Private channel SharePoint sites support document libraries only. They do not support custom SharePoint Lists with the field schemas defined in the Architecture Plan (Student Name, Hours, Deliverables, etc.).

**Impact:** Weekly Task Reports cannot be built as designed. The entire per-team data capture layer breaks.

**Version B:** Not affected — separate Team Sites have full SharePoint List support.

---

## Gap 3 — Flow 3 Routing Breaks (CRITICAL for Version A)

**What the plan requires:**
> Flow 3 (Weekly Task Report) sends a form link every Monday and routes responses to each team's specific SharePoint List.
> `Architecture Plan.md:332–340`

**What 2-Tier Version A cannot do:**
If team-specific SharePoint Lists do not exist (Gap 2), Flow 3 has no destination to write to. The automation cannot route responses to 9 private channel sites that have no Lists.

**Impact:** Weekly reporting automation is fully broken. Ops reverts to manual collection.

**Version B:** Not affected — Lists exist per site, Flow 3 works as designed.

---

## Gap 4 — Hub Search Roll-Up (Both Versions)

**What the plan requires:**
> Searching on the IMPACT Hub finds documents across all 9 project sites at once.
> `Architecture Plan.md:57`

**What both 2-Tier versions cannot do:**
Without Hub registration, search is siloed. Leadership must search each site separately to find a file.

**Impact on current scale (5–9 teams):** Medium. Manual workaround is navigating to each site. Manageable but adds friction for Leadership.

---

## Gap 5 — Shared Navigation Bar (Both Versions)

**What the plan requires:**
> The IMPACT Hub navigation bar appears at the top of every project site automatically.
> `Architecture Plan.md:56`

**What both 2-Tier versions cannot do:**
Each site has its own navigation. Students cannot jump from their project folder to the SOP Library in one click — they need a bookmark or a manually placed link.

**Impact:** Low friction for experienced users. High friction for new students unfamiliar with the system.

---

## Gap 6 — News Aggregation for Leadership (Both Versions)

**What the plan requires:**
> Team Lead posts on project sites roll up automatically to the IMPACT Hub homepage for Leadership.
> `Architecture Plan.md:58`

**What both 2-Tier versions cannot do:**
Team Lead updates stay inside their own site. Leadership has no single feed — they must check each team site individually or rely on Teams messages.

**Impact on current scale:** Low. At 5–9 teams, a weekly Teams post from each Team Lead is a workable substitute.

---

## Gap 7 — Shared Branding Propagation (Both Versions)

**What the plan requires:**
> Changing the logo or colors on the Hub updates all project sites automatically.
> `Architecture Plan.md:59`

**What both 2-Tier versions cannot do:**
Branding must be updated manually on each site individually.

**Impact:** Very low. Branding changes are rare. One-time manual effort per site is acceptable.

---

## Gap 8 — Scalability Checklist Changes (Both Versions)

**What the plan requires:**
> "No structural changes needed — the architecture absorbs new teams by design."
> `Architecture Plan.md:385`

**What both 2-Tier versions cannot do:**
Each time a new team is added, Ops must manually:
- Add a new link on the Tier 1 Communication Site home page
- Update any navigation menus manually
- Notify team members of the new entry point

In the 3-Tier plan, Hub association handles this automatically.

**Impact on current scale:** Low. At 5–9 teams, one manual link addition per new team is negligible.

---

## Gap 9 — Pre-Build Verification Items Affected

Two items from the Architecture Plan verification checklist become irrelevant in 2-Tier, and one remains:

| Item | 3-Tier | 2-Tier | Change |
|---|---|---|---|
| V4 — IT registers IMPACT Hub | Required | **Not needed** | Removed — this is the entire point of 2-Tier |
| V5 — Hub association capacity for 9+ sites | Required | **Not needed** | Removed |
| V3 — OAuth consent for Power Automate | Required | **Still required** | Unchanged — mailbox automation still needs OAuth |

---

## Open Questions Resolved or Changed by 2-Tier

| # | Question | 3-Tier Status | 2-Tier Impact |
|---|---|---|---|
| Q8 | Hub capacity — does WSU IT support Hub registration? | Open | **Resolved — no longer needed** |
| Q5 | Confidentiality — NDA data on team sites | Open | Version A: private channels provide partial isolation. Version B: unchanged — same as 3-Tier |
| Q7 | Weekly routing — one Form to 9 lists | Open | Version A: **broken** — no Lists in private channels. Version B: unchanged |

---

## Summary: What You Actually Lose

| Gap | Version A (Private Channels) | Version B (Separate Sites, No Hub) | Severity |
|---|---|---|---|
| Planner tab per team | Lost | Not lost | Critical (A only) |
| SharePoint Lists in team sites | Lost | Not lost | Critical (A only) |
| Flow 3 weekly report routing | Broken | Works | Critical (A only) |
| Hub search roll-up | Lost | Lost | Medium |
| Shared navigation bar | Lost | Lost | Medium |
| News aggregation for Leadership | Lost | Lost | Low |
| Shared branding propagation | Lost | Lost | Very low |
| Auto-scaling on new team add | Lost | Lost | Very low at current scale |

---

## Recommendation

**Do not use Version A (private channels).** It breaks three critical components of the Architecture Plan — Planner, SharePoint Lists, and Flow 3.

**Version B is the correct 2-Tier approach:** Keep separate Team Sites per project exactly as the Architecture Plan specifies, but skip Hub registration. The only things lost are the 4 Hub features — all manageable at 5–9 team scale with minor manual workarounds.

**Version B build path:**
1. Ops creates the Communication Site (Tier 1 equivalent) — no IT needed
2. Ops creates a separate Team Site for Operations (Tier 2) — no IT needed
3. IT creates each Team (M365 Group + Teams) per project — still requires IT per team, same as 3-Tier
4. Hub registration step is simply skipped — everything else in the Architecture Plan proceeds unchanged

**The only IT dependency that remains is creating the M365 Group / Teams team per project.** Hub registration is removed. All automation, SharePoint Lists, Planner, and flows work exactly as designed.
