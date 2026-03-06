# 🏆 Module 2 Challenge: The Skill Test

## Your Mission

Ask your agent 5 different questions that each require a different skill (or combination of skills). Document what happened.

## Requirements

1. **Ask 5 questions**, each designed to trigger different behavior:
   - One that needs **web search** (current events, recent info)
   - One that needs **weather** (forecast, conditions)
   - One that needs **math/calculator** (computation)
   - One that needs **no skill at all** (general knowledge)
   - One that needs **multiple skills combined** (complex question)

2. **For each question, write down:**
   - The question you asked
   - Which skill(s) your agent used
   - Whether the answer was actually helpful

3. **Find a question that trips your agent up.** Every agent has blind spots. What question did yours struggle with? Why do you think that happened?

## Example Log

```
Q1: "What's the current temperature in Reykjavik?"
Skill used: Weather
Answer quality: ⭐⭐⭐⭐⭐ — accurate and fast

Q2: "What's 15% tip on a $47.83 dinner bill?"
Skill used: Calculator
Answer quality: ⭐⭐⭐⭐⭐ — got $7.17, also showed 18% and 20%

Q3: "Who won the latest Formula 1 race?"
Skill used: Web search
Answer quality: ⭐⭐⭐⭐ — found it, but included some irrelevant info

Q4: "Why is the sky blue?"
Skill used: None (answered from knowledge)
Answer quality: ⭐⭐⭐⭐⭐ — great explanation

Q5: "I'm going to London next week. What should I pack?"
Skills used: Weather + Web search
Answer quality: ⭐⭐⭐⭐ — checked forecast, suggested layers and umbrella
```

## Bonus Points

- 🌟 Find a question where the agent uses a skill when it shouldn't (or doesn't when it should)
- 🌟 Ask the same question in two different ways and see if the agent picks different skills
- 🌟 Try to ask something that genuinely surprises you with how well it handles it

## When You're Done

You should have a log of 5+ questions with skill observations. You now understand how your agent thinks about tool use — that understanding will be important as we add more capabilities.

Check [solution/](solution/) for an example log.
