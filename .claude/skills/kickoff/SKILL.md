---
name: kickoff
description: Intake project baru — buat folder project dari template, isi brief lewat tanya-jawab terstruktur, update dashboard _INDEX.md. Pakai saat ada project/prospek baru masuk.
---

# /kickoff <nama-project>

Intake project baru langkah demi langkah.

## Langkah

1. **Normalisasi nama**: ubah argumen jadi kebab-case (mis. "Toko Online Acme" → `toko-online-acme`). Kalau tidak ada argumen, tanya nama project dulu.

2. **Cek duplikat**: kalau `projects/<nama>/` sudah ada, tanya mau lanjut update atau batal.

3. **Tanya TIPE project dulu** — menentukan jalurnya:
   - **Web dev / mobile baru** → jalur penuh: brief → `/prd` → `/breakdown` → `/timeline`
   - **Design/creative** (branding, banner set, company profile, dsb.) → brief pakai struktur `templates/design-brief.md` (BUKAN PRD; deliverable + spek + referensi + jatah revisi) → next step langsung `/breakdown` (task creative) → `/timeline`
   - **Existing/maintenance** (project lama yang mau dicatat) → **registrasi ringan**: brief retroaktif singkat (sistemnya apa, stack, status, kontak client, link repo/ClickUp) — jangan paksa lewat discovery penuh; cukup 1 putaran tanya, sisanya `{belum dicatat}`
   - **SaaS internal** → jalur penuh, stakeholder = internal (PO/management)

4. **Kumpulkan informasi** — tanya Hari (pakai AskUserQuestion bila cocok, boleh multi-pertanyaan sekaligus, jangan lebih dari 2 putaran):
   - Client: siapa, kontak utama, sudah ada profil di `clients/`?
   - Ringkasan kebutuhan: apa yang diminta client (kalau ada dokumen/email requirement EN, minta di-paste)
   - Deadline & alasannya; budget (kalau tahu)
   - Tim yang dialokasikan
   - Materi yang sudah ada: design? konten? akses?
   
   Kalau Hari belum tahu jawabannya, JANGAN paksa — tulis sebagai open question di brief. Justru tunjukkan: "ini daftar yang perlu kamu tanyakan ke client di discovery call" (ambil dari `playbooks/requirement-gathering.md`).

5. **Buat folder project**: copy struktur `projects/_TEMPLATE/` ke `projects/<nama>/` (brief.md, timeline.md, stakeholders.md, risks.md, decisions.md + subfolder meeting-notes/, status-reports/, client-comms/).

6. **Isi `brief.md`** dengan semua jawaban — untuk tipe design, gunakan struktur `templates/design-brief.md`. Tanggal absolut. Bagian yang belum terjawab → masuk "Asumsi & Open Questions" sebagai checklist.

7. **Isi awal `stakeholders.md`** (minimal kontak client yang diketahui) dan `risks.md` (centang checklist risiko umum yang relevan). Untuk registrasi existing: boleh skip kalau info belum ada.

8. **Update `projects/_INDEX.md`**: tambah baris di tabel Project Aktif (atau Pipeline kalau belum deal) — status awal 🟢; fase Discovery (baru) / Maintenance (existing).

9. **Kalau ada profil client baru**: buat `clients/<nama-client>.md` dari `clients/_TEMPLATE.md`.

10. **Tutup dengan langkah berikutnya, sesuai tipe**:
    - **Web dev/SaaS**: banyak open questions → sarankan discovery call + daftar pertanyaan EN; sudah jelas → `/prd <nama>`.
    - **Design**: brief lengkap → `/breakdown <nama>` (task creative); referensi/aset kurang → daftar yang harus diminta ke client (EN).
    - **Existing**: selesai — pembaruan berikutnya tinggal `/task <nama>`.
    - Tampilkan ringkasan: folder dibuat, isi brief, open questions, next step.
