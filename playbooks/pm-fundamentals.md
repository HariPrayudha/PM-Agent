# Playbook: Fondasi Project Management

> Konsep dasar yang dipakai playbook lain. Dibaca sekali di awal, dirujuk saat butuh.
> Gaya belajar: tiap konsep dikaitkan ke analogi dev karena Hari ex-fullstack developer.

## Peran PM dalam satu kalimat

**Memastikan hal yang tepat dibangun oleh orang yang tepat pada waktu yang tepat — dan semua pihak tahu statusnya.** Kamu tidak mengerjakan task; kamu membuat task-task itu mungkin selesai.

## Agile / Scrum-lite / Kanban — praktis saja

Jangan terjebak ritual. Yang penting prinsipnya:

- **Iteratif > big bang**: rilis kecil sering (seperti CI/CD) > satu rilis raksasa. Feedback dini = koreksi murah.
- **Scrum-lite untuk project client**: milestone 1–2 mingguan sebagai "sprint", standup async harian, demo per milestone, retro di akhir. Tidak perlu story point/poker kalau tim kecil — estimasi jam/hari cukup.
- **Kanban untuk maintenance & SaaS internal**: kolom `Backlog → To Do → In Progress → Review → Done` di ClickUp; batasi WIP (dev pegang max 2 task aktif) — context switching adalah pembunuh throughput (kamu tahu ini sebagai dev).
- **Waterfall-ish tetap valid** untuk project fixed-scope-fixed-price: fase design → build → test dengan gerbang approval (lihat [web-dev-lifecycle.md](web-dev-lifecycle.md)). Kebanyakan project agency = hybrid: fase waterfall, eksekusi harian kanban.

## RACI — siapa melakukan apa

| Huruf | Arti | Contoh |
|---|---|---|
| **R**esponsible | Yang mengerjakan | Dev |
| **A**ccountable | Yang bertanggung jawab akhir (1 orang!) | PM / client decision maker |
| **C**onsulted | Dimintai pendapat sebelum keputusan | Dev lead, designer |
| **I**nformed | Cukup dikabari | Tim lain, management |

Analogi dev: R = assignee, A = code owner yang approve merge, C = reviewer, I = subscriber notifikasi. Dipakai saat keputusan besar (template stakeholders.md sudah menyertakan RACI ringkas).

## Stakeholder Mapping

Dua sumbu: **pengaruh** (bisa mengubah nasib project?) dan **kepentingan** (peduli detail?).

```
Pengaruh tinggi + kepentingan tinggi → Kelola erat (decision maker client)
Pengaruh tinggi + kepentingan rendah → Jaga puas (bos-nya client — muncul tiba-tiba!)
Pengaruh rendah + kepentingan tinggi → Rajin kabari (end user, day-to-day contact)
Pengaruh rendah + kepentingan rendah → Pantau saja
```

Kesalahan klasik: melayani yang cerewet (kepentingan tinggi) sambil mengabaikan yang diam tapi berkuasa — lalu si berkuasa muncul di UAT membawa opini baru. Identifikasi di `/kickoff`.

## Prioritization: MoSCoW

- **Must have** — tanpa ini, launch tidak ada artinya
- **Should have** — penting, tapi launch bisa jalan tanpanya
- **Could have** — nice to have, dikerjakan kalau waktu sisa
- **Won't have (this time)** — eksplisit TIDAK, sekarang. ← paling penting ditulis!

Dipakai di PRD & saat nego deadline (potong dari bawah: Could → Should).

## Triple Constraint (Scope–Time–Cost)

Segitiga besi: ubah satu sisi, sisi lain ikut bergerak. Client minta lebih cepat? → kurangi scope atau tambah biaya. Minta fitur tambah? → waktu/biaya naik. **Tidak pernah gratis.** Kualitas adalah yang hancur diam-diam kalau kamu pura-pura segitiga ini tidak ada. Ini dasar semua nego (lihat frasa di [estimation-timeline.md](estimation-timeline.md)).

## Komunikasi = 80% pekerjaan PM

- Informasi harus mengalir 3 arah: client ↔ kamu ↔ tim, dan kamu ↔ management. Kamu router-nya — dan router yang baik menerjemahkan protokol, bukan sekadar meneruskan paket.
- Tertulis > lisan untuk apapun yang menyangkut scope, uang, tanggal.
- Ringkas > lengkap. Status 5 baris yang dibaca > laporan 3 halaman yang di-skip.

## Istilah yang akan sering kamu dengar

**Scope creep** (scope membengkak pelan-pelan tanpa keputusan sadar) · **Milestone** (titik capaian bermakna) · **Deliverable** (hasil konkret yang diserahkan) · **Sign-off** (persetujuan formal) · **UAT** (client menguji & menerima) · **DoD** (definisi selesai) · **Blocker** (penghambat yang harus diangkat PM) · **Buffer** (cadangan waktu) · **Change request** (permintaan di luar scope disepakati) · **Post-mortem/retro** (evaluasi setelah selesai). Kamus lengkap EN↔ID: [knowledge/glossary.md](../knowledge/glossary.md).
