---
name: task
description: Intake universal pekerjaan masuk yang BUKAN project baru penuh — pembaruan/bug/change request di project existing, atau design job untuk tim creative. Klasifikasi, format task yang benar, push ke ClickUp. Termasuk registrasi ringan project lama yang belum tercatat.
---

# /task [nama-project]

Pekerjaan masuk (apapun bentuknya) → task ClickUp yang benar, tercatat rapi. Jalur cepat — bukan semua pekerjaan butuh `/kickoff` + PRD.

## Langkah

1. **Terima input**: minta Hari paste permintaannya — umumnya dari **chat grup WhatsApp** (DPA/client), bisa juga email, ClickUp comment, atau ide internal. EN atau ID. Tanya project terkait kalau tidak disebut — tampilkan daftar dari `projects/_INDEX.md`.

2. **Kalau project belum terdaftar** (project lama/existing yang belum ada foldernya):
   - Tawarkan **registrasi ringan** (bukan kickoff penuh): buat `projects/<nama>/` dari `_TEMPLATE`, isi brief singkat retroaktif — cukup: sistemnya apa, stack, status (live/maintenance), kontak client, link repo & ClickUp list. Tanya seperlunya (1 putaran), sisanya tandai `{belum dicatat}`.
   - Tambah baris di `_INDEX.md` (tipe: Maintenance/Existing).
   - Kalau Hari menolak registrasi → tetap lanjut proses task, jangan memaksa.

3. **Baca konteks** yang ada: brief/PRD/design-brief project itu, `decisions.md`, task ClickUp terkait (via MCP — cari duplikat: jangan buat task yang sudah ada).

4. **Klasifikasi** permintaan (tampilkan penilaianmu + alasan):
   - **🐛 Bug** — tidak sesuai kesepakatan/spec semula → fix, prioritaskan sesuai dampak
   - **🔧 Pembaruan kecil** — dalam semangat scope/maintenance → langsung task
   - **📋 Change request** — di luar scope kesepakatan / butuh effort signifikan → INGATKAN flow: estimasi dampak dulu → approval client → baru kerjakan. Tawarkan draft balasan EN "yes, and here's the cost" (`playbooks/client-communication.md`)
   - **🎨 Design job** — untuk tim creative → format task creative
   Kalau satu permintaan berisi campuran → pecah jadi beberapa task dengan klasifikasi masing-masing.

5. **Susun task** sesuai jenis:
   - **Dev** (format `playbooks/team-coordination.md`): `[Modul] Kata kerja + objek`, konteks, detail ID, acceptance criteria, prioritas.
   - **Design/creative** (format section "Koordinasi dengan Tim Creative"): objective + konteks bisnis, deliverable dengan spek eksplisit (format, dimensi, varian, kanal), referensi visual, sumber copy/aset, jatah revisi, due date. Kalau job design besar/multi-deliverable → sarankan `templates/design-brief.md` penuh + `/kickoff` tipe design.
   - Requirement EN → deskripsi task tetap ID (maksud, bukan terjemahan literal — `knowledge/glossary.md`).

6. **Preview → konfirmasi → push ke ClickUp** via MCP (tanya list tujuan: list project atau list tim creative). Fallback: markdown copy-paste + ingatkan `/mcp`.

7. **Catat jejak**: permintaan penting/CR → arsip ke `projects/<nama>/client-comms/{tanggal}-{topik}.md`; keputusan scope → `decisions.md`; kalau deadline project terpengaruh → ingatkan update `timeline.md` + `_INDEX.md`.
