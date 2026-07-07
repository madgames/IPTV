# Claude toolkit repo (John's)

This repo is John's personal Claude toolkit: reusable skills live in `.claude/skills/`
and load automatically in every session. It has no application code; it used to be
called IPTV and may be renamed to "Claude".

## How John works with Claude

- Casual, direct, sweary — match it. No corporate tone, no fluff, no lectures.
- Deliver results, not options. If something can't be done, say so bluntly and give
  the one workaround that actually works.
- He shares "Claude tips" infographics from social media. Extract anything genuinely
  useful, call out the snake oil, and codify keepers as skills here rather than
  pretending to "learn" them.

## Distilled playbook (the parts of the guru advice that are actually true)

- One well-written context file beats dozens of pasted prompts. Be intentional about
  what goes in this file; don't dump everything.
- Skill vs project: if it's a repeatable behavior you could teach a person, make it a
  skill in `.claude/skills/`. If it's one client/one job, it's just a task.
- Writing for the outside world goes through the `humanizer` skill: no em dashes, no
  "delve/leverage/game-changer", varied sentence rhythm.
- Long thread going stale? Use the `handoff` skill to compress state, then start
  fresh — better than dragging a 100-message session. (But "new session every 20
  messages" as a hard rule is nonsense; restart when quality drops, not on a counter.)
- Scheduled/recurring jobs are real and useful (send_later / Routines) — e.g. the
  daily tracklist watches used in this repo's sessions.
- Genuinely useful GitHub projects if ever needed: anthropics/skills (official skill
  examples), Repomix (pack a repo into one AI-readable file), ccusage (Claude Code
  token/cost tracking), obra/superpowers (planning/review workflows).
- Ignore: "delete all your .md files", "turn every setting off", "never follow up",
  and any advice that contradicts the same poster's other advice.

## Repo conventions

- Skills: one folder per skill, `SKILL.md` with frontmatter (`name`, `description`
  with explicit trigger phrasing), body under ~60 lines. Use the `write-a-skill`
  skill to add new ones.
- Work happens on `claude/*` branches; this repo's default branch currently is
  `claude/facebook-share-link-gm81rf` (the repo started empty).
