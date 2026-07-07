---
name: status-report
description: Generate status report mingguan untuk client (EN) dari catatan project + progress real ClickUp — selesai, in progress, blocker, kebutuhan dari client. Pakai tiap Jumat atau saat client minta update.
---

# /status-report [nama-project]

Laporan progres yang membuat client tenang — sebelum mereka bertanya.

## Langkah

1. **Tentukan project**: dari argumen, atau tanya kalau kosong (tampilkan daftar project aktif dari `_INDEX.md`).

2. **Kumpulkan data**:
   - ClickUp via MCP: task selesai minggu ini, in progress, yang akan dikerjakan minggu depan, overdue
   - `projects/<nama>/timeline.md`: posisi vs milestone
   - `risks.md` + `decisions.md`: hal yang perlu disebut
   - Status report sebelumnya di `status-reports/` (konsistensi: apa yang minggu lalu dijanjikan "next week"? — harus ter-address!)

3. **Draft report EN** pakai `templates/status-report-client-en.md`, format teks siap paste ke **grup WhatsApp (DPA+client)** — paragraf pendek, tanpa subject line, tetap professional English:
   - Bahasa hasil/outcome, bukan aktivitas teknis ("Product pages are live on staging" ✅, "worked on frontend components" ❌)
   - Overall status jujur (On Track / Needs Attention / At Risk) — jangan hijau terus lalu meledak
   - "Needs Your Input" selalu ada + deadline-nya; kosong → "Nothing needed from your side this week 👍"
   - Timeline: kalau ada slip, sebut + mitigasi (bad news early — `playbooks/client-communication.md`)
   - Tanggal + zona waktu (SGT)

4. **Review dengan Hari**: tampilkan draft + 1 kalimat catatan tone. Iterasi.

5. **Simpan** ke `projects/<nama>/status-reports/{tanggal}.md`.

6. **Kirim**: berikan versi siap paste untuk **grup WA** (default — ini kanal utama ke DPA & client). WhatsApp belum terintegrasi MCP, jadi Hari yang paste manual. JANGAN sarankan kirim via Slack — Slack tidak menjangkau client/DPA. Versi email hanya kalau memang ada thread email formal terpisah untuk project ini.

7. **Update `_INDEX.md`** kalau status/milestone berubah.
