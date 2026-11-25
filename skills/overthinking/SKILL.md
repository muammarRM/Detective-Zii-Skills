---
name: overthinking
description: Anticipates hidden risks, projects 1–12+ month consequences, and translates complex technical threats into plain-language risk management and actionable mitigations. Triggers automatically on feature and architecture tasks, via "/overthinking", or when asked to evaluate future risks or edge cases.
license: MIT
metadata:
  author: muammarRM
  version: "1.0.0"
---

# Overthinking: Anticipatory Risk & Future Radar

## Overview
**`overthinking`** turns constructive overthinking into **Proactive Risk Intelligence**—not analysis paralysis, but always looking 3–5 steps ahead to spot hidden traps before they explode in production.

### Core Principles
1. **Think Across Time Horizons:** Don't only evaluate whether code works today; project what happens in 1 week, 3 months, and 12+ months.
2. **Plain, Calm Communication:** Translate complex failure modes into clear, approachable analogies that non-specialists can grasp immediately.
3. **Actionable Mitigations Only:** Every risk raised must include both a **quick safe guard today** and a **long-term scaling path**.

---

## Tri-Trigger Activation

1. **Automatic:** Activates when designing architecture, API endpoints, database schemas, or new product flows.
2. **Slash Command:** Invoked directly via `/overthinking [idea/feature]`.
3. **Natural Language:** Triggered when asked *"overthink this feature"*, *"what could go wrong later?"*, or *"check long-term risks"*.

---

## The 3-Horizon Risk Radar

```text
[Proposed Feature / Architecture]
              │
              ├──> Horizon 1: Days 1–7 (Immediate Bugs & Edge Cases)
              │    Weird inputs, accidental clicks, missing validation, unhandled errors.
              │
              ├──> Horizon 2: Months 1–3 (Scale & Operations)
              │    Table growth slowing queries, race conditions, rising API costs, dirty data.
              │
              └──> Horizon 3: Months 6–12+ (Tech Debt & Long-Term Durability)
                   Rigid coupling, vendor lock-in, painful refactors, privacy/compliance gaps.
```

---

## Output Format: Plain-Language Risk Briefing

```markdown
### 🔮 Future Radar (Overthinking Check)
[2-3 clear sentences explaining what happens if this design runs in production for 6–12 months]

### ⚠️ Key Risks Detected
1. **[Risk 1]:** [Why this hurts users or operations, explained with a simple real-world analogy]
2. **[Risk 2]:** [An unexpected failure mode that is easy to overlook early on]

### 🛡️ Risk Management & Mitigations
- **Quick Guard Today:** [Low-effort safeguard applied immediately in the current implementation]
- **Long-Term Path:** [Clean architectural step once volume or usage grows]

### 💡 Balanced Next Step
[Practical recommendation balancing shipping speed and long-term safety]
```

---

## Common Risk Categorization Matrix

| Risk Category | Classic Oversight | Plain-Language Impact | Concrete Mitigation |
| :--- | :--- | :--- | :--- |
| **Data Loss & Human Error** | Bulk delete button without secondary confirmation. | *"One accidental click could wipe out years of customer records in a second."* | Use **Soft Delete** + typed confirmation for destructive bulk actions. |
| **Security & Abuse** | Public form with zero rate limiting or server sanitization. | *"A bot could flood this form with 1,000 spam rows a minute and crash the database."* | Add IP/user rate limiting, bot protection, and strict server validation. |
| **Performance Bottleneck** | Unpaginated `SELECT *` queries while test tables only have 10 rows. | *"It feels instant with 10 records, but at 50,000 rows the page will spin until users give up."* | Enforce pagination and explicit column projection from day one. |
| **Concurrency / Race Condition** | Two users claiming the last stock item in the same millisecond. | *"During a flash sale, two buyers can check out the same last item, causing negative inventory."* | Use atomic updates or database transaction locks. |
| **Hidden Financial Cost** | Uncached paid third-party/AI API calls on every page reload. | *"Every browser refresh hits a paid API. A traffic spike could quietly burn through your billing card."* | Add response caching and per-user/hourly rate caps. |
