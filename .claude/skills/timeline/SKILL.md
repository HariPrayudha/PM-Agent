---
name: timeline
description: Susun timeline & milestone project dari breakdown + estimasi tim + kapasitas, dengan buffer 20-30%, lalu komunikasikan due date via Slack (TIDAK set due date di ClickUp). Pakai setelah /breakdown dan estimasi dev masuk.
---

# /timeline <nama-project>

Breakdown + estimasi → milestone & deadline yang bisa ditepati.

## Langkah

1. **Baca** `projects/<nama>/breakdown.md`, `brief.md` (deadline & alasannya), `timeline.md` existing. Tarik task dari ClickUp via MCP kalau tersedia (cek estimasi yang sudah diisi tim).

2. **Kumpulkan input dari Hari** (yang belum ada):
   - Estimasi dev per epic (kalau belum → berhenti, minta Hari adakan sesi estimasi dulu; tawarkan agenda sesinya)
   - Kapasitas: siapa saja, alokasi %, cuti/libur yang diketahui, project paralel
   - Tanggal mulai efektif

3. **Hitung timeline**:
   - Urutkan epic berdasar dependensi (design → dev → QA → UAT → launch)
   - Terapkan buffer: komitmen = estimasi × 1.2–1.3 (lihat `playbooks/estimation-timeline.md`; pilih faktor sesuai kejelasan scope — jelaskan pilihanmu)
   - Deadline internal tim = estimasi asli; buffer tidak diumumkan sebagai waktu santai
   - Sisipkan jeda internal QA sebelum UAT; UAT client beri 1–2 minggu
   - **Deadline milik client** (konten, feedback, UAT) masuk sebagai milestone eksplisit
   - Semua tanggal absolut

4. **Bandingkan dengan deadline client**: kalau tidak muat → JANGAN paksa muat dengan memotong buffer/QA. Tawarkan opsi trade-off (potong scope Could/Should, atau geser tanggal) pakai kerangka "Option A/B + rekomendasi" dari `playbooks/estimation-timeline.md`, termasuk draft pesan EN-nya.

5. **Tulis `timeline.md`** project (format template) + update baris project di `projects/_INDEX.md` (next milestone + deadline).

6. **Komunikasikan due date via Slack** (setelah konfirmasi eksplisit): siapkan draft pesan due date per task/epic sesuai timeline, siap paste ke channel tim. **JANGAN update due date di ClickUp** — Hari hanya penerima task di ClickUp, bukan pengelola.

7. **Tutup dengan langkah berikutnya**: kickoff meeting tim (walkthrough PRD + timeline) & kickoff call client — tawarkan buatkan agenda keduanya. Setelah itu ritme harian: `/daily`.
