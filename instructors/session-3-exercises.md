---
title: "Session 3 — Exercises: Fork, Pull Request, and Issues"
---

## Overview

In this session you will learn to contribute to a repository you do not own
by forking it, and you will practise using GitHub Issues.

**Time frame:** approximately 75 minutes of hands-on work.

**Pair setup:** work in the same pairs as Session 2. This time you will
contribute to your partner's repository **without** being a collaborator.

---

## Task 1: Fork Workflow

### Level 1 — Fork your partner's repository

1. Go to your **partner's** repository on GitHub (the one from previous
   sessions).
2. Click the **Fork** button in the top-right corner.
3. Keep the default settings and click **Create fork**.
4. Clone **your fork** (not the original) in GitHub Desktop.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 1

You now have a copy of your partner's repository under your own GitHub
account. GitHub Desktop shows the fork as your current repository.

::::::::::::::::::::::::::::::::::::::::::::::::

### Level 2 — Make changes on your fork

1. Create a new branch on your fork (e.g. `improve-readme`).
2. Edit `README.md` — for example, fix a typo, add a section, or improve
   formatting.
3. Commit with a clear message (e.g. `Improve README formatting`).
4. Push the branch to your fork.

### Level 3 — Add a new file

In addition to editing the README, create a new file (e.g. `tips.md`) with
helpful tips or notes. Commit and push this as a separate commit on the same
branch.

---

## Task 2: Pull Request to Upstream

### Level 1 — Open a PR against the original repository

1. On GitHub, navigate to your fork.
2. Click **Contribute → Open pull request**.
3. Make sure the **base repository** is your partner's repo and the **base
   branch** is `main`.
4. Fill in a descriptive title and description explaining your changes.
5. Click **Create pull request**.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 2

Your partner can see the pull request on their repository. The PR shows your
changes and allows them to review and comment.

::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::: spoiler

### Understanding the fork workflow

```text
Partner's repo (upstream)     Your fork (origin)       Your computer (local)
         │                          │                          │
         │       fork               │                          │
         │◄─────────────────────────│                          │
         │                          │        clone             │
         │                          │◄─────────────────────────│
         │                          │                          │
         │                          │   edit + commit + push   │
         │                          │◄─────────────────────────│
         │     pull request         │                          │
         │◄─────────────────────────│                          │
```

::::::::::::::::::::::::

### Level 2 — Review your partner's PR

1. Go to **your own** repository (not your fork).
2. Open the **Pull requests** tab — you should see your partner's PR.
3. Go to the **Files changed** tab and review the diff.
4. Leave at least one comment on a specific line.
5. If the changes look good, **Approve** the PR.

### Level 3 — Merge or discuss

1. If the PR is approved, click **Merge pull request** → **Confirm merge**.
2. If changes are needed, request changes and have your partner update the PR
   by pushing additional commits to their branch.
3. After merging, verify that the changes appear on `main`.

---

## Task 3: GitHub Issues

### Level 1 — Create an issue

1. On your own repository, go to the **Issues** tab.
2. Click **New issue**.
3. Write a clear title (e.g. "Add a licence file").
4. In the description, explain what needs to be done and why.
5. Submit the issue.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 3

Your issue is visible in the Issues tab with a unique number (e.g. #1).

::::::::::::::::::::::::::::::::::::::::::::::::

### Level 2 — Labels and linking

1. Add a label to your issue (e.g. `enhancement` or `documentation`). If no
   labels exist yet, create one.
2. Create a new branch, make the change described in the issue, and open a PR.
3. In the PR description, write `Closes #1` (replacing `1` with your issue
   number) to link the PR to the issue.

:::::::::::::::: spoiler

### How issue linking works

When you include `Closes #1`, `Fixes #1`, or `Resolves #1` in a PR
description, GitHub will **automatically close** the linked issue when the PR
is merged.

::::::::::::::::::::::::

### Level 3 — Issue templates and advanced features

1. Explore the **Labels** page and create a few custom labels for your
   repository (e.g. `help wanted`, `good first issue`).
2. Write a second issue with a detailed bug report format:
   - **Steps to reproduce**
   - **Expected behaviour**
   - **Actual behaviour**
3. Cross-reference the two issues by mentioning one in the other (e.g.
   "Related to #1").

---

## Summary

By the end of this session you should have:

- [ ] Forked a partner's repository and cloned the fork
- [ ] Made changes on a branch and opened a PR to the upstream repository
- [ ] Reviewed and merged (or discussed) a partner's PR
- [ ] Created at least one issue with a clear title and description
- [ ] Linked a PR to an issue using `Closes #N` syntax
