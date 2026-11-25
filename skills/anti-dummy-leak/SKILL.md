---
name: anti-dummy-leak
description: Strict Git hygiene and pre-commit audit to prevent AI prompt files, agent specs, design plans, dummy data, temporary scratch scripts, debug dumps, compiled binaries, and archives from being committed or pushed to remote repositories like GitHub.
license: MIT
metadata:
  author: muammarRM
  version: "1.0.0"
---

# Anti-Dummy, Anti-Prompt & Repository Hygiene Skill

This skill enforces a pre-commit and pre-push audit protocol so AI instruction dumps, agent specs/plans, temporary scratch scripts, dummy dumps, local binaries, and distribution archives never leak into GitHub or team repositories.

## When to Use
- **Mandatory:** Automatically before any `git commit` or `git push`.
- Whenever temporary scripts, migration fixers, test dumps, or scratch files are created during development.
- When initializing or auditing `.gitignore`.
- When an agent workflow creates local specs or design docs in `docs/` or `.superpowers/`.

## Prohibited Files Checklist
Before committing or pushing, verify that **none** of the following appear in `git status` or `git ls-files`:

1. **AI Prompts, Specs, Plans & Agent Configs:**
   - `docs/superpowers/`, `.superpowers/`, `docs/specs/`, `docs/plans/`
   - `*design.md`, `*plan.md`, `*.prompt`, `*.agent`, prompt dumps, transcript logs
   - `GEMINI.md`, `CLAUDE.md`, `.agents/`, `.agent/` (unless the repository itself is explicitly an agent-config repo)
2. **Compiled Binaries & Build Artifacts:**
   - `*.exe`, `build/`, `dist/`, `*.spec` (unless intentionally tracked as release artifacts)
3. **Archives & Compressed Bundles:**
   - `*.zip`, `*.tar.gz`, `*.rar`, `*.7z`
4. **Temporary & Scratch Scripts:**
   - `fix.*`, `update_*.*`, `test_*.*` (outside proper `tests/`), `temp.*`, `*.tmp`, `*.bak`, `middle.txt`, `scratch/`
5. **Dump & Extracted Data Files:**
   - `extracted.json`, `dump.sql`, `test_output.*`, raw debug log dumps
6. **Local-Only Docs & Assets:**
   - Internal/local-only reports or temporary screenshots (e.g., `docs/INTERNAL_*.docx`, `docs/assets/` debug captures)

## Verification Protocol

1. **Audit Staged & Tracked Files:**
   ```bash
   git status --short
   git diff --cached --name-only
   ```
2. **Scan Git Index for Prohibited Patterns:**
   ```bash
   git ls-files | grep -E "docs/superpowers|GEMINI|CLAUDE|\.tmp$|\.exe$|dump\.|extracted\.|\.bak$|\.spec$|\.zip$"
   ```
3. **If a Prohibited File Is Staged or Tracked:**
   - Untrack immediately without deleting required local files:
     ```bash
     git rm --cached -r <file-or-dir>
     ```
   - Or remove temporary garbage files completely:
     ```bash
     git rm -f <file>
     rm -f <file>
     ```
4. **Verify `.gitignore` Coverage:**
   Ensure `.gitignore` contains the standard exclusion block:
   ```gitignore
   # AI Prompts, Agent Specs, Plans, and Local Agent Configs
   GEMINI.md
   CLAUDE.md
   .agents/
   .agent/
   .superpowers/
   docs/superpowers/
   *.spec.md
   *.plan.md
   *.prompt
   *.agent

   # Packaging, Archives & Binaries
   build/
   dist/
   *.exe
   *.spec
   *.zip
   *.tar.gz

   # Scratch & Temporary Testing Files
   temp.*
   *.tmp
   *.bak
   scratch/
   middle.txt
   extracted.json
   dump.*
   test_output.*
   ```
5. **Optional Pre-Push Hook Guardrail:**
   Configure `.git/hooks/pre-push` to reject pushes whenever prohibited patterns remain tracked in the branch.
