# Ketua RT — v0.9.5

Simulasi naratif jadi Ketua RT selama 52 minggu. Satu file statis (`index.html`), tanpa backend.
Progres pemain tersimpan di browser masing-masing (localStorage), kunci `rt-simulator-v2-auto` / `manual`, data versi 4.

## Isi update ini
- **v0.9.5:** layar akhir = badge. Ada 7 hasil: RT Teladan, Perekat Warga, Sang Penengah, Pengelola Kas, RT Terawat, Mindmaster dan RT Morat-Marit.
- Satu layar akhir dengan badge besar, plus kartu hasil 2400×1260 untuk dibagikan.
- Save lama dengan ending versi sebelumnya otomatis dipetakan ke hasil baru.
- **Optimasi bandwidth:**
  - Font Inter dipisah ke `assets/fonts/` dan ikut tersimpan di cache browser.
  - JS/CSS diperkecil.
  - Gambar Open Graph 2 MB diganti JPG 120 KB.
  - Banner pembuka pakai WebP.
  - `vercel.json` menyimpan `assets/` di cache browser selama 1 minggu.
- **Link share dan Open Graph mengarah ke `https://ketua-rt.mbagasah.workers.dev/`** (Cloudflare). Ini disengaja, supaya pemain baru masuk lewat Cloudflare dan kuota Vercel tidak cepat habis.

## Struktur

```text
/
├── index.html
├── vercel.json                ← cache 1 minggu untuk /assets/*
├── README.md
└── assets/
    ├── favicon/favicon.png    ← ikon tab + apple-touch-icon
    ├── fonts/inter-400/500/600/700.woff2
    ├── home/background-home-ketua-rt.webp (+ .png cadangan)
    ├── opengraph/open-graph-ketua-rt.jpg   ← 1200×630
    └── ending/                ← badge hasil akhir, SVG utama + PNG cadangan
        ├── rt-teladan, perekat-warga, sang-penengah, pengelola-kas,
        ├── rt-terawat, mastermind (hasil "Mindmaster"), morat-marit
```

Nama file harus persis seperti di atas: huruf kecil, pakai tanda hubung.

## Boleh dihapus dari repo (sudah tidak dirujuk `index.html`)
- `assets/opengraph/open-graph-ketua-rt.png` (diganti `.jpg`)
- `assets/logo/` (logo sudah ada di banner)
- `assets/home/background-home-ketua-rt.svg`
- `assets/favicon/favicon.svg` (kalau ada)

## Deploy (Vercel)
- Framework Preset: **Other**
- Build Command: kosong
- Output Directory: kosong (root)
