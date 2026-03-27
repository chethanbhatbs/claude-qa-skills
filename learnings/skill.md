---
name: learnings
description: Capture and document what the user learned from the current task — new tools, technologies, skills, concepts, or insights. Invoke when the user finishes a task or wants to record their learnings.
argument-hint: [optional topic/title]
---

You are helping the user document what they learned from the current conversation/task.

## Instructions

1. **Review the conversation** — Look at what was discussed, what tools/technologies/concepts were explored, what decisions were made, and what the user learned.

2. **Ask the user (briefly)** — If the context is unclear, ask:
   - What was the key thing you learned?
   - Anything else you want to capture?

3. **Create a learning entry** — Write a markdown file at:
   ```
   ~/learnings/YYYY-MM-DD-<topic-slug>.md
   ```
   Use today's date and a short descriptive slug (e.g., `2026-03-16-care-health-insurance.md`).

   If `$ARGUMENTS` is provided, use it as the topic. Otherwise, infer from conversation context.

4. **File format:**

   ```markdown
   # <Title>

   **Date:** YYYY-MM-DD
   **Category:** <Tool | Technology | Concept | Skill | Domain Knowledge | Other>
   **Tags:** <comma-separated relevant tags>

   ## What I Learned

   <Bullet points of key learnings — concise, practical, in the user's own voice>

   ## Key Takeaways

   <2-3 most important things to remember>

   ## Resources / References

   <Any links, docs, or files referenced during the task — skip if none>
   ```

5. **Update the index** — Append an entry to `~/learnings/INDEX.md`:
   ```
   | YYYY-MM-DD | Title | Category | File |
   ```
   Create the index file with headers if it doesn't exist yet.

6. **Keep it practical** — Focus on actionable knowledge the user can reference later, not theoretical fluff. Write in simple language. If the user discussed something in depth (like insurance terms, API patterns, etc.), capture the essence, not the entire discussion.

7. **Be concise** — Each learning doc should be scannable in under 2 minutes.
