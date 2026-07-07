---
name: superduper
description: Operator guide for SuperDuper! — the simple Mac drive cloning/backup tool. Use when the user wants a dead-simple Mac backup or clone with SuperDuper, or is choosing between SuperDuper and Carbon Copy Cloner.
---

# SuperDuper!

Guide the user through SuperDuper! (Shirt Pocket, free tier + ~$28 license). Its whole personality is one sentence on screen: "Copy Macintosh HD to Backup Drive using Backup - all files." If the user wants simple and cheap, this is it; if they want snapshots, dashboards and per-file history, point at the carbon-copy-cloner skill.

## Core jobs

**Full backup ("Backup - all files"):**
1. External drive erased as **APFS, GUID partition map** in Disk Utility.
2. SuperDuper: Copy [Macintosh HD] to [External] using **"Backup - all files"** → Copy Now.
3. The result is a complete, Finder-browsable copy of your data.

**Keep it fresh (needs the paid license):**
- **Smart Update** — recopies only what changed; turns hours into minutes. This is the feature you're paying for.
- **Schedule** ("Copy on a schedule" / when drive connects) so it happens without you.
- **Sandbox** — a niche gem: a bootable-ish test copy you can try risky updates on.

**Restore:**
- Files: drag them back in Finder — it's all plain files.
- Whole Mac: reinstall macOS → **Migration Assistant → point it at the SuperDuper backup drive**. (Same modern-Mac reality as CCC: on Apple Silicon, data backup + Migration Assistant beats chasing a bootable clone; SuperDuper's "fully bootable" era was Intel Macs.)

## Rules

- "Backup - all files" is the only copy script most people should ever use; "Backup - user files" skips apps/settings and makes restores worse.
- Smart Update ERASES things on the destination that no longer exist on the source — the destination mirrors the source. It is a clone, not a version history. For deleted-file protection pair it with Time Machine.
- Free version = full copies only, no Smart Update, no scheduling. Fine for a one-off clone before a risky change; pay if it's your routine backup.
- Same hygiene as any backup: encrypt the drive if using FileVault, grant Full Disk Access when prompted, and spot-check the copy occasionally in Finder.
