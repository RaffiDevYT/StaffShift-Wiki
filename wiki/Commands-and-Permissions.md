# Commands & Permissions ⚔️

StaffShift includes an intuitive, highly optimized command framework designed for rapid in-game moderation.

---

## 💻 Commands Overview

Base commands feature shorthand aliases for rapid typing during live server moderation:

| Command | Aliases | Permission | Description |
|---|---|---|---|
| `/staffshift` | `/ss`, `/duty`, `/adminduty` | `staffshift.staff` | Toggle your own staff duty mode on or off. |
| `/staffshift <player>` | `/ss <player>`, `/duty <player>` | `staffshift.admin` | Force toggle staff duty mode for another player. |
| `/staffshift list` | `/ss list`, `/duty list` | `staffshift.staff` | List all staff members currently clocked on duty. |
| `/staffshift setspawn` | `/ss setspawn` | `staffshift.admin` | Set the Diamond tool spawn point to your location. |
| `/staffshift reload` | `/ss reload` | `staffshift.admin` | Hot-reload configuration and language files. |
| `/spec` | `/spectate` | `staffshift.staff` | Toggle spectator / x-ray mode while on duty. |
| `/freeze <player>` | `/fr <player>` | `staffshift.freeze` | Freeze or unfreeze a suspected player. |
| `/freeze list` | `/fr list` | `staffshift.freeze` | View all players currently frozen under examination. |
| `/unfreeze <player>` | `/unfr <player>` | `staffshift.freeze` | Manually unfreeze a player and restore normal play. |
| `/staffchat [message]` | `/sc [message]`, `/staffo` | `staffshift.staff` | Send a staff message or toggle persistent auto-staffchat. |

---

## 🔑 Permissions Breakdown

All permissions are granular and fully compatible with **LuckPerms**:

| Permission Node | Default | Description |
|---|---|---|
| `staffshift.staff` | `op` | Allows entering Staff Mode, using spectator mode, and reading staff chat. |
| `staffshift.freeze` | `op` | Allows executing `/freeze`, `/unfreeze`, and viewing frozen suspects. |
| `staffshift.admin` | `op` | Allows reloading configuration, setting spawn, and force-toggling others. |
| `staffshift.tool.kill` | `op` | Allows receiving and using the Execution Sword (Slot 5) in staff mode. |
| `staffshift.bypass.duty` | `false` | Exempts administrator from the mandatory duty requirement for admin commands. |

---

## 🛡️ Recommended LuckPerms Setup

Here is a recommended production hierarchy using LuckPerms groups:

### 1. Helper / Trainee Role
Helpers can monitor staff chat and freeze suspects for senior staff review:
```bash
/lp group helper permission set staffshift.freeze true
/lp group helper permission set staffchat.staff true
```

### 2. Moderator Role
Moderators receive full staff patrol duty, inspector GUI, and teleport tools:
```bash
/lp group mod permission set staffshift.staff true
/lp group mod permission set staffshift.freeze true
```

### 3. Administrator / Owner Role
Administrators have access to management subcommands and optional duty bypass:
```bash
/lp group admin permission set staffshift.staff true
/lp group admin permission set staffshift.freeze true
/lp group admin permission set staffshift.admin true
/lp group admin permission set staffshift.tool.kill true

# Optional: Allow server owners to run /ban or /kick without toggling /duty
/lp group admin permission set staffshift.bypass.duty true
```
