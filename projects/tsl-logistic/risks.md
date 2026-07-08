# Risk Register — TSL Logistic

> Di-review oleh `/risk-check`. Tambah risiko begitu tercium, jangan tunggu jadi masalah.

| # | Risiko | Kemungkinan | Dampak | Mitigasi | Pemilik | Status |
|---|---|---|---|---|---|---|
| R1 | Task ClickUp dikerjakan DPA tapi status tidak diupdate real-time → keliatan overdue padahal sudah beres | Sedang | Salah baca status oleh Hari/DPA lain, laporan ke client jadi tidak akurat | Cross-check status ClickUp saat `/daily`/`/risk-check`; catat alasan on-hold/duplikat di sini atau decisions.md | Hari | 🟡 Aktif |

## Risiko Umum Project Web Dev (checklist awal)
- [ ] Konten/aset dari client terlambat
- [ ] Scope creep — permintaan kecil beruntun di luar PRD
- [ ] Akses (hosting, domain, API pihak ketiga) belum diberikan
- [ ] Decision maker tidak terlibat sampai UAT → feedback besar di akhir
- [ ] Estimasi dev terlalu optimis (tanpa buffer)
- [ ] Dependensi pihak ketiga (payment gateway, API eksternal) bermasalah
