# Git Workflow Guide

## Overview

This document outlines our team's Git workflow for collaborative development. Following these practices will help maintain a clean repository, minimize merge conflicts, and ensure a smooth collaboration process.

## Branching Strategy

We follow a modified GitFlow workflow with the following branch structure:

- **main**: Production-ready code. Stable and deployable at all times.
- **develop**: Integration branch for new features. Merges into main when ready for release.
- **feature branches**: Individual work branches for each team member or specific feature.
- **release branches**: Preparation for a new production release.
- **hotfix branches**: Emergency fixes for production issues.

## Workflow for Team Members

### Getting Started

1. Clone the repository:
   ```
   git clone <repository-url>
   git checkout develop
   ```

2. Create your personal branch from develop:
   ```
   git checkout -b <your-name>
   ```

### Daily Workflow

1. Before starting work each day, pull the latest changes from develop:
   ```
   git checkout develop
   git pull origin develop
   git checkout <your-branch>
   git merge develop
   ```

2. Work on your assigned tasks in your branch.

3. Commit changes regularly with descriptive messages:
   ```
   git add <files>
   git commit -m "Meaningful description of changes"
   ```

4. Push your changes to your remote branch:
   ```
   git push origin <your-branch>
   ```

5. When a feature is complete, create a pull request to merge into develop.

### Working with Notebooks

1. Store all notebooks in the designated `notebooks/` folder.
2. Name your notebook descriptively: `notebooks/<your-name>_<purpose>.ipynb`
3. Remember to clear output cells before committing (to avoid merge conflicts).

## Best Practices

- **Commit Often**: Small, focused commits are easier to review and troubleshoot.
- **Pull Regularly**: Sync with develop frequently to minimize merge conflicts.
- **Descriptive Commit Messages**: Begin with a verb and describe what the change accomplishes.
- **Review Before Pushing**: Check your changes before pushing to the remote repository.
- **Document Your Code**: Add comments and documentation to make your code understandable.

## Handling Merge Conflicts

If you encounter merge conflicts:

1. Identify the conflicting files:
   ```
   git status
   ```

2. Open each file and resolve the conflicts (look for the `<<<<<<<`, `=======`, and `>>>>>>>` markers).

3. After resolving, mark as resolved:
   ```
   git add <resolved-files>
   ```

4. Complete the merge:
   ```
   git commit
   ```

## Additional Resources

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Flow Guide](https://guides.github.com/introduction/flow/)
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)