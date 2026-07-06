# Playbook: Menggali Kebutuhan Client (Requirement Gathering)

> KPI terkait: Understanding of stakeholder needs, Low revision rate.
> Prinsip inti: **yang client MINTA ≠ yang client BUTUHKAN**. Tugasmu menemukan yang kedua.

## Kenapa ini skill PM #1

Revisi tinggi & client kecewa hampir selalu berakar di requirement yang salah paham — bukan di kualitas coding. 1 jam menggali di awal menghemat 1 minggu revisi di akhir.

## Pola: Diminta vs Dibutuhkan

| Client bilang | Kemungkinan kebutuhan sebenarnya | Gali dengan |
|---|---|---|
| "I want a website like Airbnb" | Butuh listing + booking sederhana untuk 20 properti | "What would users do on the site, step by step?" |
| "We need a mobile app" | Butuh web responsive (budget & user-nya tidak butuh app) | "What problem should the app solve that your website can't?" |
| "Add a chat feature" | Butuh cara user bertanya cepat → form/WhatsApp cukup | "What kind of questions do you expect? How fast do you need to respond?" |
| "Make it pop / more modern" | Tidak percaya diri dengan brand; butuh referensi konkret | "Can you show me 2–3 sites whose look you love, and what specifically you like?" |

Teknik: selalu tanya **"what problem does this solve?"** sebelum mencatat fitur.

## Daftar Pertanyaan Discovery (EN — siap pakai di call)

### Bisnis & tujuan
1. "What does success look like for this project, 6 months after launch?"
2. "What's the main problem this website/app should solve for your business?"
3. "Who are your customers, and what should they do when they visit?" (call-to-action utama)
4. "How do you get customers today? How does this project fit into that?"

### Scope & fitur
5. "Walk me through the ideal user journey, step by step."
6. "Which features are must-have for launch vs nice-to-have later?" (langsung MoSCoW)
7. "Is there an existing system/site? What works, what doesn't?"
8. "Any systems we need to integrate with?" (payment, CRM, inventory, email)

### Konten & aset
9. "Who will provide the content — copy, images, product data? By when?"
10. "Do you have brand guidelines (logo, colors, fonts)?"

### Constraint
11. "Is there a hard deadline? What's driving it?" ← alasan deadline menentukan seberapa keras deadline itu
12. "What budget range are we working with?" (kalau belum dibahas sales)
13. "Who has the final say on approvals?" ← WAJIB. Cari decision maker.
14. "How would you like to communicate — Slack, email? How often do you want updates?"

### Pasca-launch
15. "Who will maintain the site after launch?"
16. "Do you expect ongoing work after this phase?"

## Teknik Playback (konfirmasi pemahaman)

Setelah client menjelaskan, ulangi dengan kata-katamu:

> "Let me play that back to make sure I've got it right: you need X so that Y, and the most important thing is Z. Did I miss anything?"

- Client mengoreksi → bagus, kesalahpahaman ketangkap sekarang (murah), bukan di UAT (mahal).
- Selalu tutup meeting dengan playback + kirim ringkasan tertulis <24 jam ([templates/meeting-notes.md](../templates/meeting-notes.md)).

## Red Flags saat Discovery

- 🚩 "Just make it like {kompetitor}, but better" tanpa bisa menjelaskan "better"-nya apa → gali sampai konkret.
- 🚩 Tidak bisa menyebut siapa decision maker → feedback akan berputar-putar.
- 🚩 "Budget-nya fleksibel, yang penting bagus" → tidak ada budget; buat opsi bertingkat.
- 🚩 Deadline sangat dekat + scope besar → tawarkan pemotongan scope (MoSCoW), jangan telan mentah.
- 🚩 Banyak stakeholder hadir tapi saling beda pendapat → minta client tunjuk 1 suara resmi.

## Output fase ini

Semua jawaban masuk `brief.md` (via `/kickoff`), pertanyaan yang belum terjawab masuk "Open Questions". Lanjut ke `/prd` hanya setelah pertanyaan kritis (scope, decision maker, deadline) terjawab.
