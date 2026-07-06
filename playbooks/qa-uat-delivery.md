# Playbook: QA, UAT & Delivery Berkualitas

> KPI terkait: Low revision rate, Fast delivery, High satisfaction.
> Prinsip inti: **revisi rendah bukan hasil dev yang sempurna, tapi hasil ekspektasi yang terkelola di setiap gerbang.**

## Definition of Done (DoD)

Sebuah task "selesai" hanya kalau:
1. Semua acceptance criteria di task ClickUp terpenuhi (dicek, bukan diasumsikan)
2. Sudah di-review (code review / peer check)
3. Jalan di staging, bukan cuma di lokal ("works on my machine" ≠ done)
4. Tidak merusak fitur lain yang sudah jalan (regression check ringan)

Tulis DoD ini di ClickUp sebagai checklist template. Task yang "done" lalu balik lagi = pseudo-progress yang merusak timeline.

## Bug vs Revisi vs Change Request — bedakan dengan tegas!

| Jenis | Definisi | Perlakuan |
|---|---|---|
| **Bug** | Tidak sesuai PRD/acceptance criteria | Fix gratis, prioritaskan |
| **Revisi** | Sesuai PRD tapi client ingin penyesuaian (dalam jatah putaran) | Kerjakan dalam jatah revisi yang disepakati |
| **Change request** | Di luar PRD / jatah revisi habis | Estimasi dampak → approval → baru kerjakan |

Tanpa pembedaan ini, semua jadi "revisi gratis" dan KPI low revision rate mustahil. Definisi ini harus tertulis di proposal & diulang saat UAT kickoff (lihat template [uat-checklist.md](../templates/uat-checklist.md)).

## Membatasi Revisi Secara Sehat

- **Jatah putaran feedback tertulis sejak proposal**: mis. design 2x, UAT 2x.
- **Feedback dikumpulkan per batch**, bukan tetes demi tetes: "Please collect all feedback in one list by {date}" — 10 feedback dalam 1 batch = 1 putaran; 10 feedback di 10 hari = kekacauan.
- **Satu suara dari client**: minta client konsolidasi feedback internal mereka dulu (terutama kalau stakeholder banyak).
- Feedback ke-3 dst setelah jatah habis → change request flow. Sampaikan dengan frasa "yes, and here's the cost" (lihat [client-communication.md](client-communication.md)).
- Akar revisi berulang biasanya: (a) PRD kabur → perbaiki di `/prd` berikutnya, (b) decision maker tidak terlibat sejak awal → perbaiki di stakeholder mapping, (c) demo terlalu jarang → feedback menumpuk di akhir.

## Alur Internal QA (sebelum client melihat apa pun)

1. QA vs acceptance criteria per task — sistematis, per halaman/fitur.
2. Smoke test alur kritis end-to-end (daftar → beli → bayar → email masuk).
3. Cek umum web: responsive (device utama sesuai PRD), form + validasi + error state, 404, link mati, gambar berat, console error, SEO/meta dasar, analytics terpasang.
4. Bug triage: High (blocker alur utama) wajib 0 sebelum UAT; Low bisa dicatat & dijadwalkan.
5. Baru setelah itu → kirim ke client untuk UAT.

**Aturan tak tertulis paling penting**: apapun yang client sentuh harus sudah kamu tes sendiri. Bug yang kamu temukan = profesional. Bug yang client temukan = menggerus trust + mengundang mereka mencari-cari bug lain.

## Alur UAT

1. Kirim UAT plan: periode (1–2 minggu), skenario uji, cara lapor, definisi bug vs CR, deadline feedback.
2. Triage temuan harian; update client tiap 1–2 hari selama UAT ("5 of 7 items resolved…").
3. Putaran fix → verifikasi → minta sign-off tertulis.
4. Temuan setelah deadline UAT → siklus berikutnya/maintenance (kecuali bug kritis).

## Delivery Cepat TANPA Mengorbankan Kualitas

- Potong **scope**, jangan potong **QA**. Launch dengan 80% fitur yang stabil > 100% fitur yang rapuh.
- Rilis bertahap (soft launch → full launch) mengurangi risiko & mempercepat feedback nyata.
- Demo sering ke client (tiap milestone) = koreksi arah dini = total waktu lebih pendek, walau terasa "mengganggu dev".
- Otomasi yang murah: deploy staging otomatis, checklist QA template — pengulangan manual adalah musuh kecepatan.
