# Git Cheat Sheet

## Basic Configuration

```bash
# Set your username and email
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# View your configuration
git config --list
```

## Getting Started

```bash
# Initialize a new repository
git init

# Clone a repository
git clone <repository-url>
git clone <repository-url> <directory-name>

# Check repository status
git status
```

## Basic Commands

```bash
# Add files to staging area
git add <file-name>        # Add specific file
git add .                  # Add all files
git add *.js              # Add all JavaScript files

# Commit changes
git commit -m "Your commit message"
git commit -am "Your commit message"  # Add and commit in one command

# View commit history
git log
git log --oneline         # Compact view
git log --graph          # Show branch graph
```

## Branching

```bash
# List branches
git branch               # Local branches
git branch -r           # Remote branches
git branch -a           # All branches

# Create and switch to new branch
git branch <branch-name>
git checkout <branch-name>
git checkout -b <branch-name>  # Create and switch in one command

# Switch branches
git checkout <branch-name>
git switch <branch-name>      # Newer Git versions

# Delete branch
git branch -d <branch-name>   # Safe delete
git branch -D <branch-name>   # Force delete
```

## Remote Operations

```bash
# Add remote repository
git remote add origin <repository-url>

# List remotes
git remote -v

# Fetch changes
git fetch origin
git fetch --all

# Pull changes
git pull origin <branch-name>
git pull --rebase origin <branch-name>

# Push changes
git push origin <branch-name>
git push -u origin <branch-name>  # Set upstream branch
```

## Stashing

```bash
# Save changes temporarily
git stash
git stash save "message"

# List stashes
git stash list

# Apply stash
git stash apply          # Keep stash
git stash pop           # Remove stash after applying
git stash drop          # Remove specific stash

# Clear all stashes
git stash clear
```

## Advanced Operations

```bash
# Merge branches
git merge <branch-name>
git merge --no-ff <branch-name>  # Create merge commit

# Rebase
git rebase <branch-name>
git rebase -i HEAD~3    # Interactive rebase last 3 commits

# Cherry-pick
git cherry-pick <commit-hash>

# Reset changes
git reset HEAD~1        # Soft reset (keep changes)
git reset --hard HEAD~1 # Hard reset (discard changes)

# Revert commit
git revert <commit-hash>
```

## Working with Tags

```bash
# Create tag
git tag <tag-name>
git tag -a <tag-name> -m "Tag message"

# List tags
git tag
git tag -l "v1.*"

# Push tags
git push origin <tag-name>
git push origin --tags
```

## Advanced Git Features

```bash
# Bisect (find bad commit)
git bisect start
git bisect bad
git bisect good <commit-hash>

# Submodules
git submodule add <repository-url>
git submodule update --init --recursive

# Worktree
git worktree add <path> <branch>
git worktree list
```

## Useful Aliases

```bash
# Add these to your .gitconfig
[alias]
    st = status
    co = checkout
    br = branch
    ci = commit
    unstage = reset HEAD --
    last = log -1 HEAD
    visual = !gitk
```

## Best Practices

1. Write clear, descriptive commit messages
2. Keep commits atomic and focused
3. Use branches for new features/fixes
4. Regularly pull from remote
5. Review changes before committing
6. Use .gitignore for unnecessary files
7. Keep your repository clean and organized

## Common Use Cases

### Starting a New Project

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin <repository-url>
git push -u origin main
```

### Working on a Feature

```bash
git checkout -b feature/new-feature
# Make changes
git add .
git commit -m "Add new feature"
git push origin feature/new-feature
```

### Updating Your Local Repository

```bash
git fetch origin
git pull origin main
git checkout feature/new-feature
git rebase main
```

### Fixing Mistakes

```bash
# Undo last commit (keep changes)
git reset HEAD~1

# Undo last commit (discard changes)
git reset --hard HEAD~1

# Revert a specific commit
git revert <commit-hash>
```

### Cleaning Up

```bash
# Remove untracked files
git clean -n  # Dry run
git clean -f  # Force remove

# Remove untracked directories
git clean -fd
```
