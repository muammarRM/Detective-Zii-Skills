---
name: human-uiux-design
description: Human-centric, calm UI/UX design discipline for web applications and consumer utilities. Eliminates AI slop patterns (badge proliferation, sparkle spam, icon-tile cards, robotic copy, and cookie-cutter feature grids) in favor of focused, high-utility interfaces inspired by top human-crafted tools.
license: MIT
metadata:
  author: muammarRM
  version: "1.0.0"
---

# Human-Centric UI/UX Design & Anti-AI-Slop Skill

This skill enforces human-first product design principles for web applications, consumer utilities, and developer tools. It actively audits and strips away the visual hallmarks of generic AI-generated interfaces ("AI slop") in favor of calm, confident, and intuitive software.

---

## 1. The Core AI Slop Checklist (What to Eliminate)

When reviewing or building UI, immediately flag and remove these recurring generator patterns:

1. **Badge Proliferation ("Badge Diet"):**
   * *The Tell:* Floating pill badges (`rounded-full px-2 py-0.5 bg-blue-500/10`) slapped onto every headline, card, section, and button (e.g., "Presets", "Studio", "Pro Plan", "Fast", "Sponsor").
   * *The Fix:* **Strict Badge Diet.** A screen should have 0—or at most 1—badge reserved strictly for essential real-time state (e.g., "Offline", "Error", "Beta"). Rely on clean typographic hierarchy instead of wrapping labels in pills.

2. **Sparkle / Magic Wand Overuse:**
   * *The Tell:* Sparkles (`✨`, `<Sparkles />`, `<Wand2 />`) sprinkled across logos, headers, submit buttons, and cards as hollow decoration.
   * *The Fix:* Use purposeful, direct functional icons (`<ArrowRight />`, `<Download />`, `<Upload />`, `<Settings />`). If an icon does not aid comprehension, delete it.

3. **The Cookie-Cutter Feature Grid:**
   * *The Tell:* Symmetrical 3-column or 4-column card grids with `icon-in-colored-square + bold title + 2-line generic blurb` (e.g., `01. AI Engine, 02. Smart Crop, 03. Watermark, 04. Multiplatform`).
   * *The Fix:* Put the working tool front and center. Utility visitors come to finish a job, not read a marketing brochure. Keep secondary info in clean expandable FAQs or subtle contextual help.

4. **Robotic "Happy Talk" & Hype Slogans:**
   * *The Tell:* Inflated marketing prose ("Unlock unlimited creative power...", "Universal all-in-one studio...", "Next-gen revolutionary browser engine...").
   * *The Fix:* Speak like a calm, competent engineer talking to a real user:
     * *Bad:* "Revolutionary instant all-in-one graphic conversion studio without limits."
     * *Good:* "Compress or convert photos directly in your browser."

5. **Dashed-Box Placeholders with Developer Notes:**
   * *The Tell:* Giant dashed borders displaying setup instructions (*"Ad Slot: Set NEXT_PUBLIC_ADSENSE_CLIENT_ID..."*). Real users interpret this as a broken or unfinished site.
   * *The Fix:* Use quiet neutral placeholder surfaces with minimal editorial labels ("Sponsor") or clean whitespace that avoids Cumulative Layout Shift (CLS).

6. **Over-Nested Dark Cards with Monotonous Borders:**
   * *The Tell:* Card inside card inside card with identical `#1e293b` borders and low-contrast slate text.
   * *The Fix:* Establish crisp surface separation through subtle tonal elevation (e.g., `#0f172a` canvas with clean `#1e293b` elevated panels) rather than nested bordered boxes.

---

## 2. Principles of Friendly Consumer Utilities (e.g., Squoosh, TinyPNG, Linear)

### A. Dropzone-First, Zero-Friction Hierarchy
* Within **200 milliseconds** of opening the page, the primary action must be unmistakable.
* Provide an inviting upload zone with a high-contrast primary button (e.g., **"Choose Photos"** / **"Select File"**) and a clear drag-and-drop cue.
* Once files are loaded, smoothly transition prominence to the editing workspace or file queue.

### B. Purposeful, Tangible Controls
* Replace opaque technical parameters with practical controls:
  * "Target Size" (e.g., `200 KB`) with direct numeric input and real-world presets (`100 KB`, `200 KB`).
  * "Output Format" as clean segmented buttons (`JPG`, `PNG`, `WebP`, `PDF`).
  * "Preset Dimensions" with practical real-world labels (`Passport 2x2`, `ID Card`, `35x45mm`).

### C. Visual Feedback & Tactile Clarity
* Immediate thumbnail previews of selected files.
* Before/After metrics: display original size -> output size with a calm green reduction indicator (e.g., `2.4 MB -> 180 KB (-92%)`).
* One-click download for single files, plus a clear **"Download All (.ZIP)"** action for batches.

### D. Calm & Trustworthy Aesthetics
* Palette: Clean neutral slate/charcoal base, sharp typography, and a single confident primary accent (e.g., Royal Blue `#2563eb` or Indigo `#4f46e5`).
* Generous touch targets (minimum `44x44px` on mobile) and natural breathing room.

---

## 3. Step-by-Step Refactoring Workflow

When auditing or refactoring an existing interface:
1. **Audit & Cut Badges:** Count every pill/chip element and remove at least 80% of decorative ones.
2. **De-AI the Copy:** Rewrite headings, buttons, and helper copy in plain, grounded language.
3. **Streamline Above the Fold:** Make the core tool immediately usable without scrolling past promotional fluff.
4. **Polish Peripheral Containers:** Keep sponsor/footer/status containers subtle and free of developer debug text.
5. **Verify Mobile Flow:** Inspect tap targets, button wrapping, and vertical scroll at `375px–414px` viewport widths.
