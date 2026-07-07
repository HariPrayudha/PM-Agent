---
name: prd
description: Generate PRD (Product Requirements Document) lengkap dari brief project — sitemap, fitur per halaman, user flow, acceptance criteria, out-of-scope, dan open questions EN untuk client. Pakai setelah /kickoff, sebelum /breakdown.
---

# /prd <nama-project>

Ubah brief menjadi PRD yang siap di-approve client dan siap di-breakdown jadi task.

## Langkah

1. **Baca konteks**: `projects/<nama>/brief.md` (wajib — kalau belum ada, arahkan ke `/kickoff` dulu), `stakeholders.md`, dan profil client di `clients/` kalau ada. Kalau ada requirement mentah dari client (EN), baca juga.
   ⚠️ Kalau project bertipe **design/creative**: PRD bukan dokumen yang tepat — arahkan ke design brief (`templates/design-brief.md`, biasanya sudah dibuat `/kickoff` tipe design) lalu `/breakdown`. Jangan paksa struktur PRD untuk design job.

2. **Identifikasi gap**: bandingkan informasi yang ada vs yang dibutuhkan template `templates/prd.md`. Buat daftar gap, pisahkan:
   - **Bisa dijawab Hari sekarang** → tanya langsung (maks 1–2 putaran, kelompokkan pertanyaan).
   - **Harus dijawab client** → jangan tanya Hari; masukkan ke bagian "Open Questions untuk Client" dalam English siap kirim.

3. **Generate `prd.md`** di folder project, pakai struktur `templates/prd.md`:
   - Sitemap realistis dari kebutuhan (bukan template kosong)
   - Fitur per halaman/modul dengan prioritas MoSCoW — tandai jelas mana Must untuk launch
   - **Acceptance criteria terukur per fitur utama** — ini kunci KPI low revision rate; hindari kata ambigu ("menarik", "cepat", "user-friendly") → ganti kondisi yang bisa dites
   - User flow untuk alur kritis (checkout, signup, dsb.)
   - Out of Scope EKSPLISIT — pikirkan apa yang kemungkinan diminta client belakangan dan tulis sekarang
   - Bagian konten & aset: apa yang harus disediakan client + deadline
   - Aturan revisi (default: 2 putaran per fase, bisa disesuaikan)

4. **Bahasa**: dokumen dalam Bahasa Indonesia (untuk tim), KECUALI bagian "Open Questions untuk Client" dalam English.

5. **Review bersama Hari**: tampilkan ringkasan PRD (bukan seluruh file) — jumlah halaman/fitur, keputusan penting yang kamu asumsikan, daftar open questions. Minta koreksi.

6. **Tutup dengan langkah berikutnya**:
   - Sarankan kirim PRD summary + open questions ke client untuk approval — tawarkan draft email/message EN-nya sekalian (gaya: `playbooks/client-communication.md`).
   - Ingatkan: JANGAN `/breakdown` & mulai development sebelum PRD di-approve client (tertulis).
   - Setelah approved → `/breakdown <nama>`.
