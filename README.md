# ⭐ Rate Us — Halaman Ulasan Google Maps

Halaman HTML simpel (1 file) untuk meminta ulasan & rating dari pelanggan di Google Maps. Siap di-hosting di **GitHub Pages**.

## ✨ Fitur

- Desain modern & responsif (bisa dibuka dari HP)
- Tombol besar **"Tulis Ulasan di Google"** yang langsung membuka formulir ulasan resmi Google
- Nama bisnis **otomatis muncul dari Google** — tidak perlu diketik manual di halaman
- Animasi bintang & efek hover yang halus

## 🔗 Cara Mengganti Link Review (WAJIB)

1. Cari bisnismu di **Google Maps**
2. Buka **https://googleplaceidfinder.com** → cari bisnismu → salin **Place ID** (contoh: `ChIJN1t_tDeuEmsRUsoyG83frY4`)
3. Buka file **`index.html`**
4. Cari bagian ini (paling bawah, di dalam `<script>`):

   ```js
   const REVIEW_URL = "https://search.google.com/local/writereview?placeid=YOUR_PLACE_ID";
   ```

5. Ganti `YOUR_PLACE_ID` dengan Place ID milikmu, contoh:

   ```js
   const REVIEW_URL = "https://search.google.com/local/writereview?placeid=ChIJN1t_tDeuEmsRUsoyG83frY4";
   ```

   > 💡 Selama link masih `YOUR_PLACE_ID`, tombol akan menampilkan peringatan (toast) alih-alih membuka Google — jadi kamu tidak akan lupa menggantinya.

> Cara alternatif: jika kamu sudah punya Google Business Profile, link review juga bisa diambil dari dashboard Google Business dengan klik **"Minta ulasan" → Salin link**.

## 🚀 Cara Deploy ke GitHub Pages

### Persiapan (sekali saja)
1. Buat akun di **github.com** (jika belum punya)
2. Klik **+** (pojok kanan atas) → **New repository**
3. Nama repository bebas (contoh: `rate-us`), pilih **Public**, lalu **Create repository**

### Upload file
**Cara termudah (tanpa install apa pun):**
1. Di halaman repository, klik **Add file → Upload files**
2. Pilih **semua** file di bawah ini dari komputer (jangan ada yang ketinggalan, terutama `.nojekyll` — di Windows, buka folder dengan `Win+E`, aktifkan **View → Hidden items** agar file tersembunyi terlihat, lalu pilih semua):

   ```
   .gitignore
   .nojekyll        ← penting! cegah GitHub memproses dengan Jekyll
   404.html
   favicon.svg
   index.html
   README.md
   ```

3. Scroll bawah → **Commit changes**

### Aktifkan GitHub Pages
1. Di repository, buka tab **Settings**
2. Menu kiri → **Pages**
3. Bagian **Branch** → pilih `main` → folder `/ (root)` → **Save**
4. Tunggu 1–2 menit, lalu buka alamat: `https://<username-kamu>.github.io/<nama-repository>/`

Contoh: `https://budi123.github.io/rate-us/`

### Update link review di kemudian hari
1. Edit file `index.html` di GitHub (klik file → ikon pensil ✏️)
2. Ganti `YOUR_PLACE_ID`
3. Klik **Commit changes** — perubahan langsung aktif otomatis

## 📱 Bagikan ke Pelanggan

Bagikan URL GitHub Pages-mu lewat:
- WhatsApp / Instagram bio
- QR code di kasir / meja
- Struk atau kartu ucapan terima kasih

## 🗂️ Struktur Repo GitHub Pages (WAJIB)

```
├── index.html   ← halaman utama (desain + link review) — WAJIB di root
├── 404.html     ← halaman error, otomatis dipakai GitHub Pages
├── favicon.svg  ← ikon tab browser (bintang ⭐)
├── .nojekyll    ← penting: cegah GitHub memproses dengan Jekyll
├── .gitignore   ← abaikan file sampah sistem
└── README.md    ← panduan ini
```

### Aturan emas
- **`index.html` harus di root** (bukan di subfolder) dan namanya **harus `index.html`** — ini satu-satunya nama yang otomatis jadi halaman utama
- **Jangan hapus `.nojekyll`** — tanpa file ini, GitHub Pages menjalankan Jekyll yang bisa bikin file/folder berawalan `_` tidak terbaca
- File tersembunyi seperti `.nojekyll` juga **harus ikut ter-upload** (lihat panduan di atas)
- URL website: `https://<username>.github.io/<nama-repository>/`

### Opsi: pakai git lokal (lebih rapi untuk update)
Kalau kamu biasa pakai terminal, cara ini membuat update ke depan lebih mudah:

```bash
# 1. buat repo di GitHub, lalu di folder proyek:
git init
git add .
git commit -m "Rate Us page"
git branch -M main
git remote add origin https://github.com/<username>/<nama-repository>.git
git push -u origin main
```

Setelah itu, update cukup dengan `git add . && git commit -m "update" && git push`.

---

Dibuat dengan ❤️ — semoga bisnismu makin ramai ulasan positifnya!
