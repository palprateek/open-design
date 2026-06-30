---
name: web-design-guidelines
description: |
  Review UI code for Web Interface Guidelines compliance by the Vercel engineering team. Covers layout, typography, color, motion, and accessibility for product UI.
triggers:
  - "web design guidelines"
  - "vercel design"
  - "product ui standards"
  - "design checklist"
  - "review my UI"
  - "check accessibility"
  - "audit design"
  - "review UX"
  - "设计审查"
metadata:
  author: vercel
  version: "1.0.0"
  argument-hint: <file-or-pattern>
od:
  mode: design-system
  surface: web
  platform: desktop
  category: design-systems
  upstream: "https://github.com/vercel-labs/web-interface-guidelines"
  source-commit: 4e799d45c17aec1498c269287a83b9dba22b966b
  preview:
    type: markdown
  example_prompt: |
    Review my UI code against the Vercel Web Interface Guidelines — check layout, typography, color, motion, and accessibility compliance.
---

# Web Interface Guidelines

Review files for compliance with Web Interface Guidelines.

## How It Works

1. **Try** to fetch the latest guidelines from the source URL below
2. **If the fetch fails** (offline, air-gapped, or unsupported runtime), fall back to the pinned local copy at [`references/guidelines.md`](references/guidelines.md)
3. Read the specified files (or prompt user for files/pattern)
4. Check against all rules in the guidelines
5. Output findings in the terse `file:line` format

## Guidelines Source

**Primary (live):** Fetch fresh guidelines before each review from:

```
https://raw.githubusercontent.com/vercel-labs/web-interface-guidelines/main/command.md
```

**Fallback (pinned):** If the fetch fails, use the local copy at [`references/guidelines.md`](references/guidelines.md) instead. The pinned copy is a snapshot of the upstream guidelines and may be slightly stale, but guarantees the skill works in any runtime environment.

## Usage

When a user provides a file or pattern argument:
1. Try to fetch guidelines from the source URL above; if that fails, load [`references/guidelines.md`](references/guidelines.md)
2. Read the specified files
3. Apply all rules from the guidelines
4. Output findings using the format specified in the guidelines

If no files specified, ask the user which files to review.
