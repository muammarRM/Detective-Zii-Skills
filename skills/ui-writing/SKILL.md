---
name: ui-writing
description: Professional UI Writing, UX Microcopy, and Human-Centric Interface Messaging standards. Use when writing copy for UI components, buttons, error messages, empty states, modals, onboarding, labels, and microcopy to ensure clarity, high conversion, and zero AI-slop.
---

# UI Writing & UX Microcopy Discipline

This skill governs the writing, tone of voice, terminology, and microcopy for digital interfaces. Great UI writing makes products intuitive, reduces cognitive friction, and builds user trust.

---

## 1. The Four Core Pillars of UI Writing

1. **Clear (Jelas & Lugas)**:
   * No technical jargon, no ambiguous words.
   * A 12-year-old or an elderly person should understand what will happen before clicking.
   * *Anti-pattern:* "Eksekusi parameter kompresi algoritmik."
   * *UI Writing standard:* "Kecilkan ukuran file foto."

2. **Concise (Ringkas & Efisien)**:
   * Every word must pull its weight. Cut filler words ("silakan", "mohon untuk", "anda dapat").
   * *Anti-pattern:* "Silakan klik tombol di bawah ini untuk memulai proses pengunduhan semua file foto yang telah berhasil dikonversi."
   * *UI Writing standard:* "Unduh Semua (.ZIP)"

3. **Useful (Bermanfaat & Aplikatif)**:
   * Provide the right information at the exact moment of decision.
   * If a user must choose a setting (e.g. Target KB), give real-world context: *"200 KB (Rekomendasi CPNS & KTP)"*.

4. **Human (Hangat, Empatis, Tanpa AI Slop)**:
   * Sound like a helpful, competent human assistant.
   * Zero fake hype or buzzwords (*"revolusioner"*, *"kekuatan AI tingkat dewa"*, *"all-in-one powerhouse"*).
   * Honest, calm, and respectful of the user's attention.

---

## 2. Component Microcopy Standards

### A. Buttons & CTAs (Call to Action)
* **Formula:** `[Active Verb]` + `[Specific Noun]`
* ✅ **Good:** "Pilih Foto", "Mulai Kompres", "Unduh Semua (.ZIP)", "Salin Link", "Buka Penawaran"
* ❌ **Bad:** "Klik Sini", "Submit", "Proses", "OK", "Lanjut", "Go"
* **Destructive Actions:** Use clear cautionary verbs: "Hapus Semua Foto" (red/muted), not "Batal" or "Clear".

### B. Input Fields & Placeholders
* **Labels:** Always present, clear, and positioned above or left of the input.
* **Placeholders:** Show an example of valid input, NOT the label repeated.
  * ✅ Label: `Link Instagram atau Video` | Placeholder: `https://instagram.com/p/...`
  * ❌ Label: `Link` | Placeholder: `Ketik link di sini`
* **Helper Text:** Kept under 10 words, placed directly below input.

### C. Error Messages & Recovery
Never blame the user or display raw system codes. Follow the **3-Part Error Rule**:
1. What happened? (Simple explanation)
2. Why did it happen? (Brief cause)
3. How to fix it? (Clear recovery step)
* ✅ *"File tidak dapat dibaca. Format ini belum didukung. Coba unggah file JPG, PNG, WebP, atau HEIC."*
* ❌ *"Error 422: Unprocessable Entity. Upload failed."*

### D. Empty States & Drag-and-Drop Zones
* State the primary benefit and the immediate physical action.
* Include a primary button fallback for users who don't drag and drop (especially on mobile/tablets).
* ✅ *"Tarik foto ke sini atau klik untuk memilih file dari galeri / komputer."*
* Include supported formats and size limits upfront: *"Mendukung JPG, PNG, WebP, HEIC hingga 50 MB per file."*

### E. Feedback, Progress & Success States
* Show real metrics, not vague animations:
  * ✅ *"Mengompres 3 dari 5 foto (60%)... Foto 1: 1.8 MB → 185 KB (-89%)"*
  * ❌ *"Memproses gambar..."*
* After completion, celebrate utility, not arrogance:
  * ✅ *"Selesai! 5 foto berhasil dikompres. Total hemat 4.2 MB (82%)."*

---

## 3. Localization & Tone (Bahasa Indonesia)
When writing UI in Indonesian:
* Use standard, natural Indonesian (baku namun santai dan modern).
* Avoid excessive English loanwords if natural Indonesian equivalents are well-understood:
  * Use *Unduh* (not *Download*), or *Unduh Foto*.
  * Use *Unggah* (not *Upload*).
  * Use *Pratinjau* (not *Preview*).
  * Use *Ukuran Asli* (not *Original Size*).
  * If a technical term is universally recognized (e.g. *JPG, WebP, GIF, .ZIP, URL*), keep the technical format name.

---

## 4. Pre-Ship UI Writing Checklist
Before finalizing any UI screen, verify:
- [ ] Are all button labels action-oriented (`Verb` + `Noun`)?
- [ ] Are error messages actionable with recovery advice?
- [ ] Are technical jargon, AI hype buzzwords, and marketing filler removed?
- [ ] Is helper text giving real-world context (e.g. CPNS 200 KB)?
- [ ] Are file sizes, metrics, and units (`KB`, `MB`, `px`) clearly visible?
- [ ] Is cognitive load minimized so the user never hesitates on what to do next?
