---
name: writing-guidelines
description: |
  Review docs/prose for Writing Guidelines compliance. Use when asked to "review my docs", "check writing style", "audit prose", "review docs voice and tone", or "check this page against the writing handbook".
triggers:
  - "review my docs"
  - "check writing style"
  - "audit prose"
  - "review docs voice and tone"
  - "writing handbook"
  - "文档审查"
metadata:
  author: vercel
  version: "1.0.0"
  argument-hint: <file-or-pattern>
od:
  mode: prototype
  surface: web
  platform: desktop
  category: documentation
  upstream: "https://github.com/vercel-labs/writing-guidelines"
  source-commit: 83e2316b034cf572400513538e4e4da01c4cc742
  preview:
    type: markdown
  example_prompt: |
    Review my documentation files for compliance with the Vercel Writing Guidelines — check voice, tone, formatting, and structure.
---

# Writing Guidelines

Review files for compliance with Writing Guidelines.

## How It Works

1. **Try** to fetch the latest guidelines from the source URL below
2. **If the fetch fails** (offline, air-gapped, or unsupported runtime), fall back to the pinned local copy at [`references/guidelines.md`](references/guidelines.md)
3. Read the specified files (or prompt user for files/pattern)
4. Check against all rules in the guidelines
5. Output findings in the terse `file:line` format

## Guidelines Source

**Primary (live):** Fetch fresh guidelines before each review from:

```
https://raw.githubusercontent.com/vercel-labs/writing-guidelines/main/command.md
```

**Fallback (pinned):** If the fetch fails, use the local copy at [`references/guidelines.md`](references/guidelines.md) instead. The pinned copy is a snapshot of the upstream guidelines and may be slightly stale, but guarantees the skill works in any runtime environment.

## Usage

When a user provides a file or pattern argument:
1. Try to fetch guidelines from the source URL above; if that fails, load [`references/guidelines.md`](references/guidelines.md)
2. Read the specified files
3. Apply all rules from the guidelines
4. Output findings using the format specified in the guidelines

If no files specified, ask the user which files to review.
