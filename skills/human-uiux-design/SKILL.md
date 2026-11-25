---
name: human-uiux-design
description: >-
  Human-centric, friendly UI/UX design discipline for web applications and consumer utilities.
  Eliminates AI slop patterns (badge proliferation, sparkle spam, icon-tile cards, robotic copy,
  and cookie-cutter feature grids) in favor of calm, high-utility, intuitive interfaces inspired
  by top human-crafted tools (e.g. Squoosh, TinyPNG, Linear, Apple utilities).
---

# Human-Centric UI/UX Design & Anti-AI-Slop Skill

This skill enforces human-first product design principles for web applications, consumer utilities, and developer tools. It actively audits and removes the visual hallmarks of AI-generated interfaces ("AI slop") to create calm, confident, and intuitive software that real humans enjoy using.

---

## 1. The Core AI Slop Checklist (What to Eliminate)

When reviewing or building UI, immediately flag and remove these recurring AI-generator patterns:

1. **Badge Proliferation ("Badge Diet"):**
   * *The Tell:* Floating pill badges (`rounded-full px-2 py-0.5 bg-blue-500/10`) on every headline, card, section, and button (e.g. "Presets", "Studio", "Future Plan", "Quick", "Sponsor").
   * *The Fix:* **Strict Badge Diet.** A screen should have 0 or at most 1 badge reserved exclusively for essential real-time status (e.g., "Offline", "Error", "New"). Use clean typographic hierarchy instead of enclosing every label in a pill.

2. **Sparkle / Magic Wand Overuse:**
   * *The Tell:* Sparkles (`✨`, `<Sparkles />`, `<Wand2 />`) sprinkled on logos, headers, submit buttons, and cards as generic decoration.
   * *The Fix:* Use purposeful, direct functional icons (e.g. `<ArrowRight />`, `<Download />`, `<Upload />`, `<Settings />`). If an icon doesn't aid comprehension, remove it.

3. **The Cookie-Cutter Feature Grid:**
   * *The Tell:* Symmetrical 3-column or 4-column card grid with `icon-in-colored-square/circle + bold title + 2-line generic description` (e.g. `01. AI Tool, 02. Smart Crop, 03. Watermark, 04. Multiplatform`).
   * *The Fix:* Focus on the tool itself. Utility users come to accomplish a job, not read a promotional brochure. If information is needed, use clean expandable FAQs, contextual tooltips, or natural step flows.

4. **Robotic "Happy Talk" & Slogans:**
   * *The Tell:* Bombastic AI marketing prose ("Unlock unlimited power...", "Universal all-in-one studio...", "Selesaikan urusan tanpa batas...", "Prinsip Privasi Utama: Zero Server Storage").
   * *The Fix:* Write like a human product engineer speaking to a user:
     * *Bad:* "Platform revolusioner konversi grafis modern instan tanpa batas."
     * *Good:* "Kecilkan ukuran atau ubah format foto langsung di browser."

5. **Dashed Box Placeholders with Debug Copy:**
   * *The Tell:* Giant dashed borders with technical instructions ("Slot Iklan: Pasang NEXT_PUBLIC_ADSENSE_CLIENT_ID di Vercel..."). Real users see this as a broken, unfinished site.
   * *The Fix:* Clean, quiet placeholder surfaces with standard neutral backgrounds and minimal labels ("Sponsor") or clean whitespace that gracefully loads the ad script without layout shifts (CLS).

6. **Over-Nested Dark Cards with Monotonous Borders:**
   * *The Tell:* Card inside card inside card with identical `#1e293b` borders and faint slate text.
   * *The Fix:* Establish clear foreground/surface separation. Use subtle tonal shifts (e.g., `#0f172a` body with clean `#1e293b` elevated surfaces) rather than multiple nested bordered boxes.

---

## 2. Principles of Friendly Consumer Utilities (e.g. Squoosh, TinyPNG, CloudConvert)

Real-world consumer utility tools follow these five tenets:

### A. Dropzone-First, Zero-Friction Hierarchy
* When the user opens the page, the **primary action is obvious within 200 milliseconds**.
* Provide a prominent, inviting upload area with a high-contrast primary button (e.g., **"Pilih Foto"** / **"Pilih File"**) and a friendly drag-and-drop sub-caption.
* When files are selected, the dropzone smoothly yields prominence to the workspace or file queue.

### B. Purposeful, Tangible Controls
* Instead of confusing technical jargon, use intuitive labels:
  * "Target Ukuran" (e.g., 200 KB) with direct number input and simple presets (`100 KB`, `200 KB`).
  * "Format Hasil" with clean segmented buttons (JPG, PNG, WebP, PDF).
  * "Ukuran / Pas Foto" with clear practical labels (Pas Foto 3x4, 4x6, KTP).

### C. Visual Feedback & Tactile Delight
* Instant thumbnail previews of selected images.
* Before/After comparison: Show original size $\to$ new size with a quiet, satisfying green reduction badge (e.g. `2.4 MB → 180 KB (-92%)`).
* Direct one-click download for single files, plus a prominent "Unduh Semua (.ZIP)" when multiple files are processed.

### D. Calm & Trustworthy Aesthetics
* Palette: Clean slate/charcoal neutral base, crisp typography, and a single confident primary accent (e.g. Royal Blue `#2563eb` or Indigo `#4f46e5`).
* High readability: Clean font sizes, generous touch targets (minimum 44x44px for mobile fingers).
* Natural whitespace: Give content room to breathe; don't pack the screen with decorative boxes.

---

## 3. Step-by-Step Refactoring Workflow

When applying this skill to an existing web app:
1. **Audit & Delete Badges:** Count every `<span className="... rounded-full ...">` or chip. Remove at least 80% of them.
2. **De-AI the Copy:** Rewrite headings, descriptions, and labels in simple, natural, conversational Indonesian or English.
3. **Streamline Hero:** Ensure the primary tool/dropzone is above the fold or immediately reachable without scrolling through marketing fluff.
4. **Clean up Ad Containers:** Ensure ad banners are discreet, responsive, and look like professional editorial ad slots rather than technical wireframes.
5. **Verify Mobile Usability:** Test touch targets, button widths, and vertical flow on small viewport widths (375px–414px).
