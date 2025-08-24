Git Interview Question and Answer

---

# Table of Contents – Git Interview Questions

### Basics of Git

1. [What is Git?](#1-what-is-git)
2. [Git vs GitHub](#2-what-is-the-difference-between-git-and-github)
3. [Repository in Git](#3-what-is-a-repository-in-git)
4. [Types of Git repositories](#4-what-are-the-two-types-of-git-repositories)
5. [git init vs git clone](#5-what-is-the-difference-between-git-init-and-git-clone)
6. [git status](#6-what-does-git-status-do)
7. [git add](#7-what-does-git-add-do)
8. [git commit](#8-what-does-git-commit-do)
9. [git pull vs git fetch](#9-what-is-the-difference-between-git-pull-and-git-fetch)
10. [git push](#10-what-does-git-push-do)

### Branching and Merging

11. [What is a branch?](#11-what-is-a-branch-in-git)
12. [Create a branch](#12-how-do-you-create-a-branch-in-git)
13. [Switch branch](#13-how-do-you-switch-to-a-branch-in-git)
14. [Create and switch](#14-how-do-you-create-and-switch-to-a-branch-in-one-command)
15. [git merge](#15-what-is-git-merge)
16. [git rebase](#16-what-is-git-rebase)
17. [Merge vs Rebase](#17-difference-between-merge-and-rebase)
18. [Fast-forward merge](#18-what-is-a-fast-forward-merge)
19. [Git conflict](#19-what-is-a-conflict-in-git)
20. [Resolve conflicts](#20-how-do-you-resolve-conflicts-in-git)

### Git Staging and Undoing

21. [Staging area](#21-what-is-the-staging-area-in-git)
22. [Remove file from staging](#22-how-do-you-remove-a-file-from-the-staging-area)
23. [Discard changes](#23-how-do-you-discard-changes-in-a-file)
24. [Undo last commit (keep changes)](#24-how-do-you-undo-the-last-commit-but-keep-changes)
25. [Undo last commit (remove changes)](#25-how-do-you-undo-the-last-commit-and-remove-changes)
26. [git revert](#26-what-is-git-revert)
27. [Reset vs Revert](#27-what-is-the-difference-between-git-reset-and-git-revert)
28. [git stash](#28-how-do-you-stash-changes-in-git)
29. [Apply stash](#29-how-do-you-apply-stashed-changes)
30. [List stashes](#30-how-do-you-list-stashes)

### Git Logs and History

31. [View commit history](#31-how-do-you-view-commit-history)
32. [One-line summary](#32-how-to-see-a-one-line-summary-of-commits)
33. [Last 5 commits](#33-how-to-see-the-last-5-commits)
34. [Show commit changes](#34-how-to-see-the-changes-made-in-a-commit)
35. [Compare commits](#35-how-do-you-compare-commits)
36. [Diff working dir vs last commit](#36-how-do-you-see-changes-between-working-directory-and-last-commit)
37. [Diff staged vs last commit](#37-how-to-see-changes-between-staging-and-last-commit)
38. [File history](#38-how-to-see-file-history-in-git)
39. [Blame](#39-how-to-see-who-changed-a-line-in-git)
40. [Search commit messages](#40-how-to-search-commit-messages)

### Remote Repositories

41. [Add remote](#41-how-do-you-add-a-remote-repository)
42. [View remotes](#42-how-do-you-see-configured-remotes)
43. [Remove remote](#43-how-do-you-remove-a-remote)
44. [Rename remote](#44-how-do-you-rename-a-remote)
45. [Push branch](#45-how-do-you-push-a-branch-to-remote)
46. [Delete remote branch](#46-how-do-you-delete-a-remote-branch)
47. [Fetch all branches](#47-how-do-you-fetch-all-branches)
48. [Pull specific branch](#48-how-do-you-pull-changes-from-a-specific-branch)
49. [Origin](#49-what-is-origin-in-git)
50. [Upstream](#50-what-is-upstream-in-git)

### Advanced Git Concepts

51. [Detached HEAD](#51-what-is-a-detached-head-state-in-git)
52. [Fix detached HEAD](#52-how-do-you-fix-detached-head)
53. [Cherry-pick](#53-what-is-git-cherry-pick)
54. [Bisect](#54-what-is-git-bisect)
55. [Reflog](#55-what-is-git-reflog)
56. [Submodule](#56-what-is-git-submodule)
57. [Add submodule](#57-how-to-add-a-submodule)
58. [.gitignore](#58-what-is-gitignore)
59. [Ignore tracked file](#59-how-do-you-force-git-to-ignore-a-file-that-is-already-tracked)
60. [Untracked files](#60-how-do-you-see-untracked-files)

### Collaboration and Workflow

61. [Pull request](#61-what-is-a-pull-request)
62. [Fork vs Clone](#62-difference-between-fork-and-clone)
63. [Git hook](#63-what-is-a-git-hook)
64. [Git tag](#64-what-is-a-git-tag)
65. [Create tag](#65-how-do-you-create-a-tag)
66. [Push tags](#66-how-do-you-push-tags-to-remote)
67. [Lightweight vs annotated tags](#67-what-is-the-difference-between-lightweight-and-annotated-tags)
68. [Delete local tag](#68-how-do-you-delete-a-local-tag)
69. [Delete remote tag](#69-how-do-you-delete-a-remote-tag)
70. [Git Flow](#70-what-is-git-flow)

### Performance and Optimization

71. [File sizes](#71-how-do-you-see-file-sizes-in-a-git-repo)
72. [Cleanup](#72-how-do-you-clean-up-unnecessary-files)
73. [Remove untracked files](#73-how-do-you-remove-untracked-files)
74. [git fsck](#74-what-is-git-fsck)
75. [git prune](#75-what-is-git-prune)
76. [git filter-branch](#76-what-is-git-filter-branch)
77. [Replacement for filter-branch](#77-what-is-the-replacement-for-git-filter-branch)
78. [Shallow clone](#78-how-to-shallow-clone-a-repo)
79. [Sparse checkout](#79-what-is-git-sparse-checkout)
80. [Split repository](#80-how-do-you-split-a-git-repository)

### Real-World Scenarios

81. [Squash commits](#81-how-do-you-squash-commits)
82. [Amend last commit](#82-how-do-you-amend-the-last-commit)
83. [Change commit message](#83-how-do-you-change-commit-message-in-history)
84. [Recover deleted commits](#84-how-do-you-recover-deleted-commits)
85. [Diff between branches](#85-how-do-you-see-the-difference-between-two-branches)
86. [Delete local branch](#86-how-do-you-delete-a-local-branch)
87. [Rename branch](#87-how-do-you-rename-a-branch)
88. [Track remote branch](#88-how-do-you-track-a-remote-branch)
89. [Unstage all files](#89-how-do-you-unstage-all-files)
90. [Rollback to commit](#90-how-do-you-rollback-to-a-specific-commit)

### Miscellaneous

91. [Git LFS](#91-what-is-git-lfs)
92. [Centralized vs distributed VCS](#92-what-is-the-difference-between-centralized-and-distributed-version-control)
93. [.gitattributes](#93-what-is-gitattributes)
94. [Configure Git user](#94-how-do-you-configure-git-user-details)
95. [List Git config](#95-how-do-you-list-all-git-configurations)
96. [Local, global, system config](#96-what-is-the-difference-between-local-global-and-system-git-config)
97. [Alias Git commands](#97-how-do-you-alias-git-commands)
98. [Diff between tags](#98-how-do-you-see-the-difference-between-two-tags)
99. [git archive](#99-what-is-git-archive)
100.  [Migrate SVN to Git](#100-how-do-you-migrate-from-svn-to-git)

---

Here’s a full set of **100 Git interview questions and answers** formatted in **Markdown** for easy reading, note-taking, or practice.

---

# Git Interview Questions and Answers

## Basics of Git

### 1. What is Git?

Git is a distributed version control system that allows multiple developers to track changes in source code during software development.

---

### 2. What is the difference between Git and GitHub?

- **Git**: A version control system.
- **GitHub**: A cloud-based hosting service for Git repositories with collaboration features.

---

### 3. What is a repository in Git?

A repository (repo) is a collection of files, directories, and history that Git manages.

---

### 4. What are the two types of Git repositories?

- **Local Repository** (on your machine).
- **Remote Repository** (hosted on a server like GitHub, GitLab, Bitbucket).

---

### 5. What is the difference between `git init` and `git clone`?

- `git init`: Initializes a new Git repository.
- `git clone`: Copies an existing repository into a new directory.

---

### 6. What does `git status` do?

Shows the current state of the working directory and staging area (untracked, modified, staged files).

---

### 7. What does `git add` do?

Adds changes from the working directory to the staging area.

---

### 8. What does `git commit` do?

Saves staged changes to the repository with a commit message.

---

### 9. What is the difference between `git pull` and `git fetch`?

- `git fetch`: Downloads commits but does not merge.
- `git pull`: Downloads commits and merges them into the current branch.

---

### 10. What does `git push` do?

Uploads local commits to a remote repository.

---

## Branching and Merging

### 11. What is a branch in Git?

A branch is a lightweight movable pointer to a commit.

---

### 12. How do you create a branch in Git?

```bash
git branch branch_name
```

---

### 13. How do you switch to a branch in Git?

```bash
git checkout branch_name
```

or

```bash
git switch branch_name
```

---

### 14. How do you create and switch to a branch in one command?

```bash
git checkout -b branch_name
```

---

### 15. What is `git merge`?

Combines changes from one branch into another.

---

### 16. What is `git rebase`?

Reapplies commits on top of another base branch.

---

### 17. Difference between `merge` and `rebase`?

- **Merge**: Preserves history, creates a new merge commit.
- **Rebase**: Rewrites history, creates a linear sequence of commits.

---

### 18. What is a fast-forward merge?

A merge where the target branch is directly updated without creating a merge commit.

---

### 19. What is a conflict in Git?

A situation where changes from two branches affect the same part of a file, and Git cannot merge automatically.

---

### 20. How do you resolve conflicts in Git?

Manually edit the conflicting file(s), then:

```bash
git add <file>
git commit
```

---

## Git Staging and Undoing

### 21. What is the staging area in Git?

An intermediate area where changes are prepared before committing.

---

### 22. How do you remove a file from the staging area?

```bash
git reset HEAD <file>
```

---

### 23. How do you discard changes in a file?

```bash
git checkout -- <file>
```

---

### 24. How do you undo the last commit but keep changes?

```bash
git reset --soft HEAD~1
```

---

### 25. How do you undo the last commit and remove changes?

```bash
git reset --hard HEAD~1
```

---

### 26. What is `git revert`?

Creates a new commit that undoes changes from a previous commit.

---

### 27. What is the difference between `git reset` and `git revert`?

- **Reset**: Moves HEAD and deletes commits.
- **Revert**: Creates a new commit to undo changes without deleting history.

---

### 28. How do you stash changes in Git?

```bash
git stash
```

---

### 29. How do you apply stashed changes?

```bash
git stash apply
```

---

### 30. How do you list stashes?

```bash
git stash list
```

---

## Git Logs and History

### 31. How do you view commit history?

```bash
git log
```

---

### 32. How to see a one-line summary of commits?

```bash
git log --oneline
```

---

### 33. How to see the last 5 commits?

```bash
git log -5
```

---

### 34. How to see the changes made in a commit?

```bash
git show <commit_id>
```

---

### 35. How do you compare commits?

```bash
git diff <commit1> <commit2>
```

---

### 36. How do you see changes between working directory and last commit?

```bash
git diff
```

---

### 37. How to see changes between staging and last commit?

```bash
git diff --cached
```

---

### 38. How to see file history in Git?

```bash
git log -- <file>
```

---

### 39. How to see who changed a line in Git?

```bash
git blame <file>
```

---

### 40. How to search commit messages?

```bash
git log --grep="keyword"
```

---

## Remote Repositories

### 41. How do you add a remote repository?

```bash
git remote add origin <url>
```

---

### 42. How do you see configured remotes?

```bash
git remote -v
```

---

### 43. How do you remove a remote?

```bash
git remote remove <name>
```

---

### 44. How do you rename a remote?

```bash
git remote rename <old> <new>
```

---

### 45. How do you push a branch to remote?

```bash
git push origin branch_name
```

---

### 46. How do you delete a remote branch?

```bash
git push origin --delete branch_name
```

---

### 47. How do you fetch all branches?

```bash
git fetch --all
```

---

### 48. How do you pull changes from a specific branch?

```bash
git pull origin branch_name
```

---

### 49. What is `origin` in Git?

The default name given to the remote repository when you clone.

---

### 50. What is `upstream` in Git?

Refers to the original repository from which a fork was created.

---

## Advanced Git Concepts

### 51. What is a detached HEAD state in Git?

When HEAD points to a specific commit instead of a branch.

---

### 52. How do you fix detached HEAD?

```bash
git checkout branch_name
```

---

### 53. What is `git cherry-pick`?

Applies a specific commit from one branch onto another.

---

### 54. What is `git bisect`?

Helps find the commit that introduced a bug using binary search.

---

### 55. What is `git reflog`?

Shows a log of where HEAD and references have been.

---

### 56. What is `git submodule`?

A way to include external repositories inside another repository.

---

### 57. How to add a submodule?

```bash
git submodule add <url>
```

---

### 58. What is `.gitignore`?

A file that specifies intentionally untracked files Git should ignore.

---

### 59. How do you force Git to ignore a file that is already tracked?

```bash
git rm --cached <file>
```

---

### 60. How do you see untracked files?

```bash
git status
```

---

## Collaboration and Workflow

### 61. What is a pull request?

A request to merge changes from one branch into another (mostly on GitHub/GitLab).

---

### 62. Difference between fork and clone?

- **Fork**: Copies repo to your GitHub account.
- **Clone**: Downloads repo to your local machine.

---

### 63. What is a Git hook?

Scripts that run automatically on certain Git events (e.g., pre-commit, post-merge).

---

### 64. What is a Git tag?

A reference that points to a specific commit, often used for releases.

---

### 65. How do you create a tag?

```bash
git tag v1.0
```

---

### 66. How do you push tags to remote?

```bash
git push origin --tags
```

---

### 67. What is the difference between lightweight and annotated tags?

- **Lightweight**: Just a pointer.
- **Annotated**: Stores metadata (message, date, author).

---

### 68. How do you delete a local tag?

```bash
git tag -d v1.0
```

---

### 69. How do you delete a remote tag?

```bash
git push origin :refs/tags/v1.0
```

---

### 70. What is Git Flow?

A branching model for Git that defines how features, releases, and hotfixes are managed.

---

## Performance and Optimization

### 71. How do you see file sizes in a Git repo?

```bash
git count-objects -vH
```

---

### 72. How do you clean up unnecessary files?

```bash
git gc
```

---

### 73. How do you remove untracked files?

```bash
git clean -f
```

---

### 74. What is `git fsck`?

Checks the integrity of the Git object database.

---

### 75. What is `git prune`?

Removes unreachable or orphaned objects.

---

### 76. What is `git filter-branch`?

Rewrites history (e.g., to remove sensitive data).

---

### 77. What is the replacement for `git filter-branch`?

`git filter-repo`

---

### 78. How to shallow clone a repo?

```bash
git clone --depth 1 <url>
```

---

### 79. What is `git sparse-checkout`?

Allows checking out only specific directories instead of the whole repo.

---

### 80. How do you split a Git repository?

Using `git filter-repo` or `git subtree split`.

---

## Real-World Scenarios

### 81. How do you squash commits?

```bash
git rebase -i HEAD~n
```

---

### 82. How do you amend the last commit?

```bash
git commit --amend
```

---

### 83. How do you change commit message in history?

```bash
git rebase -i HEAD~n
```

---

### 84. How do you recover deleted commits?

```bash
git reflog
git checkout <commit>
```

---

### 85. How do you see the difference between two branches?

```bash
git diff branch1..branch2
```

---

### 86. How do you delete a local branch?

```bash
git branch -d branch_name
```

---

### 87. How do you rename a branch?

```bash
git branch -m old_name new_name
```

---

### 88. How do you track a remote branch?

```bash
git checkout --track origin/branch_name
```

---

### 89. How do you unstage all files?

```bash
git reset
```

---

### 90. How do you rollback to a specific commit?

```bash
git reset --hard <commit_id>
```

---

## Miscellaneous

### 91. What is Git LFS?

Git Large File Storage, used for versioning large files.

---

### 92. What is the difference between centralized and distributed version control?

- **Centralized**: Single server (e.g., SVN).
- **Distributed**: Every user has a full copy (e.g., Git).

---

### 93. What is `.gitattributes`?

Defines attributes like text encoding, merge strategies, diff settings for files.

---

### 94. How do you configure Git user details?

```bash
git config --global user.name "Name"
git config --global user.email "email@example.com"
```

---

### 95. How do you list all Git configurations?

```bash
git config --list
```

---

### 96. What is the difference between local, global, and system Git config?

- **Local**: Repo-specific.
- **Global**: User-specific.
- **System**: Applies to all users on a system.

---

### 97. How do you alias Git commands?

```bash
git config --global alias.co checkout
```

---

### 98. How do you see the difference between two tags?

```bash
git diff tag1 tag2
```

---

### 99. What is `git archive`?

Creates a tar or zip file of a particular commit or branch.

---

### 100. How do you migrate from SVN to Git?

Using tools like `git svn` or `svn2git`.

---