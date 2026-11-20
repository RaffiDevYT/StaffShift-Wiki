# FAQ & Troubleshooting ❓

Frequently asked questions, common configuration hurdles, and diagnostic tips for StaffShift.

---

## 💾 Data & Crash Safety

### What happens if the server crashes while a moderator is on duty?
StaffShift includes a built-in fail-safe disk persistence engine. When staff duty is activated, the moderator's survival inventory, armor, off-hand slot, and XP are written to `plugins/StaffShift/data/<uuid>.yml`. If a crash occurs:
1. The moderator's patrol loadout is discarded on reboot.
2. The player's original survival state is restored from disk upon their next login.
3. The temporary session file is deleted safely.

---

## 🛑 Administrative Guards

### Why can't my admins run `/ban` or `/kick`?
You have enabled `require-duty-for-admin-commands: true` in `config.yml`. This security feature requires staff to enter `/adminduty` (or `/ss`) before running punishment commands, preventing accidental or rogue off-duty bans.
* **To bypass this restriction for server owners**, grant the permission:
  ```bash
  /lp user <player> permission set staffshift.bypass.duty true
  ```
* **Or disable the requirement entirely** in `config.yml`:
  ```yaml
  require-duty-for-admin-commands: false
  ```

---

## 🧭 Patrol Tools & Spawns

### How do I configure where the Diamond teleport tool sends staff?
1. Stand at your desired server spawn location in-game.
2. Run the command:
   ```bash
   /staffshift setspawn
   # Or shorthand:
   /ss setspawn
   ```
3. StaffShift will update `spawn:` coordinates in `config.yml` automatically without requiring a restart.

---

## 👻 Vanish & Stealth Mechanics

### Does StaffShift require SuperVanish or PremiumVanish?
**No.** While StaffShift hooks seamlessly into SuperVanish or PremiumVanish if present, it has a built-in, native Paper packet-level vanish fallback. Vanished staff will not appear in tablists, will not trigger mob targeting, and will not emit Sculk Sensor vibrations.

---

## 🌐 Server Platform Compatibility

### Is StaffShift compatible with Purpur and Folia?
**Yes.** StaffShift is developed against modern Paper 1.21+ API standards. It is fully verified on:
* **Paper** 1.21+
* **Purpur** 1.21+
* **Folia** 1.21+ (utilizing thread-safe Adventure components)
