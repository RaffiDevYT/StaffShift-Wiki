# Configuration Guide ⚙️

StaffShift features a clean, well-documented `config.yml` that allows administrators to tailor moderation rules, punishments, and command protection.

---

## 📁 File Location

The main configuration file is located at:
```text
plugins/StaffShift/config.yml
```

---

## 📄 Complete `config.yml` Reference

```yaml
# ============================================================
# StaffShift 1.0.0 Configuration
# Modern Staff Duty & Freeze Plugin for Paper 1.21+
# ============================================================

# Language file to use ("en" for English, "id" for Indonesian)
# Language files are located in: plugins/StaffShift/messages/
# Default: "en"
language: "en"

# Automatically vanish staff when entering Staff Mode
# Default: true
staffmode-on-vanish: true

# Require staff/admin to be in /adminduty before executing administrative/punishment commands
# When true, commands listed in admin-commands are blocked if the player is off-duty.
# Bypass permission: staffshift.bypass.duty
# Default: true
require-duty-for-admin-commands: true

# List of commands that require /adminduty before execution (case-insensitive, with or without slash)
# Supports command names and namespaces (e.g., 'ban' or 'minecraft:ban')
admin-commands:
  - "ban"
  - "tempban"
  - "unban"
  - "pardon"
  - "banip"
  - "ban-ip"
  - "unbanip"
  - "unban-ip"
  - "pardon-ip"
  - "ipban"
  - "tempipban"
  - "kick"
  - "kickall"
  - "mute"
  - "tempmute"
  - "unmute"
  - "warn"
  - "tempwarn"
  - "unwarn"
  - "jail"
  - "unjail"
  - "freeze"
  - "fr"
  - "unfreeze"
  - "unfr"
  - "punish"
  - "alts"
  - "history"
  - "dupeip"
  - "clearchat"

items:
  # Enable execution sword in slot 5 (requires permission staffshift.tool.kill)
  # Default: true
  execution-sword: true

spawn:
  # Server spawn coordinates for the Diamond teleport tool (Slot 2)
  # Can be configured in-game using /staffshift setspawn (or /ss setspawn)
  world: "world"
  x: 0.5
  y: 64.0
  z: 0.5
  yaw: 0.0
  pitch: 0.0

freeze:
  # Interval in seconds to repeat freeze chat card. Set to 0 to send ONCE (no chat spam).
  # Default: 0
  reminder-interval-seconds: 0

  # Countdown duration in seconds for the suspect examination screenshare
  # Default: 300 (5 minutes)
  countdown-seconds: 300
  
  # Display animated countdown BossBar at the top of the screen
  # Default: true
  bossbar: true
  
  # Automatically execute a punishment command if a frozen suspect disconnects
  disconnect-auto-punish: true
  disconnect-punish-command: "ban <player> Disconnected while frozen -s"
  
  # Automatically execute a punishment command if the countdown timer expires
  timeout-auto-punish: true
  timeout-punish-command: "ban <player> Screenshare examination timeout -s"

  # Commands frozen suspects are permitted to run (all other commands are blocked)
  allowed-commands:
    - "/msg"
    - "/r"
    - "/reply"
    - "/tell"
```

---

## 🔍 Key Settings Explained

### 🛡️ Admin Command Guard (`require-duty-for-admin-commands`)
When enabled, StaffShift monitors command dispatches. If an off-duty moderator attempts to use commands like `/ban`, `/kick`, or `/freeze`, StaffShift intercepts the command and sends an alert instructing them to switch to `/adminduty` first.
* **Why it matters:** Prevents staff from abusing moderation commands while playing competitively in survival mode.
* **Bypass:** Players with `staffshift.bypass.duty` can execute commands off-duty.

### ⏱️ Freeze Examination & Anti-Combat Log
* **`reminder-interval-seconds: 0`**: When set to `0`, rules are printed to the suspect's chat **only once** upon being frozen, leaving their chat box uncluttered for communication with staff.
* **`disconnect-auto-punish`**: When a frozen player logs out to avoid examination, StaffShift automatically dispatches `disconnect-punish-command` from the server console and broadcasts their logout coordinates to active staff.
* **Auto Re-Freeze**: If a suspect reconnects within 60 seconds (e.g. accidental crash), StaffShift automatically grounds and re-freezes them with the remaining timer preserved.
