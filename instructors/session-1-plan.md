---
title: "Session 1 — First Workflow with GitHub Desktop"
---

## Session Plan

**Duration:** 90 minutes
**Goal:** clone a repo, create commits, push/pull, and explore history.

**Prerequisite material:** Material 1 — Git Basics and Single-Person Workflow.

---

### 1. Clone the Repository (10 min)

- Live demo: clone the repository created in Session 0 using GitHub Desktop.
- Participants follow along.
- Verify everyone can see the repository files locally.

---

### 2. Make a Local Edit and Commit (20 min)

- Demo: edit `README.md`, stage changes, write a commit message, commit.
- Emphasise good commit messages (short, descriptive, imperative mood).
- Participants make their own edits and commit.

::::::::::::::::::::::::::::::::::::: callout

### Important: commit message best practices

Before participants start committing, take 2 minutes to discuss:

- Start with a verb ("Add", "Fix", "Update")
- Keep it under 50 characters
- One logical change per commit

Show a bad example vs a good example side by side.

::::::::::::::::::::::::::::::::::::::::::::::::

---

### 3. Push Changes and Verify on GitHub (10 min)

- Demo: push from GitHub Desktop, then show the result on GitHub.
- Participants push and verify their changes appear online.

---

### 4. Edit on GitHub, Then Pull (15 min)

- Demo: make an edit in the GitHub web editor, then pull in GitHub Desktop.
- This demonstrates the remote → local direction of the workflow.
- Participants do the same.

::::::::::::::::::::::::::::::::::::: callout

### Common confusion point

Participants may not understand the difference between **fetch** and **pull**.
Explain briefly:

- **Fetch** = check for updates (does not change your files)
- **Pull** = fetch + merge (updates your files)

::::::::::::::::::::::::::::::::::::::::::::::::

---

### 5. Browse History (15 min)

- Demo: use the History tab in GitHub Desktop to inspect previous commits.
- Show how to view diffs (green/red highlighting).
- Participants explore their own history.

---

### 6. Best Practices Mini-Talk (10 min)

- Commit messages: why they matter and how to write them.
- Small commits: one change per commit.
- Pull often: avoid diverging too far from the remote.
- Introduce `.gitignore` briefly (will be covered more in Material 3).

---

### 7. Q&A Buffer (10 min)

- Open floor for questions.
- Help anyone who fell behind.

---

## Exercise File

See [Session 1 — Exercises](session-1-exercises.md) for the detailed student
tasks.
