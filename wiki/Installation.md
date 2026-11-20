# Installation & Setup 📥

StaffShift is distributed as a lightweight, zero-dependency Paper plugin optimized for modern 1.21+ servers.

---

## 🖥️ Platform Requirements

* **Java Runtime:** Java 21 or higher.
* **Server Platform:** Paper, Purpur, Pufferfish, or Folia **1.21.x+**.
* **External Dependencies:** **None** (100% standalone, no ProtocolLib required).

---

## 🚀 Step-by-Step Installation

1. Download [`StaffShift-1.0.0.jar`](https://modrinth.com/plugin/staffshift) from Modrinth.
2. Place the JAR file inside your server's `plugins/` directory:
   ```text
   server-root/
   └── plugins/
       └── StaffShift-1.0.0.jar
   ```
3. Start or restart your server. StaffShift will generate its default directory and configuration files:
   ```text
   plugins/StaffShift/
   ├── config.yml           # Main configuration & rules
   ├── data/                # Encrypted disk backups of off-duty staff inventories
   └── messages/
       ├── messages_en.yml  # English language file (Default)
       └── messages_id.yml  # Indonesian language file
   ```
4. Adjust your desired options in `plugins/StaffShift/config.yml` (such as language or punishment commands).
5. Run `/staffshift reload` (or `/ss reload`) to hot-reload changes without restarting.

---

## 🔌 Optional Integrations (Soft Dependencies)

StaffShift is completely autonomous, but integrates automatically with the following plugins if detected:

* **PlaceholderAPI**: Exposes real-time staff status, vanish state, and freeze status to TAB, scoreboards, and chat plugins.
* **SuperVanish / PremiumVanish**: Hooks into premium vanish APIs for network-wide ghost stealth. If not installed, StaffShift automatically falls back to its built-in native Paper packet vanish.

---

## ✅ Verifying Installation

To confirm StaffShift is loaded properly, execute the following command from the console or in-game:

```bash
/staffshift
# Shorthand alias:
/ss
```

If you have operator status or the `staffshift.staff` permission, you will enter staff mode immediately, receive your patrol tools, and hear the mode change chime.
