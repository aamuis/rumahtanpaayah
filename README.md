# Flipbook — Rumah Tanpa Ayah

Website pembaca buku ala FlipHTML5/AnyFlip. Langsung terbuka di halaman cover dan bisa di-flip (klik/drag/swipe/tombol panah).

## Isi folder
- `index.html` — satu-satunya file website (memuat PDF.js untuk merender PDF & StPageFlip untuk efek flip, keduanya dari CDN)
- `book.pdf` — file buku kamu (WAJIB pakai nama ini dan berada satu folder dengan `index.html`)

## Cara upload ke GitHub
1. Buat repo baru di GitHub (public atau private, bebas).
2. Upload `index.html` dan `book.pdf` ke root repo (bukan di dalam subfolder).

## Cara deploy ke Vercel
1. Buka vercel.com → **Add New Project** → import repo GitHub tadi.
2. Framework Preset pilih **Other** (situs statis, tidak perlu build command apa pun — biarkan kosong).
3. Klik **Deploy**. Selesai — link Vercel-nya langsung bisa dibuka dan buku tampil dari cover.

## Cara ganti buku di kemudian hari
Cukup timpa `book.pdf` dengan PDF baru (nama file harus tetap `book.pdf`), lalu push ulang ke GitHub — Vercel otomatis re-deploy.

## Catatan teknis
- Tidak ada judul/header yang tampil — halaman langsung menampilkan cover buku memenuhi layar.
- Semua 423 halaman dirender langsung di browser pengunjung dari `book.pdf` (bukan gambar terpisah), jadi ukuran repo tetap kecil (~1.7 MB).
- Halaman cover & 1 halaman berikutnya dirender dulu sebelum buku dibuka (supaya cepat tampil), sisanya dirender di belakang layar sambil pembaca mulai membaca; kalau pembaca lompat cepat ke halaman jauh, halaman di sekitarnya diprioritaskan agar tidak nunggu lama.
- Kontrol di bawah: tombol ‹ ›, indikator nomor halaman, dan tombol layar penuh. Bisa juga pakai tombol panah kiri/kanan di keyboard, atau klik di tepi kiri/kanan layar, atau swipe/drag halaman.
- Butuh koneksi internet saat dibuka (untuk memuat library PDF.js & page-flip dari CDN) — file `book.pdf`-nya sendiri sudah ikut di-host bareng website.
