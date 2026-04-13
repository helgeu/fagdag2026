# VS Code + Copilot — Get Started

Set up VS Code with GitHub Copilot on **Windows**, **Mac**, or **Linux**.

## Prerequisites

- [ ] Connect your GitHub account to Itera by following [the process described by Chris Searle](https://iterano.slack.com/archives/CA1JMUT50/p1774950332485479)

## 1. Install VS Code

| Platform | Command |
|----------|---------|
| **Windows** | `winget install Microsoft.VisualStudioCode` |
| **Mac** | `brew install --cask visual-studio-code` |
| **Linux** | `sudo snap install code --classic` or see [apt instructions](#vs-code-on-linux-via-apt) if snap is not available |

## 2. Install Git

| Platform | Command |
|----------|---------|
| **Windows** | `winget install Git.Git` |
| **Mac** | `xcode-select --install` |
| **Linux** | `sudo apt install git` |

## 3. Sign in to GitHub

> **Important:** You may have multiple GitHub accounts (personal, customer, employer).
> Make sure you sign in with the account that has Copilot access.
> If you're on a customer machine, you might need to switch to your employer account (e.g. Itera) or vice versa.

Checklist:

- [ ] Decide which GitHub account to use (the one with Copilot access)
- [ ] Open VS Code, click the person icon in the bottom left
- [ ] Sign in with the correct GitHub account
- [ ] Verify Copilot access at [github.com/settings/copilot](https://github.com/settings/copilot) — it should look like this:

![Copilot settings](copilot-settings.png)
- [ ] If Copilot is not enabled, check that you're signed in with the right account

## 4. Start using Copilot

Once signed in, Copilot just works:

- **Autocomplete** — start typing and Copilot suggests code. Press `Tab` to accept.
- **Chat** — press `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Shift+I` (Mac) to ask Copilot questions about your code.
- **Agent mode** — in the chat panel, switch to "Agent" to let Copilot make multi-file changes for you.

That's it. You're coding with AI.

## 5. Install extensions

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

## VS Code on Linux via apt

If snap is not available on your system, use Microsoft's official apt repo instead (Ubuntu/Debian):

```bash
sudo apt install -y wget gpg apt-transport-https
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg
echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list > /dev/null
rm -f packages.microsoft.gpg
sudo apt update
sudo apt install -y code
```
