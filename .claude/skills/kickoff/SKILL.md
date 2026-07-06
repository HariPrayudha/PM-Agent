---
name: kickoff
description: Intake project baru — buat folder project dari template, isi brief lewat tanya-jawab terstruktur, update dashboard _INDEX.md. Pakai saat ada project/prospek baru masuk.
---

# /kickoff <nama-project>

Intake project baru langkah demi langkah.

## Langkah

1. **Normalisasi nama**: ubah argumen jadi kebab-case (mis. "Toko Online Acme" → `toko-online-acme`). Kalau tidak ada argumen, tanya nama project dulu.

2. **Cek duplikat**: kalau `projects/<nama>/` sudah ada, tanya mau lanjut update atau batal.

3. **Kumpulkan informasi** — tanya Hari (pakai AskUserQuestion bila cocok, boleh multi-pertanyaan sekaligus, jangan lebih dari 2 putaran):
   - Client: siapa, kontak utama, sudah ada profil di `clients/`?
   - Tipe: web dev / mobile / SaaS internal / lainnya
   - Ringkasan kebutuhan: apa yang diminta client (kalau ada dokumen/email requirement EN, minta di-paste)
   - Deadline & alasannya; budget (kalau tahu)
   - Tim yang dialokasikan
   - Materi yang sudah ada: design? konten? akses?
   
   Kalau Hari belum tahu jawabannya, JANGAN paksa — tulis sebagai open question di brief. Justru tunjukkan: "ini daftar yang perlu kamu tanyakan ke client di discovery call" (ambil dari `playbooks/requirement-gathering.md`).

4. **Buat folder project**: copy struktur `projects/_TEMPLATE/` ke `projects/<nama>/` (brief.md, timeline.md, stakeholders.md, risks.md, decisions.md + subfolder meeting-notes/, status-reports/, client-comms/).

5. **Isi `brief.md`** dengan semua jawaban. Tanggal absolut. Bagian yang belum terjawab → masuk "Asumsi & Open Questions" sebagai checklist.

6. **Isi awal `stakeholders.md`** (minimal kontak client yang diketahui) dan `risks.md` (centang checklist risiko umum yang relevan).

7. **Update `projects/_INDEX.md`**: tambah baris di tabel Project Aktif (atau Pipeline kalau belum deal) — status awal 🟢, fase Discovery.

8. **Kalau ada profil client baru**: buat `clients/<nama-client>.md` dari `clients/_TEMPLATE.md`.

9. **Tutup dengan langkah berikutnya**:
   - Masih banyak open questions → sarankan discovery call + berikan daftar pertanyaan EN siap pakai.
   - Requirement sudah cukup jelas → sarankan `/prd <nama>` sebagai langkah berikutnya.
   - Tampilkan ringkasan: folder dibuat, isi brief, open questions, next step.
