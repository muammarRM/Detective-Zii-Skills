---
name: anti-overengineering
description: Enforces brutal code and architecture simplicity, eliminates bloat and premature abstractions, and applies Occam's razor (Ponytail Ladder). Triggers on all coding/refactoring tasks, via "/anti-overengineering" or "/simple", or when prompted with "anti overengineering" / "sederhanakan" / "pangkas kode".
---

# Anti-Overengineering: The Occam's Razor & Code Minimalist

## Overview
Skill **`anti-overengineering`** adalah rem darurat dan sensor kesederhanaan untuk segala kode dan arsitektur. Skill ini memastikan solusi yang dibangun **sesederhana mungkin, minim baris, tanpa abstraksi mubazir, dan mudah dipelihara**.

> *"Kode terbaik adalah kode yang tidak pernah ditulis. Solusi paling elegan adalah solusi paling sedikit menghasilkan baris baru."*

Prinsip Utama:
1. **Aturan Ponytail Ladder**: Jika fitur standar bahasa/framework sudah menyediakannya, GUNAKAN itu. Jangan buat helper/class baru.
2. **Larang Abstraksi Prematur**: Jangan buat *Repository Pattern*, *Service Layer*, *Interface*, atau *Factory* jika cuma untuk 1 operasi CRUD biasa.
3. **Larang Dependensi Raksasa**: Jangan install library 20MB jika fungsi tersebut bisa diselesaikan dengan 5 baris fungsi native PHP/JavaScript/Python.
4. **Larang Over-Configuration**: Jangan buat sistem konfigurasi modular rumit untuk sesuatu yang nilainya statis atau jarang berubah.

---

## 3 Jalur Pemicu (Tri-Trigger Activation)

1. **Jalur Otomatis**: Berjalan otomatis di setiap penulisan kode, refactoring, atau desain fitur untuk memangkas bloat sebelum disajikan ke user.
2. **Jalur Slash Command**: Dipicu secara mendalam ketika user mengetik `/anti-overengineering` atau `/simple`.
3. **Jalur Prompt Alami**: Dipicu ketika user berkata *"sederhanakan"*, *"anti overengineering"*, *"pangkas kodenya"*, *"bikin yang simpel aja"*, atau sejenisnya.

---

## 4 Lensa Pemangkas Bloat (The 4 Simplicity Lenses)

```
                     [Draf Kode / Usulan Arsitektur]
                                    │
       ┌────────────────────────────┼────────────────────────────┐
       ▼                            ▼                            ▼
[1. Lensa YAGNI]          [2. Lensa Standar Native]    [3. Lensa Lapisan Abstraksi]
"Apakah ini beneran        "Bisa pakai fungsi           "Kenapa harus ada 3 file class
 dibutuhkan hari ini?"      bawaan bahasa?"              kalau 1 fungsi cukup?"
       │                            │                            │
       └────────────────────────────┼────────────────────────────┘
                                    │
                                    ▼
                      [4. Lensa Beban Pemeliharaan]
                      "Siapa yang mau baca dan paham
                       kode rumit ini 6 bulan lagi?"
                                    │
                                    ▼
                      ┌───────────────────────────┐
                      │    KODE RAMPING & BERSIH  │
                      │ (Minim baris, nol bloat)  │
                      └───────────────────────────┘
```

### 1. Lensa YAGNI (You Aren't Gonna Need It)
- Tolak keras: *"Nanti kalau aplikasinya butuh multi-tenant / multi-database / microservices gimana?"* -> **TIDAK. Buat untuk kebutuhan hari ini.**
- Jika user minta fitur A, selesaikan fitur A saja. Jangan menyelipkan fitur A.1, A.2, dan A.3 yang belum diminta.

### 2. Lensa Native Platform (Gunakan Bawaan)
- Contoh PHP/Laravel: Jangan buat trait atau class regex custom jika `Str::slug()` atau validasi `regex` bawaan Laravel sudah ada.
- Contoh JS/HTML: Jangan buat popup modal custom 200 baris dengan 3 dependensi kalau `<dialog>` HTML native atau alert sederhana cukup.
- Contoh CSS: Jangan buat custom utility rumit jika flexbox/grid 2 baris menyelesaikan masalah.

### 3. Lensa Pemangkasan Lapisan (Flatten the Layers)
- Jika Controller langsung panggil Model sudah aman dan bersih, **jangan paksa buat DTO + Service + Action + Repository**.
- Buat abstraksi **HANYA jika kode tersebut sudah terbukti terduplikasi minimal 3 kali** (Rule of Three).

### 4. Lensa Beban Pemeliharaan (Maintenance Burden)
- Setiap baris kode baru adalah liabilitas (potensi bug baru).
- Mengurangi 50 baris kode sambil mempertahankan fungsi yang sama adalah kemenangan besar.

---

## Format Output: The Simplicity & Anti-Bloat Review

```markdown
### 🪒 Audit Anti-Overengineering (Simplicity Check)
- **Status Kompleksitas**: [Ramping / Sempat Bengkak & Dipangkas]
- **Abstraksi yang Ditolak/Dihapus**:
  - ❌ [Contoh: Tidak perlu membuat 3 class interface baru]
  - ❌ [Contoh: Menghapus package pihak ketiga, diganti 3 baris fungsi native]

### ✂️ Hasil Pemangkasan (Sebelum vs Sesudah)
- **Sebelum**: [Jumlah baris atau lapisan rumit]
- **Sesudah**: [Solusi ringkas, to-the-point, dan elegan]

### 💡 Keuntungan Pemeliharaan
[1-2 kalimat mengapa kode yang lebih simpel ini jauh lebih minim bug dan mudah dibaca]
```
