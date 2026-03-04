---
title: "Git Basics and Single-Person Workflow"
teaching: 30
exercises: 30
---

:::::::::::::::::::::::::::::::::::::: questions

- What is version control and why should I use it?
- What are the basic git concepts I need to know?
- How do I work with a repository on my own?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain what git is and why version control matters
- Describe the difference between local and remote repositories
- Perform the core loop: edit → commit → push → pull
- Write meaningful commit messages
- Use a `.gitignore` file to exclude unwanted files

::::::::::::::::::::::::::::::::::::::::::::::::


## What Is Git?

!["What is git?" by [R. Fadatare](https://medium.com/javaguides/git-explained-how-git-works-in-3-minutes-960404135fc4)](what-is-git.png){alt="git summary" width="80%"}

![](https://git-scm.com/images/logos/downloads/Git-Logo-2Color.png){alt="git logo" width="70px"} is a **version control system** — a tool that tracks changes to your files over time. 
Think of it as an "undo history" on steroids: you can go back to any
previous version, see exactly what changed, and even work on multiple versions
in parallel.

The following screenshot shows a git commit history with messages and timestamps. 
Each commit is a snapshot of the project at a point in time, allowing you to track the evolution of your work and understand the context of changes.

![Git commit timeline](gh-commit-history.png){alt="Git commit history showing a linear sequence of commits with messages and timestamps."}


::::::::::::::::::::::::::::::::::::: callout

### Why use version control?

- **Reproducibility:** every version of your work is saved and can be
  restored.
- **Collaboration:** multiple people can work on the same project without
  annihilating each other's changes.
- **Publishing:** share your work publicly or with a team.
- **Archiving:** keep a permanent, citable record of your project.

::::::::::::::::::::::::::::::::::::::::::::::::

## What Is GitHub?

**GitHub** is a web platform that hosts git repositories online. It adds
collaboration features such as pull requests, issues, and project boards on
top of git's version control.

- **Git** = the version control engine (runs on your computer).
- **GitHub** = the hosting service (stores your repository in the cloud).


## Local vs Remote Repositories

Before we start working with git, it's important to understand the difference between the **local** and **remote** repositories:

| Term | Meaning |
|------|---------|
| **Local repository** | The copy of the project on *your* computer |
| **Remote repository** | The copy hosted on GitHub (often called **origin**) |

![Relationship between local and remote repositories, with arrows indicating push (local → remote) and pull (remote → local) actions.](local-remote-repo.png){alt="local and remote repositories with push and pull arrows." width="70%"}

When you **clone** a repository, you download the remote copy of the project to your machine.
From that point on, you will synchronise changes between the two copies using **push** (local → remote) and **pull** (remote → local) git actions.
The same can be done by multiple people working on the same project, allowing for collaboration based on a synchronised central remote repository.
This is one of the major advantages of using systems like git for file management.

## The Core Loop


::::::: callout

## Repository vs Working Directory

**Note:** the local repository kind of a local database of all the changes you make on all the files in your project.
It is controlled by git not the same as the files on your computer that you edit and work with!
In order to work with the files on your computer, git creates a **working directory** that is a copy of the project files at a specific point in time (the last commit).
When you make changes to the files, they are not automatically saved in the local repository until you **commit** them. 
This is an important distinction to understand as it allows you to control when and how your changes are recorded in the history of the project.

::::::::::::

In the end, the git workflow operates in three places:

1. **Working directory** — where you edit files on your computer.
2. **Local repository** — where your commits are stored on your computer.
3. **Remote repository** — where your commits are stored on GitHub.

The interchange between these three places can be illustrated as follows by
relating the git operations with a similar workflow without digital tools:

![Illustration of the git workflow showing the working directory, local repository, and remote repository with arrows indicating the flow of changes: edit (working directory), commit (local repository), push (remote repository), and pull (working directory).](gh-workflow-illustrated.png){alt="Diagram of the git workflow showing the working directory, local repository, and remote repository with arrows indicating the flow of changes." width="90%"}


Therefore, the everyday git workflow follows four steps:

0. **Pull** — get the latest changes from the remote repository before you start working. Note, this also updates your working directory!
1. **Edit** — change files in your working directory.
2. **Commit** — save a snapshot of your changes with a descriptive message in your local repository.
3. **Push** — upload your recent commits from the local to the remote repository on GitHub.

We strongly recommend to start your daily work by pulling the latest changes from GitHub to ensure you are working with the most up-to-date version of the project and to minimise potential conflicts later on.


### Making a Commit in GitHub Desktop

1. Open GitHub Desktop and select your repository.
2. You will see changed files listed in the left panel.
3. Select the files you want to include in this commit.
4. Write a short, descriptive **Summary** (commit message).
5. Click **Commit to main**.

<!-- TODO: add screenshot of the GitHub Desktop commit panel with changes staged -->

### Pushing Changes

After committing, click the **Push origin** button in the toolbar to upload
your commits to GitHub.

<!-- TODO: add screenshot of the Push origin button in GitHub Desktop -->

### Pulling Changes

If changes were made on GitHub (for example via the web editor), click
**Fetch origin** and then **Pull origin** to bring them to your local copy.

<!-- TODO: add screenshot of the Pull origin button in GitHub Desktop -->

:::::::::::::::: spoiler

### CLI equivalents

```bash
# Clone a repository
git clone https://github.com/USERNAME/REPO.git

# Check what has changed
git status

# Stage changes for commit
git add filename.md      # stage a specific file
git add .                # stage all changes

# Commit with a message
git commit -m "Add goals section to README"

# Push commits to GitHub
git push

# Pull changes from GitHub
git pull
```

::::::::::::::::::::::::

## Tracking Changes and History

Every commit is a snapshot in your project's timeline. You can browse the
history to see:

- **what** changed (which files, which lines),
- **when** it changed (date and time),
- **who** made the change, and
- **why** (the commit message).

### Viewing History in GitHub Desktop

1. Click the **History** tab in the left panel.
2. Select any commit to see the files that changed and the exact differences
   (green = added, red = removed).

<!-- TODO: add screenshot of the History tab in GitHub Desktop showing a diff -->

:::::::::::::::: spoiler

### CLI equivalents

```bash
# View commit history
git log --oneline

# Show details of a specific commit
git show abc1234

# Compare working directory with last commit
git diff
```

::::::::::::::::::::::::

## What Makes a Good Commit?

::::::::::::::::::::::::::::::::::::: callout

### Best practices for commits

- **Small and focused:** each commit should represent one logical change.
- **Clear message:** start with a short summary (≤ 50 characters), optionally
  followed by a blank line and more detail.
- **Commit often:** frequent small commits are easier to understand and undo
  than rare large ones.

**Good examples:**

- `Add project goals to README`
- `Fix typo in introduction section`

**Bad examples:**

- `Update files`
- `asdfgh`

::::::::::::::::::::::::::::::::::::::::::::::::

## Ignoring Files with `.gitignore`

Not every file belongs in a repository. Build outputs, temporary files, and
credentials should be excluded.

Create a file called `.gitignore` in the root of your repository and list the
patterns to ignore:

```text
# Compiled files
*.exe
*.o

# Editor backups
*~
*.swp

# OS files
.DS_Store
Thumbs.db

# Credentials — never commit these!
secrets.yaml
.env
```

:::::::::::::::: spoiler

### CLI equivalent

```bash
# Create a .gitignore file
echo "*.exe" > .gitignore
echo ".DS_Store" >> .gitignore

# Check which files are ignored
git status --ignored
```

::::::::::::::::::::::::

## Fetch vs Pull (Optional)

| Command | What it does |
|---------|-------------|
| **Fetch** | Downloads new data from the remote but does *not* change your local files. |
| **Pull** | Fetches *and* merges the remote changes into your current branch. |

In GitHub Desktop, clicking **Fetch origin** checks for updates. If there are
new commits, the button changes to **Pull origin**.

For more details, see
[Git fetch and merge](https://longair.net/blog/2009/04/16/git-fetch-and-merge/).

::::::::::::::::::::::::::::::::::::: challenge

## Exercise: Explain in Your Own Words

Write one or two sentences explaining each of the following terms:

1. **Commit**
2. **Push**
3. **Pull**

:::::::::::::::::::::::: solution

### Example answers

1. **Commit** — a saved snapshot of changes in my project, together with a
   message describing what I changed and why.
2. **Push** — uploading my local commits to the remote repository on GitHub so
   others (or other devices) can see them.
3. **Pull** — downloading and merging commits from the remote repository into
   my local copy so I have the latest changes.

:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- Git is a version control system that tracks changes to files over time.
- GitHub hosts git repositories in the cloud and adds collaboration features.
- The core workflow is: **edit → commit → push → pull**.
- Good commits are small, focused, and have clear messages.
- Use `.gitignore` to keep unwanted files out of your repository.

::::::::::::::::::::::::::::::::::::::::::::::::
