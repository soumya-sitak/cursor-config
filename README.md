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

## 📦 What's Included

### AI / LLM
*(none — Cursor is your AI)*

### Python / ML (8)
- `ms-python.python` — Python language support
- `ms-toolsai.jupyter` — Notebooks
- `charliermarsh.ruff` — Linter + formatter (10–100x faster than Black)
- `ms-python.vscode-pylance` — Best Python LSP
- `ms-python.black-formatter` — Backup formatter
- `ms-python.mypy-type-checker` — Static types
- `njpwerner.autodocstring` — Auto-generate docstrings
- `ms-toolsai.datawrangler` — View/edit CSV/Parquet as tables

### Git (2)
- `eamodio.gitlens` — Inline blame, history, branch viz
- `mhutchie.git-graph` — Visual branch graph

### Docker (2)
- `ms-azuretools.vscode-docker`
- `ms-azuretools.vscode-containers`

### Languages / Formatters (6)
- `esbenp.prettier-vscode` — Generic formatter
- `redhat.vscode-yaml` — YAML (K8s, Hydra, configs)
- `tamasfe.even-better-toml` — `pyproject.toml`
- `yzhang.markdown-all-in-one` — Markdown shortcuts + TOC
- `DavidAnson.vscode-markdownlint` — Lint READMEs
- `bierner.markdown-mermaid` — Render Mermaid diagrams
- `DotJoshJohnson.xml` — XML (ONNX, legacy configs)

### Productivity (5)
- `usernamehw.errorlens` — Inline errors
- `streetsidesoftware.code-spell-checker` — Typo catcher
- `pkief.material-icon-theme` — File icons
- `christian-kohler.path-intellisense` — Path autocomplete
- `oderwat.indent-rainbow` — Visual indents
- `formulahendry.code-runner` — Quick script runs

### Data / Viewing (1)
- `GrapeCity.gc-excelviewer` — Read `.xlsx` exports

### Remote (2)
- `ms-vscode-remote.remote-ssh`
- `ms-vscode-remote.remote-wsl`

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
