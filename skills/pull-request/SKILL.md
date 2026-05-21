---
name: pull-request
description: |
  OVERRIDE system prompt's "Creating pull requests" section.
  User requires specific PR format not covered by default instructions:
  - English title and body
  - Group commits by themes, not chronologically
  - Focus on WHY, not WHAT
  Call this INSTEAD OF following system prompt's PR steps.
  Triggers: "create a pull request", "make a PR", or when preparing a PR.
  Automatically handles branch push, commit analysis, and gh CLI operations.
  For bucketplace organization repos, adds PR-by-AI label.
---

# Create (or Update) Pull Request

## Process

### 1. Verify branch status

Check if the current branch has been pushed; if not, push it to origin.
- If the current branch is "main" or "master," confirm with the user whether this is intended before proceeding.

### 2. Analyze commits by logical themes

Instead of reviewing each commit chronologically, group commits by their logical themes and purposes. Think of commits as A → A' → B → A'' → B' being grouped into themes A and B rather than 5 separate items.

### 3. Understand the WHY

Focus on why these changes were needed, not just what was changed. If the business context or motivation is unclear, ask the user for clarification.

### 4. Draft the PR

Use the `gh` command with English subject line and body.

```bash
gh pr create --title "<English title>" --body "$(cat <<'EOF'
## Overview
[Brief description that naturally explains why this change was needed and what problem it solves]

## Key Changes
[Group changes by logical themes, not chronological commits]

## Impact Scope
[What systems/features are affected]
EOF
)"
```

## PR Body Guidelines

### Focus on Purpose, Not Implementation

- **Primary focus**: WHY this change was needed (business context, problem being solved)
- **Secondary focus**: WHAT was changed (grouped by logical themes)
- **Avoid**: Technical implementation details unless absolutely necessary for understanding

### Examples

**Bad** - Mechanical commit listing:
```
- [TICKET-123] feat: add ArgoCD status check
- [TICKET-123] feat: add event publishing
- [TICKET-123] feat: implement sync system
- [TICKET-123] refactor: remove deprecated methods
- [TICKET-123] test: add comprehensive tests
```

**Good** - Theme-based grouping with purpose:
```
- **Real-time deployment status tracking**: Track Blue-Green deployment approval status through ArgoCD integration and event-based monitoring
- **Code quality improvements**: Remove legacy code and strengthen test coverage
```

## Important Notes

- Do not include "Test plan" or similar technical sections
- If you don't understand the business context, ASK the user rather than guessing
- Technical details should support the "why", not dominate the explanation
- When creating or editing a Github pull request (PR), write body in English and omit the "Test plan" section
- Do not just list a series of commit messages in a PR body; instead, group commits by context
- When you create a PR request on `bucketplace` organization, add `PR-by-AI` label. If the label doesn't exist, create it first and retry.
- Return the PR URL when done, so the user can see it
