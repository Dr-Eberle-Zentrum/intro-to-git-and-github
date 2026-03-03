---
title: "Session 4 — Exercises: Publish and Automate"
---

## Overview

In this session you will publish a website using GitHub Pages and set up a
simple GitHub Actions workflow.

**Time frame:** approximately 75 minutes of hands-on work.

---

## Task 1: GitHub Pages

### Level 1 — Enable GitHub Pages

1. Go to your repository on GitHub.
2. Navigate to **Settings → Pages**.
3. Under **Source**, select the `main` branch and the `/ (root)` folder.
4. Click **Save**.
5. Wait 1–2 minutes, then visit the URL shown (typically
   `https://USERNAME.github.io/git-intro-yourname/`).

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 1

Your `README.md` is now rendered as a web page accessible via the GitHub Pages
URL. Share the link with your partner to confirm it works.

::::::::::::::::::::::::::::::::::::::::::::::::

### Level 2 — Improve your site

1. Edit your `README.md` to make it look better as a web page:
   - Add a main heading (`# My Project Page`).
   - Add sections with subheadings.
   - Include a link to your GitHub profile.
2. Commit and push the changes.
3. Wait for the site to rebuild and check the updated page.

### Level 3 — Add a separate page

1. Create a new file `about.md` with information about yourself.
2. Add a link from `README.md` to `about.md`:

   ```markdown
   [About me](about.md)
   ```

3. Commit, push, and verify that the link works on your published site.

:::::::::::::::: spoiler

### Minimal HTML alternative

If you want more control, create an `index.html` file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Project</title>
</head>
<body>
    <h1>Welcome to My Project</h1>
    <p>This site is published with GitHub Pages.</p>
</body>
</html>
```

Note: if `index.html` exists, GitHub Pages will use it instead of `README.md`.

::::::::::::::::::::::::

---

## Task 2: GitHub Actions — Spell Check

### Level 1 — Add a spell-check workflow

1. On GitHub, click **Add file → Create new file**.
2. Name the file `.github/workflows/spellcheck.yml` (GitHub will create the
   directories automatically).
3. Paste the following content:

   ```yaml
   name: Spell Check
   on:
     pull_request:
       branches: [main]

   jobs:
     spellcheck:
       runs-on: ubuntu-latest
       steps:
         - uses: actions/checkout@v4
         - uses: streetsidesoftware/cspell-action@v6
   ```

4. Commit the file with the message `Add spell-check workflow`.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 2

The file `.github/workflows/spellcheck.yml` exists in your repository. You
can see it in the Code tab under `.github/workflows/`.

::::::::::::::::::::::::::::::::::::::::::::::::

### Level 2 — Trigger the workflow

1. Create a new branch (e.g. `test-spellcheck`).
2. Edit any file and intentionally introduce a spelling error (e.g.
   "Tihs is a tset").
3. Commit and push the branch.
4. Open a **Pull Request** from `test-spellcheck` to `main`.
5. Go to the **Actions** tab and watch the spell-check workflow run.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 3

The Actions tab shows a workflow run. It may report spelling errors — that is
expected! You have successfully triggered a GitHub Action.

::::::::::::::::::::::::::::::::::::::::::::::::

### Level 3 — Fix and re-run

1. Fix the intentional spelling errors in your branch.
2. Commit and push again.
3. The workflow will re-run automatically on the updated PR.
4. Verify that the workflow passes (green check mark).

:::::::::::::::: spoiler

### Where to find workflow results

1. Go to the **Actions** tab in your repository.
2. Click on the workflow run to see details.
3. Click on the job name (e.g. `spellcheck`) to see the log output.
4. On the PR page, you can also see the status check at the bottom.

::::::::::::::::::::::::

---

## Task 3: Wrap-Up and Reflection

### Level 1 — Review your learning

Write a short summary (3–5 sentences) in your `README.md` about what you
learned in this workshop. Include:

- The most important concept you learned.
- Something that surprised you.
- One thing you want to explore further.

Commit and push.

### Level 2 — Create a release

1. On GitHub, go to **Releases → Draft a new release**.
2. Create a tag `v1.0.0`.
3. Title it "Workshop Complete".
4. Write a brief description of the repository content.
5. Click **Publish release**.

### Level 3 — Explore further

- Browse the [GitHub Actions Marketplace](https://github.com/marketplace?type=actions)
  and find another action that could be useful for your project.
- Look into [Zenodo](https://zenodo.org/) and how you would link your
  repository for automatic DOI creation.

---

## Summary

By the end of this session you should have:

- [ ] A published GitHub Pages site with a working URL
- [ ] A spell-check GitHub Action configured in your repository
- [ ] Successfully triggered and observed a workflow run
- [ ] A workshop reflection in your README
- [ ] (Optional) A tagged release of your repository
