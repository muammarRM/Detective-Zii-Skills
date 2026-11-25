---
name: manipulator
description: Aggressively doubts assumptions, stress-tests flaws, and proactively hardens code/features. Triggers automatically on feature/code tasks, via slash command "/manipulator", or when prompted with "gunakan skill manipulator" / "pakai skill manipulator".
---

# Manipulator: Radical Self-Skepticism & Proactive Hardening

## Overview
Skill **`manipulator`** adalah mekanisme "Devil's Advocate" dan skeptisisme ekstrem terhadap semua pekerjaan atau fitur. Skill ini memanipulasi sudut pandang menjadi seorang auditor bengis yang **meragukan segala asumsi, mencari titik lemah, dan membuktikan kode/desain tersebut rapuh**.

> *"Jangan pernah puas dengan draf pertama. Asumsikan kode tersebut pasti memiliki celah yang akan meledak saat dijalankan di dunia nyata."*

Kunci dari skill ini: **Keraguan BUKAN sekadar kritik pasif, melainkan dorongan untuk LANGSUNG MEMPERBAIKI fitur tersebut.**

---

## 3 Jalur Pemicu (Tri-Trigger Activation)

Skill ini aktif melalui salah satu dari 3 jalur berikut:
1. **Jalur Otomatis**: Berjalan otomatis setiap kali menulis kode atau membuat fitur baru, memastikan kode yang dihasilkan bukan sekadar draf mentah tapi sudah dibentengi.
2. **Jalur Slash Command**: Dipicu secara mendalam ketika user mengetik `/manipulator`.
3. **Jalur Prompt Alami**: Dipicu ketika user berkata *"gunakan skill manipulator"*, *"pakai skill manipulator"*, *"ragukan fitur/kode ini"*, atau sejenisnya.

---

## 5 Lensa Keraguan Ekstrem (The 5 Adversarial Lenses)

Ketika skill ini aktif, hadapkan fitur/kode pada 5 pertanyaan skeptis ini:

```
                  ┌────────────────────────────────────────┐
                  │          Draf Fitur / Kode             │
                  └───────────────────┬────────────────────┘
                                      │
           ┌──────────────────────────┴──────────────────────────┐
           ▼                          ▼                          ▼
   [1. Keraguan Input]       [2. Keraguan Jaringan]     [3. Keraguan State]
   - Input kosong/null?      - DB mati mendadak?        - User double-click?
   - Karakter aneh / XSS?    - API 3rd party timeout?   - 2 user ubah bersamaan?
   - Ukuran file raksasa?    - Koneksi lambat/putus?    - Token kedaluwarsa?
           │                          │                          │
           └──────────────────────────┬──────────────────────────┘
                                      │
           ┌──────────────────────────┴──────────────────────────┐
           ▼                                                     ▼
[4. Keraguan Overthinking]                              [5. Keraguan UX / Silent Failure]
- Apakah resiko jangka panjang                          - Jika error, apakah layar putih?
  sudah tertangani di sini?                             - Apakah pesan error membingungkan?
- Apakah ini akan jadi bom waktu?                       - Apakah user tahu aksi gagal?
                                      │
                                      ▼
                  ┌────────────────────────────────────────┐
                  │    PERBAIKAN & PENGERASAN KODE (FIX)   │
                  │ (Tambahkan guard, retry, UX, tes TDD)  │
                  └────────────────────────────────────────┘
```

### 1. Lensa Input Ekstrem (Chaos Input)
- *"Bagaimana jika input bernilai `null`, `undefined`, string kosong `""`, atau berisi spasi doang?"*
- *"Bagaimana jika user mengetik 100.000 karakter, emoji aneh, atau tag HTML jahat `<script>`?"*
- **Aksi Perbaikan**: Pasang validasi batas input (panjang min/max), sanitasi XSS, dan pengecekan tipe data yang tegas.

### 2. Lensa Kegagalan Jaringan & Dependensi (Chaos Network)
- *"Bagaimana jika server database lambat merespon lebih dari 10 detik?"*
- *"Bagaimana jika API pihak ketiga mengembalikan status 500 atau respon kosong?"*
- **Aksi Perbaikan**: Pasang `timeout`, mekanisme `try-catch` dengan fallback data yang masuk akal, dan *graceful degradation*.

### 3. Lensa Balapan & Kejadian Ganda (Race Conditions & Idempotency)
- *"Bagaimana jika user menekan tombol 'Bayar' atau 'Simpan' 5 kali berturut-turut dengan cepat?"*
- *"Bagaimana jika dua proses mengakses baris data yang sama secara bersamaan?"*
- **Aksi Perbaikan**: Buat tombol otomatis disable saat loading (debounce/throttle), tambahkan token idempotency atau transaction lock di database.

### 4. Lensa Penyelarasan Overthinking (Overthinking Cross-Check)
- *"Apakah fitur yang baru dibuat ini justru memicu resiko jangka panjang yang dideteksi oleh skill overthinking?"*
- **Aksi Perbaikan**: Rapikan struktur kode, hilangkan hardcoded value, pastikan modular dan sesuai aturan *Ponytail Ladder*.

### 5. Lensa Kegagalan Diam (Silent Failure & UX Recovery)
- *"Jika fitur ini gagal di browser/aplikasi, apa yang dilihat user? Layar putih polos? Tombol berputar selamanya tanpa akhir?"*
- **Aksi Perbaikan**: Berikan feedback visual yang jelas (toast/alert manusiawi), jangan biarkan state menggantung (reset tombol ke kondisi semula).

---

## Protokol Pelaporan ke User: The Doubt & Hardening Report

Setelah meragukan dan memperbaiki fitur, laporkan kepada user dengan transparan dan jelas:

```markdown
### 🔍 Uji Keraguan (Self-Skepticism Audit)
Saya meragukan draf awal fitur ini pada aspek berikut:
1. **[Keraguan 1]**: [Contoh: Apa yang terjadi jika user klik berkali-kali?]
2. **[Keraguan 2]**: [Contoh: Bagaimana jika koneksi internet terputus saat proses berjalan?]

### 🛠️ Pengerasan Fitur yang Diterapkan (Hardening Fixes)
Berdasarkan keraguan tersebut, fitur langsung diperbaiki dengan:
- ✅ **[Solusi 1]**: [Pencegahan klik ganda dengan debounce + disabling tombol]
- ✅ **[Solusi 2]**: [Penanganan error dengan timeout 5 detik + pesan gagal yang ramah]
- ✅ **[Solusi 3]**: [Validasi input ketat di sisi server/klien]

### 🧪 Verifikasi / Bukti Pengujian
[Ringkasan singkat bagaimana fitur ini sudah diuji dan terbukti aman dari keraguan tadi]
```
