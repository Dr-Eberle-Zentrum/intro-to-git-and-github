---
title: "Session 0 — Exercises: First Repository and GitHub Tour"
---

## Overview

In this session you will create your first repository on GitHub, write a short
README, and explore the GitHub interface.

**Time frame:** approximately 60 minutes of hands-on work.

---

## Task 1: Create Your First Repository

### Step 1 — Create a new repository on GitHub

<!-- spell-checker:ignore yourname -->

1. Go to [github.com](https://github.com/) and sign in.
2. Click the **+** button in the top-right corner and select **New repository**.
3. Name your repository `git-intro-<yourname>` (replace `<yourname>` with your
   actual name or username).
4. Check **Add a README file**.
5. Click **Create repository**.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 1

You should now see your new repository page with a `README.md` file displayed.

::::::::::::::::::::::::::::::::::::::::::::::::

### Step 2 — Alter content of your README

1. Click the pencil icon (✏️) on the `README.md` file to edit it.
2. Add a heading with your name and 2–3 bullet points about yourself, for
   example:

   ```markdown
   # About Me

   - I study biology at the University of Tübingen.
   - I like hiking and cooking.
   - I want to learn git for my thesis project.
   ```

3. Scroll down, write a short commit message (e.g. "Add personal info to
   README"), and click **Commit changes**.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 2

Your README now shows your name and personal information. You should see
**2 commits** in the repository history.

::::::::::::::::::::::::::::::::::::::::::::::::

### Step 3 — Explore Markdown formatting

Enhance your README with [additional Markdown features](https://github.com/adam-p/markdown-here/wiki/markdown-cheatsheet):

- Add a **link** to this course material.
- Add a **numbered list** of your top 3 goals for this workshop.
- Try using **bold** and *italic* text.

:::::::::::::::: spoiler

### Markdown cheat sheet

```markdown
# Heading 1
## Heading 2

- Bullet point
1. Numbered item

**bold text**
*italic text*

[Link text](https://example.com)

![Image alt text](https://example.com/image.png)
```

::::::::::::::::::::::::

---

## Task 2: Explore the GitHub Interface

### Level 1 — Navigate the repository page

Explore the following areas of your repository and note what you find:

1. **Code tab** — Where are your files listed?
2. **Commits** — Click on the commit count to see your commit history.
3. **Settings** — Find where you can change the repository name or visibility.

### Task

Change the visibility of your project to "private" (if it is currently public) or to "public" (if it is currently private). 

To do this:

- go to "Settings"
- find the respective option in the "General" section
- change the visibility and confirm the change by typing the repository name when prompted.

::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 3

You can navigate to the commit history and identify who made each commit and
when.

::::::::::::::::::::::::::::::::::::::::::::::::

### Level 2 — Discover more GitHub features

Explore these additional features:

1. **Issues tab** — Open a new issue titled "Test issue" with a short
   description. Close it afterwards.
2. **Pull requests tab** — Note that it is empty for now (we will use it
   later).



### Task 

Open a new issue by spotting a "typo" in your README and describing how to fix it.
To this end:

- go to "Code"
- click on your `README.md` file (to show its content)
- switch from "Preview" to "Code" to see the raw markdown
- select on of the markdown lines (should be highlighted in yellow)
- this should trigger the popup of a `...` menu, where you can select "Reference in new issue" to create a new issue with the selected line as content.
- add a title and description to the issue, and submit it.


### Level 3 — Repository settings deep dive

1. Disable "Wiki" and "Projects" features in the **Features** section of the **General** Settings.
2. Find the **Danger Zone** in Settings. What other options are available there?
3. **Settings** — Find where you would add a collaborator.


### Task 

You should add your course supervisor as a collaborator to your repository, 
so that they can see it and provide feedback. 

To do this:

- go to "Settings"
- click on "Collaborators" in the left sidebar
- add the GitHub user name of your course supervisor and click "Add collaborator"
  - choose "write" permissions for the collaborator, so that they can also edit the repository if needed.

The course supervisor will receive an email invitation to collaborate on your repository, which they need to accept before they can see it.


::::::::::::::::::::::::::::::::::::: callout

### Checkpoint 4

You can navigate the GitHub page, identify where to find commits, issues, and settings, and understand the
different features available in the repository settings.

**Task to complete before next session:**

Either add the course supervisor as a collaborator to your repository, or 
make sure your repository is public so that we can see it.

::::::::::::::::::::::::::::::::::::::::::::::::


---

## Summary

By the end of this session you should have:

- [ ] A repository named `git-intro-<yourname>` on GitHub
- [ ] A README with at least 2–3 bullet points about yourself
- [ ] Familiarity with the GitHub repository interface (Code, Commits,
      Issues, Settings)
