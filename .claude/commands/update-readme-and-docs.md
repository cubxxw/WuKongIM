---
name: update-readme-and-docs
description: Workflow command scaffold for update-readme-and-docs in WuKongIM.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /update-readme-and-docs

Use this workflow when working on **update-readme-and-docs** in `WuKongIM`.

## Goal

Update project documentation, especially README files and related images or diagrams.

## Common Files

- `README.md`
- `README_CN.md`
- `README_EN.md`
- `docs/*.png`
- `docs/*.gif`
- `docs/*.pdf`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit README.md and/or README_CN.md and/or README_EN.md
- Optionally update/add images or diagrams in docs/
- Commit changes with a docs/update message

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.