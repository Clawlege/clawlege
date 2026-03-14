# Module 7: Hardware Week

**⏱ Time: ~60 minutes | 🟡 Difficulty: Intermediate | 💻 Coding: Some**

Your agent has been living inside a terminal. Comfortable, sure. But a little... caged.

Time to let it out.

In this module, your agent escapes the computer and enters the physical world — running on your phone, seeing through cameras, knowing where you are, and maybe living on a $35 Raspberry Pi that never sleeps.

---

## Why Hardware Matters

Up until now, your agent has been all brain and no body. It can think, remember, search the web, send messages — but it has no senses. It can't see what's in front of you, doesn't know if you're at home or at the coffee shop, can't hear you call its name.

Hardware changes that. Connect your phone and your agent gains **eyes** (camera), **location sense** (GPS), and **a way to tap you on the shoulder** (notifications). Connect a Raspberry Pi and it gains **insomnia** — it never sleeps, never needs your laptop open.

Think of it like this: your agent has been a brain in a jar. Now you're giving it a body. Multiple bodies, actually — and they all share the same brain.

---

## The Node System

OpenClaw uses a **node system**. Your main machine is the brain. Other devices connect as **nodes** — extensions of that agent into the physical world.

```
         Your Agent (brain)
         ┌──────────────┐
         │   Laptop /   │
         │   Desktop    │
         └──────┬───────┘
                │
    ┌───────────┼───────────┐
    │           │           │
 📱 Phone    🍓 Pi     🔊 Speaker
  (node)     (node)     (node)
```

Each node brings different capabilities. Phone gives you camera and GPS. Pi gives you always-on persistence. But it's still **one agent** — same personality, same memory, same everything. The nodes are just its hands and eyes in different places.

**✅ Try it now!** Check your current nodes:

```bash
openclaw node list
```

You should see at least one: your current machine. That's home base.

---

## Lesson 1: Phone as a Node

Your phone is the most powerful sensor package you own. Camera, GPS, accelerometer, microphone — always in your pocket. Let's connect it.

### Pairing

**Step 1:** Install the OpenClaw app from the App Store (iOS) or Google Play Store (Android).

**Step 2:** Generate a pairing code on your computer:

```bash
openclaw node pair
```

This shows a QR code and a 6-digit code. Either works.

**Step 3:** Open the app on your phone, tap "Connect to Agent," and scan the QR code or enter the code.

**Step 4:** Verify:

```bash
openclaw node list
```

```
NODES:
  📍 macbook-pro (this device) — brain
  📱 davids-iphone — node (connected)
```

Your phone is now part of your agent.

**✅ Try it now!** Pair your phone. If you don't have the app yet, read through and come back — everything else in this module works without it.

---

### What Your Phone Can Do

Once paired, just talk naturally. No new syntax needed.

**Camera:** "Take a photo and tell me what you see." Your agent captures from the phone camera and analyzes it. Try pointing at a plant ("what kind is this?"), a document ("read this for me"), or a whiteboard after class.

**Location:** "Where am I right now?" or "Find coffee shops near me." Your agent accesses GPS (with your permission) and combines it with web search for location-aware answers.

**Notifications:** "Remind me to buy milk when I'm near a grocery store." Your agent pushes proactive alerts to your phone — even when you're away from your computer.

**✅ Try it now!** With your phone paired, ask your agent to describe what your phone camera sees. Watch the request flow from computer → phone → back.

### Privacy Controls

Your agent accessing your camera and location is powerful. It's also sensitive. You control everything:

```bash
openclaw node permissions davids-iphone --camera off
openclaw node permissions davids-iphone --location on
openclaw node permissions davids-iphone --notifications on
```

Every hardware request triggers a confirmation on your phone the first time. No creepy surveillance — you're always in control.

---

## Lesson 2: Raspberry Pi Setup (Optional)

A Raspberry Pi is a $35 computer the size of a credit card. And it's the perfect home for an always-on agent.

### Why a Pi?

Your laptop sleeps. Your desktop might be off. A Pi is a little digital hearth — always on, always ready, barely sipping electricity (~$5/year).

With your agent on a Pi:
- Heartbeat checks run 24/7
- Cron jobs fire without your laptop open
- Email/calendar monitoring happens overnight
- It's ready the instant you message it

If your phone gives your agent eyes, the Pi gives it *insomnia*.

### What You Need

- **Raspberry Pi 4 or 5** (4GB RAM recommended)
- **microSD card** (32GB+) with Raspberry Pi OS
- **USB-C power supply**
- **Ethernet or WiFi**
- Optional: a case (keeps dust out)

Never set up a Pi? The [Raspberry Pi getting started guide](https://www.raspberrypi.com/documentation/computers/getting-started.html) walks you through it. Flash the OS, plug it in, done.

### Installation

SSH into your Pi and install OpenClaw:

```bash
ssh pi@raspberrypi.local

# Install Node.js
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt-get install -y nodejs

# Install OpenClaw
npm install -g openclaw

# Join as a node of your existing agent
openclaw node join
```

The `node join` command connects your Pi to your main machine. It's now another body for the same agent brain.

**Set it to auto-start on boot:**

```bash
openclaw service install
```

Reboot, unplug the monitor. Your Pi agent is running invisibly.

**✅ Try it now!** If you have a Pi, set it up. If not, skip to Lesson 3 — you can always come back.

---

## Lesson 3: Sensors and the Physical World

With hardware connected, your agent perceives things it never could before.

### Cameras

The most immediately useful sensor. With your phone or a USB camera on your Pi:

- **Read text** — point at a sign, document, or whiteboard
- **Identify objects** — "what kind of bird is that?" (try it, seriously)
- **Scan barcodes/QR codes** — instant product lookup
- **Help with homework** — photo of a math problem → solution

```
You: "Take a photo and tell me what you see"
Agent: [captures from phone camera]
Agent: "I see a desk with a laptop, a coffee mug (almost empty),
        two textbooks — biology and calculus — and a fidget spinner.
        Study session? How's it going?"
```

### Location as Context

GPS isn't just coordinates — it's *context*. When your agent knows where you are:

- **At home:** "Morning! No classes until 10. Review flashcards?"
- **At school:** Agent enters quiet mode automatically
- **At the store:** "You're near Target. Didn't you need a phone charger?"
- **New city:** "Want me to find restaurants nearby?"

This is **context-aware computing** — your agent reads the situation, not just your messages.

### Microphones

With a mic (phones have them, USB mics work on Pis):

- **Voice commands** — talk to your agent hands-free
- **Transcription** — record a lecture, get notes back
- **Sound detection** — doorbell, alarm, specific triggers

Imagine walking into your room: "Hey [agent name], what's on my schedule?" and hearing it respond through a speaker. That's the vibe.

**✅ Try it now!** Use a hardware sensor — take a photo, check your location, or try a voice command. Pick whichever device you have connected.

---

## Lesson 4: Multi-Device Setups

This is where the node system really shines.

### One Brain, Multiple Bodies

```
  📱 Phone      🍓 Pi         💻 Laptop
  • Camera      • Always on    • Heavy work
  • GPS         • Cron jobs    • Coding
  • Notify      • Monitoring   • Research
```

Your agent automatically routes requests to the right node. Need a photo? → Phone. Scheduled job at 3 AM? → Pi. Large dataset analysis? → Laptop.

You can also set explicit preferences:

```bash
openclaw node route --capability camera --prefer davids-iphone
openclaw node route --capability always-on --prefer raspberrypi
```

### A Day in the Life

**7:00 AM:** Your Pi has been running overnight — checked email, pulled weather, compiled your calendar. When you grab your phone:

> "Morning! Nothing urgent. Team meeting at 10, soccer practice at 4. 65° — perfect for practice. ⚽"

**At school:** Phone GPS detects you're at school → quiet mode. After class, you snap the whiteboard:

> "Got it. Those are the Chapter 7 equations — kinetic energy and momentum. Add to study notes?"

**Walking home:** Your phone shares your location:

> "You're passing the library. Science fair bibliography is due Thursday — want to grab those two books?"

**Evening:** At your laptop. Your agent pulls up the whiteboard photos, study notes, and textbook chapters. Seamless.

**Overnight:** Pi keeps running. Checks email, preps tomorrow's briefing.

One agent. Three devices. Moving through your day like a shadow with a brain.

**✅ Try it now!** If you have multiple devices connected, check your capabilities map:

```bash
openclaw node capabilities
```

---

## Troubleshooting

Hardware adds complexity. Quick fixes for common issues:

**Phone keeps disconnecting:** Enable "Background Activity" for OpenClaw in your phone settings. Exempt it from battery optimization.

**Pi not responding:**

```bash
ssh pi@raspberrypi.local "openclaw service status"
ssh pi@raspberrypi.local "openclaw service restart"
```

**Camera/location won't work:** Check your phone's system settings (not just the app). On iOS, Location needs "Always" for background features.

**Nodes can't find each other:** If devices are on different networks, enable the relay:

```bash
openclaw node relay enable
```

**✅ Try it now!** Quick health check:

```bash
openclaw node health
```

---

## Challenge: Go Physical 🏆

Prove your agent has a body.

### Requirements

1. **Connect at least one additional device** as a node (phone or Pi)
2. **Use a hardware feature** — camera, location, or agent-triggered notification
3. **Bonus:** Set up a location-based trigger or a scheduled task on a different device

### Test It

```bash
openclaw node list          # Verify nodes
openclaw node test camera   # Test hardware
openclaw chat               # Try it live
> "Take a photo and describe what you see"
> "Where am I right now?"
> "Send me a test notification"
```

---

## What You Built 🎉

Big module. You:

- ✅ Learned the OpenClaw node system
- ✅ Paired your phone (camera, GPS, notifications)
- ✅ Explored Raspberry Pi for always-on operation
- ✅ Used sensors for real-world perception
- ✅ Designed a multi-device architecture
- ✅ Completed the hardware challenge

Your agent is no longer just software. It has a presence in the physical world — it can see, knows where you are, and lives across multiple devices.

That's not a tool anymore. That's a partner.

---

## Next Up

In [Module 8: Polish & Ship](../08-polish-and-ship/), you'll take everything you've built and polish it into something you're proud to show off. Reliability, edge cases, and that last 10% that separates "cool project" from "thing that actually impresses people."

Your agent is almost done. Let's make it shine.

→ [Continue to Module 8](../08-polish-and-ship/)
