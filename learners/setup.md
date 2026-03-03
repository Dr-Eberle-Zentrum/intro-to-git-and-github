---
title: Setup
---

## Overview

Before the first session, please complete the following setup steps.
This should take about **20–40 minutes**.

## 1. GitHub Account

If you do not already have a GitHub account, register for free at
[github.com](https://github.com/).

### Enable Two-Factor Authentication (2FA)

Two-factor authentication is **required** for many organisational repositories
and is strongly recommended for every account.

1. Go to [github.com/settings/security](https://github.com/settings/security).
2. Under "Two-factor authentication", click **Enable**.
3. Follow the prompts (authenticator app or SMS).

<!-- TODO: add screenshot of 2FA settings page -->

## 2. Install GitHub Desktop

GitHub Desktop is the graphical interface we will use throughout this workshop.

:::::::::::::::: spoiler

### Windows / macOS

1. Download GitHub Desktop from <https://github.com/apps/desktop>.
2. Run the installer and follow the on-screen instructions.
3. Open GitHub Desktop and sign in with your GitHub account.

::::::::::::::::::::::::

:::::::::::::::: spoiler

### Linux (Ubuntu)

GitHub Desktop is not officially supported on Linux, but a community build is
available:

1. Follow the instructions at
   <https://linuxcapable.com/how-to-install-github-desktop-on-ubuntu-linux/>.
2. Open GitHub Desktop and sign in with your GitHub account.

::::::::::::::::::::::::

## 3. Sign In to GitHub Desktop

1. Open GitHub Desktop.
2. Go to **File → Options** (Windows) or **GitHub Desktop → Preferences** (macOS).
3. Under the **Accounts** tab, sign in to your GitHub.com account.

<!-- TODO: add screenshot of the sign-in dialog in GitHub Desktop -->

## 4. Configure Your Identity

Git needs to know your name and email so it can label your commits.

1. In GitHub Desktop, go to **File → Options → Git** (Windows) or
   **GitHub Desktop → Preferences → Git** (macOS).
2. Enter your **Name** and **Email** (use the same email as your GitHub account).

<!-- TODO: add screenshot of the Git identity settings in GitHub Desktop -->

:::::::::::::::: spoiler

### CLI equivalent

If you prefer or need to set this via the command line:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"  # use the same email as your GitHub account
```

::::::::::::::::::::::::

## 5. Verify Your Setup

- [ ] GitHub account registered
- [ ] 2FA enabled
- [ ] GitHub Desktop installed
- [ ] Signed into GitHub Desktop
- [ ] Name and email configured in GitHub Desktop

::::::::::::::::::::::::::::::::::::: callout

### Confirmation

Take a screenshot of your GitHub Desktop main window (showing you are signed
in) or simply confirm to your instructor that everything is ready.

::::::::::::::::::::::::::::::::::::::::::::::::

