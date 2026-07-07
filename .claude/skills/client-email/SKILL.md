---
name: client-email
description: Draft atau polish komunikasi client dalam English profesional — reply requirement, kabar delay, nego scope, reminder, situasi sulit. Pakai setiap mau kirim pesan penting ke client.
---

# /client-email

Komunikasi client EN yang profesional, dengan tone yang tepat untuk situasinya.

## Langkah

1. **Pahami situasi**: minta Hari jelaskan (ID boleh) — mau ngomong apa, ke siapa, konteksnya apa. Kalau ada pesan client yang mau dibalas, minta di-paste. Kalau Hari sudah punya draft, minta — tugasmu polish, bukan tulis ulang total (hormati suaranya).

2. **Baca konteks**: profil client di `clients/` (gaya komunikasi, history), project terkait (brief, decisions, komunikasi sebelumnya di `client-comms/`). Konsistensi dengan yang pernah dijanjikan itu krusial.

3. **Pilih pola dari playbook**: `playbooks/client-communication.md` punya frasa per situasi (delay, scope creep, menagih, komplain, sign-off, payment). Pakai sebagai dasar, sesuaikan konteks.

4. **Draft dengan aturan**:
   - Concise, to the point (client SG), warm secukupnya
   - Format default: **teks siap paste ke grup WhatsApp** (DPA+client bareng) — paragraf pendek, tanpa subject line/salam surat formal, tetap professional English. Kalau memang untuk dokumen formal terpisah (invoice, sign-off resmi), pakai format email.
   - Satu pesan satu tujuan; kebutuhan aksi eksplisit + tanggal (dengan SGT)
   - Bad news → selalu bersama mitigasi; minta maaf maksimal 1x
   - Scope tambahan → "yes, and here's the cost", bukan "no"
   - Rekomendasi jelas, bukan sekadar opsi ("I recommend A because…")
   - JANGAN membuat komitmen baru (tanggal/harga/fitur) yang belum dikonfirmasi Hari — tandai `[confirm: …]` kalau perlu

5. **Sajikan**: draft + 1–2 kalimat penjelasan tone yang dipakai & kenapa (ini bagian belajarnya Hari). Kalau situasinya sensitif, beri 2 varian (lebih tegas / lebih lunak).

6. **Setelah final**: berikan versi siap paste untuk **grup WA** (kanal utama — belum ada otomasi, Hari paste manual). JANGAN tawarkan kirim via Slack — Slack cuma internal tim, tidak menjangkau client/DPA. Arsipkan pesan penting ke `projects/<nama>/client-comms/{tanggal}-{topik}.md`. Kalau mengandung keputusan → ingatkan catat di `decisions.md`.
