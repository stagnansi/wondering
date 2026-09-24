# Changelog

Semua perubahan penting pada proyek ini dicatat di sini.
Format mengikuti [Keep a Changelog](https://keepachangelog.com/).

## [Unreleased]

## [0.1.2] - 2026-09-25

### Added
- Deploy Cloudflare Pages: https://wondering.pages.dev
- Environment variable `HUGO_VERSION=0.166.0` (match versi Termux, menghindari error `.Site.Language.Locale`)

## [0.1.1] - 2026-09-25

### Added
- Repo GitHub: https://github.com/stagnansi/wondering (public)
- Git identity lokal: stagnansi / wondering@nordra.me
- Branch di-rename `master` → `main`
- Commit pertama + push ke origin/main

## [0.1.0] - 2026-09-25

### Added
- Inisialisasi proyek Hugo dengan tema Bear Blog (submodule)
- Konfigurasi `hugo.toml` (baseURL, locale, timeZone, permalinks, params)
- Override `baseof.html` untuk title browser
- Halaman: Home, Blog, About
- Artikel perdana: "Iklan di ChatGPT"
- `.gitignore` dan `README.md`
- Alias Termux `w` untuk pindah ke folder project
