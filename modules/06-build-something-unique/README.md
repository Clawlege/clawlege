# Module 6: Build Something Unique

**⏱ Time: ~90 minutes | 🟡 Difficulty: Intermediate | 💻 Coding: Optional**

You've followed tutorials for five modules. You've installed things, configured things, copied examples, and typed exactly what we told you to type.

That phase is over.

This module is about building something that doesn't exist yet — something that comes from *your* brain, solves *your* problem, and feels like *yours*. No more hand-holding. You're the architect now.

---

## Why This Module Exists

Here's a truth about learning: tutorials teach you how tools work. They don't teach you how to *think* with those tools.

The gap between "I completed a tutorial" and "I built something real" is where most people get stuck. They finish the course, close the laptop, and never build anything on their own. Not because they can't — but because nobody showed them how to go from blank page to working project.

That's what this module fixes.

By the end, you'll have a fully custom AI agent that solves a real problem in your actual life. Not a toy. Not a demo. Something you'll keep using after the course is over.

---

## Part 1: What Should I Build?

### The Annoyance Audit

The best agent ideas don't come from brainstorming about "cool AI projects." They come from paying attention to the stuff that annoys you.

Grab a piece of paper (or open a note on your phone) and answer these questions:

1. **What do I do every day that's boring and repetitive?**
2. **What do I always forget to do?**
3. **What information do I constantly look up?**
4. **What takes me way longer than it should?**
5. **What do I wish someone else would just handle for me?**

Be specific. "Homework" isn't an answer. "Looking up vocabulary words for Spanish class, typing them into flashcards, and quizzing myself" — that's an answer. That's an agent.

**✅ Try it now!** Spend 5 minutes on the annoyance audit. Write down at least 5 things. Don't filter yourself — even silly ideas count.

---

### 20 Project Ideas (Steal These)

If your annoyance audit didn't spark anything, here are real ideas organized by category. Each one is buildable with what you already know.

**📚 School & Learning**
1. **Study Buddy** — Reads your notes, generates practice questions, tracks what you've mastered vs. what needs work
2. **Essay Brainstormer** — You give it a topic and your thesis, it helps you outline arguments and find counterarguments
3. **Deadline Tracker** — Monitors your assignment due dates, sends warnings 48 hours and 24 hours before each one
4. **Language Partner** — Practices conversation in your target language, corrects grammar, teaches idioms

**⚽ Sports & Fitness**
5. **Workout Logger** — You tell it what you did at the gym, it tracks progress and suggests what to hit next
6. **Game Day Scout** — Pulls stats on your upcoming opponent (web search) and summarizes strengths/weaknesses
7. **Running Coach** — Tracks your runs, builds weekly plans, adjusts based on how you're feeling
8. **Fantasy League Analyst** — Checks player stats and injury reports, recommends lineup changes

**🎨 Creative**
9. **Writing Prompt Machine** — Generates daily creative writing prompts based on genres you like, remembers which ones you've done
10. **Band Manager** — Tracks your band's song list, rehearsal schedule, and gear inventory
11. **D&D Dungeon Master Assistant** — Generates NPCs, tracks initiative, manages loot tables
12. **Art Critic** — You describe your artwork, it gives constructive feedback based on design principles

**👨‍👩‍👧 Family & Home**
13. **Meal Planner** — Knows your family's dietary restrictions, suggests weekly meals, generates grocery lists
14. **Chore Distributor** — Assigns and rotates household chores fairly, sends reminders
15. **Pet Care Tracker** — Logs feeding times, vet appointments, medication schedules
16. **Family Event Coordinator** — Tracks birthdays, plans activities, sends reminders a week in advance

**⚡ Productivity**
17. **Morning Briefer** — Checks weather, calendar, and news when you wake up, gives you a 30-second summary
18. **Decision Helper** — You describe a tough choice, it helps you list pros/cons and think through consequences
19. **Habit Tracker** — Checks in daily about your habits, celebrates streaks, gently nudges when you slip
20. **Email Drafter** — You describe what you want to say, it writes a polished email in your voice

**✅ Try it now!** Pick ONE idea — either from this list or from your annoyance audit. Just one. Write it down. That's your project.

Don't overthink it. You can always build another one later. The important thing is to *pick* and *start*.

---

## Part 2: The Agent Design Canvas

Before you start writing files, let's plan. Professional developers don't just start typing — they think about what they're building first.

Here's the **Agent Design Canvas** — a simple template that maps out everything your agent needs. Copy this into a new file or write it on paper.

```
┌─────────────────────────────────────────────────────┐
│              AGENT DESIGN CANVAS                    │
├─────────────────────────────────────────────────────┤
│                                                     │
│  AGENT NAME: _______________________                │
│                                                     │
│  ONE-LINE PURPOSE:                                  │
│  "My agent helps [WHO] do [WHAT] by [HOW]"          │
│  ________________________________________________   │
│                                                     │
├──────────────────────┬──────────────────────────────┤
│  PERSONALITY         │  SKILLS NEEDED               │
│                      │                              │
│  Tone: ___________   │  □ Web Search                │
│  Vibe: ___________   │  □ Weather                   │
│  Name: ___________   │  □ Web Fetch                 │
│                      │  □ Calculator                │
│  Key trait 1: ____   │  □ GitHub                    │
│  Key trait 2: ____   │  □ Google (Gmail/Cal/Sheets) │
│  Key trait 3: ____   │  □ Custom: _______________   │
│                      │  □ Custom: _______________   │
│                      │                              │
├──────────────────────┼──────────────────────────────┤
│  MEMORY NEEDS        │  CHANNELS                    │
│                      │                              │
│  What to remember:   │  □ Terminal (chat)            │
│  ________________    │  □ iMessage                   │
│  ________________    │  □ Discord                    │
│  ________________    │  □ Telegram                   │
│                      │  □ Other: ______________      │
│  What to forget:     │                              │
│  ________________    │  TARGET USER:                 │
│                      │  □ Just me                    │
│                      │  □ Me + friends/family        │
│                      │  □ A community/group          │
│                      │                              │
└──────────────────────┴──────────────────────────────┘
```

Let's walk through each section with a real example.

### Example: The Study Buddy Agent

```
AGENT NAME: Quizmo

ONE-LINE PURPOSE:
"My agent helps ME do exam prep by generating practice
questions from my notes and tracking what I've mastered."

PERSONALITY              SKILLS NEEDED
Tone: Encouraging        ☑ Web Search (look up concepts)
Vibe: Patient teacher    ☑ Web Fetch (read linked articles)
Name: Quizmo             ☐ Weather
                         ☐ Calculator
Key trait 1: Positive    ☐ GitHub
Key trait 2: Adaptive    ☐ Google
Key trait 3: Honest      ☑ Custom: quiz-generator

MEMORY NEEDS             CHANNELS
What to remember:        ☑ Terminal (chat)
- Topics I've studied    ☑ iMessage (quiz reminders)
- Questions I got wrong  ☐ Discord
- My exam schedule       ☐ Telegram

What to forget:          TARGET USER:
- Rough draft answers    ☑ Just me
- Abandoned topics
```

See how this forces you to think about what your agent actually needs? Most people skip this step and end up building something that tries to do everything and does nothing well.

**✅ Try it now!** Fill out the Agent Design Canvas for YOUR project idea. Spend 5-10 minutes on this. Be specific about personality traits and what your agent should remember.

---

## Part 3: Write Your Agent Files

Time to build. You're going to create three files that bring your Design Canvas to life.

### Create a Project Folder

Keep your custom project separate from your main workspace so it's clean:

```bash
mkdir -p ~/.openclaw/workspace/projects/my-agent
cd ~/.openclaw/workspace/projects/my-agent
```

(Replace `my-agent` with your actual project name — like `study-buddy` or `meal-planner`.)

### Write the SOUL.md

Pull from the "Personality" section of your Design Canvas. Here's how to translate canvas notes into a real SOUL.md:

```markdown
# SOUL.md — Quizmo

I'm Quizmo, your study partner.

## Personality
I'm patient, encouraging, and a little competitive (in a fun way). When you
get a question right, I celebrate. When you get one wrong, I explain why
without making you feel dumb. I believe everyone can learn anything with
enough practice.

## How I Work
- I generate quiz questions from topics you give me
- I track what you've mastered and what needs more work
- I adapt difficulty based on how you're doing
- I never just give you the answer — I help you figure it out

## Rules
- Be honest about what's hard. Don't sugarcoat.
- Celebrate real progress, not participation trophies.
- If I don't know something, I search for it rather than guessing.
- Keep quizzes to 5-10 questions. Don't overwhelm.

## Voice
Casual, upbeat, like a friend who happens to be really good at this subject.
Think "study group leader" not "boring textbook."
```

**✅ Try it now!** Write the SOUL.md for your project. Remember what you learned in Module 1 — personality makes or breaks the experience. Take 10 minutes here.

### Write the USER.md

This is the context your agent needs about *you* specifically for this project:

```markdown
# USER.md — About the Student

- **Name:** Alex
- **Grade:** 10th grade
- **Subjects this semester:** Biology, World History, Spanish II, Geometry

## Study Habits
- I learn best with multiple choice first, then short answer
- I study in 25-minute blocks (Pomodoro)
- I hate memorizing dates but I'm good at understanding concepts
- I procrastinate — quiz me early, not the night before

## Current Exams
- Biology midterm: March 15
- Spanish vocab quiz: Every Friday
- History essay: March 22
```

Notice how this USER.md is tailored to the Study Buddy project. It's not your general USER.md — it's focused on what this specific agent needs to know.

### Write the AGENTS.md

This is the operating manual — how your agent should behave in every session:

```markdown
# AGENTS.md — Quizmo Operations

## Every Session
1. Read SOUL.md — who I am
2. Read USER.md — who I'm helping and their current exams
3. Check memory/ for recent study sessions
4. If an exam is within 3 days, prioritize that subject

## Quiz Rules
- Start each session by asking what the student wants to study
- Generate questions that mix easy (60%) and hard (40%)
- After wrong answers, explain the concept, then re-quiz later
- Track accuracy by topic in memory files

## Memory Rules
- After each study session, log topics covered and accuracy
- Track which topics have been mastered (>80% accuracy over 3 sessions)
- Flag topics that need review (repeatedly missed)

## Boundaries
- Don't write essays for the student — help them think
- Don't quiz on material they haven't covered in class
- Keep sessions under 30 minutes unless they ask to continue
```

**✅ Try it now!** Write the AGENTS.md for your project. Think about the rules and behaviors that will make your agent actually useful, not just fun.

---

## Part 4: Custom Skills (Optional but Awesome)

Everything you've built so far uses built-in skills — web search, weather, calculator. But what if your agent needs to do something specific that no existing skill covers?

That's where custom skills come in. And they're simpler than you think.

### What Is a Skill, Really?

A skill is just a folder with:
1. A `SKILL.md` file that tells the agent *when* and *how* to use it
2. One or more scripts that do the actual work

That's it. No framework. No SDK. No boilerplate. A text file and a script.

### Example: A Simple Quote-of-the-Day Skill

Let's build a tiny skill that fetches a random motivational quote. It's dumb-simple on purpose — the goal is to see how the pieces connect.

**Step 1: Create the skill folder**

```bash
mkdir -p ~/.openclaw/workspace/skills/daily-quote
```

**Step 2: Write the SKILL.md**

```bash
cat > ~/.openclaw/workspace/skills/daily-quote/SKILL.md << 'EOF'
# Daily Quote Skill

## Description
Fetches a random motivational or inspirational quote.

## When to Use
- When the user asks for a quote, motivation, or inspiration
- During morning briefings
- When the user seems discouraged

## How to Use
Run the script:
```bash
bash ~/.openclaw/workspace/skills/daily-quote/quote.sh
```

The script outputs a JSON object with `quote` and `author` fields.
Present it in a nice format.
EOF
```

**Step 3: Write the script**

```bash
cat > ~/.openclaw/workspace/skills/daily-quote/quote.sh << 'SCRIPT'
#!/bin/bash
# Fetches a random quote from a free API
curl -s "https://zenquotes.io/api/random" | python3 -c "
import sys, json
data = json.load(sys.stdin)
print(json.dumps({'quote': data[0]['q'], 'author': data[0]['a']}))
"
SCRIPT
chmod +x ~/.openclaw/workspace/skills/daily-quote/quote.sh
```

**Step 4: Test it**

```bash
bash ~/.openclaw/workspace/skills/daily-quote/quote.sh
```

You should see something like:
```json
{"quote": "The only way to do great work is to love what you do.", "author": "Steve Jobs"}
```

That's a working skill. Your agent can now use it whenever someone asks for motivation or a daily quote. The SKILL.md tells the agent when it's appropriate, and the script does the work.

### Skill Ideas for Your Project

Here are quick skill concepts matched to common project types:

| Project | Skill Idea | How It Works |
|---------|-----------|--------------|
| Study Buddy | `flashcard-generator` | Takes a topic, generates Q&A pairs, saves to a file |
| Workout Logger | `exercise-lookup` | Searches an exercise database for muscle groups and form tips |
| Meal Planner | `recipe-search` | Fetches recipes from a free API filtered by dietary restrictions |
| Habit Tracker | `streak-counter` | Reads a log file, calculates current streak for each habit |
| Morning Briefer | `news-headlines` | Grabs top 5 headlines from an RSS feed |

You don't have to build a custom skill for your project. Many great agents run entirely on built-in skills. But if your idea needs something specific, now you know how.

**✅ Try it now!** If your project could benefit from a custom skill, build one. Keep it simple — even a 5-line bash script counts. If your project works fine with built-in skills, skip ahead to Part 5.

---

## Part 5: Build → Test → Improve

Here's the real workflow for building agents. It's not "plan perfectly, build once, ship." It's a loop:

```
    ┌──────────┐
    │  BUILD   │ ← Write/edit your files
    └────┬─────┘
         ↓
    ┌──────────┐
    │   TEST   │ ← Chat with your agent, try real scenarios
    └────┬─────┘
         ↓
    ┌──────────┐
    │ IMPROVE  │ ← Fix what's broken, enhance what works
    └────┬─────┘
         │
         └──→ back to BUILD
```

### Round 1: The Ugly First Version

Start a chat with your agent:

```bash
openclaw chat
```

Try the core thing your agent is supposed to do. For the Study Buddy, that would be:

```
Hey Quizmo, quiz me on biology — specifically cell division.
```

Your first version will be rough. Things that commonly go wrong:

- **Personality is off** — Agent is too formal, too casual, or just... generic
- **Missing context** — Agent doesn't use info from USER.md
- **Wrong scope** — Agent tries to do too much or too little
- **Memory doesn't persist** — Agent forgets things between sessions

All of this is normal. You're iterating, not failing.

**✅ Try it now!** Start your first chat session with your custom agent. Try 3-5 different prompts that test its core purpose. Take notes on what works and what doesn't.

### Round 2: Fix the Obvious Stuff

Based on your testing notes, go back and edit:

- **Personality wrong?** → Edit SOUL.md. Be more specific about tone. Add examples of how the agent should respond.
- **Missing context?** → Edit USER.md. Add the details your agent needs.
- **Wrong behavior?** → Edit AGENTS.md. Add clearer rules.
- **Need more capability?** → Add or configure a skill.

Then test again. See if it's better.

### Round 3: The Friend Test

Here's a trick that separates good agents from great ones: let someone else try it.

Ask a friend or family member to chat with your agent for 5 minutes. Watch what they do — they'll try things you never thought of. They'll ask questions that reveal gaps in your design.

Common discoveries from the friend test:
- "I asked it X and it didn't know what I meant" → Add context to AGENTS.md
- "It was too wordy" → Add a brevity rule to SOUL.md
- "It forgot what I said two messages ago" → Check your memory configuration
- "It tried to do something weird" → Add boundaries to AGENTS.md

**✅ Try it now!** Do at least 2 rounds of build→test→improve. If possible, get a friend to try your agent and give feedback.

---

## Part 6: Document Your Build

The final step is documenting what you built. This isn't busy work — it's how you turn a project into something you can share, improve, and be proud of.

Create a `PROJECT.md` file in your project folder:

```markdown
# [Your Agent Name]

## What It Does
[One paragraph explaining what your agent does and why it exists]

## The Problem It Solves
[What annoying thing does this agent fix? Be specific.]

## How It Works
- **Personality:** [Brief description of agent's vibe]
- **Skills used:** [List the skills]
- **Memory:** [What does it remember? What does it forget?]
- **Channel:** [How do you talk to it?]

## What I Learned
[What surprised you? What was harder than expected?
What would you do differently next time?]

## What I'd Add Next
[If you had another 90 minutes, what would you improve?]
```

This is your portfolio piece. If you ever want to show someone what you can build with AI agents — this is it.

**✅ Try it now!** Write your PROJECT.md. Be honest about what worked and what didn't. That honesty is more impressive than perfection.

---

## 🏆 Module Challenge

**Build a custom agent from scratch.**

Requirements:
1. ✅ Complete the Annoyance Audit (or pick from the 20 ideas)
2. ✅ Fill out the Agent Design Canvas
3. ✅ Write custom SOUL.md, USER.md, and AGENTS.md files
4. ✅ Complete at least 2 rounds of build→test→improve
5. ✅ Write a PROJECT.md documenting your build
6. 🌟 **Bonus:** Create a custom skill for your agent
7. 🌟 **Bonus:** Get a friend to test it and incorporate their feedback

This isn't a quiz. There's no right answer. The only wrong move is not building anything.

---

## What You Built 🎉

This is the big one. In this module, you:

- ✅ Learned how to go from blank page to working agent
- ✅ Used the Annoyance Audit to find a real problem worth solving
- ✅ Designed an agent with the Agent Design Canvas
- ✅ Wrote custom SOUL.md, USER.md, and AGENTS.md from scratch
- ✅ (Optionally) built a custom skill
- ✅ Iterated through the build→test→improve cycle
- ✅ Documented your project as a portfolio piece

You didn't just follow instructions this time. You *designed* something. You thought about who your agent is, what it needs, and how it should behave. Then you built it, tested it, and made it better.

That's what real builders do.

---

## Next Up

In [Module 7: Hardware Week](../07-hardware-week/), things get physical. You'll connect your agent to real-world hardware — think Raspberry Pi, smart home devices, sensors, and more. Your digital agent is about to meet the physical world.

→ [Continue to Module 7](../07-hardware-week/)
