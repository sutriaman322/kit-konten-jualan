# Landing — Kit Konten Jualan 30 Hari

Halaman promosi statis untuk produk digital **Kit Konten Jualan 30 Hari**.
Tanpa framework, tanpa build step, tanpa backend. Siap GitHub Pages.

## Struktur

    index.html          satu file: HTML + CSS + JS inline
    assets/             4 gambar (JPG, sudah dikompres)
    .nojekyll           agar GitHub Pages tidak memproses lewat Jekyll
    robots.txt

## WAJIB DIGANTI SEBELUM PUBLIK

Cari `LINK_LYNK` di `index.html` — ada **3 tempat** (hero, bagian harga,
sticky CTA bawah). Ganti semuanya dengan URL produk Anda di lynk.id:

    <a class="cta" href="https://lynk.id/namatoko/abc123">

Ganti juga di blok JSON-LD paling bawah (`"url":"LINK_LYNK"`).

Kalau lupa, semua tombol beli mengarah ke halaman mati.

## Ganti URL canonical & OG (setelah nama repo diketahui)

Di `<head>`, ganti `USERNAME` dan nama repo:

    https://USERNAME.github.io/kit-konten-landing/

Ini dipakai untuk `canonical`, `og:url`, dan `og:image`. Beberapa crawler
(termasuk WhatsApp) butuh URL absolut untuk gambar pratinjau.

## Deploy GitHub Pages (manual, tanpa gh CLI)

1. Buat repo publik baru, misal `kit-konten-landing`.
2. Unggah isi folder ini ke root repo (index.html harus di root).
3. Repo → Settings → Pages → Source: *Deploy from a branch*
   → Branch: `main`, folder: `/ (root)` → Save.
4. Tunggu 1-2 menit, buka `https://USERNAME.github.io/kit-konten-landing/`.

Lewat terminal:

    cd ~/kit-konten/landing
    git init
    git add .
    git commit -m "Landing Kit Konten Jualan 30 Hari"
    git branch -M main
    git remote add origin https://github.com/USERNAME/kit-konten-landing.git
    git push -u origin main

Lalu aktifkan Pages seperti langkah 3.

## Uji lokal sebelum push

    cd ~/kit-konten/landing
    python -m http.server 8000
    # buka http://localhost:8000

Cek: semua gambar muncul, ketiga tombol beli menuju URL yang benar,
tampil rapi di lebar 360px (HP kecil) dan 1280px.

## JANGAN taruh file produk di repo ini

GitHub Pages menyajikan semua file di repo publik. Kalau
`Kit-Konten-Jualan-v1.zip` ikut ter-commit, siapa pun bisa mengunduhnya
tanpa membayar. ZIP hanya disimpan di lynk.id.

Folder `assets/` berisi gambar promosi saja — itu memang publik.

## Catatan harga

Harga tertulis di HTML (`Rp39.000` dan `Rp129.000`). Kalau harga di
lynk.id berbeda, ubah juga di `index.html` supaya tidak ada
ketidakcocokan antara halaman promosi dan halaman checkout.
