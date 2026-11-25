# 🚀 Panduan Pasang (`Detective-Zii-Skills`)

Pilih cara pasang yang paling cocok dengan AI coding agent yang kamu pakai.

---

## Cara 1: Pakai CLI `skills` (Paling Praktis)

```bash
npx skills add muammarRM/Detective-Zii-Skills
```

Untuk memilih skill tertentu saja:

```bash
npx skills add muammarRM/Detective-Zii-Skills --skill be-detective hakim anti-overengineering
```

---

## Cara 2: Pasang Manual Global di Antigravity

Agar seluruh skill & pemicu otomatisnya aktif di semua proyek:

### 1. Salin Folder `skills/`
Copy **semua folder di dalam `skills/`** ke direktori skill global Antigravity:
- **Windows:** `C:\Users\<NAMA_USER>\.gemini\config\skills\`
- **macOS / Linux:** `~/.gemini/config/skills/`

### 2. Salin File `rules/` (Opsional tapi Direkomendasikan)
Copy file di dalam `rules/` ke:
- **Windows:** `C:\Users\<NAMA_USER>\.gemini\config\rules\`
- **macOS / Linux:** `~/.gemini/config/rules/`

> [!TIP]
> Jika kamu tidak ingin agent otomatis menjalankan mode *Cognitive Council* di setiap prompt, **lewati langkah 2** (`auto_context_skill_router.md` dan `overthinking_and_manipulator.md`). Semua skill tetap bisa dipanggil kapan saja lewat prompt atau nama skill.

---

## Cara 3: Pasang Per Project (Antigravity / Claude Code / Codex / Cursor)

1. Salin folder skill dari `skills/` ke salah satu folder proyek berikut:
   - `.agents/skills/` (standar Antigravity / Codex)
   - `.claude/skills/` (Claude Code)
2. Jika ingin pemicu otomatis ikut aktif hanya di proyek tersebut, salin aturan dari `rules/` ke file instruksi proyekmu (`GEMINI.md` atau `CLAUDE.md`) dan masukkan ke `.gitignore` agar tidak terbawa ke repo tim.
