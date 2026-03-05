---
title: "Session 1 — Exercises: First Workflow with GitHub Desktop"
---

## Overview

In this session you will clone your repository, make local edits, commit, push,
pull, and explore the commit history using GitHub Desktop.

**Time frame:** approximately 70 minutes of hands-on work.

---

## Task 1: Clone and First Local Commit

### Level 1 — Clone your repository

1. Open **GitHub Desktop**.
2. Click **File → Clone repository** (or the **Clone a repository** button on
   the start screen).
3. Find your `git-intro-<yourname>` repository in the list and click **Clone**.
4. Choose a local path (e.g. your Desktop or Documents folder).

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 1

GitHub Desktop shows your repository with "No local changes". The repository
files are now on your computer in the folder you selected.

::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::: spoiler

### CLI equivalent

```bash
git clone https://github.com/USERNAME/git-intro-yourname.git
cd git-intro-yourname
```

::::::::::::::::::::::::

### Level 2 — Make a local edit and commit

1. Open your `README.md` in a text editor (you can right-click the repository
   in GitHub Desktop and choose **Open in Visual Studio Code** or your
   preferred editor).
2. Add a new section:

   ```markdown
   ## Goals for This Workshop

   - Learn the basics of version control
   - Collaborate with others using GitHub
   - Build confidence with git workflows
   ```

3. Save the file.
4. Switch back to GitHub Desktop — you should see the changes highlighted.
5. Write a commit message: `Add workshop goals to README`
6. Click **Commit to main**.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 2

The commit appears in the **History** tab. 
Your change summary shows the added lines in green.

Note, so far, your changes are still only known within your local repository.
They have not been shared with GitHub or anyone else until you push them (Task 2).

::::::::::::::::::::::::::::::::::::::::::::::::

### Level 3 — Make multiple commits

Create a new file within your project and add/commit it to the local repository.
Use a descriptive message for the new file to practice the habit of
small, focused commits.

---

## Task 2: Push and Pull

### Level 1 — Push your commits

1. In GitHub Desktop, click the **Push origin** button in the toolbar.
2. Go to your repository on [github.com](https://github.com/) and verify that
   your new commits are visible.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 3

Your GitHub repository page shows the updated README with the goals section.

::::::::::::::::::::::::::::::::::::::::::::::::

### Level 2 — Edit on GitHub and pull

1. On GitHub, click the pencil icon on `README.md`.
2. Add a "Fun fact" section:

   ```markdown
   ## Fun Fact

   I once ate an entire pizza by myself in under 10 minutes. 🍕
   ```

3. Commit the change directly on GitHub with the message `Add fun fact`.
4. Switch back to GitHub Desktop and click **Fetch origin**, then **Pull
   origin**.
5. Open `README.md` locally — the fun fact should now be there.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 4

Your local `README.md` contains both the workshop goals (added locally) and
the fun fact (added on GitHub). Both edits are visible in the History tab.

::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::: spoiler

### CLI equivalents

```bash
# Push local commits
git push

# Pull remote changes
git pull
```

::::::::::::::::::::::::

### Level 3 — Inspect the history in detail

1. In GitHub Desktop, go to the **History** tab.
2. Click on different commits and examine the diff (green = added, red =
   removed).
3. On GitHub, go to the **Commits** page and click on a commit to see the same
   diff in the web UI.
4. Can you find the commit SHA (the short code like `a1b2c3d`) for each of
   your commits?

---

## Task 3: Best Practices Review

### Level 1 — Evaluate commit messages

Look at the commit messages in your history. For each one, answer:

- Is it clear what changed?
- Is it short enough (≤ 50 characters)?
- Could someone else understand it without context?

### Level 2 — Refine your workflow

1. Create a `.gitignore` file in your repository that ignores `.DS_Store` and
   `Thumbs.db`.
2. Commit and push the `.gitignore` file.

:::::::::::::::: spoiler

### Example `.gitignore`

```text
.DS_Store
Thumbs.db
*~
```

::::::::::::::::::::::::

---

## Summary

By the end of this session you should have:

- [ ] Repository cloned locally via GitHub Desktop
- [ ] At least 3 commits with meaningful messages in your history
- [ ] Successfully pushed local changes and pulled remote changes
- [ ] Explored the commit history in both GitHub Desktop and the GitHub web UI
