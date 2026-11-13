# Git and GitHub

## What is Version Control

Version control tracks changes to files over time. Without it you end up with files like `project_final.py`, `project_final_new.py`, `project_final_latest_fixed.py` and no idea which one is correct.

With version control:
- You can see what changed and when
- You can go back to any previous version
- Multiple people can work on the same project without overwriting each other

## Types of Version Control

1. **Local VCS** - versions stored on one computer only
2. **Centralized VCS** - one central server stores everything (eg SVN)
3. **Distributed VCS** - every clone has the full history (eg Git)

## What is Git

Git is a distributed version control system. It tracks changes through commits — each commit is a snapshot of your project at a point in time.

Key features:
- Works offline (local repository)
- Supports branching for parallel work
- Fast and lightweight
- Merges changes from different branches

## Git vs GitHub

| | Git | GitHub |
|---|-----|--------|
| Type | Version control tool | Hosting platform |
| Works | Locally | Online |
| Purpose | Track changes | Share and collaborate |
| Network | Works offline | Needs internet |

Git is the tool, GitHub is a website that hosts Git repositories and adds collaboration features.

## How Git Works

Three areas in Git:

1. **Working Directory** - where you edit files
2. **Staging Area** - files ready to be committed
3. **Repository** - committed snapshots stored here

Flow: Edit files → `git add` (stage) → `git commit` (save snapshot)

## Basic Commands

```bash
# initialize a new repo
git init

# check status
git status

# stage files
git add filename.txt
git add .            # stage everything

# commit
git commit -m "your message"

# see commit history
git log
git log --oneline

# see changes
git diff
```

## Branching

Branches let you work on features without affecting the main code.

```bash
# create a branch
git branch feature-x

# switch to it
git checkout feature-x
# or
git switch feature-x

# create and switch in one step
git checkout -b feature-x

# merge branch into main
git checkout main
git merge feature-x

# delete branch after merging
git branch -d feature-x
```

## Working with GitHub

```bash
# clone a remote repo
git clone https://github.com/user/repo.git

# add remote
git remote add origin https://github.com/user/repo.git

# push to github
git push origin main

# pull latest changes
git pull origin main
```

## Pull Requests

On GitHub you can create pull requests to propose changes:

1. Fork or create a branch
2. Make your changes and push
3. Go to GitHub and click "New Pull Request"
4. Others review your code
5. Once approved, merge it

## .gitignore

A `.gitignore` file tells Git which files to ignore (not track):

```
*.exe
*.o
node_modules/
.env
```

## Useful Commands

```bash
# undo changes in working directory
git checkout -- filename

# unstage a file
git reset HEAD filename

# see remote info
git remote -v

# list branches
git branch

# stash changes temporarily
git stash
git stash pop
```

## Why Git Matters

- Used everywhere in software development
- Makes collaboration possible
- Keeps history of everything
- Required for open source contribution
- Even useful for solo projects to track your own changes
