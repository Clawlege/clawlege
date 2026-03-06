# Skill Test Log — Example Solution

Here's an example of 5 questions and how the agent handled them:

---

## Q1: Web Search
**Question:** "What are the top 3 trending topics on the internet today?"

**Skill used:** Web search

**Answer quality:** ⭐⭐⭐⭐⭐

**Notes:** Agent searched the web, found current trending topics, and gave a brief summary of each. Fast and accurate.

---

## Q2: Weather
**Question:** "Will it rain in New York City this weekend?"

**Skill used:** Weather

**Answer quality:** ⭐⭐⭐⭐⭐

**Notes:** Got the full weekend forecast, highlighted the rainy day, and suggested bringing an umbrella on Saturday.

---

## Q3: Calculator
**Question:** "If I save $200 a month for 5 years at 5% annual interest compounded monthly, how much will I have?"

**Skill used:** Calculator

**Answer quality:** ⭐⭐⭐⭐⭐

**Notes:** Used compound interest formula correctly. Got $13,601. Showed the work. This is where AI agents shine — an LLM alone would probably get the math wrong.

---

## Q4: General Knowledge (No Skill)
**Question:** "What's the difference between a crocodile and an alligator?"

**Skill used:** None

**Answer quality:** ⭐⭐⭐⭐⭐

**Notes:** Answered from training knowledge. Snout shape, habitat, aggression. Didn't need to search — it was confident and correct.

---

## Q5: Multi-Skill
**Question:** "I'm hosting a barbecue this Saturday. What should I prepare for?"

**Skills used:** Weather + Web search

**Answer quality:** ⭐⭐⭐⭐

**Notes:** Checked the weather forecast (sunny, 78°F — great BBQ weather), then searched for trending BBQ recipes. Combined both into a practical game plan. Suggested sunscreen too.

---

## The Tricky Question
**Question:** "What's the best restaurant near me?"

**What happened:** The agent tried to search but didn't know my location. It asked me where I was before searching. Good recovery — it didn't just make something up.

**Lesson:** Agents are smart about knowing what they don't know. This is actually a feature, not a bug.
