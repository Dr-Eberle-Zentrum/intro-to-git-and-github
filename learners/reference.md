---
title: 'Reference'
---

## Glossary

Branch
: A parallel line of development within a repository. Branches allow you to
  work on new features or fixes without affecting the stable `main` branch.
  Once the work is complete, the branch is merged back.

Clone
: Creating a local copy of a remote repository on your computer. Cloning
  downloads all files, history, and branches so you can work offline.

Commit
: A saved snapshot of changes in your project. Each commit records *what*
  changed, *when*, *who* made the change, and a *message* describing *why*.
  Commits form the building blocks of your project's history.

Conflict (Merge Conflict)
: A situation that arises when two sets of changes modify the same lines in
  the same file. Git cannot resolve this automatically and asks you to choose
  which version to keep (or combine both).

Diff
: A comparison showing exactly which lines were added, removed, or modified
  between two versions of a file.

Fetch
: Downloading new data (commits, branches) from the remote repository
  **without** merging it into your local branch. Use fetch to see what has
  changed before you integrate.

Fork
: A personal copy of someone else's repository on GitHub. Forking lets you
  freely experiment with changes without affecting the original project. You
  can later propose your changes back via a pull request.

`.gitignore`
: A special file listing patterns of files and directories that git should
  **not** track (e.g. build outputs, temporary files, credentials).

History
: The ordered sequence of all commits in a repository, forming a timeline
  of every change ever made.

Issue
: A GitHub feature for tracking tasks, bug reports, feature requests, and
  discussions related to a repository.

Main (branch)
: The default primary branch of a repository (historically called `master`).
  This is typically the stable, production-ready version of the project.

Merge
: Combining changes from one branch into another. If there are no conflicts,
  git performs this automatically; otherwise, a manual conflict resolution is
  needed.

Origin
: The default name for the remote repository on GitHub that your local
  repository was cloned from. When you push or pull, you are typically
  communicating with `origin`.

Pull
: Downloading **and** merging changes from the remote repository into your
  current local branch. Equivalent to a fetch followed by a merge.

Pull Request (PR)
: A proposal on GitHub to merge changes from one branch into another.
  Pull requests facilitate code review, discussion, and approval before
  changes are integrated.

Push
: Uploading your local commits to the remote repository (typically `origin`
  on GitHub) so that others can see and use your changes.

Remote
: A version of your repository hosted on a server (e.g. GitHub). The most
  common remote is called `origin`.

Repository (Repo)
: A project folder tracked by git. It contains all project files plus the
  complete history of changes. Repositories can be local (on your computer)
  or remote (on GitHub).

Revert
: Creating a new commit that undoes the changes introduced by a previous
  commit. This is the safest way to undo work because it preserves history.

Tag
: A label attached to a specific commit, typically used to mark release
  versions (e.g. `v1.0.0`).

## Useful Links

- [GitHub Desktop documentation](https://docs.github.com/en/desktop)
- [GitHub Docs](https://docs.github.com/)
- [Software Carpentry — Git Novice](https://swcarpentry.github.io/git-novice/)
- [Pro Git book (free)](https://git-scm.com/book/en/v2)
- [Git cheat sheet (GitHub)](https://education.github.com/git-cheat-sheet-education.pdf)

