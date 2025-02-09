# Truck-Based Development (TBD) Guide for New Developers

## Overview
Truck-Based Development (TBD) is a Git workflow designed to minimize the "truck factor" by ensuring that knowledge is distributed across the team. It promotes frequent collaboration, short-lived branches, and a single source of truth in the `main` branch.

## Key Principles
1. **Main is Always Deployable** – The `main` branch should always be in a deployable state.
2. **Frequent Commits & Merges** – Developers merge small, incremental changes regularly.
3. **Short-Lived Feature Branches** – Work in feature branches but merge them quickly.
4. **Code Reviews Required** – All merges go through pull requests (PRs) for review.
5. **Automated Testing & CI/CD** – Every commit triggers automated tests.
6. **Knowledge Sharing** – No single developer owns any part of the codebase.

## Workflow

### 1. Cloning the Repository
```sh
 git clone <repo-url>
 cd <repo-name>
```

### 2. Creating a Feature Branch
- Always branch from `main`.
```sh
 git checkout main
 git pull origin main
 git checkout -b feature/your-feature-name
```

### 3. Committing Changes
- Make small, focused commits with meaningful messages.
```sh
 git add .
 git commit -m "feat: short description of your change"
```

### 4. Pushing Changes
```sh
 git push origin feature/your-feature-name
```

### 5. Creating a Pull Request (PR)
- Open a PR against `main`.
- Request at least one reviewer.
- Ensure all CI/CD checks pass.

### 6. Merging the PR
- Use **Squash & Merge** to keep a clean history.
- Delete the feature branch after merging.

### 7. Syncing Your Local Branch
```sh
 git checkout main
 git pull origin main
```

## Handling Release Branches
- Release branches are created only for stabilization and hotfixes.
- Example: Creating a release branch for `v1.2`
```sh
 git checkout -b release/v1.2 main
 git push origin release/v1.2
```

- **Critical fixes** should be applied to `main` first, then cherry-picked to release branches.
```sh
 git checkout release/v1.2
 git cherry-pick <commit-hash>
 git push origin release/v1.2
```

## Best Practices
- **Avoid long-lived branches** – Merge frequently.
- **Write descriptive commit messages** – Helps track changes.
- **Always review code before merging** – Prevents errors and spreads knowledge.
- **Document key decisions** – Keep an internal wiki or markdown files updated.
- **Keep the `main` branch stable** – Feature development happens in branches.

## Getting Help
If you have questions, check the project README, internal documentation, or reach out to the team in Slack/Teams.

---
```md
# Truck-Based Development (TBD) Guide for New Developers

## Overview
Truck-Based Development (TBD) is a Git workflow designed to minimize the "truck factor" by ensuring that knowledge is distributed across the team. It promotes frequent collaboration, short-lived branches, and a single source of truth in the `main` branch.

## Key Principles
1. **Main is Always Deployable** – The `main` branch should always be in a deployable state.
2. **Frequent Commits & Merges** – Developers merge small, incremental changes regularly.
3. **Short-Lived Feature Branches** – Work in feature branches but merge them quickly.
4. **Code Reviews Required** – All merges go through pull requests (PRs) for review.
5. **Automated Testing & CI/CD** – Every commit triggers automated tests.
6. **Knowledge Sharing** – No single developer owns any part of the codebase.

## Workflow

### 1. Cloning the Repository
```sh
 git clone <repo-url>
 cd <repo-name>
```

### 2. Creating a Feature Branch
- Always branch from `main`.
```sh
 git checkout main
 git pull origin main
 git checkout -b feature/your-feature-name
```

### 3. Committing Changes
- Make small, focused commits with meaningful messages.
```sh
 git add .
 git commit -m "feat: short description of your change"
```

### 4. Pushing Changes
```sh
 git push origin feature/your-feature-name
```

### 5. Creating a Pull Request (PR)
- Open a PR against `main`.
- Request at least one reviewer.
- Ensure all CI/CD checks pass.

### 6. Merging the PR
- Use **Squash & Merge** to keep a clean history.
- Delete the feature branch after merging.

### 7. Syncing Your Local Branch
```sh
 git checkout main
 git pull origin main
```

## Handling Release Branches
- Release branches are created only for stabilization and hotfixes.
- Example: Creating a release branch for `v1.2`
```sh
 git checkout -b release/v1.2 main
 git push origin release/v1.2
```

- **Critical fixes** should be applied to `main` first, then cherry-picked to release branches.
```sh
 git checkout release/v1.2
 git cherry-pick <commit-hash>
 git push origin release/v1.2
```

## Best Practices
- **Avoid long-lived branches** – Merge frequently.
- **Write descriptive commit messages** – Helps track changes.
- **Always review code before merging** – Prevents errors and spreads knowledge.
- **Document key decisions** – Keep an internal wiki or markdown files updated.
- **Keep the `main` branch stable** – Feature development happens in branches.

## Getting Help
If you have questions, check the project README, internal documentation, or reach out to the team in Slack/Teams.
```

