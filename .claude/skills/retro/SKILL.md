---
name: retro
description: Retrospective pasca-project — angka akhir, what went well/wrong, lessons learned menjadi aksi konkret, update playbook/template, arsipkan project. Pakai saat project selesai (atau di titik tengah project panjang).
---

# /retro <nama-project>

Setiap project selesai harus membuat project berikutnya lebih mudah.

## Langkah

1. **Kumpulkan data objektif dulu** (sebelum opini):
   - `timeline.md`: deadline meleset berapa? milestone mana yang slip?
   - ClickUp via MCP: task yang bolak-balik reopened; estimasi vs aktual (kalau tercatat)
   - `risks.md`: risiko mana yang benar terjadi? ada yang tidak terprediksi?
   - `decisions.md`: keputusan mana yang belakangan terbukti salah/benar?
   - Putaran revisi aktual (design & UAT) vs jatah
   - Feedback/kepuasan client (tanya Hari kalau tidak tertulis)

2. **Fasilitasi refleksi** dengan Hari (blameless — cari penyebab sistemik, bukan orang):
   - What went well? (pertahankan)
   - What went wrong + akar masalahnya (5 whys ringan — berhenti di penyebab yang bisa diubah proses)
   - Kalau tim ikut retro: tawarkan agenda sesi retro tim 30 menit

3. **Tulis `retro.md`** di folder project pakai `templates/retro.md` — bagian terpenting: **Lessons Learned → Aksi Konkret** (pelajaran tanpa aksi = nostalgia).

4. **Terapkan pelajaran ke sistem** (ini yang membedakan retro berguna):
   - Pelajaran berlaku umum → usulkan edit spesifik ke playbook/template terkait (tampilkan diff, konfirmasi, terapkan)
   - Pola client tertentu → update `clients/<nama>.md`

5. **Arsipkan**: pindahkan baris project ke tabel "Selesai" di `_INDEX.md` + tandai retro ✅.

6. **Ingatkan 2 hal**: minta testimonial client (timing terbaik = saat baru launch sukses), dan catat pencapaian project ini di `knowledge/kpi-tracker.md` sebagai bukti KPI (delivery, revision rate, satisfaction).
