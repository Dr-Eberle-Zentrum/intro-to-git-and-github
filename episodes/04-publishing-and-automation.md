---
title: "Publishing and Automation"
teaching: 30
exercises: 30
---

:::::::::::::::::::::::::::::::::::::: questions

- How can I publish a website from my repository?
- What are tags and releases?
- How can I automate tasks with GitHub Actions?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Enable GitHub Pages to publish a simple site from a repository
- Create a tag and a release on GitHub
- Explain what GitHub Actions are and how workflows are triggered
- Describe how git and GitHub support FAIR and open-science principles

::::::::::::::::::::::::::::::::::::::::::::::::

## GitHub Pages

**GitHub Pages** turns a repository into a website — for free. It is commonly
used for project documentation, personal portfolios, and course materials
(like this one!).

### Enabling GitHub Pages

1. Go to your repository on GitHub.
2. Click **Settings → Pages**.
3. Under **Source**, select the branch (e.g. `main`) and folder (`/ (root)` or
   `/docs`).
4. Click **Save**.
5. After a short build, your site will be available at
   `https://USERNAME.github.io/REPO/`.

<!-- TODO: add screenshot of the GitHub Pages settings page -->

<!-- TODO: add screenshot of a published GitHub Pages site in a browser -->

::::::::::::::::::::::::::::::::::::: callout

### Minimal site from a README

The quickest way to get a Pages site is to write your content in `README.md`.
GitHub Pages will render it as HTML automatically. For more control, you can
use a static site generator like Jekyll (GitHub's default) or create your own
HTML files.

::::::::::::::::::::::::::::::::::::::::::::::::

## Tags and Releases

### Tags

A **tag** is a label attached to a specific commit, typically used to mark
version numbers (e.g. `v1.0.0`).

### Releases

A **release** is a GitHub feature built on top of tags. It adds:

- Release notes describing what changed.
- Downloadable archives (`.zip`, `.tar.gz`).
- Optional binary attachments.

### Creating a release on GitHub

1. Go to your repository and click **Releases** (in the right sidebar).
2. Click **Draft a new release**.
3. Enter a tag (e.g. `v1.0.0`) and a title.
4. Write release notes summarising the changes.
5. Click **Publish release**.

<!-- TODO: add screenshot of the "Draft a new release" form on GitHub -->

:::::::::::::::: spoiler

### CLI equivalents

```bash
# Create an annotated tag
git tag -a v1.0.0 -m "First stable release"

# Push tags to GitHub
git push --tags
```

::::::::::::::::::::::::

## Zenodo Archiving and DOI

[Zenodo](https://zenodo.org/) is a research data repository that integrates
with GitHub. By linking your repository to Zenodo, every release automatically
gets a **DOI** (Digital Object Identifier) — making your work citable in
academic publications.

### Quick setup

1. Go to [zenodo.org](https://zenodo.org/) and log in with your GitHub account.
2. Enable the repository you want to archive.
3. Create a release on GitHub — Zenodo will automatically archive it and assign
   a DOI.

<!-- TODO: add screenshot of the Zenodo–GitHub integration toggle -->

## GitHub for Science

Git and GitHub support several principles that are important in research:

| Principle | How GitHub helps |
|-----------|-----------------|
| **Reproducibility** | Every version is tracked; collaborators can reproduce results from any point in time. |
| **Transparency** | Public repositories let anyone inspect the work. |
| **Collaboration** | Issues, pull requests, and reviews enable structured teamwork. |
| **Archiving** | Zenodo integration provides long-term preservation with DOIs. |
| **FAIR data** | Repositories can be Findable, Accessible, Interoperable, and Reusable when properly documented. |

::::::::::::::::::::::::::::::::::::: callout

### Limitations

- GitHub is **not** a long-term archive by itself — use Zenodo or a
  discipline-specific repository for preservation.
- Large binary files (datasets, images) are not handled well by git. Consider
  [Git LFS](https://git-lfs.github.com/) for large files.
- Private repositories limit transparency; consider making repos public when
  the work is published.

::::::::::::::::::::::::::::::::::::::::::::::::

## Alternatives to GitHub

| Platform | Notes |
|----------|-------|
| [GitLab](https://gitlab.com/) | Self-hostable, integrated CI/CD |
| [Bitbucket](https://bitbucket.org/) | Atlassian ecosystem integration |
| [Codeberg](https://codeberg.org/) | Non-profit, community-driven |
| [SourceHut](https://sourcehut.org/) | Minimalist, email-driven workflow |

All of these use **git** under the hood, so your skills transfer directly.

## GitHub Actions (Introduction)

**GitHub Actions** let you automate tasks that run whenever something happens
in your repository — for example, when you push a commit or open a pull
request.

### What is a workflow?

A **workflow** is an automated process defined in a YAML file inside the
`.github/workflows/` directory. Each workflow contains one or more **jobs**,
and each job contains one or more **steps**.

### When does a workflow run?

Workflows are triggered by **events**, such as:

- `push` — when commits are pushed to a branch.
- `pull_request` — when a PR is opened or updated.
- `schedule` — on a cron schedule (e.g. nightly).

### Example: spell-checking with GitHub Actions

A simple spell-check workflow can catch typos automatically:

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

This workflow:

1. Triggers on every pull request to `main`.
2. Checks out the repository code.
3. Runs [cspell](https://github.com/streetsidesoftware/cspell) to find
   spelling errors.

For more actions, browse the
[GitHub Marketplace](https://github.com/marketplace?type=actions).

<!-- TODO: add screenshot of a passing GitHub Actions run on the Actions tab -->

:::::::::::::::: spoiler

### Where to place the workflow file

```bash
# Create the workflows directory
mkdir -p .github/workflows

# Create the workflow file
cat > .github/workflows/spellcheck.yml << 'EOF'
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
EOF

git add .github/workflows/spellcheck.yml
git commit -m "Add spell-check workflow"
git push
```

::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

## Exercise: What Is a Workflow?

In your own words, explain:

1. What is a GitHub Actions **workflow**?
2. When does it **run**?
3. Give one example of a useful workflow for your own project.

:::::::::::::::::::::::: solution

### Example answers

1. A **workflow** is an automated process defined in a YAML file that tells
   GitHub what tasks to perform (e.g. run tests, check spelling).
2. It **runs** when a specified event occurs — such as pushing code, opening a
   pull request, or on a schedule.
3. Examples: run a spell checker on every PR, build a website on every push to
   `main`, run unit tests before merging.

:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- GitHub Pages publishes a website directly from your repository.
- Tags mark specific commits; releases add notes and downloadable archives.
- Zenodo can archive GitHub releases and assign DOIs for academic citation.
- GitHub Actions automate tasks (testing, building, checking) triggered by
  repository events.
- A workflow is a YAML file in `.github/workflows/` that defines automated jobs.

::::::::::::::::::::::::::::::::::::::::::::::::
