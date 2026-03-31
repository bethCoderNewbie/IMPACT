# IMPACT — AoL Folder Structure Guide
## 5-Year AACSB Review Organization

**Purpose:** Establish a folder structure that makes IMPACT's Assurance of Learning evidence immediately navigable for an AACSB review team — who will arrive with no prior knowledge of the program and need to find evidence of defined outcomes, embedded assessment, and continuous improvement within a single site visit.
**Applies to:** SharePoint Hub SOP Library → `AoL Records` folder
**Owner:** Operations Lead (maintain structure each semester)
**Review cycle:** Updated at the start of each semester

---

## What AACSB Reviewers Are Looking For

When an AACSB review team opens your AoL folder, they are checking for four things in order:

1. **Defined outcomes** — "We know what we're trying to teach."
2. **Embedded assessment** — "We measured it using instruments inside the program, not just surveys."
3. **Evidence of achievement** — "Here is what students actually did."
4. **Closed-loop improvement** — "Here is what we changed because of what we found."

Every folder and file in this structure is designed to answer one of those four questions directly.

---

## Top-Level Folder Structure

```
AoL Records/
│
├── 00-Program-Foundations/          ← "We know what we're trying to teach"
│
├── Spring-2026/                     ← Current semester (one folder per semester)
│   ├── 01-Assessment-Data/
│   ├── 02-Results-and-Analysis/
│   └── 03-Closing-the-Loop/
│
├── Fall-2026/                       ← Next semester (create before it starts)
│   ├── 01-Assessment-Data/
│   ├── 02-Results-and-Analysis/
│   └── 03-Closing-the-Loop/
│
└── [Repeat for each semester in the 5-year review window]
```

---

## Folder Descriptions

---

### `00-Program-Foundations/`

**Purpose:** Stable documents that define what IMPACT is and what it teaches. These rarely change — when they do, keep the old version with a date stamp.

**Required files:**

| File | Contents | Review Frequency |
|---|---|---|
| `AACSB-Learning-Outcomes.md` | The 5 defined learning outcomes with AACSB domain mapping | Update only when LOs change |
| `Assessment-Instruments-Overview.md` | One-page description of all instruments (Focus Group + Master Rubric + Client Feedback) | Update when instruments change |
| `Program-Mission-Alignment.md` | How IMPACT maps to the Barton School's mission | Update when Barton mission changes |
| `AOL-Roles-and-Responsibilities.md` | Who does what: Faculty Liaison, Operations, PM, Leadership | Update each semester if roles change |

**Note:** The `20260226-AACSB Learning Outcomes.md` file already in `Dean_report/` is the source document for this folder. Copy it here when filing.

---

### `[Semester-Year]/01-Assessment-Data/`

**Purpose:** Raw evidence — the actual completed instruments. This is where an AACSB reviewer looks to confirm that assessment happened.

**Required files:**

| File | Contents | Owner |
|---|---|---|
| `Focus-Group-Summaries/` | Subfolder: one completed interview per student (or aggregate summary if individual files not kept) | Team Leads → Operations |
| `PM-Rubric-Scorecards/` | Subfolder: one completed Master Assessment Rubric per student | PMs → Operations |
| `Client-Feedback/` | Subfolder: completed client feedback forms (if collected) | Operations |
| `Cohort-Roster.md` | List of all students assessed: name, team, major, assessment completed Y/N | Operations |

**File naming convention:**
```
Focus-Group-Summaries/
  FG-[StudentLastName]-[Team]-Spring2026.md

PM-Rubric-Scorecards/
  Rubric-[StudentLastName]-[Team]-Spring2026.md
```

**Anonymization rule:** Before sharing with AACSB reviewers, Operations creates a de-identified copy of this folder in `02-Results-and-Analysis/` that replaces student names with codes (e.g., S01, S02). The named originals stay in `01-Assessment-Data/` under restricted access.

---

### `[Semester-Year]/02-Results-and-Analysis/`

**Purpose:** The aggregated, analyzed data. This is where the numbers live — achievement rates, score distributions, patterns.

**Required files:**

| File | Contents | Owner |
|---|---|---|
| `AOL-Achievement-Summary.md` | Cohort achievement rates per LO vs. targets (fills the table in the Closing-the-Loop Memo) | Operations |
| `Score-Distribution-Table.md` | Count of students at each level (4/3/2/1) per LO | Operations |
| `Qualitative-Evidence-Excerpt.md` | De-identified quotes from focus group interviews, organized by LO | Operations |
| `De-identified-Rubric-Data.xlsx` or `.md` | All rubric scores with student names replaced by codes | Operations |

**Excel/Sheet template for `Score-Distribution-Table`:**

| LO | Exceeds (4) | Meets (3) | Approaching (2) | DNM (1) | N/O | Total | % Meets/Exceeds |
|---|---|---|---|---|---|---|---|
| LO1 | | | | | | 30 | |
| LO2 | | | | | | 30 | |
| LO3 | | | | | | 30 | |
| LO4 | | | | | | 30 | |
| LO5 | | | | | | 30 | |

---

### `[Semester-Year]/03-Closing-the-Loop/`

**Purpose:** The improvement evidence. This is the section AACSB reviewers check most carefully — many programs fail here because they collect data but never document what they did with it.

**Required files:**

| File | Contents | Owner |
|---|---|---|
| `Closing-the-Loop-Memo-[Semester]-[Year].md` | Completed memo from the template | Faculty Liaison + Operations |
| `Action-Items-Tracker.md` | Running list of decisions made + implementation status | Operations |
| `SOP-Change-Log.md` | Which SOPs or program documents were updated as a result of AOL findings | Operations |

**`Action-Items-Tracker.md` structure:**

| # | Finding | Decision | Owner | Target Semester | Status | Evidence of Impact |
|---|---|---|---|---|---|---|
| 1 | [Finding from this semester] | [Decision] | [Name] | [Next semester] | ☐ Not started / ☐ In progress / ☐ Complete | [To be filled next semester] |

---

## Complete Filing Checklist (end of each semester)

Operations completes this checklist before the semester is officially closed for AOL purposes.

**Within 2 weeks of semester end:**
- [ ] All Focus Group Interview documents collected from team leads and filed in `01-Assessment-Data/Focus-Group-Summaries/`
- [ ] All PM Master Assessment Rubrics collected and filed in `01-Assessment-Data/PM-Rubric-Scorecards/`
- [ ] Cohort Roster updated: mark assessment complete Y/N per student
- [ ] Client feedback collected (if applicable) and filed

**Within 3 weeks of semester end:**
- [ ] `AOL-Achievement-Summary.md` completed — achievement rates vs. targets
- [ ] `Score-Distribution-Table` completed
- [ ] `Qualitative-Evidence-Excerpt.md` completed — 4–6 quotes per LO

**Before next semester begins:**
- [ ] `Closing-the-Loop-Memo-[Semester]-[Year].md` completed and signed by Faculty Liaison and Program Director
- [ ] `Action-Items-Tracker.md` updated with decisions from this semester's data
- [ ] `SOP-Change-Log.md` updated if any SOPs were changed
- [ ] New semester folder created (`Fall-2026/` with subfolders) and ready to receive data

---

## 5-Year Review Readiness Check

An AACSB review team will typically request access to 5 years of AOL records. Use this checklist to verify the folder is review-ready at any point.

| Check | Question | Status |
|---|---|---|
| Foundations present | `00-Program-Foundations/` contains current learning outcomes, instrument descriptions, and role assignments | ☐ |
| All semesters filed | One folder per semester in the 5-year window, each with all 3 subfolders | ☐ |
| Data present | `01-Assessment-Data/` in each semester has evidence that assessment was conducted | ☐ |
| Results documented | `02-Results-and-Analysis/` in each semester has achievement rates vs. targets | ☐ |
| Loop closed | `03-Closing-the-Loop/` in each semester has a signed memo with specific decisions | ☐ |
| Improvement chain | At least 2 consecutive semesters show: decision made → change implemented → evidence of impact | ☐ |
| Faculty involvement | Faculty Liaison signature appears on Closing-the-Loop Memos | ☐ |
| No gaps | No semester in the review window is missing any required file | ☐ |

---

## Spring 2026 Baseline Note

Spring 2026 is the **first semester of formal AACSB AOL documentation** for IMPACT. The following applies:

- The Closing-the-Loop Memo for Spring 2026 should clearly state: *"This is the baseline semester. Prior AOL records do not exist. The improvement chain begins here."*
- Part 5 of the Closing-the-Loop Memo (evidence of change from prior semester) should be marked "First cycle — no prior semester."
- AACSB accepts a first-cycle baseline as valid evidence, provided the subsequent semester shows that the decisions from the baseline were actually implemented.
- The most important thing to get right in Spring 2026 is **Part 4 of the Closing-the-Loop Memo** — specific, named decisions with owners, timelines, and measurable success criteria. A vague baseline memo produces a weak improvement chain.

---

## Quick Reference — What Goes Where

| You have... | File it in... |
|---|---|
| A completed student focus group interview | `[Semester]/01-Assessment-Data/Focus-Group-Summaries/` |
| A completed PM assessment rubric | `[Semester]/01-Assessment-Data/PM-Rubric-Scorecards/` |
| The aggregated achievement rates table | `[Semester]/02-Results-and-Analysis/AOL-Achievement-Summary.md` |
| A student quote to use as evidence | `[Semester]/02-Results-and-Analysis/Qualitative-Evidence-Excerpt.md` |
| The signed improvement memo | `[Semester]/03-Closing-the-Loop/Closing-the-Loop-Memo-[Semester]-[Year].md` |
| A change to an SOP driven by AOL findings | `[Semester]/03-Closing-the-Loop/SOP-Change-Log.md` AND the SOP itself |
| The Dean's Bound Report | `[Semester]/03-Closing-the-Loop/` as Appendix E of the memo |
| A new version of the Learning Outcomes document | `00-Program-Foundations/` (archive the old version as `AACSB-Learning-Outcomes-[Date].md`) |
