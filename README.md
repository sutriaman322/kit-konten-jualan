# Landing — Kit Konten Jualan 30 Hari

Halaman promosi statis untuk produk digital **Kit Konten Jualan 30 Hari**.
Tanpa framework, tanpa build step, tanpa backend. Siap GitHub Pages.

Live: https://sutriaman322.github.io/kit-konten-jualan/

## Struktur

    index.html          satu file: HTML + CSS + JS inline
    assets/             4 gambar (JPG, sudah dikompres)
    .nojekyll           agar GitHub Pages tidak memproses lewat Jekyll
    robots.txt

## Link pembelian: SUDAH TERSAMBUNG

Semua tombol beli mengarah ke produk lynk.id:

    https://lynk.id/sutri01/1jgvkd3mke04

Titik yang tersambung: tombol hero, tombol bagian harga, sticky CTA
mobile, dan `offers.url` di JSON-LD.

Kalau nanti pindah produk atau ganti URL toko, cari di `index.html`:

    grep -n "lynk.id" index.html

lalu ganti keempat titik itu sekaligus.

## Deploy (sudah dilakukan)

Repo: https://github.com/sutriaman322/kit-konten-jualan
Pages: branch `main`, folder `/ (root)`, repo publik.

Push perubahan berikutnya cukup:

    cd ~/kit-konten/landing
    git add -A
    git commit -m "pesan perubahan"
    git push

## Uji lokal

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
