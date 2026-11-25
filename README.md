# 🕵️‍♂️ Detective Zii Skills (`Detective-Zii-Skills`)

Koleksi **9 AI Agent Skills** + **3 Companion Rules** untuk mengubah AI coding agent menjadi tim rekayasa disiplin: debugging forensik berbasis bukti (*zero guessing*), pengujian skeptis sebelum eksekusi, arsitektur minimalis bebas *over-engineering*, UX ramah manusia, dan kebersihan repository Git.

Setiap skill dibuat dengan prinsip universal: **ANTI-OVERENGINEERING** (ramping, elegan, minim baris, dan bebas *bloat*).

---

## ⚡ Instalasi Cepat

```bash
npx skills add muammarRM/Detective-Zii-Skills
```

Atau pasang manual untuk Antigravity, Claude Code, Codex, maupun Cursor — lihat langkah lengkapnya di **[INSTALL.md](INSTALL.md)**.

---

## 📦 Daftar Lengkap Skill (9 Skills)

### 1. The Cognitive Council (6 Skill Inti Mahkamah Kode)
Keenam skill ini bekerja bersama secara terpadu melalui arsitektur **Tri-Trigger**: otomatis di setiap prompt, melalui slash commands (`/`), maupun lewat bahasa percakapan alami.

| Skill | Ikon & Peran | Fokus Utama | Pertanyaan Kunci |
| :--- | :--- | :--- | :--- |
| **[`be-detective`](skills/be-detective/SKILL.md)** | 🕵️‍♂️ **Detektif Forensik** | Olah TKP bug & perburuan bukti nyata (*zero guessing*) | *"Mana nomor barisnya, isi variabelnya, dan bukti log saat meledak?"* |
| **[`hakim`](skills/hakim/SKILL.md)** | ⚖️ **Hakim Agung** | Menguji silang bukti detektif & mengetok palu vonis sah | *"Apakah buktinya otentik di luar keraguan wajar, atau cuma kebetulan?"* |
| **[`anti-overengineering`](skills/anti-overengineering/SKILL.md)** | 🪒 **Occam's Razor** | Memangkas kode berlebih, tolak abstraksi & library mubazir | *"Bisa selesai pakai 5 baris fungsi native tanpa bikin class baru?"* |
| **[`orang-awam`](skills/orang-awam/SKILL.md)** | 👥 **Empati Pengguna** | Bahasa manusiawi, nol jargon teknis, minimalkan friksi UI | *"Apakah staf kantor yang lelah di Jumat jam 4 sore bisa pakai tanpa bingung?"* |
| **[`overthinking`](skills/overthinking/SKILL.md)** | 🔮 **Radar Masa Depan** | Prediksi risiko 1–12 bulan ke depan & mitigasi santai | *"Apa dampak keputusan ini kalau data membengkak 10x dalam 6 bulan?"* |
| **[`manipulator`](skills/manipulator/SKILL.md)** | 🛠️ **Inkuisitor Celah** | Skeptisisme radikal, uji chaos input & langsung bentengi | *"Bagaimana jika user klik 5 kali atau internet putus mendadak?"* |

### 2. Utility & Guardrail Skills (3 Skill Tambahan)

| Skill | Fokus Utama |
| :--- | :--- |
| **[`anti-dummy-leak`](skills/anti-dummy-leak/SKILL.md)** | Audit ketat sebelum `git commit` / `git push` agar file prompt AI, spec/plan, scratch script, dump data, arsip `.zip`, dan binary tidak bocor ke GitHub. |
| **[`human-uiux-design`](skills/human-uiux-design/SKILL.md)** | Disiplin desain web & consumer utility yang tenang, intuitif, dan bebas *AI slop* (badge diet, anti sparkle spam, anti grid marketing generik). |
| **[`ui-writing`](skills/ui-writing/SKILL.md)** | Standar UI writing & UX microcopy (tombol `Verb + Noun`, aturan 3-bagian pesan error yang ramah, dan lokalisasi Bahasa Indonesia yang natural). |

---

## 🔄 Alur Kolaborasi (*The Courtroom & Engineering Pipeline*)

```text
                                [MASALAH / FITUR / PERMINTAAN USER]
                                                 │
        ┌────────────────────────────────────────┴────────────────────────────────────────┐
        ▼                                                                                 ▼
 [JALUR A: TERDETEKSI BUG / ERROR]                                             [JALUR B: FITUR / DESAIN BARU]
        │                                                                                 │
        ▼                                                                                 ▼
┌───────────────────────────────┐                                             ┌───────────────────────────────┐
│     SKILL: BE-DETECTIVE       │                                             │      SKILL: OVERTHINKING      │
│   (Olah TKP & Bukti Empiris)  │                                             │   (Radar Risiko 1 - 12 Bulan) │
│ - Baca stack trace & log presisi                                            │ - Prediksi bom waktu jangka panjang
│ - Rumuskan hipotesis terarah  │                                             │ - Bahasa santai & mitigasi ramah│
│ - Wajib bukti nomor baris     │                                             └───────────────┬───────────────┘
└───────────────┬───────────────┘                                                             │
                │ Berkas Perkara Lengkap                                                      ▼
                ▼                                                             ┌───────────────────────────────┐
┌───────────────────────────────┐                                             │      SKILL: MANIPULATOR       │
│         SKILL: HAKIM          │                                             │  (Skeptisisme & Benteng Kode) │
│   (Sidang Uji Silang Bukti)   │                                             │ - Ragukan draf pertama        │
│ - Uji silang ala Manipulator  │                                             │ - Uji input ekstrim & timeout │
│ - Uji masa depan Overthinking │                                             │ - LANGSUNG BENTENGI KODENYA   │
│ - Tolak perbaikan lebay       │                                             └───────────────┬───────────────┘
│                               │                                                             │
│ [DITOLAK] ──► Cari bukti lagi │                                                             │
│ [VONIS SAH]                   │                                                             │
└───────────────┬───────────────┘                                                             │
                │                                                                             │
                └──────────────────────────────────────┬──────────────────────────────────────┘
                                                       │
                                                       ▼
                        ┌─────────────────────────────────────────────────────────────┐
                        │                 SARINGAN GANDA TAHAP AKHIR                  │
                        ├──────────────────────────────┬──────────────────────────────┤
                        │ SKILL: ANTI-OVERENGINEERING  │      SKILL: ORANG-AWAM       │
                        │  (Pemangkas Bloat & Lapisan) │  (Audit Pengguna Nyata & UX) │
                        │ - Hapus class/interface lebay│ - Hapus semua pesan jargon   │
                        │ - Terapkan Ponytail Ladder   │ - Sederhanakan alur form     │
                        │ - Solusi seringkas mungkin   │ - Berikan feedback tenang    │
                        └──────────────────────────────┴──────────────────────────────┘
                                                       │
                                                       ▼
                                     [KODE RAMPING, TANGGUH, AMAN,
                                      TERBUKTI 100%, & RAMAH USER]
```

---

## ⚡ 3 Jalur Pemicu (*Tri-Trigger Activation*)

1. **Jalur Otomatis (dengan Companion Rules di `rules/`):**
   - **Bug / Error:** `be-detective` (olah TKP) ➔ `hakim` (uji ketok palu).
   - **Tulis / Ubah Kode:** `anti-overengineering` (ramping) + `manipulator` (bentengi celah).
   - **Desain UI / Pesan:** `orang-awam` + `human-uiux-design` + `ui-writing`.
   - **Arsitektur Baru:** `overthinking` (analisis 3 horizon risiko).
2. **Jalur Slash Command:**
   - `/be-detective` atau `/detective [masalah]`
   - `/hakim` atau `/judge [kasus]`
   - `/anti-overengineering` atau `/simple [kode]`
   - `/orang-awam` atau `/user-biasa [UI/alur]`
   - `/overthinking [ide]`
   - `/manipulator [fitur]`
3. **Jalur Bahasa Percakapan Alami:**
   - *"Jadilah detektif dan selidiki error ini"*
   - *"Uji bukti detektif dan ketok palu hakim"*
   - *"Jangan overengineering ya, bikin yang simpel aja"*
   - *"Cek dari kacamata orang awam"*
   - *"Overthinking fitur ini"*
   - *"Ragukan dan bentengi kode ini"*

---

## 📂 Struktur Repository

```text
Detective-Zii-Skills/
├── README.md
├── INSTALL.md
├── LICENSE
├── .gitignore
├── skills/
│   ├── anti-dummy-leak/SKILL.md
│   ├── anti-overengineering/SKILL.md
│   ├── be-detective/SKILL.md
│   ├── hakim/SKILL.md
│   ├── human-uiux-design/SKILL.md
│   ├── manipulator/SKILL.md
│   ├── orang-awam/SKILL.md
│   ├── overthinking/SKILL.md
│   └── ui-writing/SKILL.md
└── rules/                              # Opsional: aktifkan auto-trigger & pre-push guardrail
    ├── anti_dummy_leak.md
    ├── auto_context_skill_router.md
    └── overthinking_and_manipulator.md
```

| Komponen | Lokasi Pasang Global (Default) |
| :--- | :--- |
| **Semua Skill (`skills/*`)** | `~/.gemini/config/skills/<nama-skill>/SKILL.md` |
| **Companion Rules (`rules/*`)** | `~/.gemini/config/rules/<nama-rule>.md` |
