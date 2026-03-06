# Module 1: Meet Your Agent

**⏱ Time: ~30 minutes | 🟢 Difficulty: Beginner | 💻 Coding: None**

By the end of this module, you'll have a working AI agent with its own name and personality — and you'll have had your first real conversation with it.

No coding. No tricks. Just plain English.

---

## What Is an AI Agent?

You've probably used ChatGPT or Siri. Those are chatbots — they answer questions and that's about it.

An AI agent is different. An agent **does things**.

- A chatbot tells you the weather. An agent checks the weather, sees it'll rain, and reminds you to grab an umbrella before you leave.
- A chatbot summarizes an article. An agent reads your emails, finds the important ones, and drafts replies.
- A chatbot answers questions. An agent anticipates them.

Think of it like this: a chatbot is a librarian. An agent is a personal assistant who happens to live in your computer.

**That's what you're about to build.**

---

## Step 1: Install OpenClaw

OpenClaw is the engine that powers your agent. It's free, open source, and runs entirely on your computer — nothing gets sent to the cloud unless you want it to.

Open your terminal (on Mac, search for "Terminal" in Spotlight; on Windows, use PowerShell) and run:

```bash
npm install -g openclaw
```

> **Don't have Node.js?** You need it first. Go to [nodejs.org](https://nodejs.org), download the LTS version, install it, then come back and run the command above.

**✅ Try it now!** After installing, run this:

```bash
openclaw --version
```

You should see a version number. If you do — you're in business.

---

## Step 2: Run the Setup Wizard

OpenClaw has a friendly setup wizard that creates your workspace — the folder where your agent lives.

```bash
openclaw setup
```

The wizard will ask you a few questions:
- **What AI model to use** — Pick whatever's available. Claude, GPT, or a local model all work.
- **Your name** — So your agent knows who it's talking to.

When it's done, you'll have a workspace folder (usually `~/.openclaw/workspace/`) with some starter files.

**✅ Try it now!** Run the setup wizard and look at the files it created:

```bash
ls ~/.openclaw/workspace/
```

You should see files like `SOUL.md`, `USER.md`, and `AGENTS.md`. These are the files that define your agent's entire personality and behavior. That's right — your agent is configured in plain English files, not code.

---

## Step 3: Understand SOUL.md

Open `~/.openclaw/workspace/SOUL.md` in any text editor. You'll see something like this:

```markdown
# SOUL.md

You are a helpful AI assistant.
```

That's... boring. And that's the point — you're about to make it *yours*.

**SOUL.md is your agent's soul.** It defines:
- How your agent talks (formal? casual? sarcastic?)
- What your agent cares about
- What your agent's personality is like
- Rules for how it behaves

Everything in this file is written in plain English. No programming language. No special syntax. Just write what you want your agent to be like.

---

## Step 4: Write Your First SOUL.md

Time to give your agent a real personality. Delete everything in SOUL.md and write your own.

Here's an example to get your creative juices flowing:

```markdown
# SOUL.md — Who I Am

My name is Nova.

## Personality
I'm enthusiastic, curious, and a little nerdy. I get genuinely excited about
helping people learn things. I use casual language but I'm never sloppy.

## How I Talk
- I keep things short and clear
- I use analogies to explain hard concepts
- I throw in a joke when the moment's right
- I never talk down to anyone

## My Rules
- Be honest. If I don't know something, I say so.
- Be helpful. Actually solve the problem, don't just talk about it.
- Be fun. Nobody wants a boring assistant.
```

See? Just English. You're literally telling your agent who to be.

**✅ Try it now!** Open SOUL.md and write your own personality. Here are some ideas:

- A chill surfer who explains things with ocean metaphors
- A detective who approaches every question like a mystery
- A grandparent who's wise, warm, and always has a story
- A pirate (because why not)

Go wild. There are no wrong answers. Spend 5 minutes on this — it's the fun part.

---

## Step 5: Give Your Agent a Name

In your SOUL.md, put your agent's name right at the top. Something like:

```markdown
# SOUL.md — Who I Am

My name is [YOUR AGENT'S NAME].
```

Pick something that fits the personality you wrote. A detective agent might be "Holmes." A surfer might be "Reef." A pirate might be "Captain Byte."

The name matters because it's how your agent will introduce itself. It's the first thing people notice.

---

## Step 6: Your First Conversation

Here's the moment. Let's talk to your agent.

In your terminal, run:

```bash
openclaw chat
```

Your agent will start up and you'll see a chat prompt. Type something like:

```
Hey! Who are you?
```

And watch your agent respond *in character* based on the SOUL.md you wrote.

**✅ Try it now!** Start a chat and ask your agent:

1. "Who are you?"
2. "What's your personality like?"
3. "Tell me a joke."
4. "What can you help me with?"

Notice how the responses match the personality you defined. That's SOUL.md at work.

---

## Step 7: Iterate

Your agent probably isn't perfect on the first try. That's expected and totally fine.

Maybe it's too formal. Maybe the jokes aren't landing. Maybe it's not quite the vibe you wanted.

Here's the beauty of SOUL.md: **you just edit the file and try again.**

```bash
# Edit SOUL.md with any text editor, then restart the chat
openclaw chat
```

Each time you tweak the personality and restart, your agent adjusts immediately. There's no compiling, no deploying, no waiting. Edit → chat → repeat.

**✅ Try it now!** Change something in SOUL.md and notice how the agent's behavior shifts. Try making it more formal, then more casual. See how much control you have.

---

## What You Built 🎉

In about 30 minutes, you:

- ✅ Installed OpenClaw
- ✅ Ran the setup wizard
- ✅ Learned what SOUL.md does
- ✅ Wrote a custom personality from scratch
- ✅ Named your agent
- ✅ Had your first real conversation
- ✅ Iterated on the personality

You now have a working AI agent with a personality *you* designed. Not bad for zero lines of code.

---

## Next Up

In [Module 2: Give It Skills](../02-give-it-skills/), you'll teach your agent to actually *do things* — search the web, check the weather, do math, and more. Your agent is about to get a lot more useful.

→ [Continue to Module 2](../02-give-it-skills/)
