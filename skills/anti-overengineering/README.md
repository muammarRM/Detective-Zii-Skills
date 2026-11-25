# Anti-Overengineering (`anti-overengineering`)

Occam's razor and code minimalism skill for **Claude Code**, **Cursor**, **Codex CLI**, **Gemini CLI**, **OpenClaw**, and **Antigravity**.

Stops AI agents from generating premature abstractions (`Repository` + `Factory` + `Interface` boilerplate for single CRUD endpoints) and heavy dependencies where concise native code works reliably.

---

## Included Files

```text
anti-overengineering/
├── SKILL.md                        # 4 simplicity lenses & native-first rules
├── README.md                       # Quick usage guide
└── examples/
    └── before-after-trim.md        # Concrete example flattening bloated layers
```

## Quick Prompts

- *"Simplify this module and remove premature abstractions."*
- *"Use `/simple` on this PR—can we do this with built-in stdlib?"*

---

Part of **[Detective-Zii-Skills](https://github.com/muammarRM/Detective-Zii-Skills)**. Check out **Forensic PR Reviewer** and **Anti-Slop Next.js Audit** on Agensi for automated diff-level & UI refactoring workflows.
