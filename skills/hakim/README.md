# Hakim (`hakim`)

The Skeptical Supreme Judge skill for **Claude Code**, **Cursor**, **Codex CLI**, **Gemini CLI**, **OpenClaw**, and **Antigravity**.

Forces AI agents to cross-examine any proposed bug fix or architectural claim across three lenses—**edge-case skepticism**, **long-term impact**, and **minimalism**—before approving changes.

---

## Included Files

```text
hakim/
├── SKILL.md                  # 3-lens courtroom cross-examination & gavel verdict
├── README.md                 # Quick usage guide
└── examples/
    └── sample-verdict.md     # Example court verdict rejecting & refining a patch
```

## Quick Prompts

- *"Judge this proposed patch before I merge it."*
- *"Use `/hakim` to cross-examine the root-cause claim and check for hidden risks."*

---

Part of **[Detective-Zii-Skills](https://github.com/muammarRM/Detective-Zii-Skills)**. Pair with `be-detective` for full root-cause investigation, or check out **Forensic PR Reviewer** on Agensi for structured multi-file PR audits.
