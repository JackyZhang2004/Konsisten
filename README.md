# Konsisten

Pelacak kebiasaan, jadwal harian, to-do, dan resolusi. Berjalan sepenuhnya di
browser, menyimpan data di perangkatmu, dan bisa dipasang ke home screen seperti
aplikasi biasa (PWA).

## Isi berkas

- `index.html` — seluruh aplikasi (satu berkas).
- `manifest.webmanifest` — info aplikasi untuk pemasangan ke home screen.
- `sw.js` — service worker agar bisa dipasang & dipakai offline.
- `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` — ikon aplikasi.

Semua berkas harus berada dalam satu folder yang sama.

## Publikasi ke GitHub Pages

1. Buat repository baru di GitHub, lalu unggah seluruh berkas ini ke dalamnya.
2. Buka **Settings → Pages**.
3. Pada **Source**, pilih **Deploy from a branch**, branch `main`, folder `/ (root)`,
   lalu **Save**.
4. Tunggu sebentar; GitHub akan memberi alamat seperti
   `https://NAMA-AKUN.github.io/NAMA-REPO/`.

> Service worker dan pemasangan PWA membutuhkan HTTPS. GitHub Pages sudah HTTPS,
> jadi langsung berfungsi.

## Pasang ke home screen

- **Android (Chrome):** buka alamatnya → menu titik tiga → **Add to Home screen** /
  **Install app**. Ikon muncul di home screen dan terbuka layar penuh.
- **iPhone (Safari):** buka alamatnya → tombol **Share** → **Add to Home Screen**.

## Data & cadangan

- Data disimpan secara lokal di browser perangkatmu (`localStorage`). Tidak dikirim
  ke server mana pun.
- Buka tab **Progres → Data & cadangan** untuk **Ekspor** (mengunduh berkas
  `.json`) atau **Impor** (memulihkan dari berkas).
- Penting: data terikat pada alamat situs. Jika kamu mengembangkan/menjalankan
  aplikasi di alamat berbeda (mis. `localhost` vs GitHub Pages), **ekspor** dari
  yang lama lalu **impor** di yang baru agar data tidak hilang. Ekspor berkala juga
  berguna sebagai cadangan jika data browser dibersihkan.

## Menjalankan secara lokal

Service worker tidak aktif lewat `file://`. Jalankan server statis sederhana:

```bash
python3 -m http.server 8000
# lalu buka http://localhost:8000
```
