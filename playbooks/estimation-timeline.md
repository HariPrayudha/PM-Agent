# Playbook: Estimasi & Timeline

> KPI terkait: Fast delivery, Lead & manage timeline & expectation.
> Prinsip inti: **estimasi milik dev, komitmen milik PM**. Kamu boleh menantang estimasi, tapi jangan menimpanya.

## Proses Estimasi yang Benar

1. **Breakdown dulu, estimasi kemudian.** Estimasi "1 website = 3 minggu" selalu salah. Estimasi per epic/task (hasil `/breakdown`) jauh lebih akurat.
2. **Yang mengerjakan yang mengestimasi.** Kamu ex-dev — godaan terbesar adalah mengestimasi sendiri ("ah ini 2 jam"). Jangan: (a) kamu tidak tahu konteks & kecepatan tiap dev, (b) dev tidak akan merasa memiliki deadline yang bukan estimasinya.
3. **Tanya range, bukan angka.** "Berapa lama?" → jawaban optimis. "Best case berapa, worst case berapa?" → jawaban jujur. Pakai angka mendekati worst untuk komitmen.
4. **Estimasi = effort murni.** Meeting, review, revisi, deploy, context-switching belum termasuk → itulah gunanya buffer.

## Buffer Rule

```
Komitmen ke client = estimasi dev × 1.2 s/d 1.3
```

- Tim baru / scope masih abu-abu / banyak integrasi pihak ketiga → pakai 1.3+
- Tim sudah terbiasa + scope sangat jelas → 1.2 cukup
- **Jangan umumkan buffer ke tim sebagai "waktu santai"** — deadline internal tim = estimasi asli; buffer adalah milikmu untuk menyerap kejutan.
- Selesai lebih cepat dari komitmen = kamu terlihat hebat. Telat dari komitmen = trust rusak. Under-promise, over-deliver.

## Menyusun Timeline (via `/timeline`)

1. Urutkan epic berdasar dependensi (design → dev → QA → UAT).
2. Petakan kapasitas nyata: siapa yang tersedia, berapa %, potong hari libur & project paralel.
3. Tetapkan milestone yang **bermakna bagi client** (bisa dilihat/dites), bukan istilah teknis.
4. **Deadline client juga masuk timeline**: konten, feedback design, UAT — tulis eksplisit. Kalau client telat, timeline geser — dan itu tertulis sejak awal.
5. Sisakan jeda antara "dev selesai" dan "UAT mulai" untuk internal QA. Jangan dihimpit.

## Kalau Deadline Client Tidak Realistis

Jangan langsung "ok" (delivery gagal) atau "tidak bisa" (terkesan tidak kooperatif). Tawarkan trade-off — pilih 2 dari 3: **scope, waktu, kualitas/biaya**.

Template EN:

> "I've reviewed the timeline with the team. To deliver the full scope with the quality you expect, we'd need until {date}. If {original date} is fixed, I see two options:
> **Option A** — Launch on {original date} with the core features ({list}), and roll out {deferred features} by {date2}.
> **Option B** — Full scope by {date}, adding {extra resource/cost} to compress the schedule.
> My recommendation is Option A, because {reason}. Which direction works best for you?"

Kenapa format ini kuat: kamu tidak bilang "tidak", kamu memberi **pilihan yang semuanya bisa kamu tepati** + rekomendasi (client SG menghargai decisiveness).

## Saat Timeline Mulai Geser (di tengah project)

1. **Deteksi dini** — `/daily` & `/risk-check`; task yang "90% done" selama 3 hari = red flag.
2. **Jangan diam.** Slip 2 hari yang dikabarkan hari ini lebih baik daripada slip 1 hari yang dikabarkan saat deadline. Bad news early (lihat [client-communication.md](client-communication.md)).
3. Sebelum kabari client, siapkan: penyebab (jujur, tanpa drama), dampak, **rencana mitigasi**, tanggal baru yang SUDAH termasuk buffer (jangan geser dua kali!).
4. Catat di `decisions.md` + update `timeline.md` + `_INDEX.md`.

## Anti-pattern

- ❌ Estimasi dijadikan komitmen tanpa buffer.
- ❌ Menekan dev "masa segitu lama?" — hasilnya estimasi bohong yang meledak nanti. Kalau ragu, minta breakdown lebih detail, bukan angka lebih kecil.
- ❌ Timeline geser tapi `_INDEX.md`/client tidak dikabari — timeline dokumen ≠ timeline nyata.
- ❌ Menggeser deadline lebih dari sekali untuk alasan yang sama. Sekali geser, geser cukup jauh.
