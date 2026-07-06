# Setup Sekali Jalan (One-Time Setup)

Workspace ini butuh 2 autentikasi sekali jalan supaya integrasi ClickUp & Slack aktif.

## 1. ClickUp (MCP resmi — sudah terdaftar di `.mcp.json`)

1. Buka Claude Code di folder ini.
2. Saat pertama kali, Claude Code akan tanya apakah mau mengaktifkan MCP server `clickup` dari `.mcp.json` → pilih **Yes**.
3. Ketik `/mcp` → pilih **clickup** → ikuti flow login OAuth di browser (login pakai akun ClickUp kerja).
4. Selesai. Token disimpan Claude Code (bukan di file repo ini).

Tes: minta Claude "list task ClickUp yang assigned ke aku" — harus muncul task asli.

## 2. Slack (plugin resmi Slack)

1. Di Claude Code, jalankan:
   ```
   /plugin install slack@claude-plugins-official
   ```
2. Saat pertama kali dipakai (misal `/daily` mau kirim standup), akan muncul OAuth ke workspace Slack → login.
3. ⚠️ **Catatan**: admin workspace Slack harus mengizinkan integrasi MCP. Kalau OAuth ditolak, minta approval ke admin dulu.

Tes: minta Claude "baca 5 pesan terakhir di channel #general".

## 3. (Opsional) GitHub

Kalau `gh` CLI sudah login (`gh auth status`), Claude bisa cek progress PR/issue langsung. Tidak perlu setup tambahan.

---

Setelah keduanya hijau di `/mcp`, hapus rasa ragu: mulai dengan `/kickoff <nama-project>` untuk project pertamamu. 🚀
