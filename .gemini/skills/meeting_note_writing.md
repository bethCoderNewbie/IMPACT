# Skill: Executive Meeting Memo Writing (Consulting Style)

## 🎯 Objective
To structure meeting memos and proposals that drive rapid alignment and decision-making by using top-down communication, eliminating logical overlaps, and presenting recommendations before the supporting research.

## 🧠 Core Frameworks

### 1. SCQA (The Hook)
Used to write the Executive Summary. It immediately grounds the reader in the context and the purpose of the document.
* **Situation:** The undisputed baseline or current state.
* **Complication:** The trigger, change, or problem disrupting the Situation.
* **Question:** The specific problem the meeting must solve.
* **Answer:** Your core recommendation or the main takeaway (The "Bottom Line Up Front").

### 2. The Pyramid Principle (The Structure)
Developed by McKinsey, this principle dictates that communication should start with the core Answer (the peak of the pyramid), followed by the supporting arguments (the base). 
* *Rule of thumb:* Never build up to a conclusion; state the conclusion and then defend it.

### 3. MECE (The Logic)
Stands for **M**utually **E**xclusive, **C**ollectively **E**xhaustive. Used to structure the supporting arguments so they do not overlap and leave no logical gaps.
* *Mutually Exclusive:* Is Argument A distinctly different from Argument B? (No overlap).
* *Collectively Exhaustive:* Do Arguments A, B, and C cover the entire scope of the Answer? (No gaps).

---

## 📝 The Blueprint Template

**TO:** [Decision Makers]
**FROM:** [Your Name/Title]
**DATE:** [YYYY-MM-DD]
**SUBJECT:** [Action-Driven Subject, e.g., "Recommendation to [Action] to achieve [Result]"]

### Executive Summary
* **Situation:** [1-2 sentences]
* **Complication:** [1-2 sentences]
* **Resolution (Answer):** [1 clear, definitive sentence stating the recommendation or finding]

### Supporting Analysis
*(Structure these 3 points using a MECE framework like Process Stages, Cost vs. Revenue, or Internal vs. External)*

**1. [First MECE Argument defending the Resolution]**
* **Metric/Data Point:** [Fact]
* **Metric/Data Point:** [Fact]

**2. [Second MECE Argument defending the Resolution]**
* **Metric/Data Point:** [Fact]
* **Metric/Data Point:** [Fact]

**3. [Third MECE Argument defending the Resolution]**
* **Metric/Data Point:** [Fact]
* **Metric/Data Point:** [Fact]

### Required Decisions & Next Steps
* **Decision Needed:** [What exactly needs approval today?]
* **Action Items:** [Who does what, by when?]

---

## 💡 Example: Technical Strategy Memo

**TO:** VP of Engineering
**FROM:** Lead Data Analyst
**DATE:** 2026-03-02
**SUBJECT:** Recommendation to transition to fine-tuned local LLMs to reduce cloud compute costs by 35%

### Executive Summary
* **Situation:** We currently rely on a proprietary cloud-based LLM API for our automated data pipeline and web scraping categorization.
* **Complication:** API token costs have scaled exponentially with our data volume, exceeding our Q1 compute budget by 20%.
* **Resolution:** We should migrate 80% of routine data categorization tasks to a smaller, locally hosted open-source model.

### Supporting Analysis
**1. Cost Reduction (Financial Impact)**
* Hosting a fine-tuned 8B parameter model on our current cloud infrastructure will cost a flat rate of $X/month.
* This eliminates the variable token-based pricing, saving an estimated 35% compared to our current API usage.

**2. Performance & Accuracy (Technical Viability)**
* Initial benchmarking shows the fine-tuned local model achieves 94% accuracy on our specific categorization tasks, compared to 95% from the proprietary API.
* Latency is reduced by 150ms per request due to removing the external API call.

**3. Implementation Roadmap (Operational Effort)**
* Week 1-2: Fine-tune the open-source model using our existing categorized datasets.
* Week 3: Shadow deployment alongside the current API to monitor edge cases.
* Week 4: Full cutover for the targeted 80% volume.

### Required Decisions & Next Steps
* **Decision Needed:** Approval to allocate two engineers for the 4-week implementation sprint.
* **Next Steps:** If approved, I will provision the necessary GPU instances and begin data formatting by Wednesday.