---
name: anti-dummy-leak
description: >-
  Strict git hygiene and pre-commit audit to prevent AI prompt files, agent specs,
  design plans, dummy data, temporary scripts, scratch files, executables, and archives
  from being committed or pushed to remote repositories like GitHub.
---

# Anti-Dummy, Anti-Prompt & Repository Hygiene Skill

This skill provides an automated audit, enforcement protocol, and git hook setup to guarantee that no prompt instructions, agent specs/plans, dummy data, temporary scratch scripts, or local binaries are ever pushed to GitHub or any remote repository.

## When to Use
- **Mandatory**: Automatically before ANY `git commit` or `git push`.
- Whenever temporary files, migration fix scripts, test dumps, or scratch files are created during development.
- When configuring or reviewing `.gitignore`.
- When an agent/superpowers skill creates specs or plans in `docs/` or `.superpowers/`.

## Prohibited Files Checklist
Before running `git commit` or `git push`, verify that NONE of the following are in `git status` or tracked by git:

1. **AI Prompts, Specs, Plans & Agent Configuration**:
   - `docs/superpowers/`, `.superpowers/`, `docs/specs/`, `docs/plans/`
   - `*design.md`, `*plan.md`, `*.prompt`, `*.agent`, prompt dumps
   - `GEMINI.md`, `CLAUDE.md`, `.agents/`, `.agent/`, agent transcripts
2. **Compiled Binaries & Build Artifacts**:
   - `*.exe`, `build/`, `dist/`, `*.spec` (unless explicitly requested as an essential release asset)
3. **Archives & Compressed Files**:
   - `*.zip`, `*.tar.gz`, `*.rar`, `*.7z`
4. **Temporary & Scratch Scripts**:
   - `fix.*`, `update_*.*`, `test_*.*` (outside `tests/`), `temp.*`, `*.tmp`, `*.bak`, `middle.txt`, `scratch/`
5. **Dump & Extracted Data Files**:
   - `extracted.json`, `dump.sql`, `test_output.*`, debug log dumps
6. **Local Documentation & Reports**:
   - Project documentation marked for local use only (`docs/DOKUMENTASI_*.docx`, `docs/assets/`)

## Verification Protocol

1. **Audit Staged & Tracked Files**:
   ```powershell
   git status --short
   git diff --cached --name-only
   ```
2. **Scan for Prohibited Files in Git Index**:
   ```powershell
   git ls-files | Select-String -Pattern "docs/superpowers", "GEMINI", "CLAUDE", "\.tmp", "\.exe$", "dump\.", "extracted\.", "\.bak$", "\.spec$"
   ```
3. **If a Prohibited File is Staged or Tracked**:
   - Untrack it immediately:
     ```powershell
     git rm --cached -r <file-or-dir>
     ```
   - If it's a temporary garbage file on disk:
     ```powershell
     git rm -f <file>
     Remove-Item -Force <file>
     ```
4. **Verify .gitignore Coverage**:
   Ensure `.gitignore` contains the standard exclusion block:
   ```gitignore
   # AI Prompts, Agent Specs, Plans, Superpowers, and Transcripts
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

   # Packaging & Binaries
   build/
   dist/
   *.exe
   *.spec

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
5. **Install Pre-Push Protection Hook**:
   Create a hook at `.git/hooks/pre-push` that blocks pushes containing prohibited files.
