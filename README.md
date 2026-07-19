<div align="center">

# 🛠 ɅnyDesk Reset / Backup Tool

A safe Windows utility to **reset ɅnyDesk**, **back up your `user.conf`**, and **restore** it whenever you need to — all from a single interactive menu (colorized in PowerShell, plain in Batch).

![Platform](https://img.shields.io/badge/platform-Windows-0078D6?logo=windows&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?logo=powershell&logoColor=white)
![Batch](https://img.shields.io/badge/Batch-script-4D4D4D?logo=windowsterminal&logoColor=white)
![Admin required](https://img.shields.io/badge/requires-Administrator-red)

</div>

---

## ⚡ Quick Start

Run this **one-liner** in an elevated PowerShell window to download and launch the tool:

```powershell
iwr -useb https://raw.githubusercontent.com/OFiberPH/Adesk-Tool/main/reset-adesk-oneliner.ps1 | iex
```

> ⚠️ **Run PowerShell as Administrator first.** The script auto-prompts for elevation, but starting elevated avoids a second UAC round-trip. Without admin rights the reset/backup will fail.

---

## 📌 Features

- ✅ **Reset ɅnyDesk** without touching your `user.conf`
- ✅ **Clean reset** — auto-backup first, then remove `user.conf`
- ✅ **Backup** `user.conf` **and** `thumbnails` with a timestamp
- ✅ **Restore** from any saved backup (pick which one)
- ✅ **Auto-elevation** — the script relaunches itself as Administrator if needed
- ⚠️ Resetting **regenerates a new AnyDesk ID**
- ⚠️ Saved devices must **re-enter the password** after a reset

---

## 📂 Backup Location

All backups are stored in:

```
%USERPROFILE%\Documents\Adesk
```

Each backup is timestamped (`YYYYMMDD-HHMMSS`) and includes:

| File | Description |
|------|-------------|
| `user.conf.YYYYMMDD-HHMMSS.bak` | Your AnyDesk configuration |
| `thumbnails.YYYYMMDD-HHMMSS.bak` | Remote desktop thumbnails |

**Example:**

```
user.conf.20251001-143025.bak
thumbnails.20251001-143025.bak
```

---

## 🚀 How to Run

![How to run](tut.gif)

### 🔹 PowerShell (recommended)

**Option 1 — Run directly from the web (fastest):**

```powershell
iwr -useb https://raw.githubusercontent.com/OFiberPH/Adesk-Tool/main/reset-adesk-oneliner.ps1 | iex
```

**Option 2 — Download & run locally:**

```powershell
powershell -ExecutionPolicy Bypass -File ".\reset-adesk.ps1"
```

### 🔹 Batch version (no colors)

Prefer a plain `.bat` tool? Double-click it, or run:

```bat
reset-adesk.bat
```

---

## 📜 Menu Options

When executed, you'll see:

```
  ==================================================
     _       _           _      _____           _
    / \   __| | ___  ___| | __ |_   _|__   ___ | |
   / _ \ / _  |/ _ \/ __| |/ /   | |/ _ \ / _ \| |
  / ___ \ (_| |  __/\__ \   <    | | (_) | (_) | |
 /_/   \_\__,_|\___||___/_|\_\   |_|\___/ \___/|_|
  ==================================================
            AnyDesk Reset / Backup Tool
          github.com/OFiberPH/Adesk-Tool
  ==================================================

   Backups: C:\Users\<you>\Documents\Adesk

   [1] Reset AnyDesk          (keep user.conf)
   [2] Clean Reset AnyDesk    (backup + remove user.conf)
   [3] Backup user.conf
   [4] Restore user.conf      (from a saved backup)
   [5] Exit
  --------------------------------------------------
```

| Option | Action |
|:------:|--------|
| **1** | Reset AnyDesk, keeping your `user.conf` |
| **2** | Clean reset — back up, then remove `user.conf` |
| **3** | Back up `user.conf` (and `thumbnails`) |
| **4** | Restore `user.conf` from a saved backup |
| **5** | Exit |

---

## ⚠️ Notes & Warnings

- Works only on **Windows** with AnyDesk installed in the default path.
- Always **run as Administrator** — the script checks and auto-prompts if not elevated.
- A reset will **regenerate a new AnyDesk ID**.
- After a reset, the **Unattended Access password must be re-set**, and **all devices must re-authenticate**.

---

## 🙏 Credits

Based on the original [Adesk-Tool by Kintoyyy](https://github.com/Kintoyyy/Adesk-Tool).
Maintained by [OFiberPH](https://github.com/OFiberPH/Adesk-Tool).
