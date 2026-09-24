# Changelog

Semua perubahan penting pada proyek ini dicatat di sini.
Format mengikuti [Keep a Changelog](https://keepachangelog.com/).

## [Unreleased]

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
- Tombol back-to-top fixed di pojok kanan bawah (muncul saat scrollable & sudah di-scroll)
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
