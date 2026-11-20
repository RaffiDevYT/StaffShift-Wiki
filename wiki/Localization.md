# Localization & Placeholders 🌐

StaffShift features full native localization powered by **Kyori MiniMessage**, supporting clean modern typography, RGB color hex codes, gradients, and custom action events without legacy `&` color code clutter.

---

## 🗣️ Supported Languages

StaffShift ships out-of-the-box with complete dual-language support:

* **English (`en`)**: Default international language file (`messages/messages_en.yml`).
* **Indonesian (`id`)**: Complete Bahasa Indonesia translation (`messages/messages_id.yml`).

### Changing Language

To switch languages, edit `plugins/StaffShift/config.yml`:

```yaml
# Set to 'en' for English or 'id' for Indonesian
language: "id"
```

Save the file and run `/staffshift reload` (or `/ss reload`) to apply changes immediately.

---

## 🎨 Kyori MiniMessage Syntax

All messages support rich MiniMessage formatting:

* **Hex Colors:** `<#38bdf8>This is ice cyan text</#38bdf8>`
* **Gradients:** `<gradient:#67e8f9:#0284c7>StaffShift Modern Gradients</gradient>`
* **Text Styles:** `<bold>Bold</bold>`, `<italic>Italic</italic>`, `<underlined>Underline</underlined>`
* **Click Events:** `<click:run_command:/ss list>Click to view active staff</click>`
* **Hover Tooltips:** `<hover:show_text:'<gray>Click to teleport</gray>'>Hover me!</hover>`

---

## 🧩 PlaceholderAPI Placeholders

If **PlaceholderAPI** is installed on your server, StaffShift registers the following placeholders for use in TAB, scoreboards, actionbars, and chat formatters:

| Placeholder | Output Sample | Description |
|---|---|---|
| `%staffshift_status%` | `Staff` / `Player` | Returns whether the player is currently on staff duty. |
| `%staffshift_vanished%` | `Yes` / `No` | Returns whether the player is currently vanished. |
| `%staffshift_frozen%` | `Yes` / `No` | Returns whether the suspect is currently frozen. |
| `%staffshift_build%` | `Yes` / `No` | Returns whether staff has build mode toggled ON. |
| `%staffshift_staff_count%` | `3` | Returns the total count of staff members currently on duty. |

### Example: Tablist Integration (TAB Plugin)

```yaml
tablist-name: "%vault_prefix% %player_name% %staffshift_status%"
```
