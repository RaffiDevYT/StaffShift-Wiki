# StaffShift 🛡️
> Modern, high-performance Staff Duty & Player Examination Suite for Paper 1.21+ Minecraft servers.

[![Platform](https://img.shields.io/badge/Platform-Paper%20%7C%20Purpur%20%7C%20Folia-2ea44f?style=for-the-badge)](https://modrinth.com/plugin/staffshift)
[![Minecraft](https://img.shields.io/badge/Minecraft-1.21+-795290?style=for-the-badge)](https://modrinth.com/plugin/staffshift)
[![Modrinth](https://img.shields.io/badge/Download-Modrinth-00AF5C?style=for-the-badge&logo=modrinth)](https://modrinth.com/plugin/staffshift)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)

---

## 📌 Overview

**StaffShift** is an enterprise-grade moderation and player examination plugin built specifically for modern Paper 1.21+ networks. Designed to replace outdated, buggy staff plugins, StaffShift guarantees **zero data loss**, **creative-proof security**, and an airtight workflow for active moderators.

This repository serves as the official **Documentation, Issue Tracker, and Wiki hub** for StaffShift.

---

## ✨ Key Features

* 🛡️ **Creative-Proof Architecture:** Runs 100% on secure Survival mechanics with native Paper flight. Eliminates client-side `SetCreativeSlot` packet exploits.
* 💾 **Anti-Crash Disk Persistence:** Survival inventories, armor, and XP are serialized to disk (`plugins/StaffShift/data/<uuid>.yml`) before mode transitions. Automatic fail-safe recovery on next login.
* 🛑 **Admin Command Guard:** Mandatory duty check prevents staff from executing punishment commands (`/ban`, `/kick`, `/freeze`) while off-duty.
* 🧊 **Adventure BossBar Freeze:** Clean, animated red countdown BossBar and ActionBar indicator with zero chat spam.
* 🚨 **Anti-Combat Log & Auto Re-Freeze:** Broadcasts disconnect coordinates, executes automated console punishments, and automatically re-freezes suspects if they reconnect within 60s.
* 🔍 **Live Player Inspector GUI:** Real-time health, food, ping, coordinates, active potion effects, and direct Ender Chest access.
* 👻 **Ghost Vanish & Mob Stealth:** Built-in native packet vanish fallback with SuperVanish/PremiumVanish API hooks. Cancels mob AI targeting and Sculk vibrations.
* 🗣️ **Native Localization:** Dual-language support in English (`en`) and Indonesian (`id`) powered by Kyori MiniMessage.

---

## 📖 Documentation & Wiki

Explore our complete documentation guides:

| Guide | Description |
|---|---|
| [📥 Installation](wiki/Installation.md) | Setup instructions for Paper, Purpur, and Folia. |
| [⚙️ Configuration](wiki/Configuration.md) | Full explanation of `config.yml` settings and rules. |
| [⚔️ Commands & Permissions](wiki/Commands-and-Permissions.md) | Command syntax, shorthand aliases, and LuckPerms examples. |
| [🎒 Staff Loadout & Tools](wiki/Staff-Loadout.md) | Breakdown of the 9 hotbar patrol tools and Inspector GUI. |
| [🌐 Localization](wiki/Localization.md) | Language switching, MiniMessage formatting, and PlaceholderAPI. |
| [❓ FAQ & Troubleshooting](wiki/FAQ-and-Troubleshooting.md) | Crash recovery, Folia support, and common troubleshooting tips. |

---

## 📥 Downloads

Official binaries and release assets are distributed via Modrinth:
* 👉 **[Download StaffShift on Modrinth](https://modrinth.com/plugin/staffshift)**

---

## 🐛 Issues & Support

Encountered a bug or have a feature request?
* Open an issue on our [Issue Tracker](https://github.com/RaffiDevYT/StaffShiftt-Wiki/issues).
* Provide server platform, version (`/version`), and relevant console logs.
