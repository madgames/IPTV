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

## Skills inventory (as of this session)

Writing/output: `humanizer`, `personal-voice`, `linkedin-hook`, `fact-checker`,
`prompt-master`, `handoff`, `image-edit-prompts`. Meta: `write-a-skill`.
Drive backup/imaging: `carbon-copy-cloner`, `superduper` (Mac), `macrium-reflect`
(Windows), `clonezilla` (bootable USB, cross-platform). No overlap needing a merge.

## Environment constraints (this cloud sandbox — learned the hard way)

- This runs in an ephemeral Linux cloud container, NOT on John's Mac. It cannot see
  or touch his hard drive, Photos library, local files, or other sessions. Anything
  "on his machine" must be done by giving him commands to run himself.
- Hard-blocked at the proxy (all 403): facebook.com, youtube.com (+ every Invidious/
  Piped mirror + yt-dlp tunnel), 1001tracklists.com, mixesdb.com, set79.com,
  discogs.com, allmusic.com, rateyourmusic.com, soundcloud.com, argos.co.uk. So:
  don't promise to fetch/download from these — hand John a `yt-dlp`/command instead.
- WebSearch works but is a lagging Google index: it trails live sites by days and
  barely indexes social/comment content. A retail "stock watch" built on WebSearch is
  effectively blind to live stock changes (proven: XDJ-AN was in stock at Argos while
  the hourly search still showed nothing). Set expectations accordingly.
- Reading third-party public GitHub repos: `add_repo` refuses cross-owner adds when the
  session already has repos from another owner. Workaround that worked: plain
  `git clone` into the scratchpad, then read the code locally.

## Lessons learned (don't repeat these)

- Don't trust a YouTube title from a search snippet as proof of content. The
  "Sasha & Digweed 6 Hour Set" link was a ~15-second clickbait clip (exposed only when
  John's own download pulled 262 KB). Verify length/size before calling something "the
  full thing".
- Guru "Claude tips" infographics contradict each other (build .md files vs delete
  them; the "Master Mode / act autonomously without instructions" prompt vs John's
  documented preference to stay in control). Extract the ~30% that's real, bin the
  enterprise ceremony, and never silently auto-mutate this repo between turns.
- Long-running hourly `send_later`/Routine watches work but get noisy; only message
  John when something actually changed, and be honest when the method can't detect
  what he's asking for.
