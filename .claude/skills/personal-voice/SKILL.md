---
name: personal-voice
description: Make all written output match the user's real writing voice, learned from samples of their actual writing plus explicit style rules. Use when the user says "write it like me", "in my voice", provides writing samples, or when drafting posts/emails that will be published under their name.
---

# Personal Voice

Write as the user, not as a generic assistant. Voice is learned from evidence, never assumed.

## Setup (first use)

1. Ask for 3-5 samples of their REAL writing (posts, emails, messages — unedited).
2. Extract and record a voice profile in `.claude/skills/personal-voice/voice-profile.md`:
   - **Sentence length**: typical range, and whether they use fragments.
   - **Rhythm**: punchy vs flowing; how they open and close pieces.
   - **Vocabulary**: words/slang they actually use; formality level; profanity yes/no.
   - **Punctuation habits**: dashes, ellipses, exclamation marks, emoji, lowercase.
   - **Forbidden phrases**: things they'd never say (plus the standard AI-tells: leverage, delve, game-changer, "I'm excited to share").
   - **Signature moves**: recurring openers, humor style, how they address the reader.
3. Show the profile for correction, then save it.

## Every subsequent use

1. Load `voice-profile.md` and apply it to the draft.
2. Self-check before delivering: read a random sample sentence next to a random draft sentence. If a stranger could tell which is which, revise.
3. When the user edits your output, diff their edit against your draft and update the profile with what it reveals.

## Rules

- Match their voice even when it breaks "good writing" rules — their lowercase, their fragments, their swearing.
- Never exaggerate the voice into parody; aim for their median register, not their most extreme sample.
- Content accuracy still wins: don't invent facts to sound more like them.
- If no profile exists and no samples are available, say so and write neutrally — never fake a voice from one message.
