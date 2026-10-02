<div align="center">

<img src="Logo.png" alt="Nusly Logo" width="180">

### Simpan spot dari sosmed, biarkan AI yang menyusun perjalananmu.

Aplikasi travel planner berbasis AI untuk wisata di Indonesia.

![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-0175C2?style=for-the-badge&logo=dart&logoColor=white)
![Status](https://img.shields.io/badge/Status-Dalam_Pengembangan-orange?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)

</div>

---

## 📖 Tentang Nusly

Banyak orang Indonesia mencari inspirasi liburan dan kuliner dari TikTok dan Instagram, tetapi hasilnya hanya tersimpan berantakan di bookmark, *save*, dan catatan yang akhirnya terlupakan.

**Nusly** menyelesaikan masalah itu. Cukup *share* video atau caption wisata ke Nusly, lalu AI akan:

1. 🔍 **Mendeteksi** nama tempat dari konten yang dibagikan,
2. 📍 **Menyimpannya** sebagai pin di peta,
3. 🗓️ **Menyusun itinerary** per hari lengkap dengan rute dan estimasi waktu tempuh.

> Nusly terinspirasi dari konsep aplikasi **Roamy**, tetapi difokuskan untuk destinasi dan kebutuhan wisatawan di **Indonesia**.

---

## ✨ Fitur

### Tahap 1: MVP

| # | Fitur | Deskripsi |
|---|-------|-----------|
| 1 | **Simpan Spot dari Sosmed** | Share link atau caption dari TikTok/Instagram langsung ke Nusly |
| 2 | **Ekstraksi Tempat dengan AI** | AI mengenali nama tempat dari teks yang dibagikan, user bisa mengecek sebelum menyimpan |
| 3 | **Peta Interaktif** | Semua spot tampil sebagai pin, dengan filter kategori (kuliner, wisata alam, kafe, dll) |
| 4 | **Koleksi Spot** | Kelompokkan spot per destinasi atau tema |
| 5 | **Itinerary AI** | Input tujuan, durasi, dan preferensi, lalu AI menyusun rencana per hari |
| 6 | **Edit Itinerary Manual** | Geser urutan, tambah, atau hapus tempat |
| 7 | **Akun Pengguna** | Login agar data tersimpan dan sinkron |

### Tahap 2: Nilai Tambah

- 💸 Estimasi biaya perjalanan dalam Rupiah
- 🏨 Tombol booking hotel, tiket atraksi, dan sewa kendaraan (affiliate)
- 🌦️ Info jam buka dan cuaca
- 📤 Bagikan itinerary ke WhatsApp dan sosmed

### Tahap 3: Pengembangan Lanjutan

- 👥 Trip bareng teman (kolaborasi dan voting tempat)
- 📴 Mode offline
- ⭐ Rekomendasi tempat lokal (hidden gem)
- 🏪 Dashboard mitra untuk bisnis lokal

---

## 🔄 Alur Penggunaan

```
Temukan video wisata di TikTok/Instagram
              │
              ▼
   Share ke Nusly  ──►  AI mendeteksi tempat
              │
              ▼
   Pilih & simpan spot  ──►  Tampil di peta
              │
              ▼
  Tekan "Buat Trip"  ──►  Isi tujuan, durasi, preferensi
              │
              ▼
   AI menyusun itinerary per hari + rute
              │
              ▼
     Edit, booking, dan bagikan 🎉
```

---

## 🛠️ Teknologi

| Komponen | Teknologi |
|----------|-----------|
| Framework | **Flutter** (Dart) |
| Peta | *Rencana:* `flutter_map` + OpenStreetMap atau Google Maps |
| Share dari aplikasi lain | *Rencana:* `receive_sharing_intent` |
| Autentikasi & database | *Rencana:* Firebase Authentication + Cloud Firestore |
| AI (ekstraksi tempat & itinerary) | *Rencana:* LLM API |
| State management | *Rencana:* Provider / Riverpod |

> 📝 Item bertanda *Rencana* masih bisa berubah sesuai kesepakatan tim.

---

## 🚀 Memulai

### Prasyarat

- [Flutter SDK](https://docs.flutter.dev/get-started/install) (versi stabil terbaru)
- Android Studio atau VS Code dengan ekstensi Flutter
- Emulator Android atau perangkat fisik

### Instalasi

```bash
# 1. Clone repository
git clone https://github.com/<username>/nusly.git
cd nusly

# 2. Install dependency
flutter pub get

# 3. Jalankan aplikasi
flutter run
```

### Konfigurasi API Key

Buat file `.env` di root project (jangan di-commit ke GitHub):

```env
MAPS_API_KEY=isi_api_key_peta
AI_API_KEY=isi_api_key_ai
```

---

## 📁 Struktur Proyek (Rencana)

```
nusly/
├── lib/
│   ├── main.dart
│   ├── models/          # Model data (Spot, Trip, User)
│   ├── screens/         # Halaman (Home, Map, Trip, Profile)
│   ├── widgets/         # Komponen UI yang dipakai ulang
│   ├── services/        # Peta, AI, autentikasi, database
│   ├── providers/       # State management
│   └── utils/           # Helper dan konstanta
├── assets/              # Gambar, ikon, font
├── test/                # Unit test dan widget test
└── pubspec.yaml
```

---

## 💰 Model Bisnis

Nusly **gratis** untuk pengguna. Pendapatan datang dari:

1. **Affiliate:** komisi dari booking hotel, tiket atraksi, dan sewa kendaraan lewat mitra.
2. **Mitra bisnis lokal:** cafe, restoran, dan penginapan dapat tampil dengan label *Rekomendasi* di peta (konten sponsor selalu diberi tanda).
3. **Nusly Plus (opsional):** paket tipis untuk itinerary AI tanpa batas, sekadar menutup biaya AI.

Itinerary AI untuk pengguna gratis dibatasi per bulan agar biaya API tetap terkendali.

---

## 🗺️ Roadmap

- [ ] Desain UI/UX dan *wireframe*
- [ ] Setup proyek Flutter dan struktur folder
- [ ] Autentikasi pengguna
- [ ] Terima konten share dari TikTok/Instagram
- [ ] Ekstraksi nama tempat dengan AI
- [ ] Peta dan manajemen spot
- [ ] Pembuat itinerary AI
- [ ] Edit itinerary manual
- [ ] Pengujian dan perbaikan bug
- [ ] Presentasi proyek

---

## 👥 Tim

| Nama | NIM | Peran |
|------|-----|-------|
| _Nama Anggota 1_ | _NIM_ | _Contoh: UI/UX_ |
| _Nama Anggota 2_ | _NIM_ | _Contoh: Frontend_ |
| _Nama Anggota 3_ | _NIM_ | _Contoh: Backend & AI_ |

---

## 📸 Tampilan Aplikasi

_Screenshot akan ditambahkan setelah UI selesai._

<!--
| Beranda | Peta | Itinerary |
|---------|------|-----------|
| ![](docs/home.png) | ![](docs/map.png) | ![](docs/trip.png) |
-->

---

## 📄 Lisensi

Proyek ini dibuat untuk keperluan tugas mata kuliah **Pengembangan Aplikasi Mobile**.
Lisensi: [MIT](LICENSE) *(sesuaikan jika diperlukan)*.

---

<div align="center">

Dibuat dengan ❤️ untuk wisatawan Indonesia

</div>
