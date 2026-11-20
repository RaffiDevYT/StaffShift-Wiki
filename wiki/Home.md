<div align="center">

![StaffShift Banner](https://raw.githubusercontent.com/RaffiDevYT/StaffShiftt-Wiki/main/release/banner.png)

# StaffShift Documentation 🛡️

### Modern Staff Duty & Player Examination Suite
**Engineered from scratch for Paper, Purpur, and Folia 1.21+ Minecraft servers.**

</div>

---

**StaffShift** is an enterprise-grade, high-performance moderation and player examination plugin built specifically for modern Paper 1.21+ networks. Designed to replace outdated, buggy staff mode plugins, StaffShift guarantees **zero data loss**, **creative-proof security**, and an airtight workflow for active moderators.

---

## 🚀 Why StaffShift?

Most legacy staff plugins suffer from critical security holes and operational flaws:
* 🛑 **Creative Mode Exploits:** Putting staff into Creative mode allows hacked clients to send malicious `SetCreativeSlot` packets, spawning illegal NBT items into survival economies.
* 🛑 **Inventory Wipes on Server Crashes:** If the server restarts, crashes, or loses power while a moderator is on duty, their previous survival items, armor, and XP are often lost forever.
* 🛑 **Rogue Commands Off-Duty:** Staff can accidentally or maliciously run destructive punishment commands (`/ban`, `/kick`, `/freeze`) while playing as regular survival players.
* 🛑 **Chat Spam Freeze Systems:** Outdated freeze tools repeatedly flood the suspect's chat window with ASCII text, obscuring evidence and making screenshare communication chaotic.
* 🛑 **Mob Interference:** Mobs targeting vanished staff or Sculk sensors picking up footsteps ruins stealth patrols.

**StaffShift solves every one of these problems natively:**
1. **Creative-Proof Architecture:** Runs 100% on secure Survival mechanics with native Paper flight capabilities. No client can ever spawn illegal items.
2. **Anti-Crash Disk Persistence:** Every inventory, armor piece, off-hand slot, potion effect, XP level, and hunger state is serialized to disk (`plugins/StaffShift/data/<uuid>.yml`) *before* staff transition occurs. Automatic fail-safe recovery restores items on next login if the server crashes.
3. **Mandatory Admin Command Guard:** Blocks administrative actions (`/ban`, `/tempban`, `/kick`, `/freeze`, etc.) until the moderator is officially clocked into `/adminduty`.
4. **Cinematic Adventure BossBar:** suspect is shown a live, smooth red BossBar countdown timer and ActionBar indicator with zero chat spam.
5. **Anti-Combat Log & Auto Re-Freeze:** Broadcasts real-time coordinate logs if a frozen suspect disconnects, runs automated console punishments, and automatically re-freezes them upon reconnection.
6. **Built-in Player Inspector GUI:** Real-time suspect telemetry (HP, ping, gamemode, active potion effects, and direct Ender Chest access).

---

## 📊 Comparison Matrix

| Feature | Legacy Staff Plugins | StaffShift |
|---|---|---|
| **Supported Platforms** | Outdated Spigot / 1.12-1.16 | **Paper, Purpur, Folia 1.21+** |
| **Security Mode** | Creative Mode (`SetCreativeSlot` risk) | **Survival + Native Paper Flight (100% Secure)** |
| **Crash Safety** | In-Memory (Items lost on crash) | **Disk Serialized (`data/<uuid>.yml`)** |
| **Duty Command Guard** | ❌ None | **✅ Whitelist/Blacklist Guard (`require-duty`)** |
| **Freeze Presentation** | Repeating ASCII Chat Spam | **Live Adventure BossBar + Clean SS Chat** |
| **Combat Log Handling** | Manual broadcast | **Auto-punish command + 60s Auto Re-Freeze** |
| **Mob & Sculk Stealth** | Partial vanish | **Cancels Mob AI Targeting + Sculk Vibrations** |
| **Player Inspection** | Basic chat readout | **Live Interactive GUI with Ender Chest** |
| **Dependencies** | Requires ProtocolLib / LibsDisguises | **Zero (100% Standalone)** |
| **Localization** | Hardcoded English | **MiniMessage English (`en`) & Indonesian (`id`)** |

---

## 📚 Documentation Index

* [📥 Installation Guide](Installation) — Server requirements, setup steps, and file structure.
* [⚙️ Configuration Guide](Configuration) — Full breakdown of `config.yml` keys and security rules.
* [⚔️ Commands & Permissions](Commands-and-Permissions) — All command syntax, aliases, and LuckPerms setup.
* [🎒 Staff Loadout & Tools](Staff-Loadout) — Breakdown of the 9 hotbar patrol tools and inspector GUI.
* [🌐 Localization Guide](Localization) — Switching languages, MiniMessage formatting, and PlaceholderAPI.
* [❓ FAQ & Troubleshooting](FAQ-and-Troubleshooting) — Crash recovery, permission bypass, and common questions.
