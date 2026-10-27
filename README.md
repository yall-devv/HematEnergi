# EcoHome — Rumah Hemat Energi

Website edukasi masyarakat bertema **Hemat Energi — Rumah Ramah Lingkungan**.
Mendukung **SDG 7** (Energi Bersih dan Terjangkau) dan **SDG 13** (Penanganan Perubahan Iklim).
Proyek UTS Mata Kuliah Pemrograman Web.

## Anggota Kelompok

| No | Nama | NIM | Tugas |
|----|------|-----|-------|
| 1 | [Nama Anggota 1] | [NIM 1] | [Tugas] |
| 2 | [Nama Anggota 2] | [NIM 2] | [Tugas] |
| 3 | [Nama Anggota 3] | [NIM 3] | [Tugas] |
| 4 | [Nama Anggota 4] | [NIM 4] | [Tugas] |

## Deskripsi Website

EcoHome mengenalkan konsep hemat energi, energi terbarukan, dan kebiasaan rendah emisi kepada masyarakat umum dengan bahasa sederhana.

- **Tujuan:** meningkatkan pemahaman tentang hemat energi dan memberi langkah praktis untuk rumah tangga.
- **Manfaat:** informasi ringkas, bersumber jelas, dan mudah dipraktikkan.
- **Sasaran pengguna:** masyarakat umum, rumah tangga, pelajar, dan mahasiswa.

## Halaman Website

| Halaman | File | Isi |
|---------|------|-----|
| Beranda | `index.html` | Hero, pengantar, tiga kartu utama, pengenalan SDG 7 dan 13, ajakan bertindak |
| Edukasi | `edukasi.html` | Pengertian hemat energi, efisiensi vs terbarukan, energi dan emisi, SDG 7 dan 13, FAQ |
| Panduan | `panduan.html` | Tips pencahayaan, elektronik, pendinginan, rendah emisi, checklist "Mulai Hari Ini" |
| Artikel | `artikel.html` | Empat artikel edukatif beserta sumbernya |
| Tentang | `tentang.html` | Tujuan, anggota kelompok, pembagian tugas, referensi, atribusi |

## Teknologi

HTML5 semantik, CSS3 (eksternal, CSS variables), Flexbox, CSS Grid, CSS Media Queries. Tanpa framework CSS dan tanpa JavaScript.

## Penjelasan Implementasi

### 1. HTML semantik
Setiap halaman memakai `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, dan `<footer>` agar struktur jelas bagi pembaca maupun pembaca layar.

```html
<header class="site-header">
  <nav aria-label="Navigasi utama">...</nav>
</header>
<main id="konten">
  <section class="section">...</section>
</main>
<footer class="site-footer">...</footer>
```

### 2. Navigasi
Menu sama di semua halaman. Halaman aktif diberi class `active` dan `aria-current="page"`, lalu diberi warna berbeda lewat CSS.

```html
<a class="nav-link active" href="panduan.html" aria-current="page">Panduan</a>
```
```css
.nav-link.active { background: var(--green-dark); color: var(--white); }
```

### 3. CSS Variables
Warna dan nilai berulang disimpan di `:root` agar mudah diubah di satu tempat.

```css
:root { --green-dark: #28543B; --cream: #F5F3E8; --radius: 16px; }
```

### 4. Flexbox
Dipakai untuk header dan menu navigasi, yang dapat membungkus ke baris baru pada layar kecil.

```css
.nav-list { display: flex; flex-wrap: wrap; justify-content: center; gap: 0.25rem; }
```

### 5. CSS Grid
Dipakai untuk susunan kartu. Awalnya satu kolom, lalu bertambah pada layar lebih besar.

```css
.grid { display: grid; gap: 1.5rem; grid-template-columns: 1fr; }
@media (min-width: 1024px) { .grid-3 { grid-template-columns: repeat(3, 1fr); } }
```

### 6. Media Queries (mobile-first)
Gaya dasar untuk smartphone, lalu `min-width: 768px` untuk tablet dan `min-width: 1024px` untuk desktop. Lebar 375, 768, dan 1440 px adalah ukuran pengujian, bukan breakpoint wajib.

### 7. Fitur tanpa JavaScript
- FAQ memakai `<details>` dan `<summary>`.
- Checklist memakai `<input type="checkbox">` (progres **tidak** tersimpan).
- Tautan antarbagian memakai anchor `#id`.
- Efek hover dan `:focus-visible` memakai CSS.

## Struktur Folder

```
ecohome/
├── index.html
├── edukasi.html
├── panduan.html
├── artikel.html
├── tentang.html
├── css/
│   └── style.css
├── images/
│   ├── logo.svg
│   ├── hero-house.svg
│   ├── solar-panel.svg
│   └── energy-saving.svg
└── README.md
```

Gambar berformat SVG (ilustrasi vektor buatan sendiri), bukan JPG.

## Cara Menjalankan Secara Lokal

1. Unduh atau salin folder proyek.
2. Buka folder di Visual Studio Code.
3. Klik kanan `index.html` lalu pilih **Open with Live Server** (atau buka `index.html` langsung di browser).

## Cara Publikasi melalui GitHub Pages

1. Buat repository publik di GitHub, misalnya `ecohome`.
2. Unggah semua file dan folder proyek (pastikan `index.html` ada di root).
3. Buka **Settings → Pages**.
4. Pada **Build and deployment**, pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu **Save**.
5. Tunggu beberapa menit, lalu buka URL yang ditampilkan dan uji semua halaman.

## Website dan Repository

- URL Website: *(isi setelah publikasi)*
- URL Repository: *(isi setelah dibuat)*

## Referensi

- United Nations — SDG 7: https://sdgs.un.org/goals/goal7
- United Nations — SDG 13: https://sdgs.un.org/goals/goal13
- ENERGY STAR — Energy Savings at Home: https://www.energystar.gov/saveathome
- Energi YLKI: https://energi.ylki.or.id/

**Atribusi aset:** semua ilustrasi SVG dibuat khusus untuk proyek ini. Ikon kartu memakai emoji bawaan perangkat. Jika aset diganti, catat sumber dan lisensinya di sini dan di halaman Tentang.
