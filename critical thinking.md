# Critical Thinking Project: Source Code Management for a Distributed Development Team

## 🔧 Task 1: Evaluate Different SCM Tools

### Centralized vs. Distributed Version Control

#### Centralized VCS (e.g., Subversion/SVN):
- Relies on a central server for all version control operations
- Requires constant internet access to make commits
- Simpler to manage for small teams
- Single point of failure

#### Distributed VCS (e.g., Git):
- Every developer has a full local copy of the repository
- Enables offline work and fast local commits
- Branching and merging are faster and more flexible
- Better suited for teams working remotely or across regions

### ✅ Recommendation:
Git is highly recommended due to its speed, flexibility, and ability to support distributed teams. It integrates well with collaboration platforms like GitHub and enables seamless CI/CD automation and secure workflows.

---

## 🌿 Task 2: Git Workflow for Team Collaboration

### Branching Strategy
- `main`: Production-ready code
- `dev`: Staging branch for integrating new features
- `feature/*`: Individual features
- `bugfix/*`: Bug fixes

### Workflow Steps
1. Create a new feature branch:
   ```bash
   git checkout -b feature/feature-name
   ```
2. Push changes to remote:
   ```bash
   git push origin feature/feature-name
   ```
3. Create a **Pull Request** to `dev`
4. Run tests and get approvals
5. Merge `dev` into `main` after final testing

### Best Practices
- Commit frequently with clear messages
- Use PR templates and code review guidelines
- Rebase regularly to minimize merge conflicts

---

## ⚙️ Task 3: Automate Code Quality and Deployment

### GitHub Actions CI Pipeline (`.github/workflows/ci.yml`)

```yaml
name: CI Pipeline

on:
  push:
    branches:
      - dev
      - feature/**
  pull_request:
    branches:
      - main

jobs:
  build-and-test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '18'

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test

      - name: Lint code
        run: npm run lint
```

This pipeline automatically runs tests and lints your code when a branch is pushed or a PR is opened to `main`.

---

## 🔐 Task 4: Enforce Git Security Best Practices

### SSH Key Setup
```bash
ssh-keygen -t ed25519 -C "ariyodamola3@gmail.com"
```
Add the public key to GitHub: `~/.ssh/id_ed25519.pub`

### Enforce Signed Commits
```bash
git config --global commit.gpgsign true
```

### Branch Protection Rules
- Protect `main` and `dev`
- Require pull request review before merging
- Require status checks (CI passing)
- Require signed commits

### Access Control
- Use GitHub Teams with role-based permissions
- Remove inactive users regularly
- Enable audit logging (GitHub Enterprise)

---

## 🔁 Task 5: Handle a Real-World Git Merge Conflict

### Merge Conflict Resolution
```bash
# Step 1: Checkout main and pull latest
git checkout main
git pull origin main

# Step 2: Merge the feature branch
git merge feature/conflict-fix

# Step 3: Resolve conflicts manually in the conflicting files

# Step 4: Add and commit
git add .
git commit -m "Resolved merge conflict between feature and main"

# Step 5: Push changes
git push origin main
```

### How to Prevent Merge Conflicts
- Rebase feature branches frequently:
  ```bash
  git checkout feature/my-feature
  git fetch origin
  git rebase origin/main
  ```
- Keep PRs small and focused
- Communicate early and often

---

## ✅ Project Outcome

By completing this project, the team will:

- Understand and implement Git for distributed teams
- Use workflows and automation for code quality and deployment
- Apply best practices for security and collaboration
- Gain confidence in handling real-world Git challenges

---

**Prepared by:**  
Damola Ariyo  
Senior DevOps Engineer  
