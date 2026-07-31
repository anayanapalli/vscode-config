# VS Code Config

My personal Visual Studio Code configuration for a consistent and reproducible development environment across machines.

## Contents

- **Settings** (`settings.json`)
- **Keyboard shortcuts** (`keybindings.json`)
- **Extensions** (`extensions.txt`)
- **Snippets** (`snippets/`)
- **Workspace templates** (optional)

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/vscode-config.git
cd vscode-config
```

### 2. Copy the configuration

Copy the files to your VS Code user configuration directory.

**macOS**

```text
~/Library/Application Support/Code/User/
```

**Windows**

```text
%APPDATA%\Code\User\
```

**Linux**

```text
~/.config/Code/User/
```

Copy:

- `settings.json`
- `keybindings.json`
- `snippets/`

### 3. Install extensions

Export installed extensions:

```bash
code --list-extensions > extensions.txt
```

Install them on a new machine:

**macOS / Linux**

```bash
cat extensions.txt | xargs -L 1 code --install-extension
```

**Windows (PowerShell)**

```powershell
Get-Content extensions.txt | ForEach-Object { code --install-extension $_ }
```

## Updating

Whenever you make changes:

```bash
code --list-extensions > extensions.txt
git add .
git commit -m "Update VS Code configuration"
git push
```

## License

This repository is available under the MIT License.
