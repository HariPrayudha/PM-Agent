# Playbook: Komunikasi Client (EN, Client Singapura)

> KPI terkait: High satisfaction rate, Manage expectation.
> Prinsip inti: **client menilai project dari komunikasimu, bukan dari kodenya.** Project bagus + komunikasi buruk = client kecewa. Project ada masalah + komunikasi bagus = client tetap percaya.

## 5 Prinsip

1. **Proactive, never chased.** Kalau client sampai bertanya "any update?", kamu sudah kalah. Update rutin terjadwal (mingguan via `/status-report`) + kabar spontan saat ada perkembangan penting.
2. **Bad news early.** Kabar buruk tidak membaik dengan menunggu. Sampaikan begitu terkonfirmasi, selalu bersama rencana mitigasi.
3. **One message, one purpose.** Client SG sibuk. Pesan pendek, poin jelas, kebutuhan aksi eksplisit ("We need X by {date}").
4. **Everything important in writing.** Keputusan di call → tulis ringkasan <24 jam. "As discussed on our call today, we agreed to…"
5. **Confident, not defensive.** Kamu ahlinya. Beri rekomendasi, bukan cuma opsi. "I recommend A because…" > "up to you".

## Gaya untuk Client Singapura

- Business English yang **to the point** — mereka terbiasa komunikasi efisien; basa-basi panjang justru terasa tidak profesional.
- Tetap warm secukupnya: sapa nama, "Hope you're doing well" sekali di awal thread baru, bukan tiap pesan.
- **Waktu selalu dengan zona**: "3 PM SGT (2 PM WIB)". SGT = WIB+1.
- Respons cepat itu budaya kerja SG. Tidak bisa jawab detail sekarang? Kirim holding reply: *"Thanks — let me check with the team and get back to you by tomorrow noon."* Jangan biarkan pesan menggantung >4 jam kerja.
- Hindari slang Indonesia yang terbawa ("kindly revert" boleh — umum di SG; "please help to..." juga umum di sana).

## Frasa Siap Pakai per Situasi

### Mengabarkan delay
> "Hi {name}, I want to flag a schedule update early. {Feature/milestone} is taking longer than planned because {honest reason, no drama}. Impact: {milestone} moves from {old date} to {new date}. To keep the overall launch on track, we're {mitigation}. The rest of the timeline is unaffected. Sorry for the shift — I'll keep you posted closely on this one."

Catatan: sekali minta maaf, cukup. Fokus ke rencana, bukan penyesalan.

### Menolak scope creep dengan halus (permintaan di luar PRD)
> "Good idea — I can see how that would help {goal}. It's outside our current scope, so let me get you an estimate of the effort and timeline impact first. If it's priority, we can look at swapping it with {lower-priority item}, or schedule it right after launch. Which would you prefer?"

Kuncinya: jangan bilang "no", bilang **"yes, and here's the cost"**. Setiap permintaan tambahan = estimasi dulu, kerjakan setelah persetujuan.

### Menagih konten/feedback yang telat (tanpa terdengar menyalahkan)
> "Quick reminder: we're on track for {milestone} on {date}, and we'll need {content/feedback} by {date} to stay on schedule. If it's easier, we can hop on a 15-min call and capture it together."

Eskalasi kalau masih diam (3–4 hari kemudian):
> "Following up on the {item} — we've now reached the point where the schedule depends on it. To be transparent: if we receive it by {date}, launch stays on {date}; after that, each day shifts the launch by a day. Anything I can do to make this easier on your side?"

### Menyampaikan bug/masalah yang client temukan
> "Thanks for catching that — you're right, {issue}. We've reproduced it and a fix will be on staging by {time}. I'll confirm once it's up."

Jangan defensif, jangan menyalahkan dev di depan client ("the developer forgot…" ❌ — di mata client, tim = kamu).

### Follow-up pembayaran
> "Hi {name}, a gentle reminder that invoice #{no} ({amount}) was due on {date}. Could you check with your finance team? Happy to resend the invoice if needed."

### Menutup fase / minta sign-off
> "All UAT items have been resolved. Could you confirm your sign-off on this phase by replying 'approved' to this email? We'll then proceed with the launch preparation."

### Minta testimonial (setelah launch sukses)
> "Really glad the launch went smoothly! If you're happy with how it turned out, would you mind writing a short testimonial we could feature? Two or three sentences would be perfect."

## Ritme Komunikasi Standar per Project

| Kapan | Apa | Via |
|---|---|---|
| Jumat (atau hari yang disepakati) | Weekly status report | Email/Slack (template EN) |
| Tiap milestone selesai | Demo + link staging | Slack + call singkat |
| Ada blocker dari client | Reminder terjadwal, eskalasi bertahap | Slack |
| Keputusan penting dibuat | Ringkasan tertulis <24 jam | Email (jejak formal) |

## Anti-pattern

- ❌ Menghilang saat ada masalah (paling merusak trust).
- ❌ Update penuh jargon teknis: "we refactored the API middleware" → client tidak peduli; terjemahkan ke dampak: "the site now loads noticeably faster".
- ❌ Menjawab komplain saat emosi. Draft dulu (pakai `/client-email`), baca ulang, kirim.
- ❌ Janji di chat tanpa cek tim dulu. "Let me confirm with the team" adalah jawaban yang sah dan profesional.
