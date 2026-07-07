---
name: handoff
description: Compress the entire current conversation into a clean, structured handoff document. Use when the user says "handoff", "summarize this thread", "I need to continue this elsewhere", or a long session is ending and its state needs to survive.
---

# Handoff

Produce a document that lets a fresh session (or another person) continue this work with zero access to the current conversation.

## Structure

```
# Handoff — <topic> — <date>

## Goal
What the user is ultimately trying to achieve, in 1-3 sentences.

## Current state
What's DONE (with file paths, URLs, IDs of everything created).
What's IN PROGRESS and exactly where it stopped.
What's NOT STARTED.

## Key decisions
Each decision made along the way + the reason, one line each.
Include options that were considered and rejected, so they don't get re-litigated.

## Facts discovered
Non-obvious things learned during the work (bugs found, constraints hit,
things that turned out to be blocked/impossible, credentials or access quirks).

## Open questions
Anything unresolved that the next session must answer or ask the user.

## Next steps
Numbered, concrete, in order. First step should be executable immediately.
```

## Rules

- Write for someone with NO context: expand codenames and in-jokes, spell out paths and URLs in full.
- Facts over narrative — nobody needs the play-by-play of failed attempts, only what they proved.
- Include exact identifiers: branch names, trigger IDs, file paths, ticket numbers, links.
- Keep it under a page unless the work genuinely spans more.
- Deliver as a markdown file if the user will move it between tools; inline in chat otherwise.
