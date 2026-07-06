# Playbook: SaaS Metrics, Marketing & Churn

> KPI terkait: Concern about SaaS marketing & churn rate.
> Tujuan: cukup paham untuk (a) ikut diskusi strategis produk SaaS internal, (b) membuat keputusan project yang sadar-metrik, (c) menjawab pertanyaan management. Bukan untuk jadi growth hacker.

## Metrik Inti — dengan analogi dev

| Metrik | Arti | Analogi dev |
|---|---|---|
| **MRR/ARR** | Pendapatan berulang bulanan/tahunan | Baseline throughput sistem |
| **Churn rate** | % pelanggan yang berhenti per periode | Memory leak — kecil tapi konstan = fatal |
| **Retention** | Kebalikan churn — % yang bertahan | Uptime |
| **Activation** | % signup yang mencapai "aha moment" (nilai pertama) | Onboarding sukses = request pertama yang berhasil |
| **CAC** | Biaya mendapatkan 1 pelanggan | Biaya provisioning |
| **LTV** | Total nilai pelanggan selama hidupnya | LTV harus > 3× CAC agar sehat |
| **NPS** | Seberapa mungkin user merekomendasikan (skor -100…100) | Rating kepuasan |

## Churn: yang paling perlu kamu pahami

**Rumus**: `churn rate = pelanggan yang berhenti dalam periode ÷ pelanggan di awal periode`
Contoh: awal bulan 200 pelanggan, 10 berhenti → churn 5%/bulan. Kedengarannya kecil? 5%/bulan ≈ **46% setahun** — hampir setengah pelanggan hilang. Benchmark SaaS B2B sehat: 3–7%/TAHUN (enterprise) sampai 3–5%/bulan (SMB early stage).

**Penyebab churn yang bisa kamu pengaruhi sebagai PM:**
1. **Onboarding buruk** → user tidak pernah mencapai nilai produk → pergi diam-diam. (Fitur onboarding = prioritas tinggi, bukan polesan.)
2. **Bug & downtime** di alur inti → alasan pindah paling cepat.
3. **Fitur yang diminta tidak kunjung datang** tanpa komunikasi roadmap.
4. **Involuntary churn**: kartu kredit gagal — recovery email/dunning sering ROI tertinggi dengan effort terendah.

**Sinyal sebelum churn** (leading indicator): login menurun, fitur inti tidak dipakai, tiket komplain naik. Kalau produk internal punya data ini → usulkan alert.

## Funnel Marketing SaaS (peta besar)

```
Awareness → Acquisition → Activation → Revenue → Retention → Referral
 (kenal)     (signup)      (aha!)       (bayar)    (bertahan)   (mengajak)
```

- Marketing bukan cuma awareness — **funnel bocor di activation/retention tidak bisa ditambal dengan iklan**. Menuangkan air ke ember bocor.
- Sebagai PM, kontribusimu terbesar di **activation & retention**: onboarding mulus, alur inti stabil, waktu-ke-nilai (time to value) sependek mungkin.
- Kanal umum SaaS B2B: content/SEO (murah, lambat), paid ads (cepat, mahal), cold outreach, partnership, product-led growth (free trial/freemium yang menjual dirinya).

## Cara pakai lensa ini dalam keputusan project harian

- Prioritas fitur: "fitur ini menggerakkan metrik mana?" Fitur yang tidak menggerakkan activation/retention/revenue = pertanyakan urgensinya.
- Bug triage produk SaaS: bug di alur onboarding/pembayaran > bug kosmetik di halaman settings, SELALU.
- Saat management tanya "kenapa churn naik?", kerangka jawabannya: cek kohort mana yang churn (baru vs lama?), cek perubahan produk/harga di periode itu, cek data leading indicator, baru hipotesis.
- Project client juga bisa dilihat begini: website client = funnel acquisition mereka → paham ini membuatmu bisa bicara bisnis dengan client, bukan cuma fitur.

## Istilah tambahan yang sering muncul di meeting

**Cohort analysis** (kelompok user berdasarkan waktu daftar — cara benar membaca retention) · **Expansion revenue** (upsell ke pelanggan existing — penawar churn) · **Net Revenue Retention >100%** = ekspansi menutupi churn (kondisi ideal) · **Product-market fit** · **North star metric** (satu metrik utama produk).
