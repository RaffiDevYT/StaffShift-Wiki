# Staff Loadout & Patrol Tools 🎒

When a moderator activates Staff Duty (`/staffshift` or `/ss`), their survival inventory is safely archived to disk and replaced with a specialized 9-slot patrol kit.

---

## 🧰 Hotbar Tools Overview

| Slot | Tool | Actions & Behavior |
|:---:|:---|:---|
| **0** | **Compass** | **Right-Click:** Instantly teleport to the targeted block (up to 120 blocks away).<br>**Left-Click:** Toggle Spectator / X-Ray mode on or off. |
| **1** | **Player Head** | **Right-Click:** Randomly teleport to an online non-staff player on patrol. |
| **2** | **Diamond** | **Right-Click:** Teleport instantly to the server spawn point (configured via `/ss setspawn`). |
| **3** | **Golden Pickaxe** | **Right-Click:** Teleport directly to an underground miner (`Y ≤ 40`) to inspect potential X-Rayers. |
| **4** | **Packed Ice** | **Right-Click Suspect:** Instantly freeze or unfreeze a targeted player to begin examination. |
| **5** | **Execution Sword** | **Right-Click Suspect:** Instantly eliminate confirmed cheaters (*optional, enabled via `config.yml`*). |
| **6** | **Crafting Table** | **Right-Click:** Toggle Build Mode ON/OFF to prevent accidental block griefing while inspecting bases. |
| **7** | **Book** | **Right-Click Suspect:** Open Live Player Inspection GUI.<br>**Right-Click Air:** Open Self-Inspection GUI. |
| **8** | **Lime / Gray Dye** | **Right-Click:** Toggle Vanish visibility state (Lime = Vanished, Gray = Visible). |

---

## 🔍 Live Player Inspector GUI (Slot 7)

Right-clicking any suspect with the **Book** tool opens an interactive telemetry dashboard:

* **Vital Statistics:** Real-time health bar, food saturation, and connection ping (in milliseconds).
* **Game State:** Current game mode (Survival, Creative, Adventure) and world coordinates (`X, Y, Z`).
* **Active Status Effects:** Complete list of active potion effects, amplifier tiers, and remaining durations in seconds.
* **Direct Ender Chest Access:** One-click button inside the GUI to view and inspect the suspect's live Ender Chest contents in real-time.

---

## 💾 Zero Data-Loss Inventory Persistence

Legacy staff plugins store inventory backups in volatile RAM. If the server crashes or suffers power loss while a staff member is on duty, their original survival inventory is permanently lost.

**How StaffShift guarantees 100% data preservation:**
1. **Pre-Transition Serialization:** Before a single tool is placed in the player's hotbar, StaffShift serializes:
   * Main inventory contents (slots 0-35)
   * Armor slots (helmet, chestplate, leggings, boots)
   * Off-hand item
   * Total XP, level progress, and food exhaustion
   * Pre-duty game mode and location
2. **Persistent Disk Storage:** Data is immediately written to disk at `plugins/StaffShift/data/<uuid>.yml`.
3. **Fail-Safe Crash Recovery:** When a staff member logs back in after an unexpected crash, StaffShift detects the orphaned session file, strips the staff loadout, and automatically restores their survival items.
