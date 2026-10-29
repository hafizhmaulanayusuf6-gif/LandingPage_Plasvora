# Plasvora Landing Page

Website landing page resmi untuk **Plasvora**, platform digital bertema lingkungan yang berfokus pada inspirasi pemanfaatan sampah plastik dan penemuan bahan daur ulang.

---

## 1. Tujuan Proyek

Landing page ini berfungsi untuk:
- Memperkenalkan identitas brand dan tujuan inisiatif Plasvora.
- Menjelaskan permasalahan sampah anorganik yang ingin diselesaikan melalui pendekatan sirkularitas lokal.
- Menampilkan konsep fitur utama (Inspirasi Upcycling, Panduan Kreasi, Informasi Material, Katalog Daur Ulang).
- Menampilkan preview interaktif antarmuka aplikasi mobile pada smartphone mockup.
- Menjelaskan potensi manfaat untuk kelompok pengguna (kreator/pengrajin dan pelaku daur ulang).
- Mengarahkan pengunjung mengeksplorasi bagian website dengan navigasi yang responsif dan terarah.

---

## 2. Tech Stack

- **Backend / Routing:** Laravel 12 (PHP 8.2+)
- **Frontend Framework:** Vue 3 (Composition API dengan `<script setup>`, JavaScript biasa tanpa TypeScript)
- **Monolith Bridge:** Inertia.js (Inertia Laravel + `@inertiajs/vue3`)
- **Styling System:** Tailwind CSS v4 via `@tailwindcss/vite`
- **Build Tool:** Vite 7
- **Code Formatter:** Laravel Pint
- **Testing:** PHPUnit

---

## 3. Prasyarat Sistem

- PHP 8.2 atau lebih baru
- Composer 2.x
- Node.js 18+ atau 20+
- npm 9+ (pada lingkungan Windows PowerShell, disarankan menjalankan `npm.cmd` jika policy PowerShell membatasi script `.ps1`)

---

## 4. Cara Menjalankan Proyek (Development)

Jalankan perintah berikut pada terminal:

### Opsi 1: Menjalankan Sekaligus (Rekomendasi)
```bash
composer run dev
```
Perintah ini akan menjalankan server Laravel, queue worker, Pail log, dan Vite HMR secara bersamaan melalui `concurrently`.

### Opsi 2: Menjalankan Secara Terpisah

Terminal 1 (Backend Laravel):
```bash
php artisan serve
```
Aplikasi Laravel akan aktif di `http://127.0.0.1:8000`.

Terminal 2 (Frontend Vite HMR):
```bash
npm.cmd run dev
```

---

## 5. Cara Build Produksi

Untuk mengompilasi asset frontend (JavaScript dan CSS) menjadi bundel produksi yang optimal:

```bash
npm.cmd run build
```

Hasil kompilasi akan otomatis disimpan di direktori `public/build/`.

---

## 6. Menjalankan Pengujian & Format Kode

### Menjalankan Automated Test
```bash
composer run test
# atau
php artisan test
```

### Memeriksa dan Memformat Kode PHP
```bash
composer exec pint
```

---

## 7. Struktur Folder Utama

```text
c:\LandingPage\
├── app/
│   └── Http/
│       └── Controllers/
│           └── LandingController.php     # Controller ringan yang merender Inertia::render('Home')
├── public/
│   ├── build/                           # Output asset produksi dari Vite
│   └── images/
│       └── app-screens/                 # Direktori screenshot aplikasi aktual
│           ├── beranda.jpg
│           ├── analisis.jpg
│           ├── marketplace.jpg
│           ├── aktivitas.jpg
│           └── design-system.png
├── resources/
│   ├── css/
│   │   └── app.css                      # Konfigurasi Tailwind v4 & Design Tokens (@theme)
│   ├── js/
│   │   ├── app.js                       # Inisialisasi Inertia.js dan Vue 3
│   │   ├── bootstrap.js
│   │   ├── Components/                  # Komponen UI modular
│   │   │   ├── AppPhoneMockup.vue       # Komponen smartphone frame fleksibel
│   │   │   ├── Navbar.vue               # Navigasi desktop & mobile drawer
│   │   │   ├── HeroSection.vue          # Hero banner + mockup aplikasi
│   │   │   ├── FeatureSummary.vue       # 4 kartu ringkasan mengambang
│   │   │   ├── MainFeatures.vue         # 6 fitur unggulan (3 kiri, phone center, 3 kanan)
│   │   │   ├── VisualBanner.vue         # Banner visual lebar dengan gelombang organik
│   │   │   ├── ExplorationCards.vue     # 3 kartu eksplorasi produk
│   │   │   ├── PotentialBenefits.vue    # Potensi manfaat untuk kreator & pelaku daur ulang
│   │   │   ├── AppPreviewSection.vue    # Tab preview interaktif 4 layar aplikasi
│   │   │   ├── FinalCta.vue             # Call to action penutup
│   │   │   └── FooterSection.vue        # Footer informasi & hak cipta
│   │   └── Pages/
│   │       └── Home.vue                 # Halaman utama landing page
│   └── views/
│       └── app.blade.php                # Root template Blade untuk Inertia
├── routes/
│   └── web.php                          # Route tunggal GET / -> LandingController
├── tailwind.config.js
└── vite.config.js
```

---

## 8. Lokasi Aset & Cara Mengganti Screenshot Aplikasi

Screenshot layar aplikasi smartphone disimpan pada direktori:

`public/images/app-screens/`

Daftar file saat ini:
- `beranda.jpg`: Layar Beranda utama dan ringkasan sirkularitas.
- `analisis.jpg`: Layar analisis foto material berbasis AI (Computer Vision).
- `marketplace.jpg`: Layar katalog bahan daur ulang (PET, HDPE, PP).
- `aktivitas.jpg`: Layar jejak perjalanan material dan riwayat serah terima.

### Cara Mengganti dengan Screenshot Baru:
1. Simpan screenshot baru Anda ke direktori `public/images/app-screens/` dengan format gambar web standar (`.jpg`, `.png`, atau `.webp`).
2. Jika ingin mengganti layar pada mockup tertentu, perbarui prop `image-src` pada komponen pemanggil atau perbarui objek pada `resources/js/Components/AppPreviewSection.vue`.
3. Komponen `AppPhoneMockup.vue` secara otomatis menyesuaikan rasio aspek layar smartphone (9:19.5), dilengkapi frame bezel realistis, dynamic island, dan penanganan fallback jika gambar tidak ditemukan.

---

## 9. Design System Plasvora

- **Warna Utama:**
  - Primary: `#0D3B2E` (Dark Forest Green)
  - Secondary: `#4E9F85` (Medium Emerald Green)
  - Tertiary: `#E6F7F0` (Light Mint Surface)
  - Neutral: `#5A6E65` (Grayish Sage Neutral)
  - Base Background: `#F8FAF9` & `#FFFFFF`
- **Tipografi:**
  - Heading: `Outfit, sans-serif`
  - Body & UI: `Plus Jakarta Sans, sans-serif`

---

## 10. Fitur yang Belum Diimplementasikan (Di Luar Lingkup Landing Page)

Sesuai instruksi dan batasan proyek landing page statis:
- Autentikasi pengguna, registrasi akun, dan login belum diaktifkan pada landing page ini.
- Database transaksi, pemesanan material, dan keranjang belanja tidak dihubungkan (aplikasi ini adalah landing page perkenalan).
- API backend eksternal untuk pengenalan gambar Computer Vision dan inventaris belum diintegrasikan ke landing page ini.
