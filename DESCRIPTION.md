<div align="center">

![StaffShift Banner](banner.png)

**A modern, high-performance, and secure Staff Duty & Freeze plugin for Paper 1.21+**  
*Designed from the ground up for server administrators and moderators who demand uncompromising performance, zero data-loss, and an airtight moderation workflow.*

</div>

---

## 🌟 Key Features

### 🛡️ Hardened Staff Duty Mode (`/staffshift`, `/adminduty`)
* **Creative-Proof Architecture**: Runs entirely on secure Survival + Flight mechanics. Eliminates client-side `SetCreativeSlot` packet exploits used by hacked clients to spawn illegal items.
* **Mob & Sculk Stealth**: Automatically mutes all footstep vibrations (Sculk Sensors) and cancels mob AI targeting while on patrol.
* **Anti-Dupe & Inventory Preservation**: Automatically closes any active GUI and reclaims cursor items before duty activation. Restores your full previous inventory state upon duty exit.

### 🛑 Admin Command Guard (`require-duty-for-admin-commands`)
* **Mandatory Duty for Punishments**: Prevents staff from executing administrative commands (`/ban`, `/unban`, `/kick`, `/mute`, `/freeze`, etc.) while off-duty.
* **Configurable Command Filter**: Fully customizable command whitelist/blacklist in `config.yml` with namespace support (`minecraft:ban`, `litebans:ban`, etc.) and permission bypass (`staffshift.bypass.duty`).

### 🧊 Modern Freeze & Inspection System (`/freeze`, `/fr`)
* **Live Adventure BossBar & ActionBar**: Displays a realtime animated red BossBar countdown at the top of the screen and an active ActionBar timer.
* **Zero Chat Spam**: Full examination rules are dispatched exactly **once** to chat, keeping the suspect's chat clean for staff communication.
* **Isolated SS-Chat Channel**: Suspects talk in a dedicated channel visible only to active staff and console.
* **Vehicle & Grounding Protection**: Instantly grounds floating suspects and ejects them from vehicles (boats/horses) to prevent physics exploits.
* **Anti-Combat Log & Auto Re-Freeze**: Broadcasts instant coordinates if a suspect disconnects while frozen, triggers optional automated punishment commands, and automatically re-freezes them if they reconnect within 60 seconds.

### 🔍 Realtime Player Inspector GUI
* Right-click any suspect to view live health, food level, ping, current game mode, world coordinates, active potion effects with remaining durations, and one-click direct access to their Ender Chest.

### 👻 Ghost Vanish System
* Seamlessly hooks into **SuperVanish** or **PremiumVanish** API, with an automatic built-in native packet-based Paper vanish fallback if no external plugin is installed.

### 💾 Zero Data Loss (Anti-Crash Disk Persistence)
* Staff inventories, armors, off-hand items, XP, levels, and hunger are serialized per-slot to disk (`plugins/StaffShift/data/<uuid>.yml`) before mode transition. If the server crashes or power fails while staff is on duty, inventories are automatically restored upon next login.

### 🎨 Clean Modern Typography & Multi-Language
* Styled with clean, minimalist Kyori MiniMessage formatting (no distracting rainbow clutter).
* Ships with full dual-language support:
  * `messages/messages_en.yml` (Default English)
  * `messages/messages_id.yml` (Indonesian)
* Switch languages seamlessly in `config.yml` (`language: "en"` or `language: "id"`).

---

## 📋 Commands & Permissions

| Command | Aliases | Description | Permission | Default |
| :--- | :--- | :--- | :--- | :--- |
| `/staffshift` | `/ss`, `/duty`, `/adminduty` | Toggle your own staff duty mode | `staffshift.staff` | `op` |
| `/staffshift <player>` | `/ss <player>`, `/duty <player>` | Force toggle staff mode for another player | `staffshift.admin` | `op` |
| `/spec` | `/spectate` | Toggle spectator / x-ray mode while on duty | `staffshift.staff` | `op` |
| `/staffshift list` | `/ss list`, `/duty list` | View all staff members currently on duty | `staffshift.staff` | `op` |
| `/staffshift setspawn` | `/ss setspawn` | Set staff spawn tool coordinates to current location | `staffshift.admin` | `op` |
| `/staffshift reload` | `/ss reload` | Reload configuration and language files | `staffshift.admin` | `op` |
| `/staffchat [message]` | `/sc [message]`, `/staffo` | Send a staff message or toggle auto-staffchat | `staffshift.staff` | `op` |
| `/freeze <player>` | `/fr <player>` | Freeze or unfreeze a suspected player | `staffshift.freeze` | `op` |
| `/freeze list` | `/fr list` | List all currently frozen suspects | `staffshift.freeze` | `op` |
| `/unfreeze <player>` | `/unfr <player>` | Manually unfreeze a player | `staffshift.freeze` | `op` |

---

## 🎒 Staff Hotbar Loadout

When entering Staff Duty, your survival inventory is safely archived and replaced with modern patrol tools:

| Slot | Tool | Action |
| :---: | :--- | :--- |
| **0** | **Compass** | **Right-Click:** Teleport to targeted block (up to 120 blocks).<br>**Left-Click:** Toggle Spectator / X-Ray mode. |
| **1** | **Player Head** | **Right-Click:** Teleport to a random online non-staff player. |
| **2** | **Diamond** | **Right-Click:** Teleport instantly to server spawn location. |
| **3** | **Golden Pickaxe** | **Right-Click:** Teleport to an underground miner (`Y ≤ 40`). |
| **4** | **Packed Ice** | **Right-Click Player:** Instantly Freeze / Unfreeze suspect. |
| **5** | **Execution Sword** | **Right-Click Player:** Eliminate confirmed cheaters instantly (*optional*). |
| **6** | **Crafting Table** | **Right-Click:** Toggle Build Mode ON/OFF (protects server from accidental grief). |
| **7** | **Book** | **Right-Click Player:** Open Live Player Inspection GUI. |
| **8** | **Lime / Gray Dye** | **Right-Click:** Toggle Vanish visibility state. |

---

## 🧩 PlaceholderAPI Placeholders

| Placeholder | Output | Description |
| :--- | :--- | :--- |
| `%staffshift_status%` | `Staff` / `Player` | Player's current staff mode status |
| `%staffshift_vanished%` | `Yes` / `No` | Player's vanish state |
| `%staffshift_frozen%` | `Yes` / `No` | Whether player is currently frozen |
| `%staffshift_build%` | `Yes` / `No` | Whether staff has build mode enabled |
| `%staffshift_staff_count%` | Number (e.g. `3`) | Total active staff members on duty |

---

## ⚙️ Compatibility & Requirements

* **Platform**: Paper, Purpur, or Folia **1.21+** (Java 21+)
* **Dependencies**: None (100% standalone)
* **Soft Dependencies**: PlaceholderAPI, SuperVanish, PremiumVanish
