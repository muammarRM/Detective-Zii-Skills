---
name: orang-awam
description: Evaluates and designs UI, UX, forms, workflows, and user-facing messages from the perspective of an ordinary, non-technical, fatigued user (extreme user empathy). Eliminates technical jargon and unnecessary friction. Triggers on UI/UX and copywriting tasks, via "/orang-awam" or "/user-biasa", or when asked to simplify UX for everyday users.
license: MIT
metadata:
  author: muammarRM
  version: "1.0.0"
---

# Orang-Awam: Extreme User Empathy & Anti-Jargon Lens

## Overview
**`orang-awam`** (literally *"everyday non-technical person"*) enforces radical user empathy. It forces engineers and AI agents to stop looking at software through database schemas and HTTP codes, and instead experience it through **real humans trying to finish a task quickly**.

> *"Developers think in database columns and HTTP status codes; users just want to finish their work without deciphering alien jargon."*

### Core Principles
1. **Real-World Persona:** Assume the user is a **tired office clerk or everyday consumer at 4 PM on a Friday, using an average laptop or phone on mediocre Wi-Fi**.
2. **Zero Technical Jargon:** Never expose raw technical terminology in UI labels or user error messages (`500 Internal Error`, `NullPointerException`, `SQL Integrity`, `Invalid Payload`, `CSRF Token`).
3. **Cut Input Friction:** Never ask users to manually type anything the system can infer, pre-fill, or filter automatically.
4. **Calm Reassurance (Feedback Loop):** Never leave users guessing whether the app is working, succeeded, or failed. Always give clear, calm visual feedback.

---

## Tri-Trigger Activation

1. **Automatic:** Runs whenever designing UI components, form flows, notifications, empty states, or error messages.
2. **Slash Command:** Invoked directly via `/orang-awam` or `/user-biasa`.
3. **Natural Language:** Triggered when asked to *"check from a user's perspective"*, *"make it beginner-friendly"*, or *"remove technical jargon"*.

---

## The 4 Empathy Lenses

```text
                       [UI Screen / Message / User Flow]
                                       │
         ┌─────────────────────────────┼─────────────────────────────┐
         ▼                             ▼                             ▼
 [1. Anti-Jargon Lens]        [2. Form Friction Lens]       [3. Action Clarity Lens]
 "Would a non-technical       "Why ask for 8 fields         "After clicking Save,
  parent understand this?"     when 2 are enough?"           does the user know it's working?"
         │                             │                             │
         └─────────────────────────────┼─────────────────────────────┘
                                       │
                                       ▼
                       [4. Humane Recovery Lens]
                       "If it fails, does the user know
                        the exact next step to fix it?"
                                       │
                                       ▼
                       ┌───────────────────────────────┐
                       │  CALM, HUMAN-FRIENDLY UX      │
                       │  & ZERO-CONFUSION INTERFACE   │
                       └───────────────────────────────┘
```

### 1. Human Language Lens (Anti-Jargon Filter)
- **Reject:** *"Error: Uncaught TypeError: Cannot read property of undefined."*
- **Replace with:** *"Something went wrong while loading your report. Please refresh the page in a few seconds."*
- **Reject:** *"422 Unprocessable Entity - Field `national_id` invalid format."*
- **Replace with:** *"Your ID number must be 16 digits. Please double-check and try again."*

### 2. Friction & Smart-Default Lens
- Cascade dependent selectors automatically (e.g., selecting a state/city automatically filters available districts).
- Never force manual `YYYY-MM-DD` typing when a native date picker or smart default ("Today") works.
- Never place destructive buttons (like *Delete All*) right next to primary actions (like *Save*) in a similar color.

### 3. Action Clarity Lens (Visual Reassurance)
- Clicking any action button must give immediate feedback (e.g., button text switches to *"Saving..."* and disables temporarily to prevent confusion or double submission).
- Blank white screens without loading indicators cause users to panic and think the app crashed.

### 4. Humane Recovery Lens (Actionable Guidance)
- Never stop at *"Save failed"*. Explain **why** and **what to do next**:
  *"Couldn't save because your internet connection dropped. Check your Wi-Fi and click Try Again."*

---

## Output Format: Ordinary-User Empathy Audit

```markdown
### 👥 Everyday User Empathy Audit (Orang-Awam)
- **Confusion Check:** [Is any step unclear for a non-technical user?]
- **Jargon Removed:**
  - ❌ *Before:* `[Stiff technical message or label]`
  - ✅ *After:* `[Warm, plain-language phrasing]`

### 🖱️ Friction & Reassurance Improvements
- [Simplified input/click steps]
- [Visual loading/success/error states added so users never panic]

### 💡 User-Readiness Summary
[1-2 sentences confirming the flow feels calm and intuitive for anyone]
```
