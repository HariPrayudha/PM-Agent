---
name: breakdown
description: Pecah PRD menjadi epics & tasks (deskripsi ID untuk tim, acceptance criteria, estimasi, prioritas) lalu push langsung ke ClickUp via MCP setelah konfirmasi. Pakai setelah PRD approved.
---

# /breakdown <nama-project>

PRD → daftar task siap kerja di ClickUp.

## Langkah

1. **Baca** `projects/<nama>/prd.md` (kalau belum ada → arahkan ke `/prd` dulu). Cek status PRD — kalau belum approved client, ingatkan risikonya, tapi lanjut kalau Hari mau.

2. **Susun breakdown** dalam struktur:
   - **Epics** = modul/halaman besar (mis. "Setup & Infrastruktur", "Halaman Produk", "Checkout", "CMS", "QA & Launch")
   - **Tasks** per epic, masing-masing mengikuti format `playbooks/team-coordination.md`:
     - Judul: `[Modul] Kata kerja + objek`
     - Deskripsi ID: konteks (kenapa), detail (apa), referensi (link PRD section/design)
     - Acceptance criteria (WAJIB, dari PRD)
     - Prioritas MoSCoW → mapping ke prioritas ClickUp (Must=High, Should=Normal, Could=Low)
     - Estimasi: KOSONGKAN atau tandai "perlu estimasi dev" — jangan mengarang estimasi; ingatkan Hari minta estimasi tim (prinsip: estimasi milik dev)
   - Sertakan task non-dev yang sering terlupa: setup repo/staging, input konten, internal QA, UAT prep, launch checklist.

3. **Tampilkan seluruh breakdown ke Hari** dalam bentuk ringkas (tabel per epic) → minta review: ada yang kurang? urutan oke? Iterasi sampai Hari puas.

4. **Push ke ClickUp** (hanya setelah konfirmasi eksplisit):
   - Tanya Hari: push ke Space/Folder/List ClickUp yang mana? (tampilkan pilihan dari MCP kalau bisa list)
   - Buat task via ClickUp MCP: judul, deskripsi (konteks+AC), prioritas. Assignee & due date bisa menyusul (via `/timeline`).
   - Tampilkan hasil: berapa task terbuat + link.
   - **Kalau MCP tidak tersedia/error**: output markdown lengkap siap copy-paste + ingatkan autentikasi via `/mcp` (lihat SETUP.md).

5. **Simpan salinan** breakdown ke `projects/<nama>/breakdown.md` (jejak lokal).

6. **Tutup dengan langkah berikutnya**: `/timeline <nama>` — susun milestone & due date setelah estimasi dev masuk. Ingatkan Hari jadwalkan sesi estimasi dengan tim.
