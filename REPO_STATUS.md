# REPO_STATUS: claude-code (a fork of ultraworkers/claw-code)

Last reviewed 10/12 by Alex, an AI agent.

## Summary
A local clone of the open-source "Claw Code" project (ultraworkers/claw-code, a Rust `claw` CLI agent harness with a Python/TypeScript reference tree), plus some untracked local additions. Not the company's own product; no original company commits identified.

## Status
**Archive candidate** — third-party fork, last commit 2026-04-06 matches upstream, and `origin` points at a GitHub repo that does not exist under that name.

## Stack
Rust workspace in `rust/` (canonical), Python tree in `src/`, some TypeScript in `src/`, Bun `package.json` (untracked), Containerfile, GitHub Actions (`release.yml`, `rust-ci.yml`).

## Last activity
Last commit 2026-04-06 09:38 +0000 `Use Anthropic count tokens for preflight`. 90 days: 0. Last year: 577 (upstream history). Current branch: `main`. GitHub: `tony-42069/claw-code` is a public fork (default branch `main`, pushed 2026-04-06).

## What works
- Upstream is a published project (README describes the public Rust `claw` CLI). Local `main` equals `upstream/main` (0/0) as of the last local fetch.
- CI configs and tests come from upstream. Not built or run by me.

## What's broken or unfinished
- `origin` = `https://github.com/tony-42069/claude-code.git`. `gh repo view tony-42069/claude-code` returns "Could not resolve to a Repository" and `git ls-remote origin` returns "Repository not found". The GitHub fork is `tony-42069/claw-code`, so it was renamed and the old URL does not redirect (or it was deleted and re-forked). Local `origin` is stale.
- Untracked: `package.json` (name `my-claude-code-fork`, dated 2026-03-31), `bun.lock`, `tsconfig.json`, `src/tools/` (one `TungstenTool` file) and `src/types/connectorText.ts`. Local experiments, not part of upstream. The `package.json` depends on `@anthropic-ai/sdk` and `@anthropic-ai/sandbox-runtime`; provenance of that source tree is unclear, so do not publish or redistribute it without checking.

## Stuck areas
Nothing of ours is stuck; it is a reference clone.

## Next steps
1. Archive the folder (read-only reference), or delete the clone since upstream is public.
2. If keeping: `git remote set-url origin https://github.com/tony-42069/claw-code.git` and decide what to do with the untracked files.

## TODOs found
8 TODO/FIXME/HACK in tracked files (all upstream code, none company-owned); not listed.

## Security notes
Checked: tracked secret-type filenames (none), history of added secret-type files (none), filename-only content scan.
- The scan matched `README.md`, `USAGE.md`, `rust/README.md`, `src/bridge/workSecret.ts`, `src/commands/install-github-app/CheckExistingSecretStep.tsx`, `src/services/teamMemorySync/secretScanner.ts`, `src/services/teamMemorySync/teamMemSecretGuard.ts`. By name these are doc examples and secret-detector or handling code, not committed secrets; I did not open the lines.
- GitHub fork is public, but nothing local was pushed, so no company secrets are expected there.

## Revenue potential
None directly. Reference material for agent-harness ideas only.

## Local state
6 untracked paths (listed above), 0 modified tracked files. No stashes. One local branch (`main`), no unpushed commits (0/0 vs `upstream/main`). 36 remote-tracking branches from `upstream`. `origin` unreachable, so push state against it cannot be checked.
- **Verified against GitHub (2026-10-12):** The local origin URL (tony-42069/claude-code) is stale: that repo no longer exists. The same history lives in the fork tony-42069/claw-code (public, parent ultraworkers/claw-code); local `main` HEAD be561bf is a branch head there, so nothing committed is unpushed. Fix the origin with `git remote set-url origin https://github.com/tony-42069/claw-code.git` if you keep this clone. The 6 untracked paths stay local only. Alex checked this against a full mirror of the GitHub repo, which supersedes any earlier "not fetched / unknown / diverged" caveat in this file.
