# Changelog

Semua perubahan penting pada proyek ini dicatat di sini.
Format mengikuti [Keep a Changelog](https://keepachangelog.com/).

## [Unreleased]

## [0.1.9] - 2026-09-26

### Changed

- Revert perubahan dari interfaces.dev (65ch, text-wrap, hover none, font smoothing, skip-ink, prefers-reduced-motion, focus-visible, empty state)
- Back-to-top diganti versi no-JS (anchor `#top`)
- Footer baru: `Wondering® — 2026 ↑` rata tengah, em dash samar
- Post navigator dihapus
- Link URL asli pakai IBM Plex Mono
- Arrow pakai link color, `.arrow-heading` untuk Home

### Removed

- JavaScript (web sekarang zero JS)
- `layouts/partials/custom_body.html`
- `layouts/partials/post_navigator.html`
- `layouts/_default/list.html`

### Added

- `layouts/_default/_markup/render-link.html` untuk deteksi URL asli

## [0.1.8] - 2026-09-25

### Added

- Font smoothing (antialiased)
- Underline skip-ink dan text-underline-position
- `:focus-visible` outline untuk keyboard navigation
- `prefers-reduced-motion` untuk disable animasi & smooth scroll
- Empty state blog yang lebih manusiawi

### Changed

- Aturan penulisan: tambah smart punctuation (kutip lengkung, elipsis, en dash)

## [0.1.7] - 2026-09-25

### Changed

- Background putih diganti cream hangat (`#fbfaf7`) untuk mengurangi kontras dengan link biru
- Lebar baris dibatasi 65ch
- Heading pakai `text-wrap: balance`
- Hover effect dinonaktifkan di device sentuh (`@media (hover: none)`)

## [0.1.6] - 2026-09-25

### Added

- Artikel baru: "Ketika Peliput Jadi Berita" (2026-09-20)
- Artikel baru: "Saya Minta AI Menulis Artikel yang Menyalahkan AI" (2026-09-24)

## [0.1.5] - 2026-09-25

### Added

- Artikel baru: "GitHub dan Kode Kedua"
- Home menampilkan 3 tulisan terbaru + link "Lihat semua"

### Changed

- Footer link dari Bluesky ke X @wondddering
- Arrow (ul li, "Lihat semua", post navigator) pakai heading color
- Post navigator: arrow tidak kena hover underline
- Tanggal "Iklan di ChatGPT" jadi 2026-09-23

## [0.1.4] - 2026-09-25

### Added

- og:image untuk preview di sosial media (`static/images/share.png`, 1200x630)
- Param `images` di `hugo.toml`

### Fixed

- `meta name=title` dan `og:title` untuk Home sekarang "Wondering®" (sebelumnya "Home")
- `lineNos` diubah ke `false`
- Tambah `color-scheme: light` untuk konsistensi browser UI

## [0.1.3] - 2026-09-25

### Added

- Favicon (gambar custom)
- Custom font via `custom_head.html`:
  - Heading: InterDisplay
  - Body: InterVariable / Inter
  - Mono (time, code): IBM Plex Mono
- Warna link & visited: `#0000ff`
- Dark mode dinonaktifkan (selalu light)
- Footer kustom: `2026 — Wondering®` dengan link ke Bluesky
- Tombol back-to-top fixed di pojok kanan bawah
- Post navigator pakai arrow `←` / `→`, label `Prev Post` / `Next Post`
- List bullet jadi arrow `→` (kecuali `.blog-posts`)
- Judul blog di header weight 900
- `user-select: none` di footer

## [0.1.2] - 2026-09-25

### Added

- Deploy Cloudflare Pages: https://wondering.pages.dev
- Environment variable `HUGO_VERSION=0.166.0`

## [0.1.1] - 2026-09-25

### Added

- Repo GitHub: https://github.com/stagnansi/wondering (public)
- Git identity lokal: stagnansi / wondering@nordra.me
- Branch di-rename `master` → `main`
- Commit pertama + push ke origin/main

## [0.1.0] - 2026-09-25

### Added

- Inisialisasi proyek Hugo dengan tema Bear Blog (submodule)
- Konfigurasi `hugo.toml`
- Override `baseof.html` untuk title browser
- Halaman: Home, Blog, About
- Artikel perdana: "Iklan di ChatGPT"
- `.gitignore`, `README.md`, `handoff.md`
- Alias Termux `w`
