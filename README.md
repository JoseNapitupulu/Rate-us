# ⭐ Rate Us — Halaman Ulasan Google Maps

Website untuk meminta ulasan & rating di Google Maps — bisa untuk **banyak tempat wisata sekaligus** (wisata 1, wisata 2, wisata 3, ...), dikelola lewat **Panel Admin**. Di-hosting di **GitHub Pages**.

## ✨ Fitur

- **Banyak tempat** — tiap tempat wisata punya link & halaman sendiri (cocok untuk QR code per tempat)
- **Panel Admin** (`admin.html`) — tambah/edit/hapus link tanpa perlu paham kode
- Desain modern & responsif (bisa dibuka dari HP)
- Nama bisnis otomatis muncul dari Google saat pelanggan menulis ulasan
- Halaman 404 custom + favicon bintang ⭐

## 🗂️ Struktur Repo

```
├── index.html    ← halaman depan: daftar semua tempat wisata
├── spot.html     ← halaman khusus per tempat (spot.html?id=wisata-1) — untuk QR code
├── admin.html    ← PANEL ADMIN (dilindungi password)
├── spots.json    ← ⭐ data tempat wisata + link review (diubah lewat panel admin)
├── 404.html      ← halaman error custom
├── favicon.svg   ← ikon tab browser
├── .nojekyll     ← penting: cegah GitHub memproses dengan Jekyll
├── .gitignore
└── README.md
```

## 🔐 Panel Admin (cara pakai)

1. Buka **`https://josenapitupulu.github.io/Rate-us/admin.html`** (atau `https://rating.ifs25026.fun/admin.html`)
2. Masuk dengan password: **`rateus123`**
   > 🔑 Ganti password-nya! Buka `admin.html`, cari baris `ADMIN_PASSWORD = "rateus123"`, ganti, lalu push.
3. **Tambah tempat** → isi Nama + Link review Google → **💾 Simpan**
4. **Edit / hapus** → klik ikon ✏️ / 🗑️ di tiap tempat
5. **Terbitkan** → klik **📋 Salin JSON**, lalu tempel ke file `spots.json` di GitHub:
   - Buka `spots.json` di repo → klik ✏️ (Edit file) → `Ctrl+A` → `Ctrl+V` → **Commit changes**
   - Tunggu ±1 menit, situs otomatis update 🎉

> ⚠️ **Penting**: GitHub Pages tidak punya database, jadi setelah edit di panel admin, JSON-nya harus di-paste ke `spots.json` (langkah 5). Tanpa itu, perubahan belum tampil di situs.

### Link review Google — format
```
https://search.google.com/local/writereview?placeid=PLACE_ID
```
Cara dapat **Place ID**: buka [googleplaceidfinder.com](https://googleplaceidfinder.com) → cari bisnismu → salin kode seperti `ChIJN1t_tDeuEmsRUsoyG83frY4`.

> 💡 Selama link masih berisi `YOUR_PLACE_ID`, tombol "Tulis Ulasan" akan menampilkan peringatan alih-alih membuka Google — jadi kamu tidak akan lupa mengisinya.

## 🔗 Link & QR Code per Tempat

Setiap tempat punya halaman sendiri: **`spot.html?id=wisata-1`** (id-nya sesuai `spots.json`).

Contoh untuk pelanggan:
- Wisata 1 → `https://rating.ifs25026.fun/spot.html?id=wisata-1`
- Wisata 2 → `https://rating.ifs25026.fun/spot.html?id=wisata-2`

Link ini bisa diubah jadi **QR code** gratis (misal di qr-code-generator.com) untuk ditempel di meja kasir, papan informasi, atau tiket tiap wisata.

## 🚀 Deploy

Sudah aktif di:
- **https://rating.ifs25026.fun/** (custom domain, HTTPS)
- **https://josenapitupulu.github.io/Rate-us/** (URL default, auto-redirect)

Update ke depan cukup lewat git:

```bash
git add .
git commit -m "update"
git push
```

## ⚠️ Catatan keamanan

Panel admin pakai password **client-side** (hanya di browser). Ini cukup untuk mencegah orang awam membuka panel, tapi bukan keamanan kelas bank — siapa pun yang membaca kode `admin.html` bisa melihat passwordnya. Untuk keamanan sungguhan, dibutuhkan backend (misal Firebase Auth).

---

Dibuat dengan ❤️ — semoga tempat wisatamu makin ramai ulasan positifnya!
