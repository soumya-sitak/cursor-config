# Cursor User Setup

Personal Cursor configuration — settings, keybindings, and extensions for an AI/ML engineer.

## 📁 Files

| File | Purpose |
|---|---|
| `settings.json` | Editor, terminal, Python, layout, theme |
| `keybindings.json` | AI shortcuts, Jupyter, editing power-moves |
| `extensions.txt` | List of all extensions to install (28 total) |
| `README.md` | This file |

## 🚀 Quick Install (Fresh Machine)

Run this **once** from this directory in PowerShell:

```powershell
Get-Content .\extensions.txt | ForEach-Object { cursor --install-extension $_ }
```

Equivalent one-liner (bash / Git Bash):

```bash
xargs -L 1 cursor --install-extension < extensions.txt
```

The command reads each line from `extensions.txt` and passes it to `cursor --install-extension`. Safe to re-run — Cursor skips already-installed extensions.

## ⌨️ Top Shortcuts

| Key | Action |
|---|---|
| `Ctrl+L` | Open AI chat (right panel) |
| `Ctrl+K` | AI composer (multi-file edit) |
| `Ctrl+I` | Inline AI edit |
| `Ctrl+Alt+B` | Toggle right panel |
| `Shift+Enter` | Run Jupyter cell + advance |
| `F12` | Go to definition |

## 🧭 Layout

- **Activity bar** — left side (vertical icons)
- **Sidebar** — left (Explorer)
- **Editor** — center
- **Auxiliary bar** — right (AI chat)
- **Panel** — bottom (terminal)

## 🛠️ Maintenance

### Update everything
```powershell
cursor --update-extensions
```

### See what's installed
```powershell
cursor --list-extensions
```

### Backup current setup
```powershell
Copy-Item .\settings.json .\settings.json.bak
Copy-Item .\keybindings.json .\keybindings.json.bak
cursor --list-extensions > extensions.txt
```

### Restore from backup
```powershell
Move-Item .\settings.json.bak .\settings.json -Force
Move-Item .\keybindings.json.bak .\keybindings.json -Force
Get-Content .\extensions.txt | ForEach-Object { cursor --install-extension $_ }
```

## 📌 Notes

- The install command is **idempotent** — running it twice doesn't break anything
- First Cursor launch will offer to **import from VS Code** — say yes if you want a clean migration, or skip if these new files are authoritative
- Ruff is the default Python formatter (faster than Black); Black stays as a fallback
- All extensions are first-party Microsoft or widely-trusted community extensions
