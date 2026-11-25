### 🕵️‍♂️ Detective Case File (Forensic Investigation)
- **Case Status:** Evidence Confirmed
- **Crime Scene:** `src/services/cartTotal.ts:24`

#### 🔍 Hypotheses Tested
1. ❌ *Hypothesis A:* Discount percentage arrives as a string from the API -> *Status:* Refuted (`typeof coupon.percent === "number"` verified at `src/services/cartTotal.ts:18`).
2. ✅ *Hypothesis B:* `items.reduce(...)` divides by `items.length` when the cart is empty (`0`) -> *Status:* **Forensically Verified**.

#### 📌 Evidence Locker
- **Faulty Code (`src/services/cartTotal.ts:22-25`):**
  ```ts
  const subtotal = items.reduce((sum, item) => sum + item.priceCents, 0);
  const avgItemCents = subtotal / items.length;
  return { subtotal, avgItemCents };
  ```
- **Observed Error Data:** When `items = []`, `avgItemCents` evaluates to `NaN`, causing downstream `Math.round(avgItemCents)` to serialize as `null` in the JSON checkout payload.
- **Flow Reconstruction:** `POST /checkout (items: [])` -> `computeCartTotal([])` -> `0 / 0 = NaN` -> payment gateway rejects `amount: null`.

#### 🎯 Minimal Fix Recommendation (Anti-Overengineering)
Guard empty `items` at `src/services/cartTotal.ts:23` (`const avgItemCents = items.length ? subtotal / items.length : 0;`) and add a unit test for `items = []`.

*(Case file ready for cross-examination by SKILL: HAKIM)*
