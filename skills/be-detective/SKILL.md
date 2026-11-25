---
name: be-detective
description: Forensic crime-scene investigator for bugs, crashes, failing tests, and logic anomalies that hunts empirical proof before proposing minimal fixes. Use when the user asks to debug an error, investigate a stack trace, find a root cause, or diagnose failing behavior. Do not use when the user asks to scaffold a brand-new feature or run a full multi-file PR review.
license: MIT
metadata:
  author: muammarRM
  version: "1.0.0"
---

# Be-Detective: Forensic Crime-Scene Investigator (Evidence-Based Debugging)

## Overview
**`be-detective`** is a rigorous forensic debugging protocol. It strictly prohibits trial-and-error ("guess & check") coding—changing lines randomly in hopes that a bug disappears.

> *"Do not touch a single line of code until you hold hard empirical evidence proving where, when, and why the failure occurred."*

### Core Principles
1. **Zero Guessing:** Hypotheses exist solely to guide evidence gathering, never as a direct excuse to edit code.
2. **Empirical Evidence Mandate:** Every bug claim must cite at least one concrete piece of proof:
   - Exact file path and line numbers.
   - Full error message or relevant stack trace snippet.
   - Observed anomalous variable/state values (`null`, `undefined`, `NaN`, malformed payload).
   - Failed database query log or unexpected API response.
3. **Source-to-Sink Reconstruction:** Trace data from the user input boundary (source), through controllers/services, to the exact crash point (sink).
4. **Anti-Overengineering Guardrail:** Keep both the investigation and the proposed fix surgical. Solve the verified root cause with the smallest possible change.
5. **Court-Ready Case File:** Package findings clearly so the `hakim` skill can cross-examine them before code changes ship.

---

## Tri-Trigger Activation

1. **Automatic:** Activates whenever errors, failing tests, exceptions, or unexpected behaviors appear.
2. **Slash Command:** Invoked directly via `/be-detective` or `/detective [issue]`.
3. **Natural Language:** Triggered when asked to *"investigate this bug"*, *"find the root cause"*, *"act like a detective"*, or *"debug with evidence"*.

---

## The 4 Investigative Steps

```text
                       [INCIDENT / BUG REPORT]
                                  │
                                  ▼
                  ┌───────────────────────────────┐
                  │ 1. EXAMINE THE CRIME SCENE    │
                  │ - Read stack traces & logs    │
                  │ - Note timestamps & context   │
                  └───────────────┬───────────────┘
                                  │
                                  ▼
                  ┌───────────────────────────────┐
                  │ 2. FORMULATE HYPOTHESIS       │
                  │ - "Function X likely receives │
                  │    null from input Y"         │
                  └───────────────┬───────────────┘
                                  │
                                  ▼
                  ┌───────────────────────────────┐
                  │ 3. HUNT EMPIRICAL EVIDENCE    │
                  │ - Inspect exact source files  │
                  │ - Verify exact line numbers   │
                  │ - Prove the data anomaly      │
                  └───────────────┬───────────────┘
                                  │
                                  ▼
                  ┌───────────────────────────────┐
                  │ 4. COMPILE CASE FILE          │
                  │ - Submit to SKILL: HAKIM      │
                  │   for cross-examination       │
                  └───────────────────────────────┘
```

### Step 1: Examine the Crime Scene
- Inspect recent logs (application logs, browser console errors, server logs, or terminal test output).
- Read the top application frames of the stack trace—never skip straight past the line where our own code calls into a library.

### Step 2: Formulate a Falsifiable Hypothesis
- State a concrete hypothesis that can be proven true or false:
  *Example:* *"Hypothesis A: Column `status_id` is `NULL` in the database because the request validator does not require it."*

### Step 3: Hunt Empirical Evidence
- Open the referenced file and inspect the exact lines.
- If Hypothesis A fails verification, **cross it out** and form Hypothesis B. Repeat until concrete evidence is caught red-handed.
- Do not modify application code before capturing that proof.

### Step 4: Compile the Case File for Cross-Examination
- Summarize the scene, tested hypotheses, exact code lines, and a minimal fix proposal (compliant with `anti-overengineering`).
- Hand off to `hakim` for final verification.

---

## Output Format: Forensic Case File

```markdown
### 🕵️‍♂️ Detective Case File (Forensic Investigation)
- **Case Status:** [Investigating / Evidence Confirmed / Solved]
- **Crime Scene:** `[path/to/file]:[line-number]`

#### 🔍 Hypotheses Tested
1. ❌ *Hypothesis A:* [Initial assumption] -> *Status:* Refuted (no supporting evidence).
2. ✅ *Hypothesis B:* [Confirmed cause] -> *Status:* **Forensically Verified**.

#### 📌 Evidence Locker
- **Faulty Code:**
  ```[language]
  [2-4 line snippet of the defective code]
  ```
- **Observed Error Data:** [Captured log, stack trace, or anomalous runtime state]
- **Flow Reconstruction:** `[Initial Input]` -> `[Processing]` -> `[Failure Point]`

#### 🎯 Minimal Fix Recommendation (Anti-Overengineering)
[1-2 sentence surgical fix targeting only the verified root cause without unnecessary structural churn]

*(Case file ready for cross-examination by SKILL: HAKIM)*
```
