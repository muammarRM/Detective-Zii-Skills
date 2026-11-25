# Rule: Anti-Dummy & Clean Repository Hygiene (Anti-Leak)

Enforce strict repository hygiene before running any `git add`, `git commit`, or `git push`.

## 1. Strictly Prohibited from Git Remotes
Never stage, commit, or push the following categories to GitHub/GitLab/remote repositories:
- **AI Prompts, Specs, Plans & Local Agent Configs:** `GEMINI.md`, `CLAUDE.md`, `.agents/`, `.agent/`, `docs/superpowers/`, `.superpowers/`, `docs/specs/`, `docs/plans/`, `*design.md`, `*plan.md`, `*.prompt`, prompt dumps, AI transcripts.
- **Compiled Binaries & Build Artifacts:** `*.exe`, `build/`, `dist/`, `*.spec` (unless explicitly tracked as an official release asset).
- **Archives & Compressed Bundles:** `*.zip`, `*.tar.gz`, `*.rar`, `*.7z` (unless explicitly tracked as an essential release binary).
- **Temporary & Scratch Scripts:** `fix.*`, `update_*.*`, `test_*.*` (outside `tests/`), `temp.*`, `*.tmp`, `*.bak`, `middle.txt`, `scratch/`.
- **Dump & Extracted Data:** `extracted.json`, `dump.sql`, `test_output.*`, debug log dumps.
- **Local-Only Docs & Assets:** Internal reports or debug screenshots (e.g., `docs/INTERNAL_*.docx`, `docs/assets/`).

## 2. Mandatory Pre-Commit & Pre-Push Audit
1. **Audit Staged Files:** Run `git status` and `git diff --cached --name-only` before committing.
2. **Untrack Prohibited Files Immediately:** If any prohibited file is staged or tracked, run `git rm --cached <file>`.
3. **Verify `.gitignore`:** Ensure all prohibited patterns are explicitly excluded in `.gitignore`.
4. **Immediate Cleanup:** Delete temporary scratch or debug files once testing completes.
