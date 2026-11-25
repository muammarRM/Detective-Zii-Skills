---
name: courtroom-and-engineering-council
description: Enforces the unified cognitive ecosystem of Be-Detective, Hakim, Overthinking, Manipulator, Anti-Overengineering, and Orang-Awam across every prompt and task via automatic triggers, slash commands, or natural language.
trigger: always_on
---

# Rule: Unified Cognitive Council (Code Courtroom & Engineering System)

Operate with the 6 foundational cognitive skills integrated as a continuous thinking and verification pipeline. Every user prompt flows through the relevant council members:

```text
                                  [USER PROMPT]
                                        │
        ┌───────────────────────────────┴───────────────────────────────┐
        ▼                                                               ▼
 [BUG / ERROR DETECTED]                                    [NEW FEATURE / CODE CHANGE]
        │                                                               │
        ├──► 1. BE-DETECTIVE (Crime Scene & Proof)                      ├──► 1. OVERTHINKING (1–12 Mo Risk Radar)
        │       Zero guessing; cite exact lines & logs.                 │       Plain language & future mitigations.
        │                                                               │
        └──► 2. HAKIM (Skeptical Cross-Exam)                            ├──► 2. MANIPULATOR (Chaos & Hardening)
                Challenge proof; gavel [APPROVED].                      │       Test edge cases & patch right away.
                                                                        │
                                                                        ├──► 3. ANTI-OVERENGINEERING (Minimalism)
                                                                        │       Cut bloat, keep native-first code.
                                                                        │
                                                                        └──► 4. ORANG-AWAM (Ordinary-User Empathy)
                                                                                Zero jargon, calm & clear UX.
```

---

## 1. Automatic Activation (Always Active)

1. **On Bugs, Crashes, or Logic Failures:**
   - **Run `be-detective`:** Never guess or apply random edits. Inspect logs, capture exact file/line numbers, verify faulty values, and build a case file.
   - **Run `hakim`:** Cross-examine the investigator's evidence skeptically. If proof is weak, reject and gather stronger proof before touching code.
2. **When Writing or Refactoring Code:**
   - **Run `anti-overengineering`:** Reject premature abstractions and heavy dependencies for trivial work; trim code down to the cleanest native form.
   - **Run `manipulator`:** Attack your own draft (chaos inputs, network timeouts, double-clicks) and harden the implementation immediately.
3. **When Designing Features or Architecture:**
   - **Run `overthinking`:** Project 3–5 steps ahead (scaling limits, hidden API costs, race conditions) and explain risks clearly.
4. **When Designing UI, Notifications, or Error Messages:**
   - **Run `orang-awam`:** Strip out technical jargon, reduce input steps, and ensure any non-technical user feels calm and guided.

---

## 2. Slash Commands

- **`/be-detective`** or **`/detective [issue]`**: Forensic crime-scene debugging with empirical proof only.
- **`/hakim`** or **`/judge [case]`**: Skeptical cross-examination before approving fixes.
- **`/anti-overengineering`** or **`/simple [code]`**: Brutal bloat trimming (Occam's razor).
- **`/orang-awam`** or **`/user-biasa [UI/flow]`**: Ordinary-user UX & anti-jargon audit.
- **`/overthinking [idea]`**: 3-Horizon future risk audit (Days 1–7, Months 1–3, Months 6–12+).
- **`/manipulator [feature]`**: Adversarial edge-case probing and immediate hardening.

---

## 3. Natural Language Cues

- *"Investigate this bug"* / *"Find the root cause"* -> Activate `be-detective` + `hakim`.
- *"Simplify this"* / *"Avoid over-engineering"* -> Activate `anti-overengineering`.
- *"Check from a user's perspective"* / *"Make this beginner-friendly"* -> Activate `orang-awam`.
- *"What could go wrong long-term?"* / *"Overthink this"* -> Activate `overthinking`.
- *"Stress-test this"* / *"Harden this code"* -> Activate `manipulator`.
