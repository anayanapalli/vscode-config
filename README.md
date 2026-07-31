# VS Code Configuration

My personal Visual Studio Code configuration for a consistent development experience across macOS and Windows machines.

This repository contains my VS Code setup, including editor settings, keyboard shortcuts, and extensions. It allows me to quickly recreate my preferred development environment on a new machine.

## Repository Structure

```text
vscode/
├── settings-mac.json              # macOS VS Code settings
├── settings-windows.json          # Windows VS Code settings
├── keybindings-mac.json           # macOS keyboard shortcuts
├── keybindings-windows.json       # Windows keyboard shortcuts
├── extensions.txt                 # Installed VS Code extensions
└── README.md
```

## Setup

### 1. Clone the Repository

```bash
git clone <repository-url>
cd vscode-config
```

---

## macOS Setup

### Copy Settings

Copy:

```text
settings-mac.json
```

to:

```text
~/Library/Application Support/Code/User/settings.json
```

### Copy Keybindings

Copy:

```text
keybindings-mac.json
```

to:

```text
~/Library/Application Support/Code/User/keybindings.json
```

### Install Extensions

Install all extensions:

```bash
cat extensions.txt | xargs -L 1 code --install-extension
```

---

## Windows Setup

### Copy Settings

Copy:

```text
settings-windows.json
```

to:

```text
%APPDATA%\Code\User\settings.json
```

### Copy Keybindings

Copy:

```text
keybindings-windows.json
```

to:

```text
%APPDATA%\Code\User\keybindings.json
```

### Install Extensions

Run:

```powershell
Get-Content extensions.txt | ForEach-Object { code --install-extension $_ }
```

---

## Exporting Updates

When adding new extensions:

```bash
code --list-extensions > extensions.txt
```

Commit the changes:

```bash
git add .
git commit -m "Update VS Code configuration"
git push
```

---

## Managing Settings

### Open User Settings JSON

In VS Code:

```
Cmd + Shift + P (macOS)
Ctrl + Shift + P (Windows)
```

Search:

```
Preferences: Open User Settings (JSON)
```

### Open Keyboard Shortcuts JSON

Search:

```
Preferences: Open Keyboard Shortcuts (JSON)
```

---

## Included Configuration

### Editor

- Fira Code font
- Font ligatures enabled
- Format on save enabled
- Auto save enabled
- Minimap disabled
- Preview tabs disabled
- Breadcrumbs disabled

### Formatting

Configured formatters:

- HTML → Prettier
- JavaScript → Prettier
- Python → Prettier

### Git

Configured:

- Automatic fetching
- Smart commit
- Repository discovery behavior

### Terminal

macOS:

- Uses Zsh

Windows:

- Uses PowerShell

### Extensions

The `extensions.txt` file contains the complete list of installed VS Code extensions.

To regenerate:

```bash
code --list-extensions > extensions.txt
```

---

## Notes

- Settings are maintained separately for macOS and Windows because terminal configuration and operating-system-specific paths differ.
- Avoid storing credentials, tokens, SSH private keys, or sensitive information in this repository.
- This repository contains configuration only and is intended to recreate a development environment quickly.

## License

MIT License
