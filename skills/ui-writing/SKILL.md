---
name: ui-writing
description: Professional UI writing, UX microcopy, and human-centric interface messaging standards. Use when crafting copy for buttons, inputs, error messages, empty states, modals, onboarding, and status feedback to ensure clarity, low cognitive load, and zero AI slop.
license: MIT
metadata:
  author: muammarRM
  version: "1.0.0"
---

# UI Writing & UX Microcopy Discipline

This skill governs tone of voice, terminology, and microcopy across digital interfaces. Great UI writing makes products effortless to scan, removes hesitation, and earns user trust.

---

## 1. The Four Core Pillars of UI Writing

1. **Clear (Plain & Unambiguous):**
   * Zero internal system jargon or vague wording.
   * A non-technical user should know exactly what happens before clicking.
   * *Anti-pattern:* "Execute algorithmic compression parameters."
   * *Standard:* "Shrink photo file size."

2. **Concise (Every Word Earns Its Spot):**
   * Cut filler phrasing (*"Please feel free to click the button below in order to begin downloading..."*).
   * *Standard:* "Download All (.ZIP)"

3. **Useful (Context at the Decision Point):**
   * Give practical guidance right where users make choices.
   * Example for Target KB: *"200 KB (Common upload limit for ID & visa portals)"*.

4. **Human (Warm, Calm, Zero AI Hype):**
   * Sound like a capable, helpful colleague.
   * Never use inflated buzzwords (*"revolutionary"*, *"AI powerhouse"*, *"infinite possibilities"*).

---

## 2. Component Microcopy Standards

### A. Buttons & CTAs
* **Formula:** `[Active Verb]` + `[Specific Noun]`
* ✅ **Good:** `"Choose Photos"`, `"Compress Images"`, `"Download All (.ZIP)"`, `"Copy Link"`
* ❌ **Bad:** `"Click Here"`, `"Submit"`, `"Process"`, `"OK"`, `"Go"`
* **Destructive Actions:** Name the consequence explicitly (`"Delete All Photos"`, `"Revoke Token"`), not vague labels like `"Clear"` or `"Cancel"`.

### B. Input Fields & Placeholders
* **Labels:** Always visible and positioned cleanly above or beside the field.
* **Placeholders:** Show a valid example format rather than repeating the label.
  * ✅ Label: `Video or Post URL` | Placeholder: `https://example.com/post/...`
  * ❌ Label: `URL` | Placeholder: `Enter URL here`
* **Helper Text:** Under 10 words, placed directly beneath the input.

### C. Error Messages & Recovery (The 3-Part Error Rule)
Never blame the user or dump raw HTTP/stack codes:
1. **What happened?** (Plain explanation)
2. **Why?** (Brief cause)
3. **How to fix it?** (Next concrete step)
* ✅ *"Couldn't read this file because the format isn't supported yet. Try uploading a JPG, PNG, WebP, or HEIC image."*
* ❌ *"Error 422: Unprocessable Entity. Upload failed."*

### D. Empty States & Dropzones
* State the immediate physical action and include a clickable button fallback for mobile/touch users.
* ✅ *"Drop photos here or click to choose files from your device."*
* List limits upfront: *"Supports JPG, PNG, WebP, and HEIC up to 50 MB per file."*

### E. Progress & Completion Feedback
* Show concrete metrics instead of vague filler:
  * ✅ *"Compressing 3 of 5 photos (60%)... Photo 1: 1.8 MB -> 185 KB (-89%)"*
  * ❌ *"Processing images..."*
* Celebrate real utility quietly:
  * ✅ *"Done! 5 photos compressed. Saved 4.2 MB total (82%)."*

---

## 3. Tone & Localization Adaptation

When adapting interfaces for non-English locales (or multilingual users):
* Use natural, everyday phrasing spoken by real people in that language rather than stiff word-for-word machine translations.
* Keep universally recognized technical formats intact (`JPG`, `WebP`, `PDF`, `.ZIP`, `URL`, `KB`, `MB`, `px`).
* Tailor helper examples to local real-world constraints (e.g., local passport sizes, regional form limits, or familiar units).

---

## 4. Pre-Ship UI Writing Checklist
Before finalizing any screen:
- [ ] Are all primary buttons action-specific (`Verb + Noun`)?
- [ ] Do error messages follow the 3-part rule (what, why, recovery step)?
- [ ] Are raw system codes, jargon, and marketing filler removed?
- [ ] Does helper text provide practical context where choices matter?
- [ ] Are units (`KB`, `MB`, `px`) and live metrics clearly formatted?
