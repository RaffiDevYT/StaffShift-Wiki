# 🚀 Modrinth Release Guide - StaffShift 1.0.0

Panduan lengkap dan siap copy-paste untuk membuat project baru dan mengunggah rilis pertama di **[Modrinth](https://modrinth.com)**.

---

## 1. Project Information (Formulir Awal)

| Field Modrinth | Nilai Rekomendasi | Catatan |
| :--- | :--- | :--- |
| **Project Type** | **Plugin** | Pilih tab Plugin |
| **Name** | `StaffShift` | Nama resmi plugin |
| **Summary** *(Max 140 chars)* | `Modern, high-performance Staff Duty & Freeze plugin for Paper 1.21+ with realtime BossBar, admin command guards & zero data-loss.` | Tampil di kartu pencarian |
| **Slug** | `staffshift` | URL Modrinth: `modrinth.com/plugin/staffshift` |
| **Side Support** | **Client:** *Unsupported*<br>**Server:** *Required* | Plugin server-side murni |
| **Categories** | `Management`, `Utility`, `Moderation` | Pilih tag relevan |
| **Icon / Avatar** | [icon.png](file:///C:/Users/raffidev/Desktop/StaffShift/icon.png) *(1024x1024 PNG)* | Upload file `icon.png` di form avatar project |
| **License** | `Custom` (All Rights Reserved) atau `MIT` | Sesuai file `LICENSE` |

---

## 2. Project Body / Description

Isi halaman utama project di Modrinth menggunakan konten dari [DESCRIPTION.md](file:///C:/Users/raffidev/Desktop/StaffShift/DESCRIPTION.md):
1. **Pasang Banner**: Drag & drop file [banner.png](file:///C:/Users/raffidev/Desktop/StaffShift/banner.png) langsung ke baris paling atas kotak teks Description di Modrinth (Modrinth akan otomatis meng-upload dan membuat link CDN).
2. **Copy Konten**: Salin seluruh teks di bawah banner dari [DESCRIPTION.md](file:///C:/Users/raffidev/Desktop/StaffShift/DESCRIPTION.md) (tabel loadout hotbar, tabel command & alias, permission, dan placeholder).

---

## 3. Version Release (Upload File v1.0.0)

Saat membuat versi baru di tab **Versions** -> **Create Version**:

| Field Versi | Nilai |
| :--- | :--- |
| **Version Name** | `StaffShift 1.0.0 - Initial Release` |
| **Version Number** | `1.0.0` |
| **Release Type** | `Release` |
| **Game Versions** | Pilih: `1.21`, `1.21.1`, `1.21.2`, `1.21.3`, `1.21.4` |
| **Loaders** | Pilih: `Paper`, `Purpur`, `Folia` |
| **File to Upload** | [StaffShift-1.0.0.jar](file:///C:/Users/raffidev/Desktop/StaffShift/build/libs/StaffShift-1.0.0.jar) *(Ukuran: ~71 KB)* |

### Dependencies (Opsional di Modrinth):
- **PlaceholderAPI** (Optional)
- **SuperVanish** (Optional)
- **PremiumVanish** (Optional)

---

## 4. Changelog v1.0.0 (Copy-Paste)

```markdown
### 🛡️ Welcome to StaffShift 1.0.0!

Initial official release of **StaffShift** — a modern, secure, and blazing-fast Staff Duty & Freeze moderation plugin built specifically for Paper, Purpur, and Folia 1.21+.

#### ✨ Highlights
* **Hardened Staff Duty**: Secure Survival + Flight architecture preventing creative-slot exploits. Mob AI immunity and silent sculk walking.
* **Admin Command Guard**: Require staff to be in `/adminduty` before executing punishment commands (`/ban`, `/unban`, `/kick`, `/mute`, etc.).
* **Non-Spamming Freeze System**: Single chat rules broadcast, realtime Adventure BossBar & ActionBar countdown, isolated SS-Chat, and auto vehicle ejection.
* **Zero Data Loss**: Per-slot disk serialization (`plugins/StaffShift/data/<uuid>.yml`) ensuring full inventory restoration even during sudden server crashes.
* **Anti-Dupe Protections**: Automatic GUI closure, cursor-item reclaiming, and projectile damage prevention for vanished staff.
* **Dual Language**: Out-of-the-box support for English (`messages_en.yml`) and Indonesian (`messages_id.yml`) with modern, clean typography.
* **Standalone**: Works with 0 external dependencies. Optional support for PlaceholderAPI, SuperVanish, and PremiumVanish.
```
