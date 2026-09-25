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
4. Artikel mengikuti gaya herman.bearblog.dev: ~500-700 kata, satu alur, paragraf pendek, tanpa heading di dalam artikel, tanpa em dash di konten website.
5. Struktur tema tidak diubah. Kustomisasi via front matter, `hugo.toml`, dan override di `layouts/partials/`.

## Aturan Penulisan

- Bahasa Indonesia
- Judul artikel pendek, konteks-spesifik (bukan judul abstrak)
- Smart punctuation: kutip lengkung (""), elipsis tunggal (…), en dash (–) untuk rentang, tanpa em dash
- Panjang ~500-700 kata

## Kustomisasi Visual

Semua di `layouts/partials/`:

- `custom_head.html` — font, warna, arrow back-to-top, footer CSS, list bullet
- `custom_body.html` — tombol back-to-top + JS
- `footer.html` — override footer
- `post_navigator.html` — override navigator prev/next

Detail:

- **Font**: InterDisplay (heading), InterVariable (body), IBM Plex Mono (mono)
- **Link**: `#0000ff` (link & visited)
- **Background**: `#fbfaf7` (cream hangat, mengurangi kontras dengan biru)
- **Lebar baris**: 65ch
- **Dark mode**: dinonaktifkan, selalu light
- **Footer**: `2026 — Wondering®` (Wondering link ke X @wondddering, weight 900)
- **Back-to-top**: kotak fixed pojok kanan bawah, muncul saat scrollable & sudah di-scroll
- **List bullet**: arrow `→` (kecuali `.blog-posts`)
- **Post navigator**: `← Prev Post` / `Next Post →`
- **og:image**: `static/images/share.png` (1200x630) untuk preview di sosial media

## Kontak

- Email: wondering@nordra.me
- Bluesky: @wondering.nordra.me

## Konfigurasi Cloudflare Pages

- **Project name**: wondering
- **Production branch**: main
- **Build command**: hugo --minify
- **Build output directory**: public
- **Framework preset**: Hugo
- **Environment variable**: HUGO_VERSION=0.166.0 (wajib, match versi Termux)

### Catatan

Cloudflare default memakai Hugo versi lebih lama (0.147.x) yang tidak mengenal `.Site.Language.Locale`. Karena itu `HUGO_VERSION` di-pin ke 0.166.0.
