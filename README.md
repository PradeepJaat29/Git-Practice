# Git Practice Repository

This is a markdown file for practicing Git commands. Nothing here is production code. The repository exists so you can experiment, make mistakes, and build confidence with Git and GitHub in a safe place.

Edit this file, create new ones, break things, and fix them again. That is the whole point.

---

## Table of Contents
 
- [Purpose](#purpose)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Core Commands](#core-commands)
- [Branching and Merging](#branching-and-merging)
- [Working with Remotes](#working-with-remotes)
- [Undoing Things](#undoing-things)
- [Practice Exercises](#practice-exercises)
- [Cheat Sheet](#cheat-sheet)
- [Tips](#tips)
- [Resources](#resources)
- [Contributing](#contributing)

---

## Purpose

This repository is a sandbox for learning Git. By working through it you will practice:

- Creating and cloning repositories
- Staging and committing changes
- Writing clear commit messages
- Creating, switching, and merging branches
- Resolving merge conflicts
- Pushing to and pulling from GitHub
- Undoing mistakes safely

## Prerequisites

- [Git](https://git-scm.com/downloads) installed on your machine
- A free [GitHub](https://github.com) account
- A terminal (Terminal on macOS/Linux, Git Bash or PowerShell on Windows)
- A text editor such as VS Code

Check that Git is installed:

```bash
git --version
```

Set your identity (one time only):

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

## Getting Started

Clone this repository to your computer:

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

Or start a brand new local repository:

```bash
mkdir git-practice
cd git-practice
git init
```

## Core Commands

| Command | What it does |
| --- | --- |
| `git status` | Shows changed, staged, and untracked files |
| `git add <file>` | Stages a file for the next commit |
| `git add .` | Stages all changes in the current directory |
| `git commit -m "message"` | Saves staged changes with a message |
| `git log` | Shows commit history |
| `git log --oneline --graph` | Compact, visual history |
| `git diff` | Shows unstaged changes |
| `git diff --staged` | Shows staged changes |

A typical workflow looks like this:

```bash
# 1. Edit a file
# 2. See what changed
git status
git diff

# 3. Stage and commit
git add README.md
git commit -m "Add practice notes to README"
```

## Branching and Merging

Branches let you work on something without affecting the main line of development.

```bash
git branch                    # list branches
git branch feature-intro      # create a branch
git switch feature-intro      # switch to it
git switch -c feature-intro   # create and switch in one step
git merge feature-intro       # merge it into your current branch
git branch -d feature-intro   # delete it after merging
```

### Practicing merge conflicts

1. Create two branches from `main`.
2. Edit the same line of this file differently on each branch.
3. Merge both into `main`.
4. Open the file, resolve the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`), then:

```bash
git add README.md
git commit
```

## Working with Remotes

```bash
git remote -v                       # list remotes
git remote add origin <url>         # connect a remote
git push -u origin main             # push and set upstream
git pull                            # fetch and merge remote changes
git fetch                           # download changes without merging
```

## Undoing Things

| Situation | Command |
| --- | --- |
| Discard changes in a file | `git restore <file>` |
| Unstage a file | `git restore --staged <file>` |
| Fix the last commit message | `git commit --amend` |
| Undo a commit, keep changes | `git reset --soft HEAD~1` |
| Undo a commit, discard changes | `git reset --hard HEAD~1` |
| Safely undo a pushed commit | `git revert <commit-hash>` |
| Temporarily shelve changes | `git stash` / `git stash pop` |

> **Warning:** `git reset --hard` permanently discards uncommitted work. Use it carefully, and never rewrite history that others have already pulled.

## Practice Exercises

Work through these in order. Check off each one as you finish.

- [ ] Clone this repository
- [ ] Create a new file called `notes.md` and commit it
- [ ] Make three separate commits with clear messages
- [ ] View your history with `git log --oneline`
- [ ] Create a branch called `practice-branch` and add a commit on it
- [ ] Merge `practice-branch` into `main`
- [ ] Create a deliberate merge conflict and resolve it
- [ ] Use `git stash` to set aside unfinished work, then restore it
- [ ] Undo a commit with `git revert`
- [ ] Add a `.gitignore` file and confirm ignored files stay untracked
- [ ] Push your changes to GitHub
- [ ] Fork this repository and open a pull request

## Cheat Sheet

```bash
git init                      # start a repo
git clone <url>               # copy a repo
git status                    # what's going on?
git add .                     # stage everything
git commit -m "msg"           # save a snapshot
git branch                    # list branches
git switch <branch>           # change branch
git merge <branch>            # combine branches
git pull / git push           # sync with remote
git log --oneline             # short history
git stash                     # shelve changes
```

## Tips

- **Commit often.** Small commits are easier to understand and undo.
- **Write useful messages.** Describe what changed and why, in the present tense: "Add login form", not "added stuff".
- **Run `git status` constantly.** It is the best way to know where you are.
- **Don't fear mistakes.** Almost everything in Git can be recovered. Try `git reflog` if you think you lost something.
- **Keep secrets out.** Never commit passwords, API keys, or tokens.

## Resources

- [Pro Git book](https://git-scm.com/book/en/v2) (free)
- [Git documentation](https://git-scm.com/doc)
- [GitHub Skills](https://skills.github.com/) (interactive courses)
- [Learn Git Branching](https://learngitbranching.js.org/) (visual practice)
- [Oh Shit, Git!?!](https://ohshitgit.com/) (fixing common mistakes)

## Contributing

This is a practice repository, so contributions are welcome and low-pressure:

1. Fork the repository
2. Create a branch: `git switch -c my-change`
3. Make a small edit and commit it
4. Push to your fork: `git push origin my-change`
5. Open a pull request

## License

This project is open for anyone to learn from. Add a license of your choice (for example, [MIT](https://choosealicense.com/licenses/mit/)) if you want to make the terms explicit.
