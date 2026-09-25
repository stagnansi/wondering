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
- Zero JavaScript di output

## Keputusan Desain

1. Menu didefinisikan via front matter (`menu = "main"`), bukan `[menu]` di `hugo.toml`.
2. `timeZone = "Asia/Jakarta"` wajib, karena Hugo baca tanggal sebagai UTC.
3. Override `layouts/_default/baseof.html` untuk title browser dan anchor `#top` di `<body>`.
4. Artikel mengikuti gaya herman.bearblog.dev: ~500-700 kata, satu alur, paragraf pendek, tanpa heading di dalam artikel.
5. Struktur tema tidak diubah. Kustomisasi via front matter, `hugo.toml`, dan override di `layouts/`.
6. Semua perubahan dari interfaces.dev sudah di-revert. Web dibuat otentik sesuai tema.
7. Back-to-top pakai anchor `#top`, tanpa JavaScript.

## Aturan Penulisan

- Bahasa Indonesia
- Judul artikel pendek, konteks-spesifik (bukan judul abstrak)
- Smart punctuation: kutip lengkung, elipsis tunggal, en dash untuk rentang, tanpa em dash (kecuali separator footer)
- Panjang ~500-700 kata

## Kustomisasi

File di `layouts/`:

- `_default/baseof.html` — title browser + `<body id="top">`
- `_default/_markup/render-link.html` — deteksi URL asli (http/https), kasih class `url-link`
- `partials/custom_head.html` — font, warna link, arrow, footer CSS, scroll-behavior
- `partials/footer.html` — footer kustom
- `index.html` — Home dengan 3 tulisan terbaru

Detail:

- **Font**: InterDisplay (heading), InterVariable (body), IBM Plex Mono (mono + URL)
- **Link**: `#0000ff` (link & visited)
- **Dark mode**: dinonaktifkan, selalu light
- **Background**: `#fff` (putih)
- **Footer**: `Wondering® — 2026 ↑` rata tengah, user-select none
- **Back-to-top**: link anchor ke `#top`, no-JS, scroll smooth via CSS
- **Arrow ul li**: `→` warna link
- **Arrow "Lihat semua"** (Home): `.arrow-heading`, warna heading
- **URL asli**: link yang teksnya `http(s)://...` pakai IBM Plex Mono
- **og:image**: `static/images/share.png` (1200x630)

## Kontak

- Email: wondering@nordra.me
- Bluesky: @wondering.nordra.me
- X: @wondddering

## Konfigurasi Cloudflare Pages

- **Project name**: wondering
- **Production branch**: main
- **Build command**: hugo --minify
- **Build output directory**: public
- **Framework preset**: Hugo
- **Environment variable**: HUGO_VERSION=0.166.0 (wajib, match versi Termux)

### Catatan

Cloudflare default memakai Hugo versi lebih lama (0.147.x) yang tidak mengenal `.Site.Language.Locale`. Karena itu `HUGO_VERSION` di-pin ke 0.166.0.
