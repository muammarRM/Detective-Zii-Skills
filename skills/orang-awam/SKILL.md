---
name: orang-awam
description: Evaluates and designs UI, UX, workflows, and messages from the lens of an ordinary, non-technical, fatigued user (extreme user empathy). Triggers on UI/UX/copywriting tasks, via "/orang-awam" or "/user-biasa", or when prompted with "kacamata orang awam" / "dari sisi user" / "bikin ramah pemula".
---

# Orang-Awam: The Extreme User-Empathy & Human Lens

## Overview
Skill **`orang-awam`** adalah instrumen empati pengguna tingkat tinggi. Skill ini memaksa sistem dan developer melihat aplikasi bukan dari sudut pandang pembuat kode, melainkan dari sudut pandang **pengguna manusia biasa yang nyata di dunia nyata**.

> *"Developer mikirin database dan status HTTP, tapi pengguna cuma ingin kerjaannya cepat beres tanpa pusing membaca istilah alien."*

Prinsip Utama:
1. **Persona Pengguna Nyata**: Asumsikan pengguna adalah **staf kantor atau warga umum yang sedang lelah di hari Jumat jam 4 sore, menggunakan laptop/HP berspesifikasi standar dengan koneksi pas-pasan**.
2. **Nol Jargon Teknis**: Larang keras pesan error atau label berbau teknis (`500 Internal Error`, `null pointer`, `SQL Integrity`, `Payload invalid`, `CSRF Token`).
3. **Pangkas Friksi Input**: Jangan pernah meminta pengguna mengetik hal yang sistem bisa tebak, ambil otomatis, atau sediakan opsinya.
4. **Kepastian & Ketenangan (Feedback Loop)**: Pengguna tidak boleh dibiarkan menebak apakah aplikasinya sedang bekerja, sukses, atau gagal. Berikan status yang menenangkan.

---

## 3 Jalur Pemicu (Tri-Trigger Activation)

1. **Jalur Otomatis**: Berjalan otomatis setiap kali merancang antarmuka (UI), alur formulir, teks notifikasi, atau pesan error.
2. **Jalur Slash Command**: Dipicu secara mendalam ketika user mengetik `/orang-awam` atau `/user-biasa`.
3. **Jalur Prompt Alami**: Dipicu ketika user berkata *"cek dari sisi user"*, *"kacamata orang awam"*, *"bikin ramah pemula"*, *"bahasa yang gampang dipahami"*, atau sejenisnya.

---

## 4 Lensa Audit Orang Awam (The 4 Empathy Lenses)

```
                       [Tampilan UI / Pesan / Alur Fitur]
                                       │
         ┌─────────────────────────────┼─────────────────────────────┐
         ▼                             ▼                             ▼
[1. Lensa Anti-Jargon]        [2. Lensa Friksi Form]        [3. Lensa Kejelasan Aksi]
"Apakah nenek atau staf       "Kenapa harus isi 8           "Setelah tombol diklik,
 kantor paham istilah ini?"    kolom kalau 2 cukup?"         apakah user tahu apa yg terjadi?"
         │                             │                             │
         └─────────────────────────────┼─────────────────────────────┘
                                       │
                                       ▼
                       [4. Lensa Pemulihan Humanis]
                       "Kalau gagal, apakah user tahu
                        langkah nyata buat solusinya?"
                                       │
                                       ▼
                       ┌───────────────────────────────┐
                       │   UI/UX RAMAH, MANUSIAWI,     │
                       │   & BEBAS BINGUNG (NO STRESS) │
                       └───────────────────────────────┘
```

### 1. Lensa Bahasa Manusiawi (Anti-Jargon Filter)
- **Tolak**: *"Error: Uncaught TypeError: Cannot read property of undefined."*
- **Ganti dengan**: *"Ups, data laporan belum bisa dimuat. Silakan muat ulang halaman dalam beberapa detik."*
- **Tolak**: *"Status: 422 Unprocessable Entity - Field `nik` invalid format."*
- **Ganti dengan**: *"Nomor NIK harus terdiri dari 16 angka ya. Tolong cek kembali."*

### 2. Lensa Friksi & Kemalasan Sehat (Lazy-User Protection)
- Jika ada pilihan kecamatan, kelurahannya harus otomatis terfilter.
- Jangan minta user input format tanggal ribet manual `YYYY-MM-DD` jika bisa pakai date picker atau otomatis terisi hari ini.
- Jangan letakkan tombol bahaya (misal: "Hapus Semua") bersebelahan persis dengan tombol utama (misal: "Simpan") dengan warna yang mirip.

### 3. Lensa Kejelasan Aksi (Visual Reassurance)
- Setiap tombol yang diklik harus langsung memberi respon visual (misal teks tombol berubah jadi *"Menyimpan..."* dan tombol dinonaktifkan sementara).
- Layar putih kosong tanpa animasi loading adalah dosa besar UX. Pengguna akan mengira aplikasi rusak.

### 4. Lensa Solusi Nyata (Actionable Guidance)
- Jangan cuma bilang *"Gagal menyimpan"*. Beritahu **mengapa** dan **apa yang harus dilakukan**:
  *"Gagal menyimpan karena koneksi internet Anda terputus. Periksa wifi Anda lalu klik coba lagi."*

---

## Format Output: The Human UX & Empathy Review

```markdown
### 👥 Audit Kacamata Orang Awam (Empathy Check)
- **Uji Kebingungan**: [Apakah alur ini membingungkan bagi pengguna non-IT?]
- **Jargon Teknis yang Dieliminasi**:
  - ❌ *Sebelum*: `[Pesan/Istilah teknis yang kaku]`
  - ✅ *Sesudah*: `[Bahasa manusiawi yang ramah dan menenangkan]`

### 🖱️ Pangkas Friksi Alur Pengguna
- [Sederhanakan klik/input yang sebelumnya berbelit-belit]
- [Feedback visual yang dipasang agar user tidak panik]

### 💡 Keputusan Akhir untuk User
[1-2 kalimat jaminan bahwa fitur ini siap dipakai dengan nyaman oleh siapa pun]
```
