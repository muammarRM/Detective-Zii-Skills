---
name: auto-context-skill-router
description: Automatically routes and triggers the best-matching global skills based on task context whenever the user prompts, reports a bug, designs a feature, or says "gunakan skill", eliminating the need to remember thousands of skill names.
trigger: always_on
---

# Rule: Context-Aware Smart Skill Router

Aturan ini memastikan pengguna TIDAK PERLU mengingat atau menghafal ribuan nama skill yang terpasang. Agent secara cerdas, otomatis, dan proaktif mendeteksi konteks pembicaraan dan mengaktifkan ekosistem skill yang paling relevan di setiap prompt.

---

## 1. Pemicu Otomatis (Trigger Activation)

Aturan ini aktif di **setiap prompt pengguna**, khususnya ketika:
- **Terdeteksi Bug / Error / Kerusakan Logika**: Otomatis aktifkan **`be-detective`** (olah TKP & buru bukti) ➔ **`hakim`** (sidang uji bukti silang).
- **Penulisan Kode / Refactoring**: Otomatis aktifkan **`anti-overengineering`** (pangkas bloat & abstraksi mubazir) + **`manipulator`** (bentengi celah).
- **Desain Antarmuka (UI/UX) & Pesan Pengguna**: Otomatis aktifkan **`orang-awam`** (empati pengguna nyata, anti-jargon, kurangi friksi).
- **Perancangan Fitur / Arsitektur Baru**: Otomatis aktifkan **`overthinking`** (radar risiko 1-12 bulan ke depan).
- **Instruksi Alami**: User mengetik *"gunakan skill"*, *"pakai skill"*, *"aktifkan skill"*, *"selidiki bug ini"*, *"sederhanakan"*, *"cek dari sisi user"*, dll.

---

## 2. Alur Routing Berdasarkan Konteks (Context Classification)

Agent secara otomatis memetakan kebutuhan user ke kategori skill terbaik:

1. **Investigasi Masalah & Debugging (Anti Tebak-Tebakan)**:
   - *Target Skill Utama*: `be-detective`, `hakim`, `investigate-first`, `systematic-debugging`
   - *Aksi*: Kumpulkan bukti nyata di TKP (log, baris kode, anomali variabel) via `be-detective`, lalu uji di mahkamah `hakim` sebelum menyentuh kode. **Dilarang keras menebak!**

2. **Kesederhanaan Kode & Anti-Bloat (Kodingan Ramping)**:
   - *Target Skill Utama*: `anti-overengineering`, `ponytail_ladder`, `clean-code`
   - *Aksi*: Pangkas lapisan class yang tidak perlu, gunakan fitur standar native, dan tolak abstraksi prematur (Occam's Razor).

3. **Desain & UI/UX Ramah Manusia (Empati Pengguna)**:
   - *Target Skill Utama*: `orang-awam`, `ui-ux-pro-max`, `frontend-ui-engineering`, `tailwind-design-system`
   - *Aksi*: Evaluasi dari kacamata orang awam yang lelah. Hapus jargon teknis, sederhanakan alur form, dan beri feedback visual yang menenangkan.

4. **Pertahanan Kode & Uji Skeptis**:
   - *Target Skill Utama*: `manipulator`, `cso`, `differential-review`, `security-best-practices`
   - *Aksi*: Ragukan draf kode sendiri terhadap chaos input, koneksi putus, dan klik ganda, lalu langsung bentengi kodenya.

5. **Radar Risiko Masa Depan & Strategi**:
   - *Target Skill Utama*: `overthinking`, `plan-ceo-review`, `marketing-mindset`
   - *Aksi*: Prediksi dampak sistem dan operasional dalam 1–12 bulan ke depan dengan bahasa yang santai dan solutif.

6. **Pengujian, TDD & QA**:
   - *Target Skill Utama*: `tdd-orchestrator`, `test-driven-development`, `playwright-skill`, `webapp-testing`
   - *Aksi*: Menulis test lebih dulu (Red-Green-Refactor) dan menjalankan validasi otomatis.

7. **Infrastruktur & Cloud (cPanel, Cloudflare, DevOps)**:
   - *Target Skill Utama*: `cloudflare`, `docker-compose`, `workers-best-practices`, `git-workflow`
   - *Aksi*: Menata konfigurasi deployment, build asset, dan automasi rilis.

---

## 3. Format Respon ke Pengguna

Ketika skill otomatis diaktifkan, berikan tanda singkat di awal respon agar pengguna tahu skill mana yang sedang bekerja, lalu langsung eksekusi tugasnya:

> [!TIP]
> 🎯 **Skill Aktif Otomatis**: `[nama-skill-1]` + `[nama-skill-2]`  
> *Konteks*: [Penjelasan 1 kalimat mengapa skill ini bekerja bersama untuk menyelesaikan permintaan]*

Setelah header tersebut, agent langsung menjalankan investigasi, audit, atau koding sesuai workflow skill tersebut tanpa meminta konfirmasi berbelit-belit.
