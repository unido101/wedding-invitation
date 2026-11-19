# Undangan Pernikahan Intan & Dimas

Undangan pernikahan online satu halaman (HTML, CSS, JavaScript biasa). Tidak ada build dan tidak ada dependensi.

## File

| File | Fungsi |
|------|--------|
| `index.html` | Halaman undangan untuk tamu |
| `config.js` | Isi undangan (nama, acara, teks, WhatsApp, rekening) |
| `admin.html` | Halaman admin: mengatur isi dan membuat link tamu |

## Mengatur isi lewat admin

1. Buka `admin.html` (di domain Anda atau lewat server lokal, misalnya `python3 -m http.server`).
2. Tab **Isi undangan**: ubah data, klik **Pratinjau** untuk melihat hasilnya.
3. Klik **Unduh config.js**, lalu ganti file `config.js` di repo dengan file itu.
4. Commit dan push. Undangan ikut berubah setelah deploy selesai.

Isi `wa` (nomor WhatsApp mempelai) agar RSVP sampai ke Anda. Bagian amplop digital hanya tampil kalau minimal satu rekening diisi.

## Link tamu

Di tab **Tamu & link** pada admin: isi alamat undangan (domain setelah deploy), tambahkan nama tamu (boleh dengan nomor WA: `Nama | 0812...`), lalu tiap tamu mendapat link seperti `https://domain-anda.com/?to=Budi+Santoso` dan tombol kirim WhatsApp. Pesan WhatsApp bisa diedit.

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

- `admin.html` bisa dibuka siapa saja yang tahu alamatnya (tidak ada login), tetapi halaman itu tidak bisa mengubah undangan. Ia hanya menghasilkan `config.js` yang harus Anda commit sendiri.
- Draf dan daftar tamu tersimpan di browser yang dipakai admin, tidak ikut ke repo.
- Ucapan tamu tersimpan di browser masing-masing tamu. Untuk buku tamu bersama dibutuhkan database.
- Judul dan deskripsi pratinjau link WhatsApp (tag `og:`) ada di `index.html` dan tidak ikut berubah dari admin.
- Font dimuat dari Google Fonts, jadi perlu internet.
