# Module 4: Memory & Personality

**⏱ Time: ~45 minutes | 🟢 Difficulty: Beginner | 💻 Coding: None**

This is the module that changes everything.

Your agent has personality and skills. But every time you start a new conversation, it forgets who you are. It doesn't know your name, your preferences, what you talked about yesterday, or that you hate mushrooms.

By the end of this module, your agent will remember you. And that changes the entire relationship.

---

## Why Memory Matters

Think about your favorite barista. The one who starts making your drink when they see you walk in. They remember your order, ask about your dog by name, know you're stressed about finals this week.

That's not because they're smarter than other baristas. It's because they **remember** you.

Memory is what transforms a tool into a partner. An agent without memory is helpful. An agent *with* memory is indispensable.

OpenClaw gives your agent memory through simple files:

- **USER.md** — everything your agent knows about you
- **AGENTS.md** — your agent's operating manual and rules
- **MEMORY.md** — your agent's long-term memories
- **memory/*.md** — daily logs of what happened

All plain English. All editable by you. Let's set them up.

---

## Step 1: Write Your USER.md

USER.md teaches your agent about *you*. Open `~/.openclaw/workspace/USER.md` in your text editor.

Here's an example:

```markdown
# USER.md — About My Human

- **Name:** Alex
- **Age:** 14
- **Location:** Portland, Oregon
- **School:** Lincoln High, 9th grade
- **Interests:** Soccer, video games (Minecraft, Zelda), drawing

## Preferences
- Explain things simply — I'm smart but I don't like jargon
- I'm a morning person, usually chat before school and after dinner
- I like when explanations use examples from games or sports
- I don't eat mushrooms or olives

## Current Focus
- Preparing for a science fair project (due April)
- Trying to learn guitar
- Soccer season starts next month
```

See what we did? We gave the agent *context*. Now when you ask "what should I have for dinner?" it won't suggest mushroom risotto. When you ask for help with homework, it'll use gaming analogies. When you ask about your day, it knows you have soccer coming up.

**✅ Try it now!** Write your own USER.md. Include:
- Your name and basic info
- At least 3 preferences or interests
- Something you're currently working on

Then start a chat and ask: "What do you know about me?"

Your agent should reference the information from USER.md. If it does — the connection is working.

---

## Step 2: Set Up AGENTS.md

AGENTS.md is your agent's operating manual. If SOUL.md is *who* the agent is, AGENTS.md is *how* it operates.

Open `~/.openclaw/workspace/AGENTS.md` and set some ground rules:

```markdown
# AGENTS.md — How I Operate

## Every Session
1. Read SOUL.md — this is who I am
2. Read USER.md — this is who I'm helping
3. Check memory files for recent context

## Communication Rules
- Keep responses concise unless asked for detail
- If something's urgent, say so clearly
- Never share personal info from USER.md with anyone else

## Memory Rules
- After each conversation, note anything important in daily memory
- If a pattern repeats 3 times, it's a stable preference — remember it
- If you make a mistake, learn from it

## Boundaries
- Ask before doing anything that affects the outside world (sending messages, etc.)
- Be honest about limitations
- If unsure, say so rather than guessing
```

This file shapes your agent's behavior across every conversation. Want it to always start with a greeting? Put it here. Want it to be extra careful with certain topics? Put it here.

**✅ Try it now!** Write your AGENTS.md with at least 3 operating rules. Then chat with your agent and see if it follows them.

---

## Step 3: Watch Memory in Action

Here's the magic moment. Let's create a memory that persists.

Start a chat with your agent:

```
Hey, just so you know — I have a big math test on Friday. I'm nervous about it.
```

Your agent should acknowledge this and probably offer to help you study.

Now **close the chat** (type `exit` or press Ctrl+C).

Wait a moment. Then **start a new chat**:

```bash
openclaw chat
```

And say:

```
Hey, what's going on this week?
```

If memory is working, your agent will mention your math test on Friday. It remembered. Across separate conversations.

**✅ Try it now!** Do the test above. Tell your agent something specific, close the chat, reopen it, and see if it remembers.

---

## Step 4: How Memory Works Under the Hood

Let's peek behind the curtain. Check your workspace:

```bash
ls ~/.openclaw/workspace/memory/
```

You'll see files like `2026-03-06.md` — these are daily memory logs. Open one and read it. Your agent has been taking notes about your conversations, written in plain English.

You can also check MEMORY.md:

```bash
cat ~/.openclaw/workspace/MEMORY.md
```

This is the long-term memory file — distilled insights your agent has promoted from daily notes. Think of daily files as a journal and MEMORY.md as wisdom.

**The key insight:** All of this is stored in readable text files. You can read your agent's memories, edit them, or delete them. You're always in control. There's no hidden database, no cloud storage, no mystery.

**✅ Try it now!** Read through your agent's memory files. Find something it remembered from your conversations. Pretty cool, right?

---

## Step 5: Edit Memory Directly

Because memories are just text files, you can directly edit them.

Try adding something to your agent's MEMORY.md:

```markdown
## Important
- Alex prefers to study with background music (lo-fi hip hop)
- Alex's favorite subject is art, least favorite is history
- When Alex says "I'm bored" it usually means they want a creative challenge
```

Now start a chat and say "I'm bored."

Your agent should suggest a creative challenge — not because you told it to in this conversation, but because it *knows* that about you from its memory.

**✅ Try it now!** Add a hidden preference to MEMORY.md, then test if your agent uses it naturally in conversation.

---

## Step 6: The Memory Cycle

Here's how the full memory system works:

```
Conversation happens
        ↓
Agent notes important things → memory/YYYY-MM-DD.md (daily log)
        ↓
Over time, patterns emerge
        ↓
Agent promotes key learnings → MEMORY.md (long-term)
        ↓
Next conversation starts
        ↓
Agent reads USER.md + MEMORY.md + recent daily logs
        ↓
Agent has full context about you
```

It's a cycle. The more you use your agent, the better it knows you. Conversations get more efficient. Suggestions get more relevant. The experience gets more... personal.

This is the thing that makes people go "whoa" when they use an agent with good memory. It stops feeling like software and starts feeling like someone who actually knows you.

---

## What You Built 🎉

In this module, you:

- ✅ Created a USER.md that teaches your agent about you
- ✅ Set up AGENTS.md with operating rules
- ✅ Watched memory persist across conversations
- ✅ Explored how memory files work under the hood
- ✅ Manually edited memory and saw the agent use it
- ✅ Understood the full memory cycle

Your agent now has personality (SOUL.md), skills (web search, weather, calculator), and memory (USER.md, MEMORY.md, daily logs). It knows who it is, what it can do, and who you are.

**That's a real AI agent.** And you built it without writing a single line of code.

---

## Next Up

In [Module 4: Connect to the World](../04-connect-to-the-world/), your agent breaks out of the terminal and starts interacting with the real world — messages, emails, calendars, and more. Things are about to get very interesting.

→ [Continue to Module 4](../04-connect-to-the-world/)
