<div align="center">

# 🏘 Sistem Informasi Desa Tanjungsari

Website Resmi Desa Berbasis AI — Cepat, Mobile-First, SEO-Friendly

[Live Demo](https://desatanjungsari.id)

![Next.js](https://img.shields.io/badge/Next.js-14-black)
![TypeScript](https://img.shields.io/badge/TypeScript-5-blue)
![React](https://img.shields.io/badge/React-18-blue)
![Prisma](https://img.shields.io/badge/Prisma-ORM-2D3748)
![MySQL](https://img.shields.io/badge/MySQL-Database-blue)
![Railway](https://img.shields.io/badge/Deploy-Railway-purple)
![Gemini AI](https://img.shields.io/badge/AI-Gemini-orange)
![Cloudinary](https://img.shields.io/badge/Cloudinary-Media-blue)
![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-red)

</div>

---

# 📖 About

Sistem Informasi Desa Tanjungsari adalah website resmi desa yang dirancang untuk menyajikan informasi layanan warga, berita, dan potensi desa secara cepat, rapi, dan mudah ditemukan di internet.

Website ini menggabungkan:

- AI Assistant untuk scraping & generate konten otomatis
- Dashboard Admin Modern
- Manajemen Berita & Pengumuman
- Manajemen UMKM & Potensi Desa
- Galeri & Layanan Desa
- SEO Otomatis (Sitemap, RSS, Open Graph)
- Global Search
- Statistik Kunjungan

Dikembangkan menggunakan Next.js App Router dengan Prisma ORM dan MySQL sehingga mudah dikembangkan untuk kebutuhan desa lain.

---

# ✨ Key Features

## Publik

- Beranda (hero, search, pengumuman, layanan populer, berita terbaru, statistik, UMKM unggulan, galeri)
- Profil Desa
- Perangkat Desa
- Struktur Organisasi
- Layanan Desa
- Potensi Desa
- UMKM
- Galeri
- Berita
- Pengumuman
- Kontak
- Global Search (`/cari`)
- Dark Mode
- Mobile-First & Responsive

---

## Admin

- Dashboard
- CRUD Berita, Pengumuman, Layanan, UMKM, Galeri, Perangkat Desa
- Draft / Publish per konten
- SEO Metadata per-konten
- Upload gambar (Cloudinary)
- Manajemen Admin (Admin Users)
- Statistik Pengunjung
- Pengaturan Situs
- **AI Assistant** (4 mode sumber konten):
  - Manual Link — tempel URL, AI ringkas & buatkan SEO
  - Auto Search — cek ulang sumber resmi terdaftar
  - Scraper WordPress — ambil otomatis dari situs WP resmi (0 kuota AI)
  - Search Engine — cari berita baru via Tavily
- Review flow (`NEEDS_REVIEW` → Approve & Publish / Draft)
- Approve All & Auto-Publish per sumber
- Kuota Gemini & Search termonitor

---

# 🚀 Tech Stack

| Frontend | Next.js 14 (App Router) + TypeScript |
|-----------|------------|
| Backend | Next.js API Route |
| Database | MySQL |
| ORM | Prisma |
| Authentication | Auth.js (NextAuth v4) |
| AI | Google Gemini (AI Studio) |
| Search Engine | Tavily API |
| Storage | Cloudinary |
| Styling | Tailwind CSS + shadcn/ui-style components |
| Hosting | Railway |

---

# 🏗 System Architecture

```text
Warga / Pengunjung

↓

Halaman Publik (Next.js)

↓

API Route

↓

Prisma ORM

↓

MySQL Database

↓

Cloudinary / Gemini / Tavily

↓

Response
```

---

# 🤖 AI Assistant Flow

```text
Admin

↓

Pilih Sumber (Manual Link / Auto Search / WordPress / Search Engine)

↓

Scraping + Ekstraksi Konten

↓

Gemini AI (Ringkasan + SEO Metadata)

↓

AiJob (status: NEEDS_REVIEW)

↓

Admin Review & Edit

↓

Approve & Publish / Simpan Draft
```

---

# 📂 Folder Structure

```
src/
├── app/
│   ├── (public pages)/       # beranda, profil-desa, layanan, umkm, dst.
│   ├── admin/
│   │   ├── login/
│   │   └── (dashboard)/
│   │       ├── ai-assistant/
│   │       ├── berita/
│   │       ├── pengumuman/
│   │       ├── layanan/
│   │       ├── umkm/
│   │       ├── galeri/
│   │       ├── perangkat/
│   │       └── pengaturan/
│   ├── api/                  # semua API routes
│   ├── sitemap.ts
│   ├── robots.ts
│   └── rss.xml/route.ts
├── components/
│   ├── ui/
│   ├── layout/
│   ├── home/
│   ├── admin/
│   └── shared/
├── lib/
│   ├── prisma.ts
│   ├── auth.ts
│   ├── ai-assistant.ts
│   └── utils.ts
└── middleware.ts

prisma/
├── schema.prisma
└── seed.ts
```

---

# 🗄 Database Overview

Main Tables

- users
- activity_logs
- seo_meta
- berita
- pengumuman
- layanan
- perangkat_desa
- potensi_desa
- umkm
- galeri
- profil_desa
- statistik
- kontak
- ai_source
- ai_job
- search_quota
- page_visit
- settings

---

# ⭐ Highlights

✔ AI Powered Content Generation

✔ Multi-Source Scraping (Manual, Auto Search, WordPress, Search Engine)

✔ Beautiful Modern UI

✔ Mobile-First Design

✔ Dark Mode

✔ SEO Otomatis (Sitemap, Robots, RSS, Open Graph)

✔ Global Search

✔ Review Flow Sebelum Publish

✔ Auto-Publish Opsional

✔ Statistik Kunjungan

✔ Railway Ready

---

# 🌍 Live Demo

https://desatanjungsari.id

---

# 🔌 API Overview

Menyediakan REST API internal menggunakan Next.js Route Handlers.

| Endpoint | Method | Description |
|----------|--------|-------------|
| /api/berita | CRUD | Manajemen Berita |
| /api/pengumuman | CRUD | Manajemen Pengumuman |
| /api/layanan | CRUD | Manajemen Layanan |
| /api/umkm | CRUD | Manajemen UMKM |
| /api/galeri | CRUD | Manajemen Galeri |
| /api/perangkat | CRUD | Manajemen Perangkat Desa |
| /api/profil-desa | GET/PUT | Profil Desa |
| /api/kontak | GET/PUT | Data Kontak |
| /api/search | GET | Global Search |
| /api/settings | GET/PUT | Pengaturan Situs |
| /api/stats/visit | POST | Catat Kunjungan |
| /api/upload | POST | Upload Gambar (Cloudinary) |
| /api/admin-users | CRUD | Manajemen Admin |
| /api/account/password | PUT | Ganti Password |
| /api/auth/[...nextauth] | * | Auth.js (Login Admin) |
| /api/ai/scrape | POST | AI Scrape — Manual Link |
| /api/ai/scrape-wp | POST | AI Scrape — WordPress |
| /api/ai/search | POST | AI Scrape — Search Engine |
| /api/ai/summarize | POST | Ringkas + SEO via Gemini |
| /api/ai/generate-tags | POST | Generate Tag Otomatis |
| /api/ai/sources | CRUD | Manajemen Sumber AI |
| /api/ai/check-source | POST | Cek Ulang Sumber Terdaftar |
| /api/ai/jobs | GET | Daftar AiJob (Review Queue) |
| /api/ai/approve-all | POST | Approve & Publish Semua Sekaligus |
| /api/ai/quota | GET | Sisa Kuota Gemini & Search |

---

# ⚙ Environment Variables

Create `.env`

```env
# Database
DATABASE_URL=

# Auth.js
NEXTAUTH_URL=
NEXTAUTH_SECRET=

# Site
NEXT_PUBLIC_SITE_URL=
NEXT_PUBLIC_SITE_NAME=
NEXT_PUBLIC_KECAMATAN=
NEXT_PUBLIC_KABUPATEN=

# AI Assistant (Gemini)
GEMINI_API_KEY=
GEMINI_MODEL=
GEMINI_RPM_LIMIT=
GEMINI_RPD_LIMIT=

# Search Engine (Tavily, opsional)
TAVILY_API_KEY=
SEARCH_ENGINE_MONTHLY_LIMIT=

# Cloudinary
CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=
MAX_UPLOAD_SIZE_MB=
```

---

# 📦 Installation

Clone repository

```bash
git clone https://github.com/USERNAME/website-desa.git
```

Masuk folder project

```bash
cd website-desa
```

Install dependency

```bash
npm install
```

Copy environment

```bash
cp .env.example .env
```

Setup database

```bash
npm run db:push
npm run db:seed
```

Development

```bash
npm run dev
```

Production

```bash
npm run build
npm start
```

---

# 🔑 Default Admin Login

Login pertama kali (**wajib ganti password setelah login**):

```
Email    : admin@desatanjungsari.id
Password : admin123
```

---

# 🚀 Railway Deployment

1. Push project ke GitHub

2. Login Railway

3. New Project → Deploy from GitHub

4. Tambah `+ New` → `Database` → `MySQL` di project yang sama

5. Tambahkan seluruh Environment Variables (`DATABASE_URL` klik "Add Reference" ke service MySQL)

6. Setelah deploy pertama sukses, buka tab **Shell**, jalankan:

```bash
npx prisma db push
npm run db:seed
```

7. Selesai — gambar otomatis ke Cloudinary, aman dari ephemeral filesystem Railway

---

# 🤖 Gemini AI Setup

1. Buat API Key gratis di Google AI Studio

```
https://aistudio.google.com/apikey
```

2. Tambahkan ke environment

```
GEMINI_API_KEY
GEMINI_MODEL
```

3. AI digunakan untuk

- Ringkasan Berita & Pengumuman
- SEO Metadata (judul, meta description, tag, slug)
- Generate Tag Otomatis

> Model default `gemini-3.1-flash-lite`. Cek daftar model aktif terbaru di
> https://ai.google.dev/gemini-api/docs/models — model versi 2.0 dan 2.5
> sudah mulai di-deprecate untuk API key baru per pertengahan 2026.

---

# 🔎 Tavily Search Setup (Opsional)

Digunakan untuk mode AI Assistant "Search Engine" (cari berita baru yang belum ada di web sendiri).

1. Daftar gratis di https://app.tavily.com (1.000 kredit/bulan, tanpa kartu kredit)

2. Tambahkan

```
TAVILY_API_KEY
SEARCH_ENGINE_MONTHLY_LIMIT
```

> Tanpa API key ini, mode Search Engine tidak aktif — mode Manual Link,
> Auto Search, dan Scraper WordPress tetap berjalan normal.

---

# ☁ Cloudinary Setup

Digunakan untuk

- Gambar Berita, Pengumuman, Galeri, UMKM
- Foto Perangkat Desa

Environment

```
CLOUDINARY_CLOUD_NAME
CLOUDINARY_API_KEY
CLOUDINARY_API_SECRET
```

---

# 🧠 Cara Kerja AI Assistant

Ada 4 mode sumber konten, semua dikelola dari `/admin/ai-assistant`:

1. **Manual Link** — admin tempel URL berita/pengumuman resmi. AI fetch halaman, ekstrak teks utama (`cheerio`), lalu kirim ke Gemini untuk diringkas + dibuatkan judul SEO, meta description, tag, dan slug.

2. **Auto Search** — admin mendaftarkan sumber resmi ke tabel `AiSource`. Klik **"Cek Sekarang"**, sistem fetch ulang sumber tersebut dan proses sama seperti Manual Link.

3. **Scraper WordPress** — ambil otomatis dari situs WordPress resmi lewat `_embed` (termasuk gambar unggulan & gambar dalam post), diurutkan kronologis berdasarkan tanggal post asli. Tidak memakai kuota AI.

4. **Search Engine** — cari berita baru berdasarkan tanggal via Tavily API, untuk sumber yang belum terdaftar tetap.

Setiap proses menghasilkan `AiJob` berstatus `NEEDS_REVIEW` — tidak ada yang otomatis publish kecuali opsi **"Otomatis publish"** (`autoApprove`) diaktifkan per sumber. Ada juga tombol **"Setujui Semua Sekarang"** untuk approve + publish semua draft sekaligus. AI Assistant mendukung tab **Berita, UMKM, Galeri, Perangkat Desa, dan Pengumuman**.

---

# 🔒 Security

### Authentication

- Auth.js (NextAuth v4)
- Secure Session
- HTTP Only Cookie
- Password Hash (bcryptjs)

### Authorization

- Middleware guard di `/admin/*`
- Manajemen multi-admin

### AI

- Server Side API
- API Key Hidden
- Rate Limiter Internal (RPM & RPD di bawah limit resmi Google)
- Kuota Search Engine dibatasi otomatis per bulan

### Database

- Prisma ORM
- Parameterized Query

---

# ⚡ Performance

- Next.js App Router

- Image Optimization (Next/Image, lazy loading)

- Server Components

- Sitemap Otomatis

- Mobile-First, rounded card, shadow halus, animasi ringan (Framer Motion)

---

# ❓ FAQ

### AI tidak bekerja?

Periksa `GEMINI_API_KEY` dan cek apakah `GEMINI_MODEL` masih aktif di daftar model Google AI Studio.

---

### Mode Search Engine tidak muncul?

Periksa `TAVILY_API_KEY`, dan pastikan kuota bulanan (`SEARCH_ENGINE_MONTHLY_LIMIT`) belum habis.

---

### Upload gambar gagal?

Periksa konfigurasi Cloudinary (`CLOUDINARY_CLOUD_NAME`, `CLOUDINARY_API_KEY`, `CLOUDINARY_API_SECRET`).

---

### Build gagal?

Jalankan

```bash
npm install
```

kemudian

```bash
npx prisma generate
```

---

### Ada perubahan schema Prisma setelah update, harus apa?

Jalankan ulang

```bash
npx prisma db push
```

di tab Shell Railway (atau lokal) setelah deploy update terkait AI Assistant.

---

# 🛣 Roadmap

### Completed

- 10 Halaman Publik (Beranda, Profil Desa, Perangkat Desa, Layanan, Potensi Desa, UMKM, Galeri, Kontak, Pengumuman, Berita)

- Dashboard Admin Lengkap (CRUD semua konten)

- AI Assistant 4 Mode Sumber

- Review Flow & Auto-Publish

- Global Search

- Sitemap, Robots, RSS Feed

- Open Graph Metadata

- Dark Mode

- Statistik Kunjungan

---

### Future

- Progressive Web App

- Notifikasi WhatsApp/Telegram untuk pengumuman baru

- Multi Language

- Export Statistik

- Multi Desa (multi-tenant)

---

# 🤝 Contributing

Saat ini proyek bersifat proprietary.

Pull Request dan kontribusi eksternal belum dibuka.

Jika ingin bekerja sama atau menggunakan sistem ini untuk desa lain, silakan hubungi pemilik proyek.

---

# 📜 License

Copyright © 2026 Zen.

All Rights Reserved.

This software is proprietary.

You may NOT:

- Copy source code
- Redistribute
- Modify
- Sell
- Re-upload
- Commercialize

without written permission.

---

# 📞 Contact

Developer

**Zen**

---

# ❤️ Credits

Built with

- Next.js

- React

- TypeScript

- Prisma

- MySQL

- Auth.js

- Google Gemini

- Tavily

- Cloudinary

- Railway

---

<div align="center">

# ⭐ Sistem Informasi Desa Tanjungsari

Website Resmi Desa Berbasis AI

Built with ❤️ by Zen

© 2026 All Rights Reserved

</div>
