---
name: auto-context-skill-router
description: Automatically routes and triggers the best-matching global skills based on task context whenever a user prompts, reports a bug, designs a feature, or asks to activate skills without needing to memorize skill names.
trigger: always_on
---

# Rule: Context-Aware Smart Skill Router

This rule removes the burden of memorizing dozens or thousands of skill names. The agent automatically detects the user's intent and activates the right combination of skills on every prompt.

---

## 1. Automatic Triggers

Active on **every user prompt**, especially when:
- **Bug / Error / Logic Failure Detected:** Activate **`be-detective`** (crime-scene investigation & empirical proof) -> **`hakim`** (skeptical cross-examination).
- **Writing / Refactoring Code:** Activate **`anti-overengineering`** (strip bloat & premature abstractions) + **`manipulator`** (stress-test & harden edge cases).
- **UI/UX Design & User Messaging:** Activate **`orang-awam`** (everyday user empathy, zero jargon, lower friction) alongside **`human-uiux-design`** and **`ui-writing`**.
- **New Feature / Architecture Design:** Activate **`overthinking`** (1–12+ month future risk radar).
- **Natural Language Cues:** Prompts such as *"use detective mode"*, *"investigate this"*, *"simplify this"*, *"check from a user's perspective"*, *"stress-test this"*, etc.

---

## 2. Context-to-Skill Routing Map

1. **Bug Investigation & Debugging (Zero Guessing):**
   - *Primary Skills:* `be-detective`, `hakim`
   - *Action:* Capture real runtime evidence (logs, line numbers, variable state) via `be-detective`, then cross-examine in `hakim` before editing code. **Never guess.**

2. **Code Minimalism & Anti-Bloat:**
   - *Primary Skills:* `anti-overengineering`
   - *Action:* Eliminate unnecessary layers, prefer native language/framework features, and reject premature abstractions (Occam's razor).

3. **Human-Centered UI/UX & Copy:**
   - *Primary Skills:* `orang-awam`, `human-uiux-design`, `ui-writing`
   - *Action:* Audit through the eyes of a tired non-technical user. Remove technical jargon, cut form friction, and provide calm recovery messages.

4. **Adversarial Hardening:**
   - *Primary Skills:* `manipulator`
   - *Action:* Challenge your own first draft against chaos inputs, network timeouts, and double-clicks, then patch vulnerabilities immediately.

5. **Long-Horizon Risk Radar:**
   - *Primary Skills:* `overthinking`
   - *Action:* Forecast 1–12 month scaling, operational, and cost risks in plain, approachable language with concrete mitigations.

6. **Repository & Commit Hygiene:**
   - *Primary Skills:* `anti-dummy-leak`
   - *Action:* Audit `git status` and `git diff --cached` before any commit or push to block local prompts, scratch scripts, dumps, and archives.

---

## 3. Response Header Format

Whenever skills activate automatically, open with a brief callout indicating which skills are active, then execute immediately:

> [!TIP]
> 🎯 **Active Skills**: `[skill-1]` + `[skill-2]`  
> *Context*: [One-sentence explanation of why these skills are working together for this request]
