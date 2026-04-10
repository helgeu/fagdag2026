# VS Code + Copilot — Get Started

Set up VS Code with GitHub Copilot on **Windows**, **Mac**, or **Linux**.

## 1. Install VS Code

| Platform | Command |
|----------|---------|
| **Windows** | `winget install Microsoft.VisualStudioCode` |
| **Mac** | `brew install --cask visual-studio-code` |
| **Linux** | `sudo snap install code --classic` |

## 2. Install Git

| Platform | Command |
|----------|---------|
| **Windows** | `winget install Git.Git` |
| **Mac** | `xcode-select --install` |
| **Linux** | `sudo apt install git` |

## 3. Sign in to GitHub

Open VS Code, click the person icon in the bottom left, and sign in with your GitHub account.

## 4. Verify Copilot access

Confirm you have access at [github.com/settings/copilot](https://github.com/settings/copilot).

## 5. Start using Copilot

Once signed in, Copilot just works:

- **Autocomplete** — start typing and Copilot suggests code. Press `Tab` to accept.
- **Chat** — press `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Shift+I` (Mac) to ask Copilot questions about your code.
- **Agent mode** — in the chat panel, switch to "Agent" to let Copilot make multi-file changes for you.

That's it. You're coding with AI.

## 6. Install extensions

### C# / .NET

| Extension | ID |
|-----------|----|
| C# | `ms-dotnettools.csharp` |
| C# Dev Kit | `ms-dotnettools.csdevkit` |
| .NET Runtime | `ms-dotnettools.vscode-dotnet-runtime` |

### JavaScript / TypeScript

| Extension | ID |
|-----------|----|
| ESLint | `dbaeumer.vscode-eslint` |
| Prettier | `esbenp.prettier-vscode` |

### Install manually

Open the Extensions panel (`Ctrl+Shift+X` / `Cmd+Shift+X`) and search by name.

### Install via terminal

```bash
code --install-extension ms-dotnettools.csharp
code --install-extension ms-dotnettools.csdevkit
code --install-extension ms-dotnettools.vscode-dotnet-runtime
code --install-extension dbaeumer.vscode-eslint
code --install-extension esbenp.prettier-vscode
```

### One-liner

**Windows (PowerShell):**

```powershell
@("ms-dotnettools.csharp","ms-dotnettools.csdevkit","ms-dotnettools.vscode-dotnet-runtime","dbaeumer.vscode-eslint","esbenp.prettier-vscode") | ForEach-Object { code --install-extension $_ }
```

**Mac / Linux:**

```bash
for ext in ms-dotnettools.csharp ms-dotnettools.csdevkit ms-dotnettools.vscode-dotnet-runtime dbaeumer.vscode-eslint esbenp.prettier-vscode; do code --install-extension "$ext"; done
```
