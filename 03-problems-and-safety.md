---
title: "Problems, Safety, and GitHub Hygiene"
teaching: 30
exercises: 30
---

:::::::::::::::::::::::::::::::::::::: questions

- What common problems will I encounter when using git?
- How do I undo mistakes safely?
- How should I organise my repository and collaborate with others?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Handle common git pitfalls (empty directories, wrong commits)
- Undo changes using revert, discard, and reset (beginner-safe)
- Explain the difference between public and private repositories
- Describe protected branches, collaborators, and permissions
- Use GitHub issues effectively

::::::::::::::::::::::::::::::::::::::::::::::::

## Common Problems

### Empty Directories

Git tracks **files**, not directories. If you create an empty folder, git will
ignore it.

**Workarounds:**

- Add a placeholder file called `.gitkeep` inside the directory.
- Make sure every directory contains at least one meaningful file.

<!-- TODO: add screenshot of a .gitkeep file inside an otherwise empty folder in a file explorer -->

:::::::::::::::: spoiler

### CLI example

```bash
# Create a directory with a placeholder
mkdir data
touch data/.gitkeep
git add data/.gitkeep
git commit -m "Add empty data directory with .gitkeep"
```

::::::::::::::::::::::::

### Accidentally Committed the Wrong File

If you committed a file by mistake (for example a large data file or
credentials):

1. **Don't panic.** The commit is only local until you push.
2. In GitHub Desktop, right-click the commit in History and choose
   **Revert this Commit**.
3. Add the file pattern to `.gitignore` so it is not tracked in the future.

<!-- TODO: add screenshot of the "Revert this Commit" option in GitHub Desktop -->

::::::::::::::::::::::::::::::::::::: callout

### Credentials and secrets

**Never** commit passwords, API keys, or other secrets. If you accidentally
push a secret to GitHub, consider it compromised — rotate the credential
immediately and remove it from the repository history.

::::::::::::::::::::::::::::::::::::::::::::::::

## Undoing Changes

There are several ways to undo work in git. Here is a beginner-friendly
overview:

| Situation | Action in GitHub Desktop | What happens |
|-----------|--------------------------|-------------|
| Changed a file but have not committed | Right-click the file → **Discard changes** | File returns to the last committed state |
| Committed but have not pushed | Right-click the commit → **Revert this Commit** | A new commit is created that undoes the changes |
| Already pushed | Use **Revert this Commit** and push again | A new revert commit is added to the remote |

<!-- TODO: add screenshot of the "Discard changes" context menu in GitHub Desktop -->

:::::::::::::::: spoiler

### CLI equivalents

```bash
# Discard changes to a file (before commit)
git checkout -- filename.md

# Revert the last commit (creates a new commit)
git revert HEAD

# Unstage a file (keep changes but remove from staging)
git reset HEAD filename.md
```

::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: callout

### A note on rebase

You may encounter the term **rebase** in online tutorials. Rebasing rewrites
commit history and is an advanced technique. **Do not use rebase** on shared
branches unless you fully understand the implications — it can cause serious
problems for collaborators. Stick with **merge** for now.

::::::::::::::::::::::::::::::::::::::::::::::::

## Repository Visibility

| Setting | Who can see the repo | Who can contribute |
|---------|---------------------|--------------------|
| **Public** | Anyone on the internet | Only collaborators (unless forked) |
| **Private** | Only you and invited collaborators | Only collaborators |

Choose **private** for sensitive or unfinished work. Choose **public** when you
want to share your project with the world.

<!-- TODO: add screenshot of the repository visibility setting on GitHub (Settings → Danger Zone) -->

## Protected Branches

Teams often **protect** the `main` branch so that:

- No one can push directly to `main`.
- All changes must go through a pull request.
- Pull requests require at least one approving review before merging.

This prevents accidental breakage on the stable branch.

<!-- TODO: add screenshot of branch protection rules on GitHub -->

:::::::::::::::: spoiler

### Where to configure branch protection

1. Go to your repository on GitHub.
2. Click **Settings → Branches**.
3. Under "Branch protection rules", click **Add rule**.
4. Enter `main` as the branch name pattern.
5. Check **Require a pull request before merging** and other options as needed.

::::::::::::::::::::::::

## Collaborators and Permissions

To give someone access to your **private** repository (or push access to a
public one):

1. Go to **Settings → Collaborators**.
2. Click **Add people** and search for their GitHub username.
3. Choose a permission level (Read, Write, or Admin).

<!-- TODO: add screenshot of the "Add collaborator" dialog on GitHub -->

## GitHub Issues

Issues are used to track tasks, report bugs, and discuss ideas. Good practices:

- **Clear title:** summarise the problem or request in a few words.
- **Description:** explain the context, steps to reproduce (for bugs), and
  expected behaviour.
- **Labels:** use labels like `bug`, `enhancement`, `question` to categorise.
- **Linking:** reference issues in commit messages or PRs using `#123` syntax.

<!-- TODO: add screenshot of a well-formatted GitHub issue with labels -->

::::::::::::::::::::::::::::::::::::: challenge

## Exercise: Your Troubleshooting Checklist

Create a short checklist titled **"What to do when something went wrong"**.
Include at least five items covering the scenarios discussed above.

:::::::::::::::::::::::: solution

### Example checklist

1. **Unwanted changes to a file?** → Discard changes in GitHub Desktop.
2. **Wrong commit (not yet pushed)?** → Revert the commit in GitHub Desktop.
3. **Wrong commit (already pushed)?** → Revert and push the revert commit.
4. **Committed a secret?** → Rotate the credential immediately. Remove from
   history if possible.
5. **Empty directory not showing up?** → Add a `.gitkeep` file.
6. **Merge conflict?** → Open the file, resolve the markers, commit, and push.
7. **Cannot push to main?** → The branch is probably protected. Create a
   branch and open a pull request instead.

:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- Git does not track empty directories — use `.gitkeep` as a placeholder.
- Use **Discard changes** for uncommitted edits and **Revert** for commits.
- Never commit secrets; rotate any that are accidentally pushed.
- Protected branches enforce a pull request workflow.
- Issues help organise work; use clear titles, descriptions, and labels.

::::::::::::::::::::::::::::::::::::::::::::::::
