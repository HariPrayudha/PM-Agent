---
name: meeting-notes
description: Rapikan catatan meeting mentah menjadi MoM terstruktur dengan action items (siapa-apa-kapan), simpan ke folder project, plus ringkasan EN untuk client bila perlu. Pakai setelah setiap meeting.
---

# /meeting-notes

Catatan mentah → MoM yang bisa ditindaklanjuti.

## Langkah

1. **Minta input**: paste catatan mentah / poin-poin / transkrip. Tanya: project mana, meeting dengan siapa (internal / client), tanggal & jam.

2. **Strukturkan** pakai `templates/meeting-notes.md`:
   - Pisahkan: diskusi vs KEPUTUSAN (keputusan harus eksplisit)
   - Action items: setiap item WAJIB punya PIC (1 nama) + deadline (tanggal absolut) — kalau di catatan tidak ada, tanya Hari atau tandai `[PIC?]` `[kapan?]`
   - Hal yang ditunda → bagian Parkir

3. **Simpan** ke `projects/<nama>/meeting-notes/{tanggal}-{topik}.md`.

4. **Tindak lanjut** (tawarkan, jangan otomatis):
   - Keputusan penting → tambahkan ke `decisions.md` project
   - Action items untuk tim → buat task ClickUp via MCP (preview → konfirmasi)
   - Meeting client → draft ringkasan EN <24 jam ("Thanks for your time today — here's a quick summary of what we agreed on: …") siap kirim via Slack/email. Ini kebiasaan yang WAJIB dijaga (jejak tertulis + cegah salah paham).
   - Deadline/scope berubah → ingatkan update `timeline.md` + `_INDEX.md`.
