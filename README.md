# 🧠 Git Essentials Summary

## 1️⃣ Start a Git Repository

```bash
git init
```

✅ Creates a `.git` folder to track changes.

---

## 2️⃣ Add & Remove Files from Staging

### General Syntax

```bash
git add <file>
git add <directory>
git add .
```

✅ Moves changes from the working directory to the staging area.

### Commands

```bash
git add <file>       # Add a specific file
git add .            # Add all modified & new files
git add -A           # Add modified, new, and deleted files
git add -p           # Choose parts of the file to stage
git restore --staged <file>  # Unstage a file (keep changes in working dir)
```

---

---

## 3️⃣ Discard & Remove Files

### General Syntax

```bash
git restore [--source=<commit>] <file>
git rm [--cached] <file>
```

### Commands

```bash
git restore <file>       # Undo changes (restore from staging or last commit)
git restore --source=HEAD <file>  # Restore file from last commit
git rm <file>            # Remove file from Git and delete it
git rm --cached <file>   # Untrack file but keep it on disk
```

---

## 4️⃣ Commit Your Changes

### General Syntax

```bash
git commit [-a] -m "Message"
git commit --amend -m "New message"
```

### Commands

```bash
git commit -m "Message"   # Commit staged changes
git commit -a -m "Message"  # Auto-stage modified files before committing
git commit --amend -m "New message"  # Modify the last commit (if not pushed)
```

---

## 5️⃣ View Commit History

### General Syntax

```bash
git log [options]
```

### Commands

```bash
git log                   # Full history
git log --oneline         # Short version (one line per commit)
git log --graph --oneline # Show branch history visually
git log -n 5              # Last 5 commits
git log -- <file>         # History of a specific file
```

---

## 6️⃣ Switch to a Previous Commit (Detached Mode)

### General Syntax

```bash
git checkout <commit-hash>
```

### Commands

```bash
git checkout <commit-hash>   # Switch to a past commit
git checkout -               # Go back to the previous branch
git checkout <branch-name>   # Return to the latest commit (current branch)
```

---

## 7️⃣ Check Differences Between Files

### General Syntax

```bash
git diff [first-place] [second-place]
```

✅ If `first-place` is omitted → compares the working directory to staging.  
✅ If `second-place` is omitted → compares with the last commit.

### Commands

```bash
git diff                 # Working directory vs. staging area
git diff --staged        # Staging area vs. last commit
git diff HEAD            # Working directory vs. last commit
git diff HEAD^ HEAD      # Compare last commit with the one before it
```

---

## 8️⃣ Undoing Commits (Reset)

### General Syntax

```bash
git reset [mode] <commit>
```

✅ Moves HEAD to the specified commit, affecting staged and working files based on the reset mode.

### Modes of `git reset`

- `--soft` → Undo commit, keep changes staged.
- `--mixed` → Undo commit, unstage changes, keep them in the working directory.
- `--hard` → Undo commit and delete all changes permanently (⚠️ cannot be undone!).

### Commands

```bash
git reset --soft HEAD~1   # Undo last commit (keep changes staged)
git reset --mixed HEAD~1  # Undo last commit (unstage changes)
git reset --hard HEAD~1   # Undo last commit (discard changes permanently ⚠️)
```

---

## 9️⃣ Reverting a Commit (Safe Undo)

### General Syntax

```bash
git revert <commit-hash>
```

✅ Unlike `reset`, `revert` creates a new commit that undoes the changes of a previous commit.

### Example

```bash
git revert HEAD  # Reverts the latest commit
git revert HEAD~2  # Reverts the commit before the last one
```

---
