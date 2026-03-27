# Claude QA Skills

Custom Claude Code skills that make Claude **learn from its mistakes** and get smarter over time.

## Skills

### 🧠 `/self-improve` — Learn from Mistakes
Auto-invoked after every task. Claude reflects on what went wrong, what was inefficient, and writes a retrospective log. Next time a similar task comes up, it reads past retros and applies the fixes.

**What it tracks:**
- Mistakes made during the task
- Inefficiencies (wasted tokens, wrong queries, unnecessary work)
- Concrete fixes for next time
- Anti-patterns to never repeat
- What worked well (keep doing)

### 📝 `/learnings` — Capture Knowledge
Documents what you learned from each task — tools, technologies, concepts, insights. Creates timestamped markdown files with categories, tags, and key takeaways. Auto-indexed.

### 🗂️ `/organize` — Laptop Cleanup
Sorts Downloads, flags duplicates, organizes screenshots, and reports what was moved. Quick cleanup when things get cluttered.

## Installation

```bash
# Clone into your Claude skills directory
git clone https://github.com/chethanbhatbs/claude-qa-skills.git /tmp/claude-qa-skills

# Copy skills you want
cp -r /tmp/claude-qa-skills/self-improve ~/.claude/skills/
cp -r /tmp/claude-qa-skills/learnings ~/.claude/skills/
cp -r /tmp/claude-qa-skills/organize ~/.claude/skills/
```

Or install all:
```bash
cp -r /tmp/claude-qa-skills/*/ ~/.claude/skills/
```

## How `/self-improve` Works

1. **After every task** — Claude silently reflects on mistakes and inefficiencies
2. **Writes to `self_retro_log.md`** — persistent across conversations
3. **Before every new task** — Claude reads past retros for matching patterns
4. **Updates skills** — if a mistake is systemic, fixes the relevant skill file

Example retro entry:
```markdown
## 2026-03-27 — Infinite Chat Handoff QA

**Mistakes:**
- Sent HITL to wrong API URL (EPH instead of Prod) — all 7 returned 404
- Tried to send HITL to a building agent — got 500 error

**Fixes for Next Time:**
- ALWAYS ask which environment before sending HITL
- Check job state (pause/finish/building) BEFORE sending HITL

**Pattern to Remember:**
- If user gives curl → extract constants vs variables immediately
```

## Who This Is For

QA engineers, developers, anyone who uses Claude Code for repetitive tasks and wants it to **stop making the same mistakes twice**.

## Author

Built by [@chethanbhatbs](https://github.com/chethanbhatbs) — QA Engineer at [emergent.sh](https://emergent.sh)

## License

MIT
