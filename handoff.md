# Handoff

Dokumen ini merangkum status proyek, keputusan desain, dan hal-hal yang perlu diketahui saat melanjutkan pekerjaan.

## Ringkasan Proyek

- **Nama**: Wondering®
- **URL produksi**: https://wondering.pages.dev
- **Bahasa**: Indonesia
- **Tema**: Hugo Bear Blog (submodule, `janraasch/hugo-bearblog`)
- **Deploy**: Cloudflare Pages
- **Repo**: https://github.com/stagnansi/wondering

## Stack

- Hugo v0.166.0+extended (Android/arm64, via Termux)
- Git 2.55.0
- GitHub CLI 2.101.0
- Cloudflare Pages

## Keputusan Desain

1. Menu didefinisikan via front matter (`menu = "main"`), bukan `[menu]` di `hugo.toml` — mengikuti konvensi tema.
2. `timeZone = "Asia/Jakarta"` — wajib, karena Hugo baca tanggal sebagai UTC (kalau tidak, artikel hari ini dianggap future).
3. Override `layouts/_default/baseof.html` untuk title browser: Home cuma tampil `Wondering®`, halaman lain `Judul | Wondering®`.
4. Artikel mengikuti gaya herman.bearblog.dev: ~500-700 kata, satu alur, paragraf pendek, tanpa heading di dalam artikel, tanpa em dash.
5. Struktur tema tidak diubah. Kustomisasi hanya via front matter, `hugo.toml`, dan override di `layouts/`.

## Aturan Penulisan

- Bahasa Indonesia
- Tanpa em dash
- Judul artikel pendek
- Panjang ~500-700 kata

## Kontak

- Email: wondering@nordra.me
- Bluesky: @wondering.nordra.me

## TODO

- [x] Buat repo GitHub `stagnansi/wondering`
- [x] Rename branch `master` → `main`
- [x] Setup Cloudflare Pages
- [ ] Favicon dan share image
- [ ] Custom domain (opsional)

## Konfigurasi Cloudflare Pages

- **Project name**: wondering
- **Production branch**: main
- **Build command**: hugo --minify
- **Build output directory**: public
- **Framework preset**: Hugo
- **Environment variable**: HUGO_VERSION=0.166.0 (wajib, match versi Termux)

### Catatan

Cloudflare default memakai Hugo versi lebih lama (0.147.x) yang tidak mengenal `.Site.Language.Locale`. Karena itu `HUGO_VERSION` di-pin ke 0.166.0.
