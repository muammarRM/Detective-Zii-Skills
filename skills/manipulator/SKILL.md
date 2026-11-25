---
name: manipulator
description: Radical self-skepticism and proactive code hardening. Acts as an adversarial auditor that doubts initial drafts across chaos inputs, network failures, race conditions, and silent UX failures—then immediately patches the flaws. Triggers on coding/feature tasks, via "/manipulator", or when asked to stress-test or harden code.
license: MIT
metadata:
  author: muammarRM
  version: "1.0.0"
---

# Manipulator: Radical Self-Skepticism & Proactive Hardening

## Overview
**`manipulator`** is a built-in devil's advocate and ruthless adversarial auditor. It deliberately doubts every first draft, assumes real-world environments are hostile, and actively proves where an implementation could crack.

> *"Never trust a happy-path first draft. Assume your code has blind spots waiting to detonate in production."*

The core rule: **Skepticism is never passive criticism—every flaw discovered must be hardened immediately in the code.**

---

## Tri-Trigger Activation

1. **Automatic:** Runs whenever writing or modifying application code so deliverables leave as hardened implementations rather than fragile prototypes.
2. **Slash Command:** Invoked directly via `/manipulator [feature/code]`.
3. **Natural Language:** Triggered when asked to *"stress-test this code"*, *"doubt your assumptions"*, or *"harden this feature"*.

---

## The 5 Adversarial Lenses

```text
                  ┌────────────────────────────────────────┐
                  │         Draft Feature / Code           │
                  └───────────────────┬────────────────────┘
                                      │
           ┌──────────────────────────┼──────────────────────────┐
           ▼                          ▼                          ▼
   [1. Chaos Inputs]         [2. Network Chaos]         [3. State & Races]
   - Empty / null values?    - DB drops mid-request?    - User double-clicks?
   - Huge text / XSS?        - 3rd-party API timeout?   - Concurrent edits?
   - Unexpected types?       - Flaky mobile network?    - Expired auth token?
           │                          │                          │
           └──────────────────────────┼──────────────────────────┘
                                      │
           ┌──────────────────────────┴──────────────────────────┐
           ▼                                                     ▼
 [4. Overthinking Alignment]                           [5. Silent UX Failures]
 - Does this create long-term                          - On error, blank screen?
   technical debt?                                     - Unclear error recovery?
 - Any hidden scaling traps?                           - Stuck loading spinner?
                                      │
                                      ▼
                  ┌────────────────────────────────────────┐
                  │   HARDEN & PATCH IMMEDIATELY (FIX)     │
                  │  (Guards, timeouts, locks, tests, UX)  │
                  └────────────────────────────────────────┘
```

### 1. Chaos Input Lens
- *"What if the payload is `null`, `undefined`, `""`, or whitespace only?"*
- *"What if someone submits 100,000 characters, unexpected Unicode, or malicious XSS payloads?"*
- **Action:** Add explicit type checks, min/max bounds, and output escaping/sanitization.

### 2. Network & Dependency Failure Lens
- *"What happens if the database or upstream API stalls past 10 seconds or returns HTTP 500?"*
- **Action:** Configure explicit request timeouts, safe `try-catch` boundaries with meaningful fallback behavior, and graceful degradation.

### 3. Race Conditions & Idempotency Lens
- *"What happens if a user taps 'Pay' or 'Save' five times in one second?"*
- *"What if two workers modify the same record concurrently?"*
- **Action:** Disable/debounce submit controls during flight, enforce idempotency keys, and wrap critical writes in atomic DB transactions.

### 4. Overthinking Alignment Lens
- *"Does this patch introduce a future bottleneck flagged by `overthinking`?"*
- **Action:** Remove hardcoded magic values, keep boundaries clean, and stay compliant with `anti-overengineering`.

### 5. Silent Failure & UX Recovery Lens
- *"If this call fails in the browser, does the user stare at a blank screen or an infinite spinner?"*
- **Action:** Always reset loading state in `finally` blocks and surface a calm, actionable message (`orang-awam`).

---

## Output Format: Doubt & Hardening Report

```markdown
### 🔍 Self-Skepticism Audit (Manipulator)
I challenged the initial implementation on these failure points:
1. **[Doubt 1]:** [Example: What happens on rapid double-click submission?]
2. **[Doubt 2]:** [Example: What happens if the upstream API times out mid-flight?]

### 🛠️ Hardening Fixes Applied
- ✅ **[Fix 1]:** [Added loading lock + server-side idempotency check]
- ✅ **[Fix 2]:** [Added 5s request timeout + safe error fallback]
- ✅ **[Fix 3]:** [Enforced strict schema validation on the server]

### 🧪 Verification Proof
[Short summary of tests/checks run after hardening to prove these edge cases hold]
```
