---
title: "Session 4 — Publish and Automate"
---

## Session Plan

**Duration:** 90 minutes
**Goal:** publish a GitHub Pages site, set up a GitHub Action, wrap up the
workshop.

**Prerequisite material:** Material 4 — Publishing and Automation.

---

### 1. GitHub Pages Setup (30 min)

- Live demo: enable GitHub Pages on a repository.
- Show how `README.md` is rendered as a website.
- Participants enable Pages on their own repository and verify the URL.

::::::::::::::::::::::::::::::::::::: callout

### Common issue: build delay

GitHub Pages can take 1–3 minutes to build after enabling or pushing changes.
Warn participants not to panic if the site does not appear immediately. Use
this waiting time to discuss what is happening behind the scenes (GitHub runs
a build pipeline).

::::::::::::::::::::::::::::::::::::::::::::::::

---

### 2. Verify Published URL (15 min)

- Participants visit their published site and share the link with a partner.
- Troubleshoot any issues (wrong branch, missing index file, etc.).
- Encourage participants to improve their page (add headings, links, images).

---

### 3. GitHub Actions — Spell Check (30 min)

- Live demo: create a spell-check workflow file.
- Explain the YAML structure: `name`, `on`, `jobs`, `steps`.
- Participants add the workflow to their repository.
- Trigger the workflow by opening a PR with a deliberate typo.

::::::::::::::::::::::::::::::::::::: callout

### Milestone: first workflow run

After participants trigger their first workflow, pause to discuss:

- Where to find the Actions tab and workflow logs.
- What a passing vs failing check looks like on a PR.
- How this relates to continuous integration (CI) in professional projects.

::::::::::::::::::::::::::::::::::::::::::::::::

---

### 4. Wrap-Up: Recap, Next Steps, Feedback (15 min)

- Quick recap of the entire workshop:
  - Session 0: setup and first repo
  - Session 1: clone, commit, push, pull
  - Session 2: collaboration, conflicts, PRs
  - Session 3: forks, contributions, issues
  - Session 4: publishing and automation
- Suggest next steps:
  - Use git for a real project (thesis, coursework, etc.)
  - Explore advanced topics (rebasing, CI/CD, Git LFS)
  - Contribute to open-source projects
- Collect feedback (survey, sticky notes, or verbal).

::::::::::::::::::::::::::::::::::::: callout

### Final discussion

Ask participants:

- What was the most useful thing you learned?
- What was the most confusing?
- Will you use git in your own work? How?

::::::::::::::::::::::::::::::::::::::::::::::::

---

## Exercise File

See [Session 4 — Exercises](session-4-exercises.md) for the detailed student
tasks.
