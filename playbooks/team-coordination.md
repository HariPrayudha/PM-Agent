# Playbook: Koordinasi Tim & Cross-Division

> KPI terkait: Clear coordination, Fast delivery, Able to lead & manage team.
> Prinsip inti: sebagai ex-dev, kekuatanmu = bisa bicara bahasa dev. Bahayamu = ikut ngoding & micromanage teknis. **Tugasmu sekarang: hilangkan blocker, jaga arah, lindungi fokus tim.**

## Transisi Dev → PM: yang berubah

| Dulu (dev) | Sekarang (PM) |
|---|---|
| Menyelesaikan task | Memastikan SEMUA task selesai (oleh orang lain) |
| Estimasi untuk diri sendiri | Fasilitasi estimasi tim |
| Dinilai dari kode | Dinilai dari delivery, komunikasi, kepuasan client |
| Ganggu = context switch | Kamu adalah **perisai context switch** untuk tim |
| Solusi teknis terbaik | Solusi yang cukup baik, tepat waktu, sesuai budget |

Godaan terbesar: mengambil alih task yang lambat ("biar cepat aku aja"). Sekali-sekali darurat boleh; sebagai kebiasaan = kamu jadi bottleneck dan tim tidak berkembang.

## Format Task ClickUp yang Baik (dipakai `/breakdown`)

Setiap task WAJIB punya:

```
Judul   : [Modul] Kata kerja + objek — "[Checkout] Implementasi validasi alamat"
Deskripsi:
  Konteks   : kenapa task ini ada (1–2 kalimat, link ke PRD section)
  Detail    : apa yang harus dibuat, dalam bahasa Indonesia yang jelas
  Referensi : link design/PRD/API doc
Acceptance Criteria (WAJIB — penentu "selesai"):
  - [ ] User bisa X dan melihat Y
  - [ ] Error state Z ditangani
Estimasi  : {dari dev}
Prioritas : Urgent/High/Normal/Low
Due date  : {tanggal}
Assignee  : {1 orang — bukan 2}
```

**Acceptance criteria adalah senjata #1 melawan revisi**: dev tahu kapan selesai, QA tahu apa yang dites, tidak ada "oh maksudku bukan gitu".

## Ritme Koordinasi

- **Standup harian** (Slack async cukup, 15 menit kalau call): kemarin, hari ini, blocker. Gunakan `/daily` untuk menyiapkan & memposting.
- **Blocker = prioritas #1 PM.** Dev lapor blocker → target respon <1 jam (walau jawabannya "aku kejar ke client dulu"). Blocker menginap = hari produktif hilang.
- **Review milestone internal** sebelum demo client — jangan pernah demo barang yang belum kamu lihat sendiri.
- **1-on-1 ringan** tiap 1–2 minggu dengan tiap dev: bukan status task, tapi "ada yang menghambat? ada yang pengen dipelajari?" — ini bedanya lead vs pembagi tugas.

## Prinsip Delegasi & Kepemimpinan

1. **Delegasikan hasil, bukan cara.** "Aku butuh halaman checkout sesuai AC ini sebelum Kamis" ✅ — bukan "pakai useReducer di sini" ❌. Dev senior terutama, hargai otonominya.
2. **Kredit ke tim, tanggung jawab ke kamu.** Demo sukses = "tim yang hebat". Ada masalah di depan client = "saya yang akan bereskan". Ini membangun loyalitas tercepat.
3. **Jangan jadi kurir pesan.** Terjemahkan: requirement client EN → konteks + task ID yang jelas (pakai `/translate-brief`); keluhan teknis dev → dampak bisnis untuk client.
4. **Keputusan teknis milik dev lead; keputusan prioritas & scope milikmu** (dengan input mereka). Jelas batasnya = tidak saling injak.
5. **Feedback ke individu secara privat, apresiasi boleh publik.**

## Koordinasi dengan Tim Creative (Design)

Prinsip yang sama dengan dev — delegasikan HASIL, bukan CARA — tapi bahasanya beda:

**Format task design** (dipakai `/task` & `/breakdown` untuk design job):

```
Judul      : [Brand/Project] Deliverable — "[Acme] Hero banner homepage"
Objective  : untuk apa & pesan utamanya (1–2 kalimat + konteks bisnis)
Deliverable: format file + dimensi + varian + kanal — EKSPLISIT
             ("banner web" tanpa dimensi = revisi pasti)
Referensi  : link visual + APA yang disukai dari referensi itu
             + yang harus DIHINDARI
Aset       : brand guideline, logo, copy (dari siapa, status)
Revisi     : jatah putaran (default 2 setelah konsep terpilih)
Due date   : konsep awal & final (dua tanggal, bukan satu)
```

Job design besar/multi-deliverable → pakai `templates/design-brief.md` penuh.

**Aturan feedback design** (ini area revisi paling liar):
- Feedback harus **spesifik & actionable**: "logo kekecilan saat dilihat di mobile" ✅, "kurang wow / kurang pop" ❌ — kalau client kasih feedback kabur, tugasmu menggali dulu ("what specifically feels off — the colors, the layout, the font?") SEBELUM diteruskan ke designer.
- **Konsolidasi feedback client jadi 1 batch** sebelum diteruskan — designer menerima 1 daftar, bukan tetesan 5 chat.
- Feedback soal **selera pribadimu bukan feedback** — kamu bukan target audience-nya. Kawal ke objective & referensi yang disepakati.
- Perubahan arah kreatif setelah konsep di-approve ("coba yang beda sekalian deh") = change request, bukan revisi.
- Approve konsep dulu (arah), baru detail — jangan biarkan client mengomentari detail di tahap konsep.

**Handoff design → dev** (kamu jembatan dua dunia ini):
- Pastikan designer menyerahkan: file source rapi (layer bernama), aset ter-export sesuai kebutuhan dev (format, ukuran, @2x), spek interaksi/state (hover, error, empty state — yang sering lupa!).
- Dev menemukan kondisi yang tidak ada design-nya → kembalikan ke designer, jangan biarkan dev mengarang.

## Koordinasi Cross-Division

Untuk design, marketing, divisi lain:
- **Kirim konteks, bukan perintah**: divisi lain tidak paham project-mu; sertakan latar 2 kalimat + kebutuhan spesifik + deadline + kenapa deadline-nya segitu.
- **Minta komitmen tanggal secara eksplisit** ("bisa selesai kapan?") dan catat — dependensi lintas divisi masuk `timeline.md` seperti dependensi client.
- **Eskalasi yang sehat**: kalau dependensi telat & mengancam deadline: (1) ingatkan langsung, (2) tawarkan bantuan mempermudah, (3) baru eskalasi ke atasan divisi itu — dengan nada "butuh bantuan prioritas", bukan "melaporkan".
- Buat 1 channel Slack per project, undang semua pihak lintas divisi → semua diskusi project di satu tempat, bukan tersebar di DM.

## Anti-pattern

- ❌ Micromanage cara coding (kamu ex-dev — ini jebakan terbesar).
- ❌ Meeting yang bisa jadi pesan Slack. Setiap meeting harus punya agenda & keputusan.
- ❌ Task tanpa acceptance criteria — sumber utama revisi & konflik "ini belum selesai".
- ❌ Semua komunikasi client hanya lewat kamu tanpa konteks ke tim → tim tidak paham "kenapa", kualitas keputusan kecil mereka menurun. Bagikan konteks bisnis.
- ❌ Menerima "hampir selesai" tanpa definisi. Tanya: "yang tersisa apa saja, dan butuh berapa lama?"
