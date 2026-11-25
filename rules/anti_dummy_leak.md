---
name: anti-dummy-leak
description: Strict pre-commit and pre-push policy to prevent dummy files, temp scripts, AI prompt instructions, and archives from being committed or pushed to remote repositories.
trigger: always_on
---

# Rule: Anti-Dummy & Clean Repository Hygiene (Anti-Leak)

You MUST enforce strict repository hygiene before performing any git staging, commit, or push operations.

## 1. Strictly Prohibited from Git Remote
The following categories MUST NEVER be staged, committed, or pushed to any remote repository (GitHub/GitLab/etc.):
- **AI Prompt, Specs, Plans & Agent Configuration Files**: `GEMINI.md`, `CLAUDE.md`, `.agents/`, `.agent/`, `docs/superpowers/`, `.superpowers/`, `docs/specs/`, `docs/plans/`, `*design.md`, `*plan.md`, `*.prompt`, prompt dumps, AI system instructions, agent transcripts.
- **Compiled Binaries & Build Artifacts**: `*.exe`, `build/`, `dist/`, `*.spec` (unless explicitly requested as an essential project release asset).
- **Archive & Compressed Files**: `*.zip`, `*.tar.gz`, `*.rar`, `*.7z` (unless explicitly requested as an essential project binary asset).
- **Temporary & Scratch Scripts**: `fix.php`, `update_*.php`, `test_*.php`, `temp.*`, `*.tmp`, `*.bak`, `middle.txt`, `scratch/`.
- **Dump & Extracted Data Files**: `extracted.json`, `dump.sql`, `test_output.*`, debug log dumps.
- **Local Documentation & Reports**: Project documentation marked for local use only (e.g., `docs/DOKUMENTASI_*.docx`, `docs/assets/`).

## 2. Mandatory Pre-Commit & Pre-Push Audit
Before executing `git commit` or `git push`:
1. **Audit Staged Files**: Run `git status` or `git diff --cached --name-only` to review every single file queued for commit.
2. **Untrack Local Files Immediately**: If any prohibited file is staged or tracked, untrack it immediately (`git rm --cached <file>` or `git rm <file>`).
3. **Verify .gitignore**: Ensure the prohibited pattern is explicitly defined in `.gitignore` so git will never track it again.
4. **Immediate Cleanup**: Any scratch or debug file generated during a task MUST be deleted immediately once testing or processing is complete.
