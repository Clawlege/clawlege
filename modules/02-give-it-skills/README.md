# Module 2: Give It Skills

**⏱ Time: ~30 minutes | 🟢 Difficulty: Beginner | 💻 Coding: None**

Your agent has a personality. Now let's give it superpowers.

In this module, you'll enable skills that let your agent search the web, check the weather, do calculations, and more. You'll watch it decide *on its own* which skill to use for each question.

---

## What Are Skills?

Right now, your agent can only talk. It's smart, it has personality, but if you ask "What's the weather in Tokyo?" it has to guess. It can't actually *check*.

**Skills are tools your agent can use.** They're like apps on a phone:

- 🔍 **Web Search** — find anything on the internet
- 🌤️ **Weather** — current conditions and forecasts for any city
- 🧮 **Calculator** — math that's actually accurate (LLMs are terrible at math on their own)
- 📰 **Web Fetch** — read the contents of any webpage

When you give your agent a skill, it doesn't just have access to it — it *decides when to use it*. Ask about the weather? It uses the weather skill. Ask a math question? Calculator. Ask a general knowledge question? It might just answer from memory, or search the web if it's not confident.

That decision-making is what separates an agent from a chatbot.

---

## Step 1: See What Skills Are Available

OpenClaw comes with built-in skills. Let's see what's on the menu:

```bash
openclaw skills list
```

You'll see a list of available skills — some enabled, some not. Each skill has a name and a short description of what it does.

**✅ Try it now!** Run the command and read through the list. Which skills sound useful for your agent?

---

## Step 2: Enable Your First Skill

Let's start with web search — it's the most universally useful skill.

Skills are managed through OpenClaw's configuration. You can enable them with:

```bash
openclaw skills enable web-search
```

That's it. Your agent can now search the internet.

**✅ Try it now!** Enable web search and then start a chat:

```bash
openclaw chat
```

Ask your agent something that requires current information:

```
What's the biggest news story today?
```

Watch what happens. Your agent will search the web, read the results, and give you a summary. You'll actually see it using the skill in the chat — it's not magic, it's transparent.

---

## Step 3: Add More Skills

Let's add a few more skills to round out your agent:

```bash
openclaw skills enable weather
openclaw skills enable calculator
```

Now your agent has three superpowers. Let's test them.

**✅ Try it now!** Start a new chat and ask these questions one after another:

1. "What's the weather like in Paris right now?"
2. "If I invest $1,000 at 7% annual return, how much will I have in 10 years?"
3. "What movies came out this week?"

Notice how your agent switches between skills automatically. It didn't ask you "should I use the calculator for this?" — it just figured it out. That's agent intelligence.

---

## Step 4: Watch the Decision-Making

Here's something cool. Ask your agent a question where multiple skills *could* work:

```
Should I wear a jacket today?
```

Your agent might:
1. Check the weather for your location
2. Consider the forecast
3. Give you a recommendation

Or ask something more complex:

```
I'm planning a weekend trip to Seattle. What should I know?
```

Your agent might search the web for events, check the weather forecast, and combine them into a useful answer. Multiple skills, one question, zero effort from you.

**✅ Try it now!** Ask a complex question and watch your agent chain skills together.

---

## Step 5: Understanding Skill Behavior

A few things to know about how skills work:

### Your agent decides, not you
You don't have to say "search the web for X." Just ask your question naturally. The agent reads your intent and picks the right tool.

### Skills are transparent
When your agent uses a skill, you can see it happening in the chat. This isn't a black box — you can watch the process.

### Not every question needs a skill
If you ask "What's the capital of France?" your agent probably knows that already. It won't waste time searching the web for something it's confident about. Smart agents know when to use tools and when not to.

### Skills can fail gracefully
Sometimes a website is down, or a search returns bad results. A good agent handles this smoothly — it'll tell you what happened and try another approach.

---

## Step 6: The Skill Ecosystem

OpenClaw's skill system is extensible. Beyond the built-in ones, there's a whole ecosystem:

```bash
# Browse community skills
openclaw skills search
```

Some examples of what's out there:
- **GitHub** — manage issues, PRs, and repositories
- **Google Workspace** — gmail, calendar, drive
- **iMessage** — read and send messages
- **Apple Notes** — manage your notes

You don't need these now, but know that as your agent grows, so can its capabilities. We'll explore advanced skills in Module 4.

---

## What You Built 🎉

In this module, you:

- ✅ Learned what skills are and why they matter
- ✅ Enabled web search, weather, and calculator
- ✅ Watched your agent choose the right skill automatically
- ✅ Tested complex questions that chain multiple skills
- ✅ Understood how agents decide when to use tools

Your agent went from "fun to talk to" to "actually useful." It can now find information, do math, and check the weather — and it decides when to do each one without you telling it.

---

## Next Up

In [Module 3: Memory & Personality](../03-memory-and-personality/), you'll teach your agent to *remember* you. Your preferences, your past conversations, things you've told it before. This is where your agent starts to feel less like software and more like... a partner.

→ [Continue to Module 3](../03-memory-and-personality/)
