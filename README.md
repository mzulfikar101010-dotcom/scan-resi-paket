# Scan Resi Paket — PWA (Progressive Web App)

Folder ini berisi aplikasi scan resi versi PWA. Setelah di-hosting, aplikasi
ini bisa **diinstal langsung dari Chrome di Android** seperti aplikasi biasa
(ada ikon di home screen, buka fullscreen, dan tetap bisa dipakai untuk
scan meski koneksi terputus).

## Isi folder
- `index.html` — aplikasinya
- `manifest.json` — identitas app (nama, ikon, warna)
- `service-worker.js` — bikin app bisa dipakai offline
- `icons/` — ikon aplikasi

## Cara hosting (pilih salah satu, semuanya gratis)

### Opsi 1 — Netlify Drop (paling mudah, tanpa akun pun bisa)
1. Buka https://app.netlify.com/drop
2. Drag & drop **seluruh folder ini** ke halaman tersebut
3. Tunggu beberapa detik → dapat link seperti `https://nama-acak.netlify.app`
4. Buka link itu di Chrome Android → selesai, tinggal install

### Opsi 2 — Vercel
1. Buat akun di https://vercel.com
2. Pilih "Add New Project" → upload folder ini (atau hubungkan dari GitHub)
3. Deploy → dapat link `https://nama-project.vercel.app`

### Opsi 3 — GitHub Pages
1. Upload isi folder ini ke repository GitHub baru
2. Masuk ke Settings → Pages → aktifkan GitHub Pages dari branch `main`
3. Link aktif di `https://username.github.io/nama-repo`

> Untuk instalasi jadi "app" di Android, situsnya **wajib https** — semua
> opsi di atas otomatis https, jadi aman.

## Cara install ke HP Android

1. Buka link hasil hosting di **Chrome** (bukan browser lain)
2. Chrome akan menampilkan banner/tombol **"Install app"** atau **"Add to Home screen"**
   (kalau tidak muncul otomatis: buka menu titik tiga di Chrome → "Install app")
3. Konfirmasi install → ikon "Scan Resi" muncul di home screen HP
4. Buka dari ikon itu → tampil fullscreen tanpa address bar, seperti app biasa

## Kalau mau ubah sesuatu nanti

Edit langsung file `index.html` (semua tampilan & logic ada di situ), lalu
upload ulang ke hosting yang sama (drag & drop lagi ke Netlify Drop misalnya).
Perubahan langsung aktif begitu user buka ulang aplikasinya — **tidak perlu
build ulang atau kirim file APK baru**.

## Catatan

- Data resi tersimpan di `localStorage` HP masing-masing — kalau dipakai di
  beberapa HP staf packing, datanya **tidak otomatis sinkron** antar HP
  (masing-masing HP punya catatannya sendiri). Kalau nanti butuh data
  terpusat/sinkron semua staf, itu perlu tambahan backend — bilang saja
  kalau sudah sampai tahap itu.
- Fitur **download report .xlsx** butuh koneksi internet aktif (karena
  memuat library dari CDN). Fitur **scan & simpan** tetap jalan offline.
- Barcode scanner Bluetooth/USB-OTG (mode keyboard/HID) otomatis terbaca,
  tidak perlu setting tambahan.
