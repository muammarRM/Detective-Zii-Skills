---
name: anti-overengineering
description: Enforces strict code and architecture simplicity, eliminates bloat and premature abstractions, and applies Occam's razor (native-first and YAGNI). Triggers on coding, design, and refactoring tasks, via "/anti-overengineering" or "/simple", or when asked to simplify or remove unnecessary complexity.
license: MIT
metadata:
  author: muammarRM
  version: "1.0.0"
---

# Anti-Overengineering: Occam's Razor & Code Minimalist

## Overview
**`anti-overengineering`** is an emergency brake against unnecessary complexity in code and architecture. It ensures every solution stays **as simple as safely possible, low in line count, free of premature abstractions, and easy to maintain**.

> *"The best code is code you never had to write. The cleanest solution solves the real problem with the fewest moving parts."*

### Core Principles
1. **Native-First Rule:** If the language standard library or existing framework already solves it, use that. Do not invent custom wrappers or helper classes.
2. **Ban Premature Abstractions:** Do not introduce a Repository Pattern, Service Layer, Interface hierarchy, or Factory for a single straightforward CRUD flow.
3. **Ban Heavy Dependencies for Trivial Tasks:** Never pull in a large third-party package when 5 lines of standard PHP, JavaScript, or Python do the job reliably.
4. **Ban Over-Configuration:** Never build a complex dynamic config engine for values that rarely change.

---

## Tri-Trigger Activation

1. **Automatic:** Runs during coding, refactoring, or system design to strip bloat before presenting solutions.
2. **Slash Command:** Invoked directly via `/anti-overengineering` or `/simple`.
3. **Natural Language:** Triggered when asked to *"simplify this"*, *"avoid over-engineering"*, *"keep it minimal"*, or *"cut the bloat"*.

---

## The 4 Simplicity Lenses

```text
                     [Draft Code / Architecture Proposal]
                                      │
         ┌────────────────────────────┼────────────────────────────┐
         ▼                            ▼                            ▼
  [1. YAGNI Lens]           [2. Native Platform]        [3. Layer Flattening]
  "Do we genuinely          "Does built-in stdlib       "Why use 3 classes
   need this today?"         already do this?"           when 1 function works?"
         │                            │                            │
         └────────────────────────────┼────────────────────────────┘
                                      │
                                      ▼
                       [4. Maintenance Burden Lens]
                       "Will someone easily understand
                        this 6 months from now?"
                                      │
                                      ▼
                        ┌───────────────────────────┐
                        │   LEAN & CLEAN CODEBASE   │
                        │  (Minimal lines, 0 bloat) │
                        └───────────────────────────┘
```

### 1. YAGNI Lens (You Aren't Gonna Need It)
- Reject hypothetical scope creep: *"What if we need multi-tenant / multi-database / microservices later?"* -> **Build for today's verified requirements.**
- If asked to build feature A, ship feature A cleanly—do not sneak in unrequested features A.1, A.2, and A.3.

### 2. Native Platform Lens
- **Backend/Frameworks:** Use built-in string helpers, validators, and query builders instead of bespoke utility traits.
- **Frontend/Browser:** Prefer native `<dialog>`, `<input type="date">`, or concise CSS Grid/Flexbox over 200-line custom modal libraries.
- **Scripts/CLI:** Reach for standard library modules (`pathlib`, `zipfile`, `json`) before installing external packages.

### 3. Layer Flattening Lens
- If a controller or handler calling the model/query directly is clean, safe, and readable, **do not force DTO + Service + Action + Repository boilerplate**.
- Extract a shared abstraction **only after genuine duplication appears 3+ times** (Rule of Three).

### 4. Maintenance Burden Lens
- Every extra line of code is a future liability (potential bug surface and cognitive load).
- Deleting 50 lines while preserving identical correctness and safety is a major win.

*(Note: Minimalism never cuts corners on input validation, security boundaries, data-loss protection, or accessibility.)*

---

## Output Format: Simplicity & Anti-Bloat Review

```markdown
### 🪒 Anti-Overengineering Audit (Simplicity Check)
- **Complexity Status:** [Lean / Trimmed From Bloated Draft]
- **Abstractions Rejected or Removed:**
  - ❌ [Example: Skipped creating 3 single-use interface classes]
  - ❌ [Example: Replaced external package with 4 lines of native stdlib]

### ✂️ Trimming Summary (Before vs. After)
- **Before:** [Original layer count or bloat description]
- **After:** [Direct, readable, minimal implementation]

### 💡 Maintainability Gain
[1-2 sentences explaining why the simpler version reduces bugs and speeds up future edits]
```
