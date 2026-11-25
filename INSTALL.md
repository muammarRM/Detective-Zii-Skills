# 🚀 Installation Guide (`Detective-Zii-Skills`)

Choose the installation method that matches your AI coding agent setup.

---

## Option 1: Install via `skills` CLI (Recommended)

```bash
npx skills add muammarRM/Detective-Zii-Skills
```

To install specific skills only:

```bash
npx skills add muammarRM/Detective-Zii-Skills --skill be-detective hakim anti-overengineering
```

---

## Option 2: Manual Global Install (Antigravity)

Make all skills and optional automatic triggers available across every project:

### 1. Copy `skills/`
Copy **every folder inside `skills/`** into your global Antigravity skills directory:
- **Windows:** `C:\Users\<YOUR_USER>\.gemini\config\skills\`
- **macOS / Linux:** `~/.gemini/config/skills/`

### 2. Copy `rules/` (Optional, Enables Always-On Routing)
Copy the `.md` files inside `rules/` into:
- **Windows:** `C:\Users\<YOUR_USER>\.gemini\config\rules\`
- **macOS / Linux:** `~/.gemini/config/rules/`

> [!TIP]
> Prefer invoking skills manually instead of automatically on every prompt? **Skip step 2** for `auto_context_skill_router.md` and `overthinking_and_manipulator.md`—you can still trigger any skill on demand by name or slash command.

---

## Option 3: Project-Local Install (Antigravity / Claude Code / Codex / Cursor)

1. Copy the desired folders from `skills/` into your project root:
   - `.agents/skills/` (Antigravity / Codex convention)
   - `.claude/skills/` (Claude Code convention)
2. To enable automatic routing only inside that project, append the contents of `rules/` to your project's `GEMINI.md` or `CLAUDE.md` (and keep personal rules ignored in `.gitignore` if collaborating on a team repo).
