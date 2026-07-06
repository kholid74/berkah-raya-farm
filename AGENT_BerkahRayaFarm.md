# AGENT.md — Berkah Raya Farm Landing Page

Instruksi lengkap untuk membangun landing page **Berkah Raya Farm**
menggunakan Astro + Tailwind CSS. Baca seluruh dokumen sebelum
menulis satu baris kode apapun.

---

## 1. KONTEKS PROYEK

**Berkah Raya Farm** adalah produsen dan supplier telur asin, telur bebek,
dan telur omega yang berbasis di Jawa Tengah dengan offline store di Ciputat,
Tangerang Selatan. Produk langsung dari peternakan sendiri, diolah dengan
metode tradisional menggunakan batu bata merah.

**Jenis website:** Landing page — 1 halaman, scroll
**Target audiens:** Semua segmen — rumah tangga, warung & toko kelontong,
restoran & katering, area distribusi Jabodetabek
**Tujuan utama:** Mengarahkan pengunjung ke WhatsApp dan marketplace Shopee
**Tone:** Hangat, terpercaya, autentik — bukan korporat

---

## 2. IDENTITAS BRAND

**Nama bisnis:** Berkah Raya Farm
**Tagline yang diusulkan:** "Dari peternakan kami, langsung ke meja makan kamu."
**Sub tagline:** Produsen & Supplier Telur Asin · Telur Bebek · Telur Omega
**Lokasi:** Ciputat, Tangerang Selatan (offline store)
**Asal produk:** Asli Jawa Tengah

**Keunggulan utama (USP):**
1. Hasil panen peternakan sendiri — bukan reseller
2. Diolah metode tradisional menggunakan batu bata merah
3. Kualitas dan rasa istimewa
4. Produk selalu dikirim dalam keadaan baru/segar

---

## 3. DESIGN SYSTEM

### 3.1 Palet Warna

```css
:root {
  /* Primary */
  --color-primary: #C8171D;      /* Merah — CTA, aksen kuat */
  --color-primary-dark: #A01015; /* Merah gelap — hover state */

  /* Secondary */
  --color-secondary: #F5C518;    /* Kuning — highlight, badge, aksen */
  --color-secondary-dark: #D4A800; /* Kuning gelap */
  --color-secondary-light: #FEF3C7; /* Kuning sangat muda — bg badge */

  /* Neutral */
  --color-white: #FFFFFF;
  --color-cream: #FFFBF0;        /* Background utama — warm white */
  --color-surface: #FFF8E7;      /* Surface card — warm cream */
  --color-border: #F0E6C8;       /* Border subtle */

  /* Text */
  --color-text-heading: #1A0A00; /* Cokelat tua — heading */
  --color-text-body: #5C3D2E;    /* Cokelat medium — body text */
  --color-text-muted: #9A7B6A;   /* Cokelat muda — caption */

  /* Dark section */
  --color-dark: #1A0A00;         /* Background dark section */
  --color-dark-surface: #2D1200; /* Surface di dark section */
}
```

### 3.2 Tipografi

```css
/* Import di global.css */
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700;800&family=Plus+Jakarta+Sans:wght@400;500;600&display=swap');

--font-display: 'Playfair Display', serif;  /* Heading — elegan, tradisional */
--font-body: 'Plus Jakarta Sans', sans-serif; /* Body — modern, readable */
```

**Reasoning font:** Playfair Display memberi kesan premium dan tradisional
yang sesuai dengan positioning "metode tradisional" — kontras elegan dengan
Jakarta Sans yang modern untuk body text.

### 3.3 Visual Direction

- Warm, earthy, autentik — seperti brand makanan premium lokal
- Foto produk sebagai hero visual — bukan ilustrasi
- Gunakan texture subtle (grain, paper) untuk kesan tradisional
- Hindari tampilan terlalu "tech" atau terlalu "modern minimalis"
- Inspirasi visual: brand telur premium, brand makanan tradisional Jawa

---

## 4. STRUKTUR FOLDER

```
berkah-raya-farm/
├── public/
│   ├── favicon.svg
│   ├── logo.png              # Logo Berkah Raya Farm (dari klien)
│   └── images/
│       ├── hero-product.jpg  # Foto produk utama (dari klien)
│       ├── products/         # Foto per varian produk
│       └── farm/             # Foto peternakan / proses produksi
│
├── src/
│   ├── components/
│   │   ├── Navbar.astro
│   │   ├── Hero.astro
│   │   ├── USP.astro
│   │   ├── Products.astro
│   │   ├── WhyUs.astro
│   │   ├── HowToOrder.astro
│   │   ├── Coverage.astro
│   │   ├── Testimonials.astro
│   │   ├── CTA.astro
│   │   └── Footer.astro
│   │
│   ├── layouts/
│   │   └── BaseLayout.astro
│   │
│   ├── pages/
│   │   └── index.astro
│   │
│   └── styles/
│       └── global.css
│
├── astro.config.mjs
└── tailwind.config.mjs
```

---

## 5. KONTEN SETIAP SECTION

### 5.1 Navbar

**Struktur:**
- Logo Berkah Raya Farm (kiri)
- Nav links: Produk · Keunggulan · Cara Order · Kontak
- CTA button: "Pesan Sekarang" → link WhatsApp
- Background: putih dengan border bottom tipis
- Sticky saat scroll

---

### 5.2 Hero Section

**Background:** Foto produk full-width dengan overlay gradient
gelap di sisi kiri agar teks terbaca

**Layout:**
```
[Badge — "🥚 Langsung dari Peternakan Sendiri"]
[H1 — Headline utama]
[Sub text]
[2 CTA buttons]
[3 trust badges bawah]
```

**Copy:**

Badge:
```
🥚 Asli Jawa Tengah · Peternakan Sendiri
```

Headline H1:
```
Telur Asin Pilihan,
Langsung dari Peternak.
```

Sub text:
```
Berkah Raya Farm menghadirkan telur asin, telur bebek,
dan telur omega berkualitas — diolah dengan metode tradisional
batu bata merah, dikirim segar ke seluruh Jabodetabek.
```

CTA Primary: `Pesan via WhatsApp →`
Link: `https://wa.me/62XXXXXXXXXX?text=Halo+Berkah+Raya+Farm,+saya+ingin+pesan+produk.`

CTA Secondary: `Lihat di Shopee`
Link: `[URL Shopee Berkah Raya Farm]`

**3 Trust badges di bawah CTA:**
```
✓ Hasil panen sendiri    ✓ Metode tradisional    ✓ Selalu segar
```

---

### 5.3 USP Section — "Mengapa Berkah Raya Farm?"

**Background:** Dark (`--color-dark`) dengan teks putih
**Header:**
```
Yang membuat kami berbeda
```

**4 keunggulan dalam kartu:**

| Icon | Judul | Deskripsi |
|------|-------|-----------|
| 🐣 | Peternakan Sendiri | Bukan reseller. Semua produk berasal langsung dari peternakan kami di Jawa Tengah — jaminan kesegaran dari sumber. |
| 🧱 | Metode Batu Bata Merah | Proses pengasinan tradisional menggunakan batu bata merah menghasilkan cita rasa yang khas dan meresap sempurna. |
| 📦 | Selalu Segar Saat Tiba | Setiap pesanan diproses dan dikirim dalam kondisi baru — tidak ada produk yang lama di gudang. |
| 🚚 | Kirim ke Jabodetabek | Melayani pengiriman ke seluruh wilayah Jabodetabek untuk kebutuhan rumah tangga maupun bisnis. |

---

### 5.4 Products Section

**Background:** Cream (`--color-cream`)
**Header:**
```
Produk Kami
Pilihan lengkap untuk kebutuhan kamu dan bisnis kamu.
```

**4 kartu produk:**

**Telur Asin**
```
Produk unggulan kami. Dibuat dari telur bebek pilihan,
diasin dengan metode batu bata merah selama proses yang
tepat — menghasilkan rasa gurih yang meresap sempurna.
[Badge: Bestseller]
```

**Telur Bebek Segar**
```
Telur bebek segar langsung dari peternakan.
Cocok untuk konsumsi sehari-hari maupun
kebutuhan usaha kuliner.
```

**Telur Omega**
```
Telur dengan kandungan omega tinggi dari bebek
yang diternakkan dengan pakan khusus.
Pilihan sehat untuk keluarga.
```

**Produk Lainnya**
```
Kami juga melayani kebutuhan supplier bahan
dapur lainnya seperti bawang bombay.
Hubungi kami untuk ketersediaan produk.
```

**CTA di bawah grid:**
```
Butuh harga grosir atau pemesanan dalam jumlah besar?
[Hubungi Kami →]
```

---

### 5.5 How To Order Section

**Background:** Surface (`--color-surface`)
**Header:**
```
Cara Pesan
Mudah, cepat, dan langsung dikonfirmasi.
```

**3 langkah:**

| No | Langkah | Deskripsi |
|----|---------|-----------|
| 01 | Hubungi Kami | Chat WhatsApp atau kunjungi toko kami di Ciputat — ceritakan produk dan jumlah yang dibutuhkan |
| 02 | Konfirmasi Pesanan | Kami konfirmasi ketersediaan, harga, dan estimasi pengiriman |
| 03 | Terima Produk Segar | Pesanan dikirim dalam kondisi baru dan segar langsung ke lokasi kamu |

**Alternatif order:**
```
Lebih suka belanja online?
[Kunjungi Toko Shopee Kami →]
```

---

### 5.6 Coverage Section

**Background:** Dark (`--color-dark`)
**Header:**
```
Area Pengiriman
Melayani seluruh wilayah Jabodetabek.
```

**Konten:**
- Peta sederhana atau ilustrasi area Jabodetabek
- List area yang dilayani dalam chip/badge:
  Jakarta · Bogor · Depok · Tangerang · Tangerang Selatan · Bekasi
- Teks tambahan:
```
Butuh pengiriman ke luar area?
Hubungi kami untuk konfirmasi ketersediaan pengiriman.
```
- Highlight lokasi offline store:
```
📍 Toko Offline: Ciputat, Tangerang Selatan
Senin–Sabtu, 08.00–17.00 WIB
```

---

### 5.7 Testimonials Section

**Background:** Cream (`--color-cream`)
**Header:**
```
Kata Mereka
```

**3 testimoni dummy realistis:**

```
"Sudah langganan Berkah Raya Farm buat stok warung saya.
Telur asinnya enak, konsisten, dan selalu segar pas datang.
Harga juga bersaing buat grosir."
— Pak Hendra, Pemilik Warung, Depok

"Pesan buat katering nikahan, hasilnya memuaskan.
Telur asinnya matang sempurna dan rasanya gurih.
Respons WhatsApp-nya cepat, pengiriman tepat waktu."
— Bu Wulandari, Pemilik Katering, Bekasi

"Beli telur omega untuk konsumsi keluarga.
Suka karena langsung dari peternak, jadi lebih yakin
kualitas dan kesegarannya."
— Ibu Ratna, Pelanggan Rumahan, Jakarta Selatan
```

---

### 5.8 CTA Section

**Background:** Merah (`--color-primary`) dengan teks putih

**Copy:**
```
Siap pesan atau ada pertanyaan?

Hubungi kami sekarang — kami siap bantu pilihkan
produk yang paling sesuai kebutuhan kamu.
```

**2 CTA buttons:**
- Primary (kuning): `Pesan via WhatsApp →`
- Secondary (outline putih): `Lihat Toko Shopee`

**Info kontak di bawah button:**
```
📍 Toko: Ciputat, Tangerang Selatan
🕐 Senin–Sabtu, 08.00–17.00 WIB
```

---

### 5.9 Footer

**Background:** Dark (`--color-dark`)

```
Logo Berkah Raya Farm
Produsen & Supplier Telur Asin · Telur Bebek · Telur Omega
Asli Jawa Tengah

[WhatsApp] [Shopee]

Ciputat, Tangerang Selatan
© 2025 Berkah Raya Farm
```

---

## 6. SEO & META

```
Title: "Berkah Raya Farm — Telur Asin & Telur Bebek Segar Asli Jawa Tengah"

Description: "Produsen dan supplier telur asin, telur bebek, dan telur
omega dari peternakan sendiri. Diolah metode tradisional batu bata merah,
dikirim segar ke seluruh Jabodetabek. Pesan via WhatsApp."

Keywords: "telur asin, telur bebek, telur omega, supplier telur asin
Jabodetabek, telur asin batu bata merah, distributor telur asin,
Berkah Raya Farm, telur asin Ciputat"
```

---

## 7. TAILWIND CONFIG

```javascript
export default {
  content: ['./src/**/*.{astro,html,js,ts}'],
  theme: {
    extend: {
      colors: {
        primary: { DEFAULT: '#C8171D', dark: '#A01015' },
        secondary: { DEFAULT: '#F5C518', dark: '#D4A800', light: '#FEF3C7' },
        cream: '#FFFBF0',
        surface: '#FFF8E7',
        dark: { DEFAULT: '#1A0A00', surface: '#2D1200' },
        body: '#5C3D2E',
        muted: '#9A7B6A',
      },
      fontFamily: {
        display: ['Playfair Display', 'serif'],
        body: ['Plus Jakarta Sans', 'sans-serif'],
      },
    },
  },
}
```

---

## 8. PLACEHOLDER ASET

Selama foto asli dari klien belum tersedia, gunakan:
- Foto telur asin: Unsplash query "salted egg", "duck egg"
- Foto peternakan: Unsplash query "duck farm", "traditional farm Java"
- Foto pengiriman: Unsplash query "fresh food delivery"

**Wajib diganti dengan foto asli dari klien sebelum deploy.**

---

## 9. LINK PLACEHOLDER

Ganti semua placeholder berikut sebelum deploy:
- `+62XXXXXXXXXX` → nomor WhatsApp Berkah Raya Farm
- `[URL Shopee Berkah Raya Farm]` → URL toko Shopee
- Alamat lengkap offline store di Ciputat

---

## 10. URUTAN BUILD

1. Setup project Astro + Tailwind
2. global.css — CSS variables, base styles
3. BaseLayout.astro — head, meta, font
4. Navbar.astro
5. Hero.astro — section terpenting, kerjakan sampai bagus
6. USP.astro
7. Products.astro
8. HowToOrder.astro
9. Coverage.astro
10. Testimonials.astro
11. CTA.astro
12. Footer.astro
13. index.astro — compose semua section
14. Mobile responsiveness — test di 375px, 768px, 1440px
15. Performance audit — target PageSpeed 90+
16. Deploy ke Vercel

---

## 11. CATATAN PENTING

- **Semua copy dalam Bahasa Indonesia**
- **Mobile-first** — mayoritas klien UMKM browsing via HP
- **Foto produk adalah kunci** — jangan pakai placeholder terlalu lama
- **Tombol WhatsApp harus visible di semua viewport** —
  pertimbangkan floating WhatsApp button di mobile
- **Warna merah dan kuning** harus digunakan dengan proporsional —
  merah untuk aksi/CTA, kuning untuk highlight/badge,
  jangan keduanya bersaing di satu area
- **Tidak ada lorem ipsum** — semua placeholder copy harus realistis

---

*AGENT.md — Berkah Raya Farm Landing Page*
*Dibangun oleh Kalsara Studio · kalsara.id*
