---
name: carbon-copy-cloner
description: Operator guide for Carbon Copy Cloner (CCC) — Mac drive cloning and backup. Use when the user wants to back up, clone, image, or migrate a Mac drive — "clone my Mac", "back up my MacBook to an external drive", "upgrade my Mac's SSD".
---

# Carbon Copy Cloner (CCC)

Guide the user through Mac backups with CCC (Bombich Software, ~$50 one-off, 30-day full trial). The modern Mac reality up front: since Big Sur/Apple Silicon, macOS locks the system volume, so **the gold standard is a "Standard Backup" of your data + apps, restored via Migration Assistant** — not the bootable clones of old. CCC can still try a full bootable "Legacy Bootable Copy" but even Bombich recommends against relying on it.

## Core jobs

**First backup (the one that matters):**
1. Connect an external drive at least as large as the data used. Erase it in Disk Utility as **APFS, GUID partition map** first.
2. CCC → New Task → Source: Macintosh HD → Destination: the external.
3. Leave "Standard Backup" selected. Run. First pass copies everything; later runs copy only changes.

**Automate it:** task → Automation → run Hourly/Daily or "When source or destination is reconnected" (best for laptops with an external drive on a desk). CCC keeps **SafetyNet snapshots** so older versions of changed/deleted files survive — leave it on.

**Restore:**
- Individual files: browse the destination in Finder or use CCC's snapshot browser — backups are plain files, no proprietary format.
- Whole Mac: clean-install macOS (or new Mac out of box) → **Migration Assistant → "From a Mac, Time Machine backup or Startup disk" → pick the CCC backup drive**. Everything comes back: apps, settings, users.

**Drive upgrade / new Mac migration:** same as restore — Standard Backup of the old drive, then Migration Assistant onto the new one. Don't chase bootability.

## Rules

- CCC and Time Machine are complements, not rivals: TM for continuous versioning, CCC for a complete, Finder-browsable second copy. Paranoid-correct setup is both, on different drives.
- Encrypt the backup drive (right-click in Finder → Encrypt) if the Mac uses FileVault — otherwise the backup is the unencrypted copy of everything.
- First run needs Full Disk Access granted to CCC (it prompts; System Settings → Privacy & Security).
- Verify occasionally: open the destination, spot-check recent files, and once in a while do a trial Migration Assistant run on a spare account. An unverified backup is a hope.
