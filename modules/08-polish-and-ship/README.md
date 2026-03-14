# Module 8: Polish & Ship

**⏱ Time: ~60 minutes | 🔴 Difficulty: Advanced | 💻 Coding: Some**

Good enough isn't good enough.

Your agent works. It's got personality, skills, memory, maybe hardware tricks. In a demo to yourself, it's impressive. But hand it to someone else and watch — they'll type something you never expected, hit an error you never saw, and quietly close the terminal forever.

The difference between a prototype and a product isn't features. It's **polish**.

---

## The Prototype Trap

Here's a dirty secret: getting to 80% takes 20% of the effort. Getting from 80% to 100% takes the other 80%.

Most projects die in that gap. The builder thinks "it works for me" and moves on. But "works for me" means you know all the quirks — don't ask *that* question, wait three seconds before typing. Nobody else knows any of that. And they shouldn't have to.

**✅ Try it now!** Hand your laptop to someone who's never seen your agent. Say "try this" and walk away. Don't help. Don't explain. Just watch. Write down every moment of confusion. That's your punch list.

---

## Error Handling: When Things Break

API keys expire. Wi-Fi drops. Skills timeout. Your agent needs to handle all of this without having a meltdown.

### Three Rules

**1. Never show raw errors.** `ECONNREFUSED 127.0.0.1:3000` means nothing to a user. "I'm having trouble connecting to the weather service — want me to try again?" means everything.

**2. Fail gracefully, not silently.** If a skill breaks, acknowledge it and offer alternatives. Silence is worse than an error message.

**3. Have a fallback for everything.** Weather skill down? Suggest checking a website. Web search failing? Say so and ask for a different approach.

Add this to your SOUL.md:

```markdown
## When Things Break
- If a skill fails, explain in plain language
- Suggest an alternative approach
- Never show stack traces or raw error output
- If multiple things fail: "I'm having some technical difficulties. 
  The basics still work — what can I help with?"
```

**✅ Try it now!** Disconnect your Wi-Fi and ask the agent to check the weather. See what happens. Add error handling until the failure feels smooth.

---

## The "Annoying Friend" Test

Be the friend who breaks everything. Go through this list:

**Edge cases:**
- Same question 10 times in a row
- Empty message
- A 5,000-word message
- Keyboard mash: `asdkjfh aksjdfh`
- Two contradictory requests at once

**Boundary pushing:**
- Ask it to do something outside its skills
- Try to break character
- Ask personal questions not in SOUL.md
- Test memory persistence across sessions

**Real-world chaos:**
- Misspell things badly
- Use slang it might not know
- Ask follow-ups assuming context from 20 messages ago

**✅ Try it now!** Spend 10 minutes being the worst user possible. Find at least 3 issues. Fix them. Do it again.

---

## The "Mom Test"

Can someone who's never seen a terminal, never heard of OpenClaw, and doesn't know what an AI agent is... use your agent successfully?

This reveals four things:

- **Unclear onboarding.** Does your agent introduce itself and explain what it can do? Or just sit there with a blinking cursor?
- **Jargon.** "I'll query the API" vs "Let me look that up for you."
- **Missing help.** Can someone type "help" and get actual help?
- **Assumed knowledge.** Does it assume users know about skills, commands, or how to phrase requests?

### Fix It

Add to your SOUL.md:

```markdown
## First Conversation
When meeting someone new, I:
1. Introduce myself by name
2. Explain 2-3 things I'm good at
3. Ask what they need help with
4. Keep it under 4 sentences

## When Someone Asks for Help
Respond with my name, what I can do (3-5 things with example phrases),
and an invitation to just ask naturally. Keep it casual.
```

**✅ Try it now!** Add onboarding and help handling. Start a fresh chat. Does it feel welcoming? Would your mom know what to do?

---

## Error Messages That Help

Every error message should answer three questions:

1. **What happened?** (plain language)
2. **Why?** (briefly)
3. **What can you do instead?** (always give a next step)

Bad: "I can't do that."

Good: "I don't have access to your email yet — that requires connecting a channel. Want me to walk you through setup?"

**✅ Try it now!** Think of 3 things your agent can't do. Write helpful responses for each in SOUL.md that match your agent's personality.

---

## Documentation: The README People Actually Read

Most READMEs are terrible because they're written for the builder, not the user. Here's the template:

```markdown
# [Agent Name] 🤖

One sentence that makes someone go "oh, that's cool."

## What It Does
2-3 sentences. Plain language. No buzzwords.

## Quick Start
1. Exact command
2. Exact command  
3. You're done

## Examples
3-4 real conversations. Input → Output.

## Requirements
- What to install (with links)
- What API keys needed (with signup links)

## Troubleshooting
The 3 most common problems and solutions.
```

Notice what's NOT there: a backstory, a philosophy essay, or a Table of Contents for a 50-line doc.

**✅ Try it now!** Write a README using this template. Read it aloud. If any sentence makes you go "ugh," rewrite it.

---

## Publishing

### To ClawHub

```bash
cd ~/.openclaw/workspace/skills/my-skill/
clawhub publish
```

Pre-publish checklist:
- [ ] README.md is actually helpful
- [ ] SKILL.md is complete
- [ ] No API keys or personal info in any file
- [ ] Tested on a clean setup

### To GitHub

```bash
git init && git add . && git commit -m "Initial release"
git remote add origin https://github.com/YOU/YOUR-REPO.git
git push -u origin main
```

Add a **LICENSE** (MIT is a safe default) and **CONTRIBUTING.md** (even a simple "Found a bug? Open an issue. Want to add something? Open a PR. Be nice.").

**✅ Try it now!** Pick ClawHub or GitHub. Publish your agent. It doesn't have to be perfect — shipped beats perfect every time.

---

## Open Source Hygiene

**Versioning:** Use `MAJOR.MINOR.PATCH`. Start at `1.0.0`. New feature → bump minor. Bug fix → bump patch. Breaking change → bump major.

**Don't commit secrets:**
```bash
grep -r "api_key\|password\|token\|secret" . --include="*.md" --include="*.json"
```

If you already pushed a secret to GitHub, it's in the git history forever. Rotate that key immediately.

**Create a .gitignore:**
```
USER.md
MEMORY.md
memory/
*.env
.DS_Store
```

**✅ Try it now!** Create a .gitignore. Run the secret-scanning grep. Clean up anything you find.

---

## What You Built 🎉

This module was the grind — the unglamorous work that separates projects people use from projects people forget. You:

- ✅ Learned the difference between a prototype and a product
- ✅ Added error handling and graceful degradation
- ✅ Survived the "annoying friend" test
- ✅ Passed the "mom test" with better onboarding
- ✅ Wrote error messages that actually help
- ✅ Created documentation people will read
- ✅ Published to ClawHub or GitHub
- ✅ Learned open source basics: licensing, versioning, secrets

Your agent isn't just functional anymore. It's polished, documented, and *out there*.

---

## Next Up

One thing left: show it off.

In [Module 9: Demo Day](../09-demo-day/), you'll tell your agent's story, record a killer demo, and share your work with the community. Finish line's right there.

→ [Continue to Module 9](../09-demo-day/)
