# 🏆 Module 3 Challenge: The Memory Test

## Your Mission

Prove your agent truly remembers you by having a multi-session conversation where context carries over naturally.

## Requirements

### Part 1: Set Up Context
1. Write a detailed **USER.md** (at least 10 facts about yourself)
2. Write an **AGENTS.md** with at least 5 operating rules
3. Have a conversation where you tell your agent:
   - Something you're excited about
   - Something you need help with
   - A preference ("I always want X when Y")

### Part 2: The Memory Test
4. **Close the chat completely**
5. **Open a new chat** and ask these questions — WITHOUT repeating any context:
   - "What should I focus on today?"
   - "Can you help me with that thing I mentioned?"
   - "What do you know about me?"

6. **Grade your agent's memory** for each question:
   - 🟢 **Remembered perfectly** — referenced specific details
   - 🟡 **Partially remembered** — got the gist but missed details
   - 🔴 **Forgot** — had no idea what you were talking about

### Part 3: Memory Surgery
7. Open your agent's memory files (`memory/` folder and `MEMORY.md`)
8. Find the memories from your conversation
9. **Add one secret preference** directly to MEMORY.md
10. Start a new chat and see if the agent uses it naturally

## Bonus Points

- 🌟 Have 3+ separate conversations across different times and track how memory builds up
- 🌟 Intentionally correct your agent ("Actually, I changed my mind about X") and see if it updates its memory
- 🌟 Read through your agent's daily memory files and rate how good its note-taking is

## When You're Done

Your agent should score at least 🟢 on 2 out of 3 memory questions, and your secret preference should surface naturally. If it does, your agent isn't just a chatbot anymore — it knows you.

Check [solution/](solution/) for example files.
