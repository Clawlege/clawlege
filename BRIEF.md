# Clawlege — Build Brief

## What We're Building
Clawlege (clawlege.com) is a FREE, open source interactive learning platform that teaches anyone — kids, teens, and non-technical adults — how to build AI agents using OpenClaw.

It ships as a downloadable GitHub repo with:
1. Interactive curriculum (8 modules)
2. Starter agent templates
3. A basic landing page (static HTML/CSS, deployable to GitHub Pages)

## Key Design Principles
- **No coding required for Modules 1-3** — uses plain English config files (SOUL.md, USER.md, MEMORY.md)
- **Runs 100% locally** — no cloud, no accounts
- **Progressive difficulty** — "never coded before" → "I built an AI agent"
- **Fun and engaging** — not dry docs. Personality, humor, challenges.
- **Works for ALL ages** — 10-year-old and 50-year-old should both feel welcome

## Repo Structure
```
clawlege/
  README.md                    # Project overview, how to get started
  docs/
    landing-page/              # Static site for clawlege.com (GitHub Pages)
      index.html
      style.css
      assets/
  modules/
    01-meet-your-agent/
      README.md                # Lesson content (interactive, step-by-step)
      challenge.md             # End-of-module challenge
      solution/                # Example solution
    02-give-it-skills/
      README.md
      challenge.md
      solution/
    03-memory-and-personality/
      README.md
      challenge.md
      solution/
    04-connect-to-the-world/
      README.md
      challenge.md
      solution/
    05-build-something-unique/
      README.md
      challenge.md
      solution/
    06-hardware-week/
      README.md
      challenge.md
      solution/
    07-polish-and-ship/
      README.md
      challenge.md
      solution/
    08-demo-day/
      README.md
      challenge.md
  templates/
    personal-assistant/        # Starter agent: daily briefing, calendar, reminders
      SOUL.md
      USER.md
      AGENTS.md
    homework-helper/           # Starter agent: research, summarize, explain
      SOUL.md
      USER.md
      AGENTS.md
    sports-tracker/            # Starter agent: scores, standings, player stats
      SOUL.md
      USER.md
      AGENTS.md
    weather-buddy/             # Starter agent: forecasts, outfit suggestions
      SOUL.md
      USER.md
      AGENTS.md
    recipe-finder/             # Starter agent: meal planning, grocery lists
      SOUL.md
      USER.md
      AGENTS.md
  CONTRIBUTING.md              # How to contribute lessons/templates
  LICENSE                      # MIT
```

## Module 1: Meet Your Agent (WRITE IN FULL)
Teach the user to:
- What is an AI agent? (not a chatbot — an agent that DOES things)
- Install OpenClaw (npm install -g openclaw)
- Run the setup wizard (openclaw setup)
- Understand SOUL.md — this is your agent's personality
- Write their first SOUL.md from scratch
- Give the agent a name
- First conversation with their agent
- Challenge: Agent introduces itself with personality that makes you smile

Tone: Friendly, encouraging, slightly irreverent. Like a cool older sibling teaching you something awesome. Use emoji sparingly. Include "Try it now!" moments every few paragraphs.

## Module 2: Give It Skills (WRITE IN FULL)
Teach the user to:
- What are skills? (tools your agent can use)
- Built-in skills: web search, weather, calculator
- Enable skills in config
- Watch your agent USE a skill in real-time
- Understanding when the agent decides to use which skill
- Challenge: Ask your agent 5 different real questions that require different skills

## Module 3: Memory & Personality (WRITE IN FULL)
Teach the user to:
- What is agent memory? (MEMORY.md, daily files)
- USER.md — teach your agent about YOU
- AGENTS.md — your agent's operating manual
- Watch memory persist across conversations
- The magic of context: why agents with memory feel different
- Challenge: Have a conversation, close it, reopen — agent remembers

## Modules 4-8: Write detailed README outlines (not full content yet)

## Landing Page
- Clean, modern, fun design
- Hero: "Learn to build your own AI agent. Free. Open source."
- What you'll learn (8 modules overview)
- For everyone: kids, teens, adults
- Starter templates preview
- CTA: "Start Learning" → links to GitHub repo
- Footer: "A Clawnagers project" → links to clawnagers.com
- Built with: simple HTML/CSS/JS, no framework, deployable to GitHub Pages
- Color scheme: dark theme with claw-orange (#FF6B35) accent

## Important
- OpenClaw is a REAL product (openclaw.ai). Reference it accurately.
- The learning modules should feel like a journey, not documentation.
- Every module should have a "what you built" summary at the end.
- Include estimated time per module (Module 1 ~30 min, etc.)
- Make it so good that someone shares it with friends.
