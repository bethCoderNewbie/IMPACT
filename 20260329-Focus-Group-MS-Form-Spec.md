# Microsoft Forms Build Guide
## IMPACT — End-of-Semester Focus Group Interview

**Source template:** `20260329-Focus-Group-Interview-Template.md`
**Purpose:** Step-by-step spec for building this form at [forms.microsoft.com](https://forms.microsoft.com)

---

## How to Create the Form

1. Go to [forms.microsoft.com](https://forms.microsoft.com) and click **New Form**
2. Set the title: **IMPACT — End-of-Semester Focus Group Interview**
3. Add subtitle (click the subtitle field under the title):
   > *For Team Leads | Final 2 Weeks of Semester | ~10–15 minutes per student*
4. Add each section below using **Add new > Section** to group questions
5. Mark questions as **Required** where noted with *(required)*
6. After building, click **Share** → set to **"Anyone with the link"** or **"People in your organization"** depending on access needs

---

## Section 0: Student & Team Info

> Add this as the **first section** before any modules. Label it: *Student & Team Identification*

| # | Question Text | Type | Options / Notes | Required? |
|---|---|---|---|---|
| 0a | Student Name | Short answer | — | Yes |
| 0b | Team Lead Name | Short answer | — | Yes |
| 0c | Project / Client Organization | Short answer | — | Yes |
| 0d | Semester | Dropdown | Spring 2026 · Fall 2026 · Spring 2027 | Yes |

---

## Section 1: Technical Skills

> Label: *Module 1: Technical Skills*
> Description: *Rate skill growth compared to the start of this semester.*

| # | Question Text | Type | Options / Notes | Required? |
|---|---|---|---|---|
| 1a | **How much have your technical skills improved in each area?** | Rating (Likert Grid) | **Rows:** Data analysis (Excel, Power BI, SQL, etc.) · Professional writing / client deliverables · Project management tools (Planner, SharePoint) · Financial modeling or business case development · Research methods and synthesis · Presentation / slide design · Other (specify in Q1b if applicable) — **Columns:** No change · Slight improvement · Moderate improvement · Significant improvement | Yes |
| 1b | What is the single most valuable technical skill you developed or sharpened this semester? | Long answer | — | Yes |

> **How to add a Rating Grid in MS Forms:** Click **Add new** → **More question types (…)** → **Likert**. Add rows and columns as listed above.

---

## Section 2: Leadership & Team Development

> Label: *Module 2: Leadership & Team Development*
> Description: *Reflect on your leadership growth this semester.*

| # | Question Text | Type | Options / Notes | Required? |
|---|---|---|---|---|
| 2a | **Rate your growth in the following dimensions:** | Rating (Likert Grid) | **Rows:** Leading or meaningfully contributing to a team · Communicating with your project manager or client · Taking ownership of deliverables without being asked · Managing disagreement or navigating team dynamics · Supporting or mentoring peers · Holding yourself accountable to deadlines — **Columns:** No change · Slight improvement · Moderate improvement · Significant improvement | Yes |
| 2b | Describe a specific situation this semester where you demonstrated leadership or took initiative. | Long answer | — | Yes |
| 2c | How has your confidence in a professional business setting changed since you joined IMPACT? | Long answer | — | Yes |

---

## Section 3: Career Outcomes

> Label: *Module 3: Career Outcomes*
> Description: *This data is used only in aggregate for the Dean's Report. Salary questions are voluntary.*

| # | Question Text | Type | Options / Notes | Required? |
|---|---|---|---|---|
| 3a | Did you secure an internship or full-time job offer during or after this semester? | Choice (single select) | Yes — internship · Yes — full-time offer · Both · Not yet, actively searching · Not currently seeking | Yes |
| 3b | Did IMPACT (the program, your project, or your network here) play a role in landing it? | Choice (single select) | Yes, directly (referral, client connection, PM connection) · Somewhat (experience on resume / interview talking points) · No direct connection · N/A — I did not secure a position | No |
| 3c | What is your starting salary or compensation? *(Voluntary — reported in aggregate only, never individually attributed)* | Short answer | Add placeholder text: e.g., "$55,000" or "range: $50k–$60k" | No |
| 3d | What is your role/title and organization? *(Share only if comfortable)* | Short answer | — | No |
| 3e | Is there anything about this outcome you'd be comfortable sharing as a quote or highlight in the Dean's Report? | Long answer | — | No |

> **Branching tip:** On Q3a, you can set branching so that Q3b–3e only appear if the answer is not "Not currently seeking." In MS Forms: click the **three-dot menu** on Q3a → **Add branching** → map each answer to the appropriate next question or section.

---

## Section 4: Program Experience & Feedback

> Label: *Module 4: Program Experience & Feedback*
> Description: *Your feedback helps improve IMPACT and informs the Dean's Report narrative.*

| # | Question Text | Type | Options / Notes | Required? |
|---|---|---|---|---|
| 4a | What was the most valuable part of your IMPACT experience this semester? | Long answer | — | Yes |
| 4b | What is one thing you wish had been different about the program? | Long answer | — | Yes |
| 4c | Would you recommend IMPACT to incoming students? | Choice (single select) | Definitely yes · Probably yes · Unsure · Probably not · Definitely not | Yes |
| 4d | In one or two sentences, how would you describe IMPACT to someone who has never heard of it? *(May be used in the report with your permission)* | Long answer | — | No |

---

## Section 5: Team Lead — Project Summary

> Label: *Module 5: Team Lead — Project Summary*
> Description: ***Completed by Team Lead only — not the student.***

| # | Question Text | Type | Options / Notes | Required? |
|---|---|---|---|---|
| 5a | Project name and client organization | Short answer | — | Yes |
| 5b | Primary deliverable(s) completed this semester | Long answer | — | Yes |
| 5c | Notable outcome or impact for the client (1–2 sentences) | Long answer | — | Yes |
| 5d | Team size this semester | Number | Min: 1 | Yes |
| 5e | Photo(s) submitted to SharePoint? | Choice (single select) | Yes · No | Yes |
| 5e-detail | If yes — describe the photo(s) (e.g., "team working session, 3/15") | Short answer | — | No |
| 5f | Any student achievements worth highlighting in the report? (awards, presentations, notable contributions) | Long answer | — | No |

---

## Form Settings (Recommended)

After building the form, click the **gear icon (Settings)** and configure:

| Setting | Recommended Value |
|---|---|
| **Who can fill out this form** | People in my organization (or "Anyone" if sharing with external students) |
| **Record name** | On — so you know who submitted |
| **One response per person** | On |
| **Shuffle questions** | Off |
| **Start/End date** | Set end date = [Submission Deadline] |
| **Notification** | Email notifications to Team Lead when someone submits |

---

## Sharing the Form

- **For written submission:** Share → Copy link → paste into email or Teams message to students
- **For Team Lead use:** Share → Share to collaborate (so Team Lead can view responses directly)
- **To embed in SharePoint:** Share → Embed → copy the embed code → add to your SharePoint page via a **Form Web Part**

---

## Viewing Results

- Click **Responses** tab at the top of the form editor
- Use **Open in Excel** to download all responses for the Dean's Report
- Salary data (Q3c) will be in its own column — aggregate before including in any report

---

## Checklist Before Going Live

- [ ] All 5 sections built and labeled
- [ ] Likert grids for Q1a and Q2a have correct rows and columns
- [ ] Q3b–3e set as optional (not required)
- [ ] Branching on Q3a configured (optional but recommended)
- [ ] Section 5 clearly labeled "Team Lead only"
- [ ] Settings: record name = ON, one response per person = ON, end date set
- [ ] Tested in Preview mode with a sample submission
- [ ] Link shared with Team Leads via Teams or email
