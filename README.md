# Pustaka Senja — Aplikasi Pemesanan Buku Online

Tugas UTS Pemrograman Web 1
Nama : Pahmi Dwika Fahlevi
NIM  : 312510389

Aplikasi web front-end sederhana untuk pemesanan buku pada toko online.
Semua data diambil dari variabel JavaScript berbentuk Array JSON di file `js/data.js`,
tanpa server atau database.

## Struktur Folder

tugas-uts-web1/
|-- index.html        (halaman login)
|-- dashboard.html
|-- stok.html
|-- checkout.html
|-- tracking.html
|-- README.md
|-- css/
|   |-- style.css
|-- js/
|   |-- script.js
|   |-- data.js
|-- assets/
|   |-- logo.png
|-- img/
|   |-- buku1.png ... buku6.png
|   |-- default.png

## Cara Menjalankan

1. Ekstrak atau clone folder `tugas-uts-web1`.
2. Buka `index.html` di browser. Disarankan memakai ekstensi **Live Server** di VS Code.
3. Login dengan akun demo berikut:

| Email              | Password |
|--------------------|----------|
| pahmi@tokobuku.com | pahmi123 |
| rina@tokobuku.com  | rina123  |
| agus@tokobuku.com  | agus123  |

Nomor Delivery Order (DO) yang bisa dicoba: `DO2026001`, `DO2026002`, `DO2026003`

## Fitur per Halaman

### 1. Login (`index.html`)
- Input email dan password, dengan validasi field kosong dan format email.
- Jika email/password salah, muncul pop-up **"Email/password yang anda masukkan salah"**.
- Tombol **Lupa Password** dan **Daftar** membuka modal box.
- Akun baru dari modal Daftar bisa langsung dipakai untuk login.
- Tombol untuk menampilkan/menyembunyikan password.

### 2. Dashboard (`dashboard.html`)
- Greeting otomatis sesuai jam lokal: Pagi / Siang / Sore / Malam.
- Jam digital dan tanggal hari ini.
- Kartu ringkasan: jumlah judul, total stok, stok menipis, dan transaksi baru.
- Menu navigasi: Informasi Stok/Katalog, Tracking Pengiriman, Laporan Pemesanan, History Transaksi.
- History Transaksi ditampilkan dalam modal.

### 3. Informasi Stok / Katalog (`stok.html`)
- Tabel dibuat dinamis dari konstanta `dataKatalogBuku`.
- Pencarian buku dan filter berdasarkan jenis.
- Penanda stok: tersedia / menipis / habis.
- Tambah baris stok baru lewat modal form, ditambahkan ke tabel dengan JavaScript DOM.
- Hapus buku dengan dialog konfirmasi.
- Tombol "Pesan" memasukkan buku ke halaman pemesanan.

### 4. Pemesanan (`checkout.html`)
- Item pesanan bisa ditambah, diubah jumlahnya (tombol −/+, dibatasi stok), atau dihapus.
- Form informasi pemesan: nama, email, no. HP, alamat.
- Pilihan ekspedisi dan metode pembayaran.
- Subtotal, ongkir, dan total dihitung otomatis.
- Validasi form dengan pesan error dan alert.
- Setelah pesanan dibuat, nomor DO baru muncul, stok berkurang, dan halaman pindah ke tracking.

### 5. Tracking Pengiriman (`tracking.html`)
- Input Nomor Delivery Order, lalu tekan tombol **Cari**.
- Menampilkan nama pemesan.
- Status pengiriman berupa progress bar 4 tahap: Dikemas → Dikirim → Dalam Perjalanan → Terkirim.
- Detail ekspedisi, tanggal kirim, jenis paket, dan total pembayaran.
- Riwayat perjalanan paket dalam bentuk timeline.
- Alert jika nomor DO kosong atau tidak ditemukan.

## Penerapan Indikator Penilaian

| Indikator | Penerapan |
|-----------|-----------|
| HTML semantik & valid | `header`, `nav`, `main`, `section`, `article`, `footer`, `fieldset`, `dl`, `label` + atribut `aria-*` |
| CSS inline, internal, external | External: `css/style.css` · Internal: `<style>` di `index.html` · Inline: atribut `style` di `index.html` |
| JavaScript DOM | Render tabel, tambah/hapus baris, keranjang, progress bar, modal dibuat dinamis |
| Validasi form & alert | Login, daftar, lupa password, tambah stok, checkout, tracking |
| Modularitas file | Data dipisah di `data.js`, logika di `script.js`, tampilan di `style.css` |
| Kreativitas | Tema "Pustaka Senja", animasi, toast notifikasi, desain responsif (HP & desktop) |

## Catatan Teknis

- `sessionStorage` dipakai untuk menyimpan status login. Halaman selain login otomatis kembali ke login jika belum masuk.
- `localStorage` dipakai agar data tambahan (stok baru, keranjang, transaksi, akun baru) tidak hilang saat pindah halaman.
- Untuk mengembalikan data ke kondisi awal, buka DevTools (F12) → Console, lalu jalankan:
  `localStorage.clear()`
- Input dari pengguna di-escape sebelum ditampilkan agar aman dari XSS.

## Teknologi

HTML5 · CSS3 (Flexbox, Grid, Custom Properties, Animation) · JavaScript (ES6+)
