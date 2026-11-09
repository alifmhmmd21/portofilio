# Portofolio — Alif Muhammad Hanif

Website portofolio statis (HTML/CSS/JS, tanpa build tool) untuk menampilkan profil dan proyek hardware/embedded systems.

## Struktur Folder

```
portofilio/
├── index.html        # Seluruh konten & struktur halaman (satu file)
├── css/
│   └── styles.css    # Semua styling
├── js/
│   └── main.js        # Interaksi/animasi halaman
└── images/            # Semua foto & screenshot proyek
```

Tidak ada proses build — cukup buka `index.html` di browser, atau pakai Live Server di VS Code untuk auto-reload.

## Bagian yang Sering Diupdate

Semua konten ada di `index.html`. Berikut peta bagian berdasarkan nomor baris agar mudah menemukan yang mau diubah:

| Bagian | Lokasi di `index.html` | Yang bisa diubah |
|---|---|---|
| **Judul tab & favicon** | baris 6–7 | `<title>` dan file favicon |
| **Navbar** | baris 15–25 | Nama di `.brand`, menu, teks status (mis. "Open to opportunities") |
| **Hero / halaman depan** | baris 27–50 | Judul utama (`<h1>`), deskripsi singkat (`.lead`), tombol CTA, foto profil (`images/profile.jpg`), kartu info (`.spec-tag`) |
| **Section "About"** | baris 52–77 | Paragraf deskripsi diri, daftar tools/stack di `.stack-list` |
| **Section "Work" — daftar proyek** | baris 79–184 | Lihat detail di bawah |
| **Section "Contact"** | baris 186–208 | Email, nomor telepon, link GitHub/LinkedIn/Instagram, tahun copyright |

### Menambah / Mengubah Proyek (Section "Work")

Setiap proyek adalah satu blok `<div class="project">...</div>` (ada 3 saat ini, baris 88–181). Untuk mengubah proyek yang sudah ada, edit di dalam blok terkait:

- `project-id` → label "PROJECT 0X · REV A"
- `<h3>` → nama proyek
- `project-sub` → sub-judul/peran
- `.partner-chip` → nama partner/klien (boleh lebih dari satu, atau dihapus)
- Paragraf deskripsi di dalam `project-body`
- `.chip-row` → daftar teknologi/tools yang dipakai (tambah/hapus `<span class="chip">...</span>`)
- `.gallery` → gambar proyek, ambil dari folder `images/`

Untuk **menambah proyek baru**: copy salah satu blok `<div class="project">...</div>` lengkap, ubah isinya, dan tambahkan sebelum tag penutup `</div>` section `#work` (sekitar baris 183).

Untuk **menambah gambar baru**: masukkan file ke folder `images/`, lalu referensikan dengan `<img src="images/nama-file.jpg" alt="...">` di galeri proyek terkait.

### Mengubah Kontak

Di section `#contact` (baris 186–208), ubah:
- Email: ada di 2 tempat — tombol CTA (baris 193) dan baris kontak (baris 196)
- Nomor telepon (baris 197)
- Link sosial media (baris 198–200)
- Tahun di footer (baris 204)

## Styling & Animasi

- Warna, font, dan layout diatur di `css/styles.css`.
- Font yang dipakai: Space Grotesk, Inter, JetBrains Mono (dimuat dari Google Fonts, baris 8–9 `index.html`).
- Interaksi (scroll, animasi, dsb.) diatur di `js/main.js`.

## Cara Deploy

Karena situs ini statis, bisa langsung di-deploy ke:
- **GitHub Pages** — push ke repo, aktifkan Pages dari branch `main`
- **Netlify / Vercel** — drag & drop folder atau hubungkan repo Git

Tidak perlu `npm install` atau build step apa pun.
