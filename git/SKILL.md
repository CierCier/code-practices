---
name: git
description: Prepare, inspect, commit, branch, merge, rebase, or publish code changes. Use to preserve user work, keep changes reviewable, and avoid unsafe history operations.
---

# Git

- Inspect branch and worktree state before editing or staging. Treat pre-existing changes as user-owned; do not reset, overwrite, or stage unrelated files.
- Keep each change focused and reviewable. Separate unrelated work; make commits buildable when practical.
- Stage explicit task files, not the whole worktree by habit. Inspect the staged diff and confirm it contains no secrets, generated junk, or unrelated changes.
- Write commit messages that describe the behavior change and its reason. Use a user-supplied message exactly.
- Fetch and compare against the correct base before updating a branch. Rebase or merge deliberately and resolve conflicts from both sides.
- Never rewrite shared history, force-push, delete branches, or push without explicit authorization. Confirm the exact target when an operation could overwrite remote work.
- Keep lockfiles and generated artifacts consistent with project policy. Do not commit local caches or build output.
- After publishing, verify the remote branch/head and local worktree state.

A clean diff is part of correctness. Do not report a commit, push, or clean state unless the corresponding state was observed.