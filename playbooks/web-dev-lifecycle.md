# Playbook: Siklus Hidup Project Web Dev

> Jawaban untuk: "Project web dev masuk — langkah pertama apa?"
> 9 fase, tiap fase punya tujuan, checklist, deliverable, dan jebakan umum.

## Peta Besar

```
1. Discovery → 2. Proposal & Estimasi → 3. Kickoff → 4. Design →
5. Development → 6. Internal QA → 7. UAT → 8. Launch → 9. Handover & Maintenance
```

Aturan emas: **tiap fase punya gerbang keluar (exit gate)** — jangan lanjut fase berikutnya sebelum gerbang fase ini tertutup. Skip gerbang = bayar mahal belakangan.

---

## Fase 1 — Discovery (menggali kebutuhan)

**Tujuan**: paham masalah bisnis client, bukan cuma daftar fitur yang mereka minta.

**Checklist**:
- [ ] Meeting/call discovery dengan client — pakai daftar pertanyaan di [requirement-gathering.md](requirement-gathering.md)
- [ ] Identifikasi: tujuan bisnis, target user, metrik sukses versi client
- [ ] Identifikasi decision maker vs day-to-day contact (lihat stakeholders template)
- [ ] Tanya deadline & alasan deadline-nya (event? campaign? budget cycle?)
- [ ] Tanya budget range (menentukan solusi yang realistis)
- [ ] Cek aset existing: brand guide, konten, sistem lama, akses

**Deliverable**: catatan discovery → jadi bahan `brief.md` (via `/kickoff`)
**Exit gate**: kamu bisa menjelaskan ulang kebutuhan client dalam 3 kalimat dan client bilang "yes, exactly".
**Jebakan**: langsung bahas solusi/teknologi sebelum paham masalah; percaya "requirement sudah jelas kok" dari email 5 baris.

## Fase 2 — Proposal & Estimasi

**Tujuan**: kesepakatan scope, harga, timeline — tertulis.

**Checklist**:
- [ ] Draft scope: in-scope, **out-of-scope eksplisit**, deliverables
- [ ] Estimasi bersama dev (lihat [estimation-timeline.md](estimation-timeline.md)) + buffer 20–30%
- [ ] Tentukan jumlah putaran revisi per fase (mis. 2x design, 2x UAT) — tulis di proposal
- [ ] Term pembayaran (mis. 40% DP, 40% UAT, 20% launch)
- [ ] Kirim proposal EN → follow up maks 3 hari kerja

**Exit gate**: proposal disetujui tertulis (email "approved" cukup) + DP masuk (kalau berlaku).
**Jebakan**: mulai kerja sebelum kesepakatan tertulis; estimasi sendirian tanpa dev; lupa tulis out-of-scope → semua "kecil kok, tambahin dong" jadi wajib.

## Fase 3 — Kickoff

**Tujuan**: semua orang (client + tim) tahu apa, siapa, kapan.

**Checklist**:
- [ ] `/kickoff <nama>` → folder project + brief
- [ ] `/prd <nama>` → PRD lengkap → **kirim ke client untuk approval**
- [ ] `/breakdown <nama>` → task di ClickUp dengan acceptance criteria
- [ ] `/timeline <nama>` → milestone + deadline (termasuk **deadline milik client**: konten, feedback, UAT)
- [ ] Kickoff meeting internal: walkthrough PRD ke tim, tanya-jawab, konfirmasi estimasi
- [ ] Kickoff call dengan client: perkenalan tim, cara komunikasi (channel, ritme update), timeline, apa yang dibutuhkan dari client & kapan
- [ ] Setup: repo, staging, channel Slack project

**Exit gate**: PRD approved client (tertulis) + tim paham task-nya + timeline disepakati dua arah.
**Jebakan**: PRD "approved" secara lisan doang; client tidak tahu mereka punya deadline juga (konten! feedback!).

## Fase 4 — Design

**Checklist**:
- [ ] Wireframe/mockup halaman kunci dulu (jangan semua) → validasi arah dengan client
- [ ] Feedback design: kumpulkan dari SATU orang di sisi client (bukan komite), maks putaran sesuai kesepakatan
- [ ] Design approved tertulis sebelum slicing/development

**Exit gate**: design sign-off tertulis.
**Jebakan**: feedback dari banyak orang client yang saling bertentangan; revisi design saat development sudah jalan.

## Fase 5 — Development

**Checklist**:
- [ ] Task jalan sesuai ClickUp; standup/check-in rutin (lihat [team-coordination.md](team-coordination.md))
- [ ] `/daily` tiap pagi: deadline dekat, blocker, follow-up
- [ ] `/status-report` mingguan ke client — **proaktif, jangan tunggu ditanya**
- [ ] Demo progress ke client di tiap milestone (staging link) — feedback dini murah, feedback telat mahal
- [ ] Perubahan scope → change request flow (catat di `decisions.md`, nilai dampak, minta approval)

**Exit gate**: semua task "Must" selesai di staging.
**Jebakan**: silent mode 3 minggu lalu kaget di akhir; menerima scope creep kecil-kecilan tanpa mencatat dampaknya.

## Fase 6 — Internal QA

**Checklist**: (detail di [qa-uat-delivery.md](qa-uat-delivery.md))
- [ ] Test vs acceptance criteria tiap task — bukan sekadar "kelihatannya jalan"
- [ ] Cross-browser/device sesuai PRD; form, validasi, error state; performa dasar
- [ ] Bug prioritas tinggi = 0 sebelum lanjut UAT

**Exit gate**: QA checklist lolos. **JANGAN kasih client barang yang belum kamu tes sendiri** — merusak trust dan menaikkan revision rate.

## Fase 7 — UAT (User Acceptance Testing)

**Checklist**:
- [ ] Kirim UAT plan ke client: periode, cara lapor, definisi bug vs change request (pakai template [uat-checklist.md](../templates/uat-checklist.md))
- [ ] Triage temuan harian: bug → fix; change request → estimasi dampak → keputusan client
- [ ] Sign-off tertulis di akhir

**Exit gate**: client sign-off tertulis.
**Jebakan**: UAT tanpa batas waktu; semua temuan diperlakukan sebagai bug gratis; decision maker baru muncul di UAT bawa opini baru (cegah dari fase 3–4!).

## Fase 8 — Launch

**Checklist**:
- [ ] Launch checklist teknis: DNS, SSL, backup, analytics, redirect, SEO dasar, form ke email yang benar
- [ ] Rencana rollback kalau ada masalah
- [ ] Launch di hari yang aman (Selasa–Kamis pagi; hindari Jumat sore!)
- [ ] Monitoring 24–48 jam pertama
- [ ] Kabari client: "We're live 🎉" + apa yang dimonitor

**Jebakan**: launch Jumat sore; lupa arahkan form/email produksi; tidak ada backup.

## Fase 9 — Handover & Maintenance

**Checklist**:
- [ ] Handover doc (template [handover-doc.md](../templates/handover-doc.md)): akses, cara update konten, warranty terms
- [ ] Walkthrough call dengan client
- [ ] `/retro <nama>` internal → lessons learned → update playbook/template
- [ ] Arsipkan project di `_INDEX.md`
- [ ] Minta testimonial saat client sedang puas
- [ ] (SaaS/retainer) definisikan SLA & scope maintenance tertulis

---

## Cheat Sheet: "Project masuk hari ini, aku ngapain?"

1. **Hari 1**: baca semua materi dari client → `/kickoff` → list pertanyaan discovery → jadwalkan call.
2. **Setelah call**: lengkapi brief → `/prd` → kirim PRD + open questions ke client.
3. **Setelah PRD approved**: `/breakdown` (task ke ClickUp) → `/timeline` → kickoff meeting tim → kickoff call client.
4. **Selama jalan**: `/daily` tiap pagi, `/status-report` tiap Jumat, `/risk-check` tiap Senin.
