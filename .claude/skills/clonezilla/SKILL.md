---
name: clonezilla
description: Operator guide for Clonezilla (free, open-source disk imaging/cloning via bootable USB — works on Windows, Linux, and Intel Mac drives). Use when the user wants free drive imaging, disk-to-disk cloning, or bare-metal backup/restore without paid software.
---

# Clonezilla

Guide the user through Clonezilla Live: a bootable Linux USB that images or clones whole drives regardless of the installed OS. Text-menu UI, zero cost, extremely reliable — but it will happily destroy the wrong disk if you pick the wrong target, so identify disks carefully at every step.

## Setup (once)

1. Download Clonezilla Live ISO from clonezilla.org (stable, amd64).
2. Write it to a USB stick with Rufus (Windows) or balenaEtcher (Mac/Linux).
3. Boot the machine from the USB (F12/F2/Del boot menu; on Intel Macs hold Option). Pick "Clonezilla live (Default settings)", accept language/keyboard defaults.

## Core jobs

**Image a disk to a file (backup):**
`device-image` → `local_dev` → pick the EXTERNAL drive as image repository → `savedisk` → name the image with date + machine → select SOURCE disk → accept defaults (`-z9p` zstd compression is fine) → say YES to "check the saved image".

**Restore an image:**
`device-image` → `local_dev` → mount the repo drive → `restoredisk` → pick image → pick TARGET disk. Target must be ≥ the original disk size (Clonezilla does not shrink; it CAN restore to bigger, then you grow the partition afterwards with GParted/Disk Management).

**Direct disk-to-disk clone (drive upgrade):**
`device-device` → `disk_to_local_disk` → SOURCE first, TARGET second — triple-check by size and model shown in the menu (`sda`/`sdb`/`nvme0n1` labels, not guesses). Everything on the target is erased.

## Disk identification ritual (do this every time)

Before confirming any operation, have the user match each device label to its size and model in the Clonezilla menu (e.g. "sda 512GB Samsung = laptop SSD, sdb 2TB Seagate = backup USB"). If the two drives are the same size and brand, unplug everything non-essential and re-check. This is the only dangerous moment in Clonezilla.

## Rules

- Clonezilla can't image a drive it's running from and can't do incremental backups — for scheduled/incremental Windows backups, use the macrium-reflect skill instead.
- Encrypted drives (BitLocker/FileVault) image fine in raw mode but bloat the image; suggest decrypting first or using sector-smart tools.
- Apple Silicon Macs cannot boot Clonezilla — Mac users on M-series need Carbon Copy Cloner or ASR instead.
- After a clone/restore, the first boot may run a disk check — that's normal, let it finish.
