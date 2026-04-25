# Git & GitHub Workshop for PhD Students in Mathematics

**Duration:** 2 lectures
**Target audience:** PhD students in Mathematics with little to no prior experience in version control or the command line
**Goal:** Enable students to confidently use Git for their own projects (papers, code, notes) and collaborate through GitHub

---

## Prerequisites

- A laptop with a Unix-like terminal (Linux, macOS, or WSL on Windows)
- Git installed (`git --version` to check)
- A free GitHub account (created before the first lecture, if possible)
- A text editor of choice (VS Code, Vim, Emacs, ...)

---

## Lecture 1 — The Shell and Git Basics

### 1. Motivation (≈ 10 min)
- Why version control? Typical mathematician's pain points:
  - `thesis_final_v2_REALLY_FINAL.tex`
  - Lost changes, overwritten files, unclear history
  - Collaborating on a paper or a code project
- What Git is (a *distributed* version control system) and what GitHub is (a hosting platform built on top of Git — they are **not** the same thing)

### 2. A Minimal Survival Kit for the Shell (≈ 15 min)
- What a shell is; the prompt; the idea of a "current working directory"
- Essential commands:
  - `pwd` — where am I?
  - `ls` (and `ls -l`, `ls -a`) — what's here?
  - `cd` — move around (`cd ..`, `cd ~`, `cd -`)
  - `mkdir`, `rm`, `cp`, `mv` — brief mention
- Tab completion and the arrow keys for history
- Getting help: `man <command>`, `<command> --help`

### 3. Configuring Git (≈ 5 min)
- `git config --global user.name "..."`
- `git config --global user.email "..."`

### 4. Creating and Inspecting a Repository (≈ 25 min)
- `git init` — turning a folder into a repo
- The three areas: **working directory**, **staging area (index)**, **repository**
- The basic cycle:
  - `git status` — the most important command
  - `git add <file>` (and `git add .`)
  - `git commit -m "message"`
- Writing good commit messages (short, imperative, meaningful)
- Inspecting history:
  - `git log`, `git log --oneline`, `git log --graph --oneline --all`
  - `git diff` (unstaged) vs. `git diff --staged`
  - `git show <commit>`

### 5. Working with Existing Repositories (≈ 10 min)
- `git clone <url>` — getting someone else's repo
- Quick tour of a cloned math-related repo (e.g., a small LaTeX or Python project)

### 6. Ignoring Files (≈ 5 min)
- The `.gitignore` file
- Typical entries for a mathematician's project: `*.aux`, `*.log`, `*.synctex.gz`, `__pycache__/`, `.DS_Store`, ...

### 7. Hands-on Exercise (≈ 20 min)
- Create a local repo containing a small LaTeX document or a Python script
- Make several commits, break something on purpose, inspect the history with `git log` and `git diff`

---

## Lecture 2 — Branching, Merging, and GitHub

### 1. Recap and Q&A (≈ 10 min)
- Review of the Lecture 1 workflow
- Address common issues from the exercise

### 2. Branching (≈ 20 min)
- What a branch really is (a movable pointer to a commit) — a short visual explanation
- Commands:
  - `git branch` — list branches
  - `git branch <name>` — create
  - `git switch <name>` (or `git checkout <name>`) — move to it
  - `git switch -c <name>` — create and switch
  - `git branch -d <name>` — delete
- Typical use cases for a mathematician:
  - Trying an alternative proof
  - Experimenting with a new section of a paper
  - Developing a new feature in code without breaking the main version

### 3. Merging (≈ 15 min)
- `git merge <branch>` — fast-forward vs. three-way merge (conceptual only)
- Merge conflicts: how to recognize them, how to resolve them by hand, then `git add` + `git commit`
- Brief note: **rebasing exists** but is out of scope for this workshop

### 4. GitHub: Concepts and Account Setup (≈ 10 min)
- Remote repositories: what they are and why they are useful
- The GitHub interface: repositories, README, issues, pull requests (overview only)
- Public vs. private repositories; academic perks (GitHub Education, unlimited private repos)

### 5. Authenticating with SSH Keys (≈ 15 min)
- Why SSH and not passwords (HTTPS with tokens only briefly mentioned)
- Generating a key pair:
  - `ssh-keygen -t ed25519 -C "your_email@example.com"`
  - Where the keys live: `~/.ssh/id_ed25519` (private, **never share**) and `~/.ssh/id_ed25519.pub` (public)
- Adding the public key to GitHub (Settings → SSH and GPG keys)
- Testing: `ssh -T git@github.com`
- Brief mention of `ssh-agent` for avoiding passphrase prompts

### 6. Working with Remotes (≈ 15 min)
- Creating a repository on GitHub
- Connecting a local repo to a remote:
  - `git remote add origin git@github.com:user/repo.git`
  - `git remote -v`
- The push/pull cycle:
  - `git push -u origin master`
  - `git pull`
  - `git fetch` vs. `git pull` (brief)
- Cloning via SSH vs. HTTPS

### 7. Collaboration Basics (≈ 10 min)
- The typical collaborative workflow: clone → branch → commit → push → pull request → merge
- Quick tour of a pull request on GitHub
- Keeping your local copy up to date (`git pull` before starting to work)

### 8. Hands-on Exercise (≈ 15 min)
- Create a repository on GitHub
- Push a local project (from Lecture 1) to it
- In pairs: clone a partner's repo, create a branch, make a change, push, open a pull request

---

## Suggested Further Reading

- **Pro Git** by Scott Chacon and Ben Straub — free online at <https://git-scm.com/book>
- GitHub's own Git cheat sheet
- *Happy Git and GitHub for the useR* by Jenny Bryan — friendly, task-oriented (examples in R, but applicable to anyone)
- The [Software Carpentry Git lesson](https://swcarpentry.github.io/git-novice/) for self-paced review

## Topics Deliberately Left Out

These are mentioned only to let students know they exist and can be learned later:
- Rebasing and history rewriting (`git rebase`, `git commit --amend`)
- Stashing (`git stash`)
- Tags and releases
- Submodules
- Git hooks
- Advanced workflows (Git Flow, trunk-based development, ...)
