# Landing — Kit Konten Jualan 30 Hari

Halaman promosi statis untuk produk digital **Kit Konten Jualan 30 Hari**.
Tanpa framework, tanpa build step, tanpa backend. Siap GitHub Pages.

Live: https://sutriaman322.github.io/kit-konten-jualan/

## Struktur

    index.html          satu file: HTML + CSS + JS inline
    assets/             4 gambar (JPG, sudah dikompres)
    .nojekyll           agar GitHub Pages tidak memproses lewat Jekyll
    robots.txt

## STATUS: BELUM SIAP JUALAN

Tombol beli masih memakai placeholder `LINK_LYNK` di **4 tempat**:

1. tombol hero
2. tombol di bagian harga
3. sticky CTA bawah (mobile)
4. `offers.url` di blok JSON-LD

Selama placeholder ini belum diganti, semua tombol beli mengarah ke
halaman mati. Ganti dengan URL produk lynk.id, misal:

    <a class="cta" href="https://lynk.id/namatoko/abc123">

Cara cepat:

    grep -n "LINK_LYNK" index.html

Lalu commit dan push ulang.

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
