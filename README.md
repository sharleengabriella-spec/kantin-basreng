# Kantin Basreng — PWA

Website kantin ringan berbasis HTML/CSS/JavaScript, siap di-deploy ke GitHub Pages atau Vercel.

## Fitur
- Katalog produk, kategori, pencarian, keranjang, dan checkout ke WhatsApp.
- Dashboard admin sederhana untuk mengelola menu, melihat ringkasan pesanan lokal, dan mengatur nama/nomor WhatsApp/PIN.
- PWA installable dengan manifest, ikon, dan service worker untuk cache aset inti.
- Responsif untuk HP dan desktop.

## Konfigurasi sebelum deploy
1. Buka `config.js`.
2. Ganti `whatsapp` menjadi nomor WhatsApp kantin dengan format internasional tanpa `+`, contoh `6281234567890`.
3. Ganti `adminPin` dari nilai awal `1234`.
4. Simpan perubahan.

## Deploy ke GitHub + Vercel
1. Buat repository baru di GitHub, misalnya `kantin-basreng`.
2. Upload seluruh isi folder ini ke root repository (pastikan `index.html` ada di root).
3. Buka https://vercel.com, login dengan GitHub, pilih **Add New → Project**.
4. Import repository `kantin-basreng`.
5. Framework preset pilih **Other**; Build Command dan Output Directory dikosongkan (static site).
6. Klik **Deploy**. Vercel akan memberikan URL publik `*.vercel.app`.
7. Setiap perubahan yang di-push ke branch utama GitHub akan memicu deployment baru.

## Cara admin
- Buka website, tekan **Admin**, masukkan PIN.
- PIN awal `1234` kecuali sudah diganti di `config.js`.
- Kelola menu di tab **Kelola Menu**.
- Atur nama kantin dan nomor WhatsApp di tab **Pengaturan**.

## Catatan penting tentang data
Versi starter ini menyimpan menu, keranjang, pengaturan, dan ringkasan checkout pada `localStorage` browser. Artinya data dashboard tidak tersinkron otomatis antar perangkat; checkout pelanggan dikirim langsung ke WhatsApp. Jangan gunakan PIN contoh untuk keamanan produksi. Untuk sistem multi-admin, stok real-time, dan pesanan pelanggan masuk otomatis ke dashboard dari semua HP, perlu backend/database (misalnya Supabase) dan autentikasi server-side.

## Uji lokal
Jalankan server statis, misalnya `python -m http.server 8000`, lalu buka `http://localhost:8000`. Service worker/PWA memerlukan localhost atau HTTPS.
