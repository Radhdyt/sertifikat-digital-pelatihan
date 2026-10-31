# Sistem Sertifikat Digital Pelatihan

Aplikasi full-stack untuk penerbitan dan verifikasi sertifikat digital pelatihan berbasis **Soulbound Token (SBT)** di jaringan **Polygon**, dengan metadata tersimpan di **IPFS** (Pinata). Sertifikat bersifat anti-palsu, tidak dapat dipindahtangankan, dan bisa diverifikasi publik oleh siapa pun tanpa login.

> **Live demo:** [sertifikat-digital-pelatihan.vercel.app](https://sertifikat-digital-pelatihan.vercel.app)

> **Tugas Akhir:** proyek ini dikembangkan sebagai Tugas Akhir Program Studi S1 Teknik Informatika, Universitas Telkom.

## Masalah yang Dipecahkan

Sertifikat pelatihan konvensional (PDF biasa) mudah dipalsukan dan sulit diverifikasi keasliannya. Solusi ini menjadikan sertifikat sebagai aset on-chain yang:

- **Anti-fraud**: kepemilikan tercatat di blockchain, tidak bisa dipalsukan.
- **Verifiable tanpa login**: siapa pun bisa cek keaslian lewat halaman publik.
- **Non-transferable**: melekat ke pemilik (Soulbound Token), tidak bisa dipindahtangankan, cocok untuk kredensial.

## Fitur Utama

- **3 Portal Role**: admin, asesor, dan peserta, masing-masing dengan akses berbeda.
- **Penerbitan Sertifikat**: generate sertifikat digital berbasis SBT di jaringan Polygon, metadata + gambar tersimpan di IPFS via Pinata.
- **Verifikasi Publik**: endpoint/halaman verifikasi tanpa login untuk cek keaslian sertifikat.
- **Download PDF**: sertifikat bisa diekspor sebagai PDF (jsPDF + canvas) lengkap dengan QR code.
- **Dashboard**: ringkasan data penerbitan (Recharts).

## Tech Stack

| Layer | Teknologi |
|-------|-----------|
| Frontend | Next.js 16, React 19, TypeScript, Tailwind CSS, shadcn/ui (Radix UI) |
| Backend | Next.js API Routes, Supabase (PostgreSQL) |
| Blockchain | Solidity (thirdweb contracts), ethers, viem, Polygon |
| Storage | IPFS + Pinata (metadata & gambar sertifikat) |
| Lainnya | jose (JWT), zod (validation), react-hook-form, jspdf, qrcode |

## Struktur Project

```
├── contracts/       # Smart contract Soulbound Token (Solidity)
├── supabase/        # Migrasi & konfigurasi Supabase
├── src/             # Aplikasi Next.js (app router, komponen, API routes)
├── public/          # Aset statis
├── tailwind.config.ts
├── components.json  # Konfigurasi shadcn/ui
└── package.json
```

## Pengembangan

Prerequisite: Node.js 20+ dan akun Supabase + Pinata (sesuaikan env).

```bash
npm install
npm run dev       # development
npm run lint      # eslint
npm run build     # production build
npm run start     # start production build
```

## Deploy

Build & deploy otomatis ke **Vercel** dari branch main. Sertifikat produksi dapat diverifikasi publik di:
[sertifikat-digital-pelatihan.vercel.app](https://sertifikat-digital-pelatihan.vercel.app)

## Lisensi

Semua hak dilindungi. Kode dipublikasikan sebagai portofolio dan tidak dimaksudkan untuk digunakan ulang tanpa izin. Kontak: github.com/Radhdyt