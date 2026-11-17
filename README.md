# Undangan Pernikahan Intan & Dimas

Undangan pernikahan online satu halaman (HTML, CSS, dan JavaScript biasa). Tidak ada build dan tidak ada dependensi, semua gambar sudah tertanam di `index.html`.

## Isi

- Cover dengan nama tamu, ayat pembuka, profil mempelai
- Hitung mundur dan tombol tambah ke kalender
- Detail akad nikah dan tombol Google Maps
- Galeri, amplop digital (muncul kalau rekening diisi)
- RSVP dan ucapan, mode terang dan gelap

## Mengubah data

Buka `index.html`, cari blok `UBAH DATA DI SINI` (di bagian `<script>`):

| Kolom   | Fungsi |
|---------|--------|
| `start`, `end` | Waktu akad (format ISO, zona WIB `+07:00`) |
| `place` | Nama tempat, dipakai juga untuk tombol Google Maps |
| `wa`    | Nomor WhatsApp mempelai, format `62812xxxx`. Kalau kosong, RSVP tidak terkirim ke siapa pun |
| `gifts` | Daftar rekening, contoh: `[{bank:"Bank BCA",no:"1234567890",an:"Nama Pemilik"}]`. Kalau kosong, bagian amplop digital disembunyikan |

Nama mempelai, orang tua, dan teks lain langsung diubah di HTML.

## Link per tamu

Tambahkan nama tamu di belakang tanda `#`, huruf kecil dipisah tanda hubung:

```
https://domain-anda.com/#budi-santoso
```

Cover akan menampilkan "Budi Santoso". Di bagian bawah halaman ada generator link (menu "Untuk mempelai").

## Commit ke GitHub

```bash
cd undangan-intan-dimas
git init
git add .
git commit -m "Undangan pernikahan Intan & Dimas"
git branch -M main
git remote add origin https://github.com/USERNAME/undangan-intan-dimas.git
git push -u origin main
```

## Deploy

- **Vercel**: Add New Project, pilih repo ini, Framework Preset `Other`, kosongkan Build Command, lalu Deploy.
- **GitHub Pages**: Settings, Pages, Source `Deploy from a branch`, branch `main`, folder `/ (root)`.

## Catatan

- Ucapan tamu disimpan di browser masing-masing (localStorage), jadi belum terkumpul di satu tempat. Untuk buku tamu bersama dibutuhkan database.
- Font dimuat dari Google Fonts, jadi perlu internet saat undangan dibuka.
