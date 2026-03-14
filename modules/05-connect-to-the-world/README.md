# Module 5: Connect to the World

**⏱ Time: ~60 minutes | 🟡 Difficulty: Intermediate | 💻 Coding: Minimal**

Your agent lives in a terminal. It's smart, it remembers you, it has skills — but it's trapped behind a blinking cursor, waiting for you to type something.

Time to break it out.

In this module, you'll connect your agent to real communication channels — Discord, iMessage, Telegram, Signal — so it can reach *you* instead of the other way around. You'll set up proactive behavior so it checks in on its own. And you'll learn about safety guardrails so your agent doesn't accidentally text your boss at 3 AM.

This is where your agent stops being a toy and starts being a partner.

---

## Why Channels Matter

Up until now, every interaction has been the same:

1. You open a terminal
2. You type `openclaw chat`
3. You ask a question
4. Your agent answers
5. You close the terminal

That's fine for learning. But real assistants don't sit behind a desk waiting for you to walk in. Real assistants *come to you*.

Channels are the bridges between your agent and the outside world. They let your agent:

- **Send you messages** when something important happens
- **Receive messages** from you on platforms you already use
- **Talk to other people** (with your permission) in group chats
- **Stay alive** between conversations — not just when you open a terminal

Think about it: what's more useful? An agent you have to remember to open, or one that pings you on Discord when it notices it's going to rain on your walk home?

---

## Step 1: Pick Your First Channel

OpenClaw supports a bunch of channels out of the box:

| Channel | Best For | Setup Difficulty |
|---------|----------|------------------|
| **Discord** | Learning, group chats, bots | 🟢 Easiest |
| **Telegram** | Personal messaging, privacy | 🟢 Easy |
| **iMessage** | Mac users, personal use | 🟡 Medium |
| **Signal** | Privacy-first messaging | 🟡 Medium |
| **WhatsApp** | International, group chats | 🟡 Medium |

**Our recommendation: start with Discord.** It's the easiest to set up, doesn't require a phone number, and has great bot support. Once you've got it working, you can add other channels later.

**✅ Try it now!** Pick which channel you want to connect first. If you're not sure, go with Discord — the rest of this section will walk you through it.

---

## Step 2: Set Up Discord (Your First Channel)

Here's how to connect your agent to Discord in about 10 minutes.

### Create a Discord Bot

1. Go to [discord.com/developers/applications](https://discord.com/developers/applications)
2. Click **"New Application"** — name it whatever you want (your agent's name works great)
3. Go to the **Bot** tab on the left
4. Click **"Reset Token"** and copy the token. **Save this somewhere safe** — you'll need it in a minute and Discord only shows it once
5. Scroll down and enable these under **Privileged Gateway Intents**:
   - ✅ Message Content Intent
   - ✅ Server Members Intent
   - ✅ Presence Intent

### Invite Your Bot to a Server

1. Go to the **OAuth2** tab
2. Under **OAuth2 URL Generator**, check `bot`
3. Under **Bot Permissions**, check:
   - Send Messages
   - Read Message History
   - Add Reactions
4. Copy the generated URL and open it in your browser
5. Select a server and click **Authorize**

You should see your bot appear in the server's member list (it'll be offline for now).

### Configure OpenClaw

Now tell OpenClaw about your Discord bot. Run:

```bash
openclaw config
```

Or edit the config file directly. You need to add your Discord channel:

```yaml
channels:
  discord:
    adapter: discord
    token: "YOUR_BOT_TOKEN_HERE"
```

That's the minimal config. Your bot token goes right there, wrapped in quotes.

**✅ Try it now!** Create your Discord bot, invite it to a server, and add the config. Then start your agent:

```bash
openclaw start
```

Go to your Discord server and send a message mentioning your bot. If it responds — you just connected your agent to the outside world. 🎉

---

## Step 3: Test the Connection

Once your agent is running with a channel connected, the relationship changes. You're no longer typing into a terminal — you're chatting on a platform you already use every day.

Try these in your Discord server:

```
@YourBot hey, who are you?
@YourBot what's the weather in Portland?
@YourBot remind me about my math test
```

Your agent will respond using its SOUL.md personality, its skills, and its memory — just like in the terminal, but now it's living inside Discord.

**Notice what just happened.** Your agent is no longer a terminal app. It's a Discord bot with personality, skills, and memory. Anyone in your server can talk to it. You can talk to it from your phone. It's *always there*.

**✅ Try it now!** Have a short conversation with your agent on Discord. Ask it something it needs a skill for (like weather). Confirm it works the same as it did in the terminal.

---

## Step 4: Adding More Channels

Once you've got one channel working, adding more is just config. Here's what the other channels look like:

### Telegram

```yaml
channels:
  telegram:
    adapter: telegram
    token: "YOUR_TELEGRAM_BOT_TOKEN"
```

Get your token from [@BotFather](https://t.me/BotFather) on Telegram — it walks you through creating a bot in about 2 minutes.

### iMessage (Mac Only)

```yaml
channels:
  imessage:
    adapter: imessage
    allowlist:
      - "+14155551234"
```

iMessage works natively on Mac — no bot token needed because it uses your Mac's Messages.app directly. The `allowlist` controls who can talk to your agent (more on that in the safety section).

### Signal

```yaml
channels:
  signal:
    adapter: signal
    phone: "+14155551234"
```

Signal requires linking to an existing Signal account on your machine.

**The pattern is always the same:** add the channel to your config, provide credentials, restart. OpenClaw handles the rest.

**✅ Try it now!** If you use Telegram or iMessage, try adding a second channel. Having your agent available on multiple platforms simultaneously is where things start to feel real.

---

## Step 5: Proactive Agents — The Heartbeat System

Here's the big shift. Everything up to now has been *reactive* — you talk, the agent responds. But the best assistants are *proactive*. They reach out to you.

OpenClaw does this through **heartbeats** — periodic check-ins where your agent wakes up and asks itself: "Is there anything I should do right now?"

### How It Works

You configure a heartbeat interval in your OpenClaw config:

```yaml
heartbeat:
  intervalMs: 1800000  # every 30 minutes
  channel: discord     # where to send proactive messages
```

Every 30 minutes (or whatever you set), your agent:

1. Wakes up
2. Reads `HEARTBEAT.md` from your workspace
3. Follows the instructions in that file
4. Either does something useful or goes back to sleep

### Writing Your HEARTBEAT.md

Create a file at `~/.openclaw/workspace/HEARTBEAT.md`:

```markdown
# HEARTBEAT.md — What to Check

When you wake up for a heartbeat, check these things:

1. **Weather** — If rain or extreme temps are expected in the next 6 hours,
   let me know
2. **Calendar** — If I have an event in the next 2 hours, remind me
3. **Vibe check** — If it's been more than 8 hours since we talked,
   say hi with something interesting

If nothing needs attention, reply HEARTBEAT_OK (this means "all quiet, going
back to sleep").

Don't check everything every time — rotate through these so you're not
spamming me.
```

That's it. Plain English instructions for what your agent should do when it checks in.

**✅ Try it now!** Create a HEARTBEAT.md with at least 2 things for your agent to check. Keep it simple — you can always add more later.

---

## Step 6: See a Proactive Message

Let's test the heartbeat system. You can either wait for the timer to fire, or trigger a heartbeat manually:

```bash
openclaw heartbeat
```

If you set up a weather check and rain is coming, your agent will message you on Discord (or whatever channel you configured) with a heads-up. If nothing's happening, it'll stay quiet — exactly like you told it to.

The first time your agent messages *you* without being asked, it hits different. That's the moment it stops feeling like software.

### Smart Heartbeat Tips

A few things that make heartbeats better:

- **Don't check too often.** Every 30 minutes is plenty. Every 5 minutes is annoying.
- **Respect quiet hours.** Add "Don't message me between 11 PM and 7 AM unless it's urgent" to your HEARTBEAT.md.
- **Rotate checks.** Your agent doesn't need to check everything every time. "Pick 1-2 things per heartbeat" keeps things efficient.
- **Batch it.** One message with 3 updates beats 3 separate messages.

**✅ Try it now!** Trigger a manual heartbeat and see what your agent does. Did it find something worth telling you about? Did it stay quiet because nothing was happening? Both are correct behavior.

---

## Step 7: External Skills from ClawHub

Your agent has built-in skills, but the community has built dozens more. **ClawHub** is the marketplace where you can find and install them.

### Browsing Skills

```bash
clawhub search weather
clawhub search github
clawhub search calendar
```

This searches the community skill library. You'll see names, descriptions, and ratings.

### Installing a Skill

Found something you want? Install it:

```bash
clawhub install skill-name
```

That's it. The skill is downloaded and available to your agent on the next restart. No code to write, no configuration to fiddle with (most of the time).

### Popular Skills

Here are some community favorites to get you started:

- **weather** — Forecasts and alerts from wttr.in and Open-Meteo
- **github** — Issues, PRs, CI status, code review
- **gog** — Google Workspace (Gmail, Calendar, Drive, Sheets)
- **apple-notes** — Create and search Apple Notes
- **things-mac** — Things 3 task management

### What Makes a Good Skill?

When browsing ClawHub, look for skills that:

- Have a clear `SKILL.md` (you can read what they do before installing)
- Are actively maintained (check the last update date)
- Solve a problem you actually have (don't install stuff "just in case")

**✅ Try it now!** Run `clawhub search` with something you're interested in. Find a skill and install it. Then chat with your agent and try using it.

---

## Step 8: Safety and Permissions

Time for the serious part. Your agent can now send messages to real people on real platforms. That's powerful — and power needs guardrails.

OpenClaw uses an **ask-first model** by default. This means:

- Your agent will **ask your permission** before sending a message to someone
- Your agent will **ask your permission** before running commands that affect the outside world
- Your agent will **ask your permission** before doing anything it hasn't done before

### Allowlists

For channels like iMessage, you can control exactly who your agent talks to:

```yaml
channels:
  imessage:
    adapter: imessage
    allowlist:
      - "+14155551234"    # just you
      - "+14155559876"    # your friend
```

If someone not on the list messages your agent, it ignores them. Simple and safe.

### Command Safety

OpenClaw also has a safety layer for shell commands and tool usage. The security modes are:

| Mode | What It Does |
|------|-------------|
| `deny` | Block the command entirely |
| `allowlist` | Only pre-approved commands run automatically |
| `full` | Everything runs (use carefully) |

Start with the defaults. They're conservative on purpose. As you build trust with your agent, you can loosen things up.

### The Trust Ladder

Think of permissions like a trust ladder:

1. **Week 1:** Agent asks before everything. You approve each action manually.
2. **Week 2:** You've approved "check weather" 50 times. Add it to the allowlist so it runs automatically.
3. **Week 3:** You trust your agent with routine messages. You let it send without asking.
4. **Month 2:** Your agent handles a lot autonomously, but still asks for anything new or unusual.

This is by design. You don't hand someone the keys to your house on day one. You build trust over time.

**✅ Try it now!** Check your current security settings:

```bash
openclaw config
```

Look at the `security` section. Understand what's allowed and what requires approval. If something seems too loose or too tight, adjust it.

---

## Step 9: Putting It All Together

Let's connect the dots. You now have:

- A channel (Discord, Telegram, iMessage, etc.)
- A heartbeat system for proactive check-ins
- External skills from ClawHub
- Safety guardrails

Here's what a typical day might look like with a connected agent:

**Morning:** Your agent checks the weather via heartbeat. Rain's coming this afternoon. It messages you on Discord: "Heads up — rain at 3 PM. Grab an umbrella if you're heading out."

**Afternoon:** You're in a Discord server with friends. Someone asks a question your agent can answer. It chimes in helpfully (because it has the right skills and permissions for that server).

**Evening:** You message your agent on iMessage: "What was that thing I told you about yesterday?" It checks its memory and reminds you.

**Late night:** Heartbeat fires, but it's past your quiet hours. Agent stays silent. HEARTBEAT_OK.

That's not a demo. That's a Tuesday. And you built it.

---

## 🏆 Challenge: Your First Proactive Message

Here's your challenge for this module:

1. **Connect at least one real channel** (Discord is the easiest)
2. **Write a HEARTBEAT.md** with at least 2 checks
3. **Have your agent send you a proactive message** — not because you asked, but because it found something worth telling you

Bonus points:
- Connect a second channel
- Install a community skill from ClawHub and use it in a heartbeat check
- Set up quiet hours in your HEARTBEAT.md

The goal isn't perfection. The goal is to experience the moment when your agent reaches out to you on its own for the first time. Trust us — that moment is worth the setup.

---

## What You Built 🎉

In this module, you:

- ✅ Understood why channels matter (reactive → proactive)
- ✅ Connected your agent to Discord (or another platform)
- ✅ Learned the config pattern for multiple channels
- ✅ Set up the heartbeat system for proactive behavior
- ✅ Wrote a HEARTBEAT.md with custom check-in instructions
- ✅ Discovered ClawHub and installed an external skill
- ✅ Learned about safety: allowlists, ask-first permissions, and the trust ladder

Your agent is no longer a terminal app. It lives on your phone, your Discord, your messaging apps. It checks in with you. It has opinions about your umbrella.

You've built something that most people think requires a team of engineers. You did it with text files and good taste.

---

## Next Up

In [Module 6: Build Something Unique](../06-build-something-unique/), you stop following tutorials and start building YOUR thing. You've got personality, skills, memory, channels, and proactive behavior — now combine them into an agent that solves a problem *you* care about.

→ [Continue to Module 6](../06-build-something-unique/)
