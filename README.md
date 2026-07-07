# PM Agent — Workspace Project Manager Hari Prayudha

Workspace ini adalah "otak" PM pribadimu di Claude Code. Bukanya di folder ini, tanya/perintah apa saja soal project — agent akan baca konteks (brief, timeline, ClickUp) sebelum jawab. Detail penuh identitas & aturan agent ada di [CLAUDE.md](CLAUDE.md).

## ⚠️ Peta Kanal Komunikasi — baca ini dulu

Tiga tool, tiga fungsi berbeda. Ini paling sering bikin bingung, jadi disimpan di paling atas:

| Kanal | Siapa di sana | Otomasi | Dipakai untuk |
|---|---|---|---|
| **Slack** | Tim internal Hari saja (dev/creative) | ✅ MCP aktif | `/daily` standup, koordinasi tim. **Client/DPA TIDAK ADA di sini.** |
| **WhatsApp** (grup DPA+client) | DPA & client bareng, 1 grup | ❌ Tidak ada — manual | Semua komunikasi eksternal. `/client-email` & `/status-report` menghasilkan teks siap paste, kamu yang kirim manual. |
| **ClickUp** | **Lintas organisasi** — kantor Hari & DPA sama-sama lihat | ✅ MCP aktif | Task management. Tulis ke sini SELALU preview+konfirmasi dulu — isinya kelihatan pihak luar, jaga bahasa tetap profesional. |

**Aturan besi**: agent tidak akan pernah menyarankan kirim pesan ke client/DPA lewat Slack. Kalau suatu saat ada saran begitu, itu bug — tegur.

## Status Integrasi
- ✅ ClickUp — terautentikasi
- ✅ Slack — terautentikasi (internal only)
- ⬜ WhatsApp — belum ada integrasi otomatis, semua draft di-copy-paste manual ke grup

Setup ulang/troubleshoot → [SETUP.md](SETUP.md)

## Peta Flow Lengkap

Begitu ada pekerjaan/permintaan masuk, tentukan dulu jenisnya — itu satu-satunya keputusan awal yang perlu kamu buat, sisanya agent yang pandu:

```
                    ┌─────────────────────────────────────┐
                    │   /daily (tiap pagi)                 │
                    │   /weekly-review (tiap Jumat sore)   │
                    └─────────────────────────────────────┘
                                 membungkus semua jalur di bawah

┌─ JALUR A ──────────────┐  ┌─ JALUR B ──────────────┐  ┌─ JALUR C ──────────────┐
│ Project BARU            │  │ Project DESIGN          │  │ Update di project       │
│ (web dev / SaaS)        │  │ (branding, banner,      │  │ EXISTING                │
│                         │  │  company profile)       │  │ (bug/fitur/CR/design    │
│                         │  │                         │  │  job kecil)             │
└─────────────────────────┘  └─────────────────────────┘  └─────────────────────────┘
        │                             │                             │
   /kickoff <nama>               /kickoff <nama>               /task [nama]
        │                        (pilih tipe: design)               │
        ▼                             │                        agent klasifikasi:
   /prd <nama>                        ▼                        bug / update kecil /
        │                        /breakdown <nama>              change request / design
        ▼                        (per deliverable)                   │
   /breakdown <nama>                  │                          → langsung jadi
   (push ke ClickUp)                  ▼                            task ClickUp
        │                        /timeline <nama>
        ▼                        (due date konsep+final)
   /timeline <nama>
        │
        ▼
   ══════════════ EKSEKUSI HARIAN (semua jalur) ══════════════
   /daily · /status-report (mingguan) · /risk-check (berkala) · /client-email · /meeting-notes
        │
        ▼
   Project selesai → /retro <nama>
```

## Cheat Sheet — Situasi → Skill

| Situasi | Pakai |
|---|---|
| Client baru, mau bikin website/app dari nol | `/kickoff` → `/prd` → `/breakdown` → `/timeline` |
| Client minta logo/banner/branding baru | `/kickoff` (pilih tipe **design**) → `/breakdown` → `/timeline` |
| DPA/client di grup WA minta "tolong tambah fitur X" atau lapor bug | `/task <nama-project>` |
| Ada project lama yang belum tercatat di workspace ini | `/task` — akan nawarin registrasi ringan dulu |
| Requirement EN dari grup WA yang membingungkan, mau diterjemahkan ke tim | `/translate-brief` |
| Mau draft/polish pesan ke grup WA (DPA+client) | `/client-email` |
| Habis meeting, mau rapikan jadi MoM | `/meeting-notes` |
| Tiap pagi buka kerja | `/daily` |
| Tiap Jumat sore | `/weekly-review` |
| Berkala (mis. tiap Senin) atau firasat tidak enak | `/risk-check` |
| Project selesai | `/retro <nama>` |

## Struktur Workspace

| Folder | Isi |
|---|---|
| [playbooks/](playbooks/) | SOP & pengetahuan PM (web dev lifecycle, requirement gathering, estimasi, komunikasi client, koordinasi tim, QA/UAT, SaaS metrics, fundamentals) |
| [templates/](templates/) | Template dokumen siap pakai (brief, PRD, design-brief, timeline, status report, UAT, handover, retro) |
| [projects/](projects/) | 1 folder per project — [_INDEX.md](projects/_INDEX.md) adalah dashboard semua project |
| [clients/](clients/) | Profil per client (gaya komunikasi, kontak DPA, history) |
| [knowledge/](knowledge/) | [KPI tracker](knowledge/kpi-tracker.md), [learning roadmap](knowledge/learning-roadmap.md), [glossary EN↔ID](knowledge/glossary.md) |
| `.claude/skills/` | Semua slash command di atas |

## Kalau Bingung "Ini Ngapain Ya?"

Baca [playbooks/web-dev-lifecycle.md](playbooks/web-dev-lifecycle.md) bagian "Cheat Sheet" — atau langsung tanya agent: "project X masuk, aku harus ngapain?" — dia akan baca konteksnya dan kasih langkah konkret.
