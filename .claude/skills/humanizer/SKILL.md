---
name: humanizer
description: Rewrite text so it sounds like a human wrote it. Use whenever the user asks to "humanize", "make this sound less AI", "make it sound like me", or before delivering any outward-facing prose (posts, emails, articles, bios). Kills em dashes, robotic tone, and dead-giveaway AI words.
---

# Humanizer

Rewrite the given text (or your own draft before delivering it) to sound like a real person wrote it. Meaning stays identical; voice changes.

## Hard bans — remove on sight

- Em dashes (—). Replace with a period, comma, or restructure the sentence.
- These words/phrases: delve, dive into, unpack, leverage, robust, seamless, elevate, unlock, supercharge, game-changer, revolutionize, landscape (metaphorical), tapestry, testament to, "it's worth noting", "in today's fast-paced world", "at the end of the day", "moreover", "furthermore", "in conclusion", "whether you're X or Y", "look no further", "that being said".
- Rule-of-three lists bolted onto sentences ("clear, concise, and compelling").
- Rhetorical questions the text immediately answers itself.
- Every sentence starting the same way, or every paragraph being 2-3 sentences of identical shape.
- Exclamation marks doing enthusiasm the words didn't earn.
- Hedging stacks: "could potentially", "might possibly", "it seems that perhaps".

## What to do instead

- Vary sentence length hard. Some short. Some that run on a bit because that's how people actually explain things.
- Use contractions (don't, it's, you're) unless the context is formal legal/academic.
- Concrete beats abstract: "cut load time from 8s to 2s" not "significantly improved performance".
- One idea can just be stated. Not every claim needs a qualifier and a counterpoint.
- Keep the occasional imperfection: a sentence fragment, a parenthetical aside, starting with "And" or "But".
- Match the register the user actually writes in (check their messages for tone).

## Process

1. Read the text, list the violations you see.
2. Rewrite fully. Do not just patch banned words with synonyms; fix the rhythm.
3. Output the rewrite only (no commentary), unless the user asked to see the changes.
