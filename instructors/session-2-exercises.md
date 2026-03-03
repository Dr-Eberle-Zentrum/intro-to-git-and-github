---
title: "Session 2 — Exercises: Merge, Conflict, and Pull Request"
---

## Overview

In this session you will work in pairs to practise merging, resolving
conflicts, and using pull requests.

**Time frame:** approximately 75 minutes of hands-on work.

**Pair setup:** decide who is **Person A** and who is **Person B**. You will
both work on Person A's repository.

---

## Task 1: Mergeable Changes (No Conflict)

### Level 1 — Edit different parts of the same file

1. **Person A:** add Person B as a collaborator on your repository:
   - Go to **Settings → Collaborators → Add people** and enter Person B's
     GitHub username.
2. **Person B:** accept the invitation (check your email or GitHub
   notifications), then clone Person A's repository in GitHub Desktop.
3. Both partners edit `README.md` at the **same time**, but in **different
   sections**:
   - **Person A:** add a "Hobbies" section at the top.
   - **Person B:** add a "Favourite Books" section at the bottom.
4. **Person A:** commit and push first.
5. **Person B:** fetch, pull, then commit and push.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 1

Both changes appear in `README.md` on GitHub. Git merged them automatically
because they did not overlap.

::::::::::::::::::::::::::::::::::::::::::::::::

### Level 2 — Try with a new file

Repeat the exercise, but this time each person creates a **new file**:

- Person A creates `hobbies.md`.
- Person B creates `books.md`.

Commit, push, and pull. Both files should appear in the repository without
conflict.

### Level 3 — Multiple rounds

Do two more rounds of non-conflicting edits to build confidence and speed with
the commit → push → pull → commit → push cycle.

---

## Task 2: Create and Resolve a Merge Conflict

### Level 1 — Intentional conflict

1. Both partners open `README.md`.
2. Both edit the **same line** (for example, change the first line of the
   "About Me" section to something different).
3. **Person A:** commit and push.
4. **Person B:** commit, then try to push — GitHub Desktop will tell you to
   pull first.
5. **Person B:** pull. A **merge conflict** will appear.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 2

GitHub Desktop shows a conflict notification. The conflicted file contains
markers like:

```text
<<<<<<< HEAD
Person A's version of the line.
=======
Person B's version of the line.
>>>>>>> main
```

::::::::::::::::::::::::::::::::::::::::::::::::

### Level 2 — Resolve the conflict

1. Open the conflicted file in your text editor.
2. Decide which version to keep (or combine both).
3. Remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).
4. Save the file.
5. In GitHub Desktop, mark the conflict as resolved and commit.
6. Push the result.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 3

The repository now has a merge commit in its history. Both partners can pull
and see the resolved file.

::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::: spoiler

### CLI equivalent

```bash
# After a conflicting pull
git status                # shows conflicted files
# ... edit the file to resolve ...
git add README.md
git commit -m "Resolve merge conflict in README"
git push
```

::::::::::::::::::::::::

### Level 3 — Document the conflict

Add a short paragraph to your README describing:

- What caused the conflict?
- How did you resolve it?
- What would you do differently next time?

---

## Task 3: Branch and Pull Request

### Level 1 — Create a branch and commit

1. In GitHub Desktop, click **Current branch → New branch**.
2. Name it `add-resources` (or another descriptive name).
3. Create a new file called `resources.md` with a few useful links related to
   your studies or interests.
4. Commit with the message `Add resources file`.
5. Click **Publish branch** to push it to GitHub.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 4

On GitHub, you can see the new branch in the branch dropdown. The file
`resources.md` exists only on the `add-resources` branch, not on `main`.

::::::::::::::::::::::::::::::::::::::::::::::::

### Level 2 — Open a pull request

1. GitHub Desktop shows a prompt **Create Pull Request** — click it.
2. On GitHub, fill in a title and description for your PR.
3. Click **Create pull request**.
4. Ask your partner to review the PR:
   - Go to the **Files changed** tab.
   - Leave at least one comment.
   - Approve the PR.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 5

The pull request page shows the conversation, file changes, and an approval.

::::::::::::::::::::::::::::::::::::::::::::::::

### Level 3 — Merge the pull request

1. On the PR page, click **Merge pull request** → **Confirm merge**.
2. Switch back to `main` in GitHub Desktop and pull.
3. Verify that `resources.md` now exists on `main`.
4. (Optional) Delete the merged branch on GitHub when prompted.

:::::::::::::::: spoiler

### CLI equivalent

```bash
# Create and switch to a new branch
git checkout -b add-resources

# ... make changes and commit ...
git add resources.md
git commit -m "Add resources file"

# Push the branch
git push -u origin add-resources

# After merging the PR on GitHub, update local main
git checkout main
git pull
```

::::::::::::::::::::::::

---

## Summary

By the end of this session you should have:

- [ ] Successfully merged non-conflicting changes with a partner
- [ ] Created, identified, and resolved a merge conflict
- [ ] Documented what happened during the conflict
- [ ] Created a branch, committed to it, and opened a pull request
- [ ] Had a pull request reviewed and merged
