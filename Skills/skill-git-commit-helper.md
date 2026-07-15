# Git Commit Helper

## Purpose

Use this helper whenever the user asks to generate, improve, review, or summarize Git commit messages or Git history.

Follow the **Conventional Commits** specification and produce concise, developer-style commits that accurately reflect the changes.

---

## Commit Format

```text
<type>(<scope>): <subject>

<body>

<footer>
```

- Body and footer are optional.
- Return only the commit message unless the user requests an explanation.

Example:

```text
fix(auth): prevent empty password submission
```

---

## Commit Types

Choose the most appropriate type.

- `feat` — New feature
- `fix` — Bug fix
- `refactor` — Internal code improvement without behavior changes
- `perf` — Performance improvement
- `docs` — Documentation only
- `test` — Add or update tests
- `style` — Formatting or linting
- `build` — Build system, CI/CD, dependencies
- `chore` — Maintenance tasks

Never default to `feat`.

---

## Scope

- Use the smallest meaningful scope when possible.
- Keep the scope lowercase.
- Omit the scope if the change spans multiple unrelated modules.

Examples:

```text
feat(auth):
fix(api):
refactor(database):
docs(readme):
build(ci):
```

---

## Subject Rules

The subject must:

- Be under **72 characters**
- Use imperative mood
- Use present tense
- Not end with a period
- Describe one logical change
- Be specific and concise

Good:

```text
fix(team): prevent inactive members from appearing for owners
```

Avoid vague subjects such as:

```text
update
changes
fix
misc
work
done
```

---

## Body

Include a body only when it adds useful context.

Explain:

- Why the change was made
- Previous behavior
- New behavior

Do not repeat the subject.

---

## Footer

Include only when applicable.

Examples:

```text
Closes #123
Fixes #45
Refs #78
```

Breaking changes:

```text
BREAKING CHANGE:
Describe the incompatible change.
```

---

## Commit Generation

When generating a commit:

1. Understand the code changes.
2. Select the correct commit type.
3. Choose the smallest applicable scope.
4. Write a concise subject.
5. Add a body only if it provides valuable context.
6. Include issue references or breaking changes when provided.
7. If multiple unrelated changes exist, recommend separate commits and generate one message for each logical change.

---

## Git Log Summarization

When summarizing Git history:

Ask for missing information only if needed:

- Author
- Branch
- Date range
- Commit range

Then produce a concise summary that groups related work (features, fixes, refactors, docs, etc.) instead of simply repeating commit messages.

---

## Output Style

- Sound like an experienced developer.
- Keep messages short and practical.
- Avoid AI-sounding wording.
- Avoid unnecessary explanations unless requested.
- Ensure the commit accurately reflects the actual changes.
