---
name: daily
description: Ringkasan pagi PM — tarik task & deadline dari ClickUp + _INDEX.md, deteksi overdue & blocker, draft standup untuk Slack. Pakai setiap pagi kerja.
---

# /daily

Briefing pagi dalam 2 menit.

## Langkah

1. **Kumpulkan data**:
   - `projects/_INDEX.md` — semua project aktif, deadline, milestone
   - ClickUp via MCP: task due hari ini / minggu ini / overdue, task yang lama tidak bergerak (in progress > 3 hari tanpa update)
   - `projects/*/risks.md` — risiko berstatus aktif
   - (Kalau MCP off: pakai data file lokal saja + beri catatan)

2. **Susun briefing** (Bahasa Indonesia, ringkas):
   ```
   ☀️ Daily Brief — {tanggal}

   🔴 Perlu aksi hari ini
   - {overdue / deadline hari ini / blocker menginap}

   🟡 Deadline dekat (≤3 hari)
   - {task + project + tanggal}

   👀 Perlu di-follow-up
   - {task diam >3 hari — siapa PIC-nya}
   - {menunggu client: konten/feedback yang belum datang}

   📅 Milestone terdekat per project
   - {project}: {milestone} — {tanggal} ({on track?})
   ```

3. **Sarankan 3 prioritas utama Hari hari ini** — spesifik, bukan generik. (Mis. "kejar feedback design ke Jane — sudah 4 hari" bukan "follow up client".)

4. **Draft standup** untuk Slack channel tim (kalau Hari mau) — format singkat: fokus hari ini, blocker yang sedang dikejar, info penting. **Tampilkan draft → konfirmasi → baru kirim via Slack MCP.** Tanya channel tujuan saat pertama kali, ingat untuk seterusnya (catat di CLAUDE.md bagian konvensi bila Hari setuju).

5. Kalau ada perubahan status yang terdeteksi (mis. deadline lewat) → tawarkan update `_INDEX.md` sekalian.
