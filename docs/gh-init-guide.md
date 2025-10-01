# GitHub CLI (gh) Initialization Guide

This guide provides instructions for installing and authenticating the GitHub CLI (`gh`) tool, which is essential for interacting with GitHub from your command line.

## 1. Installation

Follow the instructions below based on your operating system.

### macOS

Using Homebrew:

```bash
brew install gh
```

### Linux

For Debian/Ubuntu-based systems:

```bash
sudo apt update
sudo apt install gh
```

For Fedora/CentOS/RHEL-based systems:

```bash
sudo dnf install gh
```

### Windows

Using Chocolatey:

```bash
choco install gh
```

Using Winget:

```bash
winget install GitHub.cli
```

Alternatively, you can download the appropriate installer from the [GitHub CLI releases page](https://github.com/cli/cli/releases).

## 2. Authentication

After installing `gh`, you need to authenticate it with your GitHub account. This allows `gh` to access your repositories and perform actions on your behalf.

To authenticate, run the following command:

```bash
gh auth login
```

This command will guide you through the authentication process:

1.  **Choose your GitHub instance:** Select `GitHub.com` or `GitHub Enterprise Server`.
2.  **Login method:** Choose `Login with a web browser` (recommended) or `Paste an authentication token`.
    *   **Web browser (recommended):** `gh` will provide a one-time code and open your web browser. Enter the code on the GitHub authorization page and authorize `gh`. This is the most secure and convenient method.
    *   **Authentication token:** If you choose this method, you will need to generate a [Personal Access Token (PAT)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) with the necessary scopes (e.g., `repo`, `workflow`, `write:packages`, `delete:packages`, `admin:org`, `gist`, `security_events`). Paste the token into your terminal when prompted.
3.  **Git Protocol:** Choose `HTTPS` or `SSH` for Git operations.

Once authenticated, `gh` will store your credentials securely, and you can start using it to manage your GitHub repositories, issues, pull requests, and more.
