# Git Commands Usage Guide

## Basic Configuration

```bash
# Set your username and email
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

**Usage**: These commands set up your Git identity. The `--global` flag means these settings apply to all your Git repositories on your machine. This information is used to identify who made commits.

```bash
# View your configuration
git config --list
```

**Usage**: Shows all your Git configuration settings, including user name, email, and other custom configurations.

## Getting Started

```bash
# Initialize a new repository
git init
```

**Usage**: Creates a new Git repository in the current directory. This is the first command you run when starting a new project.

```bash
# Clone a repository
git clone <repository-url>
git clone <repository-url> <directory-name>
```

**Usage**:

- Downloads an existing repository from a remote source (like GitHub)
- The second form lets you specify a custom directory name
- Creates a local copy with all history and branches

```bash
# Check repository status
git status
```

**Usage**: Shows the current state of your working directory and staging area, including:

- Which files are modified
- Which files are staged
- Which files are untracked

## Basic Commands

```bash
# Add files to staging area
git add <file-name>        # Add specific file
git add .                  # Add all files
git add *.js              # Add all JavaScript files
```

**Usage**:

- Stages files for commit
- `git add .` stages all files in current directory
- `git add *.js` stages all JavaScript files
- Files must be staged before they can be committed

```bash
# Commit changes
git commit -m "Your commit message"
git commit -am "Your commit message"  # Add and commit in one command
```

**Usage**:

- Creates a snapshot of your staged changes
- `-m` flag adds a commit message
- `-am` combines add and commit in one command (only works for modified files)

```bash
# View commit history
git log
git log --oneline         # Compact view
git log --graph          # Show branch graph
```

**Usage**:

- Shows commit history
- `--oneline` shows one line per commit
- `--graph` shows branch structure visually

## Branching

```bash
# List branches
git branch               # Local branches
git branch -r           # Remote branches
git branch -a           # All branches
```

**Usage**:

- Shows all branches in your repository
- `-r` shows remote branches
- `-a` shows both local and remote branches

```bash
# Create and switch to new branch
git branch <branch-name>
git checkout <branch-name>
git checkout -b <branch-name>  # Create and switch in one command
```

**Usage**:

- `git branch` creates a new branch
- `git checkout` switches to an existing branch
- `git checkout -b` creates and switches in one command

```bash
# Delete branch
git branch -d <branch-name>   # Safe delete
git branch -D <branch-name>   # Force delete
```

**Usage**:

- `-d` safely deletes a branch (only if fully merged)
- `-D` forcefully deletes a branch (even if not merged)

## Remote Operations

```bash
# Add remote repository
git remote add origin <repository-url>
```

**Usage**: Connects your local repository to a remote one (like GitHub)

```bash
# List remotes
git remote -v
```

**Usage**: Shows all remote repositories connected to your local repository

```bash
# Fetch changes
git fetch origin
git fetch --all
```

**Usage**:

- Downloads changes from remote but doesn't merge them
- `--all` fetches from all remotes

```bash
# Pull changes
git pull origin <branch-name>
git pull --rebase origin <branch-name>
```

**Usage**:

- Downloads and merges changes from remote
- `--rebase` applies your changes on top of remote changes

```bash
# Push changes
git push origin <branch-name>
git push -u origin <branch-name>  # Set upstream branch
```

**Usage**:

- Uploads your local commits to remote
- `-u` sets up tracking between local and remote branch

## Stashing

```bash
# Save changes temporarily
git stash
git stash save "message"
```

**Usage**: Temporarily saves your changes without committing, useful when you need to switch branches but aren't ready to commit

```bash
# List stashes
git stash list
```

**Usage**: Shows all saved stashes with their messages

```bash
# Apply stash
git stash apply          # Keep stash
git stash pop           # Remove stash after applying
git stash drop          # Remove specific stash
```

**Usage**:

- `apply` applies stash but keeps it in the list
- `pop` applies and removes the most recent stash
- `drop` removes a specific stash

## Advanced Operations

```bash
# Merge branches
git merge <branch-name>
git merge --no-ff <branch-name>  # Create merge commit
```

**Usage**:

- Combines changes from different branches
- `--no-ff` creates a merge commit even if fast-forward is possible

```bash
# Rebase
git rebase <branch-name>
git rebase -i HEAD~3    # Interactive rebase last 3 commits
```

**Usage**:

- Moves your branch's commits to the tip of another branch
- `-i` allows interactive rebasing (reordering, editing, squashing commits)

```bash
# Cherry-pick
git cherry-pick <commit-hash>
```

**Usage**: Applies a specific commit from another branch to your current branch

```bash
# Reset changes
git reset HEAD~1        # Soft reset (keep changes)
git reset --hard HEAD~1 # Hard reset (discard changes)
```

**Usage**:

- `soft` undoes commit but keeps changes staged
- `hard` undoes commit and discards all changes

## Working with Tags

```bash
# Create tag
git tag <tag-name>
git tag -a <tag-name> -m "Tag message"
```

**Usage**:

- Creates a reference point in your repository history
- `-a` creates an annotated tag with a message
- Useful for marking releases

```bash
# List tags
git tag
git tag -l "v1.*"
```

**Usage**:

- Shows all tags
- `-l` filters tags by pattern

## Advanced Git Features

```bash
# Bisect (find bad commit)
git bisect start
git bisect bad
git bisect good <commit-hash>
```

**Usage**: Binary search through commits to find which one introduced a bug

```bash
# Submodules
git submodule add <repository-url>
git submodule update --init --recursive
```

**Usage**: Manages dependencies as separate Git repositories

```bash
# Worktree
git worktree add <path> <branch>
git worktree list
```

**Usage**: Allows working on multiple branches simultaneously in different directories

## Best Practices

1. **Write clear commit messages**

   - Use present tense
   - Be specific about changes
   - Keep it concise but informative

2. **Keep commits atomic and focused**

   - One logical change per commit
   - Makes it easier to review and revert if needed

3. **Use branches for new features/fixes**

   - Keeps main branch stable
   - Allows parallel development
   - Makes code review easier

4. **Regularly pull from remote**

   - Stay up to date with team changes
   - Avoid merge conflicts
   - Keep your local repository in sync

5. **Review changes before committing**

   - Use `git diff` to review changes
   - Ensure you're committing the right files
   - Check for any sensitive information

6. **Use .gitignore for unnecessary files**

   - Keep repository clean
   - Avoid committing build artifacts
   - Prevent sensitive information from being committed

7. **Keep your repository clean and organized**
   - Regular maintenance
   - Remove old branches
   - Clean up stashes

## Common Use Cases

### Starting a New Project

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin <repository-url>
git push -u origin main
```

**Usage**: Complete workflow for starting a new project and pushing it to remote

### Working on a Feature

```bash
git checkout -b feature/new-feature
# Make changes
git add .
git commit -m "Add new feature"
git push origin feature/new-feature
```

**Usage**: Standard workflow for developing a new feature

### Updating Your Local Repository

```bash
git fetch origin
git pull origin main
git checkout feature/new-feature
git rebase main
```

**Usage**: Keeping your feature branch up to date with main branch

### Fixing Mistakes

```bash
# Undo last commit (keep changes)
git reset HEAD~1

# Undo last commit (discard changes)
git reset --hard HEAD~1

# Revert a specific commit
git revert <commit-hash>
```

**Usage**: Different ways to undo changes or commits

### Cleaning Up

```bash
# Remove untracked files
git clean -n  # Dry run
git clean -f  # Force remove

# Remove untracked directories
git clean -fd
```

**Usage**: Removing untracked files and directories from your working directory
