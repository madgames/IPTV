---
name: macrium-reflect
description: Operator guide for Macrium Reflect (Windows disk imaging/cloning). Use when the user wants to image, clone, back up, restore, or migrate a Windows drive with Macrium Reflect — "image my drive", "clone to SSD", "restore my backup", "upgrade my hard drive".
---

# Macrium Reflect

Guide the user through drive imaging and cloning with Macrium Reflect (Reflect X). Windows only — on macOS point them to Carbon Copy Cloner, for free/cross-platform use the clonezilla skill.

## Core jobs

**Full disk image (the backup):**
1. Open Reflect → Backup tab → "Image selected disks" → tick the whole system disk (all partitions incl. EFI + recovery — never just C:).
2. Destination: a DIFFERENT physical drive (external USB is fine). Never image a disk onto itself.
3. Advanced options → enable "Verify image directly after creation".
4. Save as a Backup Definition File so it's repeatable, then run.

**Clone to a new drive (the migration):**
1. Connect the new drive (USB adapter or second slot). Clone tab → "Clone this disk" → source = old, target = new.
2. Drag partitions across in order; if the new drive is bigger, resize C: to fill the leftover space; if smaller, shrink C: first (target must fit USED data, not disk size).
3. Cloning ERASES the target — confirm the target model/size out loud before hitting go.
4. After cloning: swap drives or change boot order in BIOS/UEFI. Boot the clone BEFORE wiping the old drive.

**Restore:**
- Working Windows: Restore tab → pick image → target disk.
- Dead Windows: boot the Rescue Media USB → restore from there. This is why rescue media exists — walk the user through "Other Tasks → Create Rescue Media" (1 GB+ USB stick) the FIRST time they use Reflect, before they need it.

**Schedule:** edit the Backup Definition → Schedule. Sensible default: monthly Full + weekly Differential, retention "keep 2 fulls". Incrementals need the paid tier.

## Rules

- Always verify: a backup that was never verified or test-restored is a hope, not a backup.
- Images (.mrimg) are compressed snapshots you browse/mount in Explorer; clones are bootable copies. Backup = image. Drive upgrade = clone.
- Free edition is discontinued; current is Reflect X paid/trial. Don't point the user at "Reflect Free" downloads from third-party sites — malware risk.
- Laptop must be on mains power for long imaging jobs.
