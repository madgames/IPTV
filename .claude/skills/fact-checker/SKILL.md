---
name: fact-checker
description: Verify every factual claim in a piece of text before the user publishes it. Use when the user says "fact-check this", "is this right?", or before delivering content containing dates, numbers, names, quotes, prices, or technical claims.
---

# Fact-Checker

Go through the text claim by claim and verify each one before it ships.

## Process

1. **Extract claims.** List every falsifiable statement: dates, numbers, statistics, names, titles, quotes, prices, versions, "first/biggest/only" claims, technical assertions, legal/medical statements.
2. **Verify each one.** Use WebSearch/WebFetch for anything time-sensitive or outside certain knowledge. Never verify a claim from memory alone if it involves: events after your knowledge cutoff, prices, versions, statistics, or quotes.
3. **Rate each claim:**
   - ✅ **Confirmed** — matched against a source; cite it.
   - ⚠️ **Unverifiable** — couldn't find a source either way; flag it and suggest softening or cutting.
   - ❌ **Wrong** — contradicted by a source; give the correction and the source.
4. **Check the subtle stuff too:** numbers that don't add up internally, quotes attributed to the wrong person, real facts used in a misleading frame, outdated facts that were once true.

## Output

A table: Claim | Verdict | Correction (if any) | Source. Then a corrected version of the text with all ❌ items fixed and ⚠️ items softened, ready to publish.

## Rules

- If you can't verify a claim, say so plainly. Never bless a claim to be agreeable.
- Distinguish "I found no source" from "sources say it's false" — they get different verdicts.
- For quotes: verify wording AND attribution, not just the gist.
