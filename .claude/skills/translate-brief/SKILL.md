---
name: translate-brief
description: Terjemahkan requirement client (EN) menjadi analisis kebutuhan + pertanyaan klarifikasi + task breakdown Bahasa Indonesia untuk tim, dengan opsi push ke ClickUp. Pakai saat menerima email/message/change request dari client.
---

# /translate-brief

Requirement EN masuk → tim tahu persis harus ngapain.

## Langkah

1. **Minta input**: paste requirement client (email/Slack/dokumen EN). Tanya project mana (untuk konteks — baca brief/PRD project itu kalau ada).

2. **Analisis 3 lapis** (tampilkan ke Hari, Bahasa Indonesia):
   - **Yang diminta** (literal): daftar poin yang client tulis
   - **Yang kemungkinan dibutuhkan** (intent): masalah bisnis di baliknya — pakai lensa `playbooks/requirement-gathering.md` (diminta ≠ dibutuhkan)
   - **Yang ambigu/hilang**: hal yang bisa ditafsirkan ganda atau belum dijelaskan → jadi pertanyaan klarifikasi

3. **Cek terhadap scope**: kalau project sudah punya PRD — apakah permintaan ini in-scope, revisi, atau change request? Flag tegas kalau change request (lihat `playbooks/qa-uat-delivery.md`) + ingatkan flow-nya: estimasi dampak dulu, jangan langsung dikerjakan.

4. **Hasilkan output**:
   a. **Pertanyaan klarifikasi untuk client** (EN, siap kirim) — hanya yang benar-benar perlu; jangan tunda pekerjaan untuk hal yang bisa diasumsikan dengan aman (tulis asumsinya).
   b. **Task breakdown untuk tim** (ID) — format task `playbooks/team-coordination.md`: judul, konteks, detail, acceptance criteria. Sertakan asumsi yang diambil.

5. **Opsi push ke ClickUp** via MCP (preview → konfirmasi → buat). Fallback: markdown copy-paste.

6. **Arsipkan**: kalau ini komunikasi penting, simpan requirement asli + hasil analisis ke `projects/<nama>/client-comms/{tanggal}-{topik}.md`.
