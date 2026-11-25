# Be-Detective (`be-detective`)

Evidence-based forensic debugging skill for **Claude Code**, **Cursor**, **Codex CLI**, **Gemini CLI**, **OpenClaw**, and **Antigravity**.

Stops AI agents from guessing and rewriting working code blindly—every diagnosis must cite exact file paths, line numbers, runtime state, and a falsifiable hypothesis before a single line is edited.

---

## Included Files

```text
be-detective/
├── SKILL.md                    # Core 4-step forensic investigation protocol
├── README.md                   # Quick usage guide
└── examples/
    └── sample-case-file.md     # Example forensic case file output
```

## Quick Prompts

- *"Investigate why checkout throws 500 on empty cart—find exact line numbers before fixing."*
- *"Use `/be-detective` on this failing auth middleware."*

---

Part of **[Detective-Zii-Skills](https://github.com/muammarRM/Detective-Zii-Skills)**. Pair with `hakim` for skeptical pre-merge verification, or check out **Forensic PR Reviewer** on Agensi for full diff-level PR reviews with automated scripts and OWASP checklists.
