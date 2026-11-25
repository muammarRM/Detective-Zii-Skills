---
name: overthinking
description: Anticipates hidden risks, projects future consequences, and provides simple, plain-language risk management. Triggers automatically on feature/code tasks, via slash command "/overthinking", or when prompted with "gunakan skill overthinking" / "pakai skill overthinking".
---

# Overthinking: Anticipatory Risk & Future Radar

## Overview
Skill **`overthinking`** adalah kemampuan berpikir antisipatif tingkat tinggi. Ini bukan overthinking negatif (anxiety/kelumpuhan analisis), melainkan **Proactive Risk Intelligence**: selalu melihat 3-5 langkah ke depan untuk memproyeksikan resiko tersembunyi dan dampaknya di masa depan.

Prinsip Utama:
1. **Pikirkan Dampak Jauh ke Depan**: Jangan hanya melihat apa yang diminta hari ini, tapi apa dampaknya dalam 1 bulan, 6 bulan, hingga 1 tahun ke depan.
2. **Bahasa Manusiawi & Sederhana**: Pemikiran rumit harus diterjemahkan menjadi penjelasan yang sangat mudah dipahami (konsep ELI5, santai, tanpa istilah teknis yang menakut-nakuti).
3. **Manajemen Resiko yang Aplikatif**: Setiap resiko yang diidentifikasi WAJIB disertai solusi mitigasi nyata (langkah aman sekarang vs langkah jangka panjang).

---

## 3 Jalur Pemicu (Tri-Trigger Activation)

Skill ini aktif melalui salah satu dari 3 jalur berikut:
1. **Jalur Otomatis**: Berjalan otomatis setiap kali merancang arsitektur, endpoint, alur logika, atau fitur aplikasi.
2. **Jalur Slash Command**: Dipicu secara mendalam ketika user mengetik `/overthinking`.
3. **Jalur Prompt Alami**: Dipicu ketika user berkata *"gunakan skill overthinking"*, *"pakai skill overthinking"*, *"overthinking fitur ini"*, atau sejenisnya.

---

## 3 Sudut Pandang Masa Depan (The 3-Horizon Radar)

Ketika skill ini aktif, lakukan analisis mental melalui 3 horizon:

```
[Prompt / Fitur yang Dinilai]
              │
              ├──> Horizon 1: Hari 1 - 7 (Risiko Langsung & Edge Cases)
              │    Input aneh, user salah pencet, validasi jebol, error tak tertangani.
              │
              ├──> Horizon 2: Bulan 1 - 3 (Skalabilitas & Operasional)
              │    Volume data naik, query lambat, race condition, biaya server, data kotor.
              │
              └──> Horizon 3: Bulan 6 - 12+ (Tech Debt & Arsitektur Jangka Panjang)
                   Sistem kaku, vendor lock-in, sulit di-refactor, kepatuhan regulasi/privasi.
```

---

## Format Output: The Plain-Language Risk Briefing

Sajikan hasil analisis kepada user dengan struktur ramah dan jelas:

```markdown
### 🔮 Penerawangan ke Depan (Future Radar)
[Penjelasan singkat 2-3 kalimat dengan bahasa santai tapi tajam mengenai apa yang akan terjadi jika kita menjalankan ide ini sampai 6-12 bulan ke depan]

### ⚠️ Resiko Utama yang Terdeteksi
1. **[Nama Resiko 1]**: [Mengapa ini bisa berbahaya bagi user/aplikasi dengan analogi sederhana]
2. **[Nama Resiko 2]**: [Potensi masalah tak terduga yang sering luput]

### 🛡️ Manajemen Resiko & Solusi Mitigasi
- **Langkah Aman Sekarang (Mitigasi Cepat)**: [Tindakan pencegahan instan yang langsung kita terapkan di kode/desain]
- **Mitigasi Jangka Panjang**: [Langkah arsitektur agar sistem tetap aman saat aplikasi berkembang pesat]

### 💡 Rekomendasi Langkah Selanjutnya
[Saran tindakan konkrit yang paling seimbang antara kecepatan rilis dan keamanan]
```

---

## Kategori Manajemen Resiko (Risk Categorization Matrix)

| Kategori Resiko | Contoh Skenario Overthinking | Contoh Bahasa Sederhana ke User | Solusi Manajemen Resiko |
| :--- | :--- | :--- | :--- |
| **Data Loss & Human Error** | User klik tombol hapus massal tanpa konfirmasi berlapis. | *"Kalau user sengaja atau kepeleset klik, seluruh riwayat transaksi bisa hilang selamanya dalam 1 detik."* | Gunakan **Soft Delete** (tanda arsip) + konfirmasi ketik teks nama entitas. |
| **Security & Abuse** | Form input publik tanpa rate-limiting atau sanitasi. | *"Form ini bisa dibombardir oleh bot dengan 1.000 data spam per menit, membuat database penuh dan server down."* | Pasang captcha/turnstile, rate limiter IP, dan validasi ketat di sisi server. |
| **Performance Bottleneck** | Query SQL `SELECT *` tanpa pagination saat data masih sedikit. | *"Sekarang masih 10 baris data terasa cepat. Begitu data mencapai 50.000 baris, aplikasi akan loading berputar lama dan bikin user kabur."* | Terapkan pagination sejak hari pertama dan batasi kolom yang di-fetch. |
| **Concurrency / Race Condition** | Dua user membeli stok terakhir di detik yang sama. | *"Jika ada promo diskon kilat, dua pembeli bisa mengklaim 1 barang yang sama, menyebabkan stok minus dan komplain pelanggan."* | Gunakan database transaction lock / atomic decrement. |
| **Hidden Financial Cost** | Pemanggilan API berbayar atau AI model tanpa caching. | *"Tiap kali ada yang refresh halaman, kita bayar ke penyedia API. Kalau traffic naik, tagihan kartu kredit bisa melonjak tanpa disadari."* | Pasang caching response dan batasan kuota per user/per jam. |
