---
title: "Session 2 — Collaboration: Merge, Conflict, and PR"
---

## Session Plan

**Duration:** 90 minutes
**Goal:** practise merging, resolve a conflict, create and merge a pull request.

**Prerequisite material:** Material 2 — Collaboration, Branching and Pull
Requests.

---

### 1. Pair Setup (5 min)

- Organise participants into pairs (Person A and Person B).
- Person A shares their repository with Person B as a collaborator.

::::::::::::::::::::::::::::::::::::: callout

### Before the exercises begin

Take 5 minutes to recap the key concepts from Material 2:

- What is a merge? When does it work automatically?
- What is a conflict? When does it happen?
- What is a branch? What is a pull request?

Ask 2–3 participants to explain in their own words.

::::::::::::::::::::::::::::::::::::::::::::::::

---

### 2. Scenario 1 — Mergeable Changes (20 min)

- Both partners edit **different parts** of the same file simultaneously.
- Person A pushes first; Person B pulls, then pushes.
- Git merges automatically.
- Debrief: why did this work without a conflict?

---

### 3. Scenario 2 — Conflict (30 min)

- Both partners edit the **same line** of the same file.
- Person A pushes first; Person B encounters a conflict when pulling.
- Walk through the conflict resolution process:
  1. Identify the conflict markers in the file.
  2. Decide which version to keep (or combine both).
  3. Remove the markers, save, commit, push.

::::::::::::::::::::::::::::::::::::: callout

### Milestone: first conflict resolved

After the first pair resolves their conflict, pause the room briefly. Ask them
to explain what happened to the group. This reinforces learning and helps
struggling pairs.

::::::::::::::::::::::::::::::::::::::::::::::::

---

### 4. Branch and Pull Request in GitHub Desktop (25 min)

- Demo: create a branch, make changes, publish the branch, open a PR.
- Participants create their own branch and PR.
- Partners review each other's PRs on GitHub.
- Merge the PR.

::::::::::::::::::::::::::::::::::::: callout

### Important: PR review etiquette

Before participants start reviewing, briefly discuss:

- Be constructive and specific in comments.
- Use the **Files changed** tab to see exactly what was modified.
- Approve only if you actually looked at the changes.

::::::::::::::::::::::::::::::::::::::::::::::::

---

### 5. Best Practice Tips (10 min)

- Pull before you start working (avoid unnecessary conflicts).
- Communicate with your collaborators about who is working on what.
- Use branches for any non-trivial change.
- Keep pull requests small and focused.

---

## Exercise File

See [Session 2 — Exercises](session-2-exercises.md) for the detailed student
tasks.
