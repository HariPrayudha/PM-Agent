---
name: risk-check
description: Audit risiko satu atau semua project — deadline slip, scope creep, task menggantung, revisi berulang, dependensi client telat — dengan rekomendasi aksi konkret. Pakai tiap Senin atau saat firasat tidak enak.
---

# /risk-check [nama-project]

Temukan masalah selagi masih kecil.

## Langkah

1. **Scope**: project dari argumen, atau SEMUA project aktif di `_INDEX.md` kalau kosong.

2. **Kumpulkan sinyal** per project:
   - `timeline.md`: milestone vs hari ini — ada yang lewat/mepet?
   - ClickUp via MCP: task overdue; task "in progress" >3 hari tanpa update; beban task per orang (ada yang kelebihan?); task tanpa assignee/due date
   - `risks.md`: risiko aktif — ada yang statusnya berubah?
   - `decisions.md` + `client-comms/`: permintaan client di luar PRD yang belum lewat change request flow (scope creep!)
   - `status-reports/`: janji "next week" yang tidak terpenuhi ≥2x (pola slip)
   - Dependensi client: konten/feedback/UAT yang ditunggu — sudah berapa lama?

3. **Nilai tiap temuan**: kemungkinan × dampak (Rendah/Sedang/Tinggi) — jangan semua dianggap darurat; PM yang berteriak terus akan diabaikan.

4. **Laporkan** (ID, ringkas):
   ```
   🔍 Risk Check — {tanggal}

   🔴 Butuh aksi sekarang
   - {temuan} → REKOMENDASI: {aksi spesifik + siapa + kapan}

   🟡 Pantau ketat
   - {temuan} → {early action yang murah}

   🟢 Sehat
   - {project yang aman — sebut singkat, biar tenang}
   ```
   Setiap rekomendasi harus actionable hari ini (mis. "kirim reminder konten ke Jane — draft EN sudah kusiapkan di bawah"), bukan "perlu diperhatikan".

5. **Update `risks.md`** project terkait (risiko baru / status berubah) + `_INDEX.md` (kolom Risiko & status 🟢🟡🔴) — tawarkan dulu, jangan diam-diam.

6. Kalau ada risiko yang butuh komunikasi client (delay warning, reminder dependensi) → tawarkan lanjut ke `/client-email`.
