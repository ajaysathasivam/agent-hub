# Git Commit Helper

## Purpose

Use this helper whenever generating, improving, reviewing, or summarizing Git commit messages or Git history.

Follow the **Conventional Commits** specification while keeping commit messages concise, meaningful, and natural.

This helper should generate commit messages that sound like they were written by an experienced developer—not by AI.

### Goals

- Maintain a clean and consistent Git history
- Follow the Conventional Commits specification
- Improve code review readability
- Support semantic versioning
- Enable automatic changelog generation
- Produce concise, meaningful commit messages
- Summarize Git history into developer-friendly updates

---

# When to Use

Use this helper whenever the user asks to:

- Generate a commit message
- Improve or rewrite a commit message
- Recommend a commit message
- Explain Conventional Commits
- Summarize Git commits
- Summarize Git logs
- Review commit history
- Generate release notes from commits

---

# Conventional Commit Format

```text
<type>(<scope>): <subject>

<body>

<footer>
```

The **body** and **footer** are optional.

Example:

```text
feat(auth): add Google OAuth login

Allow users to authenticate using Google OAuth2.
Store user profile information after successful login.

Closes #142
```

---

# Subject Line Rules

The subject line is the most important part of the commit.

Requirements:

- Maximum **72 characters**
- Use **imperative mood**
- Use **present tense**
- Do **not** end with a period
- Keep commit type lowercase
- Keep scope lowercase
- Describe **one logical change**
- Be specific and concise

Good:

```text
fix(auth): prevent empty password submission
```

```text
feat(team): add crew invitation workflow
```

```text
refactor(database): simplify organization queries
```

Bad:

```text
Fixed login bug
```

```text
update
```

```text
changes
```

```text
misc work
```

---

# Commit Types

Always infer the most appropriate commit type.

Never default to `feat`.

| Type | Description |
|-------|-------------|
| feat | New functionality or user-facing feature |
| fix | Bug fix |
| refactor | Internal code improvements without behavior changes |
| perf | Performance improvements |
| docs | Documentation changes only |
| style | Formatting, whitespace, linting |
| test | Add or update tests |
| build | Build system, dependencies, CI/CD |
| chore | Maintenance tasks |

---

# Scope

Use the smallest meaningful scope whenever possible.

Examples:

```text
feat(auth):
fix(api):
refactor(database):
docs(readme):
test(user):
build(ci):
style(ui):
perf(search):
```

If multiple unrelated modules are affected, omit the scope.

Example:

```text
fix: resolve multiple validation issues
```

---

# Subject Writing Guidelines

Write the subject as if giving an instruction.

Use:

- add
- fix
- remove
- update
- rename
- prevent
- improve
- simplify
- support
- implement
- optimize
- replace
- extract
- migrate

Avoid:

- added
- fixed
- updated
- working on
- completed
- changes
- miscellaneous

---

# Body

The body is optional.

Include it only when it adds useful context.

Explain:

- Why the change was made
- Previous behavior
- New behavior
- Important implementation details

Do **not** simply repeat the subject.

Example:

```text
fix(upload): prevent duplicate submissions

Ignore repeated requests while a file upload is already in
progress. This prevents duplicate records when users click the
submit button multiple times.
```

---

# Footer

Use footers when appropriate.

Issue references:

```text
Closes #123
```

```text
Fixes #98
```

```text
Refs #52
```

Breaking changes:

```text
BREAKING CHANGE:
Authentication endpoints now require JWT tokens.
```

---

# AI Decision Process

When generating a commit message:

1. Understand what changed.
2. Identify the primary purpose of the change.
3. Select the correct commit type.
4. Choose the smallest meaningful scope.
5. Write a concise subject.
6. Keep the subject under 72 characters.
7. Add a body only if additional explanation is valuable.
8. Add a footer when issue references or breaking changes exist.
9. Ensure the commit represents one logical change.
10. Avoid vague or generic wording.

---

# Output Style

## Default Output

Return only the commit message.

Example:

```text
fix(team): prevent inactive members from appearing for team owners
```

---

## Detailed Output

When additional context is beneficial, include a body.

Example:

```text
fix(team): prevent inactive members from appearing for team owners

Update roster visibility logic so team owners can correctly view
their active members while preserving access restrictions for
other users.
```

---

# Multiple Changes

If the request contains multiple unrelated changes:

- Recommend splitting them into separate commits.
- Generate one commit message for each logical change.

Example:

```text
feat(auth): add password reset endpoint

fix(api): return validation errors for invalid email addresses

docs(readme): document password reset flow
```

---

# Git Log Summarization

When asked to summarize Git history:

If necessary, ask for:

- Author
- Branch
- Date range
- Commit range
- Whether merge commits should be ignored

Then produce a concise summary.

Focus on:

- Features
- Bug fixes
- Refactors
- Performance improvements
- Documentation
- Infrastructure

Do **not** simply repeat commit messages.

Group related work together.

Example:

```text
Summary (July 10–15)

Features
- Added Vessel Activity CRUD APIs
- Implemented Quick Notifications dropdown

Bug Fixes
- Fixed duplicate chat messages
- Corrected roster visibility logic

Refactoring
- Simplified organization repository
- Consolidated Prisma queries

Infrastructure
- Updated Prisma migrations
- Improved Docker configuration
```

---

# Release Impact

| Commit | Semantic Version |
|----------|-----------------|
| feat | Minor |
| fix | Patch |
| perf | Patch |
| BREAKING CHANGE | Major |

---

# Good Examples

```text
feat(auth): add password reset endpoint
```

```text
fix(api): return 404 for missing resources
```

```text
refactor(database): simplify query builder
```

```text
perf(search): optimize product indexing
```

```text
docs(readme): document Docker setup
```

```text
test(user): add registration integration tests
```

```text
build(ci): cache npm dependencies
```

```text
chore(deps): upgrade Prisma to v6
```

---

# Bad Examples

Avoid commit messages like:

```text
update
```

```text
changes
```

```text
fix
```

```text
misc
```

```text
work
```

```text
done
```

```text
new code
```

```text
testing
```

```text
bug fix
```

```text
final
```

---

# Best Practices

- One logical change per commit.
- Keep commits atomic.
- Make subjects easy to scan in `git log`.
- Use the body only when it adds value.
- Prefer clarity over clever wording.
- Write commit messages that explain intent, not implementation.
- Avoid AI-sounding phrases.
- Avoid unnecessary verbosity.
- Ensure the message accurately reflects the code changes.

---

# Summary

Every commit should answer:

1. **What changed?**
2. **Where did it change?**
3. **Why was it changed?** (when useful)

A good commit message should be understandable without reading the code and should read naturally as if written by an experienced developer.
