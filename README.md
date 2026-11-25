# 🕵️‍♂️ Detective Zii Skills (`Detective-Zii-Skills`)

A collection of **9 AI Agent Skills** + **3 Companion Rules** designed to turn AI coding assistants (Antigravity, Claude Code, Codex, Cursor, Gemini CLI) into a disciplined engineering team: **evidence-based forensic debugging** (zero guessing), **skeptical verification**, **minimalist Occam's-razor architecture**, **calm human-first UX**, and **strict Git leak prevention**.

Built around one core rule: **anti-overengineering**—clean, minimal, practical, and zero bloat.

---

## ⚡ Quick Install

```bash
npx skills add muammarRM/Detective-Zii-Skills
```

Or install manually per tool / globally — see **[INSTALL.md](INSTALL.md)**.

### 🛡️ Security-Scanned Marketplace & Pro Suite (Agensi)

Prefer 1-click MCP installs backed by an automated 8-point security scan, or looking for stack-specific **Pro skills** with runnable scripts, rubrics, and worked before/after examples?

- **Bundle — [Detective-Zii Pro Suite (`$23`, Save 30% / `$10` off `$33`)](https://www.agensi.io/r/MUAMMARRAMADHANI?to=/bundles/detective-zii-pro-suite&utm_source=github)** — All 3 Pro skills below in one bundle:
  - **[Forensic PR Reviewer (`$12`)](https://www.agensi.io/r/MUAMMARRAMADHANI?to=/skills/forensic-pr-reviewer&utm_source=github)** — File-grouped PR & diff reviews (`CRITICAL`/`WARNING`/`SUGGESTION`), read-only Bash/PowerShell diff collectors, OWASP/race checklists, and false-positive filtering.
  - **[Pre-Push Leak Guard (`$9`)](https://www.agensi.io/r/MUAMMARRAMADHANI?to=/skills/pre-push-leak-guard&utm_source=github)** — Read-only Python & PowerShell Git leak scanners plus stack-ready `.gitignore` presets catching `.env`, agent configs, dumps, and token assignments before push.
  - **[Anti-Slop Next.js Audit (`$12`)](https://www.agensi.io/r/MUAMMARRAMADHANI?to=/skills/anti-slop-nextjs-audit&utm_source=github)** — Zero-dependency Python UI scanner + React/Next.js/Tailwind refactoring rules stripping badge overload, sparkle spam, robotic hype copy, and accessibility gaps.
- **Free Verified Editions on Agensi:** [Be-Detective](https://www.agensi.io/r/MUAMMARRAMADHANI?to=/skills/be-detective&utm_source=github) · [Hakim](https://www.agensi.io/r/MUAMMARRAMADHANI?to=/skills/hakim&utm_source=github) · [Anti-Overengineering](https://www.agensi.io/r/MUAMMARRAMADHANI?to=/skills/anti-overengineering&utm_source=github) · [All Creator Skills](https://www.agensi.io/r/MUAMMARRAMADHANI?to=/creators/muammar-ramadhani-maulizidan&utm_source=github)

---

## 📦 Included Skills (9 Skills)

### 1. The Cognitive Council (6 Core Mindset & Verification Skills)
These six skills work together as a unified pipeline via **Tri-Trigger activation**: automatic context routing, `/slash` commands, and natural-language prompts.

| Skill | Role | Core Focus | Key Question |
| :--- | :--- | :--- | :--- |
| **[`be-detective`](skills/be-detective/SKILL.md)** | 🕵️‍♂️ **Forensic Investigator** | Crime-scene debugging & empirical proof (*zero guessing*) | *"Where are the exact line numbers, variable state, and stack trace?"* |
| **[`hakim`](skills/hakim/SKILL.md)** | ⚖️ **Supreme Judge** | Cross-examines evidence before approving any code change | *"Is this proof real beyond coincidence, and safe for the future?"* |
| **[`anti-overengineering`](skills/anti-overengineering/SKILL.md)** | 🪒 **Occam's Razor** | Cuts bloat, premature abstractions, and needless packages | *"Can 5 lines of native code solve this without new classes?"* |
| **[`orang-awam`](skills/orang-awam/SKILL.md)** | 👥 **User Empathy Lens** | Zero technical jargon, minimal form friction, calm UX | *"Can a tired non-technical user finish this at 4 PM Friday?"* |
| **[`overthinking`](skills/overthinking/SKILL.md)** | 🔮 **Future Risk Radar** | Forecasts 1–12+ month scaling, cost, and ops risks plainly | *"What breaks if this table grows 10x in six months?"* |
| **[`manipulator`](skills/manipulator/SKILL.md)** | 🛠️ **Adversarial Auditor** | Stress-tests chaos inputs, timeouts, and races, then patches | *"What happens if a user clicks Pay five times or Wi-Fi drops?"* |

### 2. Utility & Guardrail Skills (3 Standalone Skills)

| Skill | Core Focus |
| :--- | :--- |
| **[`anti-dummy-leak`](skills/anti-dummy-leak/SKILL.md)** | Pre-commit and pre-push Git audit blocking AI prompts, plans, scratch scripts, dumps, binaries, and `.zip` archives from leaking to remotes. |
| **[`human-uiux-design`](skills/human-uiux-design/SKILL.md)** | Calm, high-utility web & consumer tool design discipline that strips out *AI slop* (badge spam, decorative sparkles, generic 3-card grids). |
| **[`ui-writing`](skills/ui-writing/SKILL.md)** | Practical UX microcopy standards (`Verb + Noun` CTAs, 3-part humane error messages, concise helper text, and natural localization). |

---

## 🔄 How the Cognitive Council Works

```text
                                 [BUG REPORT / NEW FEATURE / PROMPT]
                                                  │
        ┌─────────────────────────────────────────┴─────────────────────────────────────────┐
        ▼                                                                                   ▼
 [PATH A: BUG OR ERROR DETECTED]                                               [PATH B: NEW FEATURE OR DESIGN]
        │                                                                                   │
        ▼                                                                                   ▼
┌───────────────────────────────┐                                               ┌───────────────────────────────┐
│     SKILL: BE-DETECTIVE       │                                               │      SKILL: OVERTHINKING      │
│   (Crime-Scene Forensics)     │                                               │   (1–12+ Month Risk Radar)    │
│ - Inspect stack trace & logs  │                                               │ - Spot future bottlenecks     │
│ - Test falsifiable hypotheses │                                               │ - Plain-language mitigations  │
│ - Require exact line numbers  │                                               └───────────────┬───────────────┘
└───────────────┬───────────────┘                                                               │
                │ Case File                                                                     ▼
                ▼                                                               ┌───────────────────────────────┐
┌───────────────────────────────┐                                               │      SKILL: MANIPULATOR       │
│         SKILL: HAKIM          │                                               │  (Skeptical Code Hardening)   │
│  (Skeptical Cross-Exam)       │                                               │ - Attack the first draft      │
│ - Edge-case stress test       │                                               │ - Test null, double-click, IO │
│ - Long-term safety check      │                                               │ - PATCH IMMEDIATELY           │
│ - Reject bloated fixes        │                                               └───────────────┬───────────────┘
│                               │                                                               │
│ [REJECTED] -> Gather proof    │                                                               │
│ [APPROVED] -> Proceed         │                                                               │
└───────────────┬───────────────┘                                                               │
                │                                                                               │
                └───────────────────────────────────────┬───────────────────────────────────────┘
                                                        │
                                                        ▼
                        ┌───────────────────────────────────────────────────────────────┐
                        │                    FINAL DUAL FILTER                          │
                        ├───────────────────────────────┬───────────────────────────────┤
                        │  SKILL: ANTI-OVERENGINEERING  │       SKILL: ORANG-AWAM       │
                        │  (Minimalist Occam's Razor)   │  (Ordinary-User Empathy Lens) │
                        │ - Remove needless abstractions│ - Strip all technical jargon  │
                        │ - Use native stdlib first     │ - Minimize form friction      │
                        │ - Keep diffs lean & readable  │ - Calm, clear status feedback │
                        └───────────────────────────────┴───────────────────────────────┘
                                                        │
                                                        ▼
                                     [LEAN, VERIFIED, HARDENED,
                                      & HUMAN-FRIENDLY OUTPUT]
```

---

## ⚡ Tri-Trigger Activation

1. **Automatic (using Companion Rules in `rules/`):**
   - **Bugs / Errors:** `be-detective` -> `hakim`
   - **Writing / Editing Code:** `anti-overengineering` + `manipulator`
   - **UI / Copy / Forms:** `orang-awam` + `human-uiux-design` + `ui-writing`
   - **System Design:** `overthinking`
2. **Slash Commands:**
   - `/be-detective` or `/detective [issue]`
   - `/hakim` or `/judge [case]`
   - `/anti-overengineering` or `/simple [code]`
   - `/orang-awam` or `/user-biasa [UI/flow]`
   - `/overthinking [idea]`
   - `/manipulator [feature]`
3. **Natural Language:**
   - *"Investigate this bug with evidence"*
   - *"Cross-examine this fix before applying"*
   - *"Simplify this and avoid over-engineering"*
   - *"Check this from a non-technical user's perspective"*
   - *"What could break 6 months from now?"*
   - *"Stress-test and harden this code"*

---

## 📂 Repository Structure

```text
Detective-Zii-Skills/
├── README.md
├── INSTALL.md
├── LICENSE
├── .gitignore
├── skills/
│   ├── anti-dummy-leak/SKILL.md
│   ├── anti-overengineering/
│   │   ├── SKILL.md
│   │   ├── README.md
│   │   └── examples/
│   ├── be-detective/
│   │   ├── SKILL.md
│   │   ├── README.md
│   │   └── examples/
│   ├── hakim/
│   │   ├── SKILL.md
│   │   ├── README.md
│   │   └── examples/
│   ├── human-uiux-design/SKILL.md
│   ├── manipulator/SKILL.md
│   ├── orang-awam/SKILL.md
│   ├── overthinking/SKILL.md
│   └── ui-writing/SKILL.md
└── rules/                              # Optional: enable always-on routing & commit guardrails
    ├── anti_dummy_leak.md
    ├── auto_context_skill_router.md
    └── overthinking_and_manipulator.md
```

| Component | Default Global Install Path |
| :--- | :--- |
| **All Skills (`skills/*`)** | `~/.gemini/config/skills/<skill-name>/SKILL.md` |
| **Companion Rules (`rules/*`)** | `~/.gemini/config/rules/<rule-name>.md` |
