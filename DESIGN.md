# Nusly: Panduan Desain (DESIGN.md)

Aplikasi travel planner berbasis AI untuk wisata Indonesia.
Dokumen ini adalah **satu-satunya acuan** untuk tampilan aplikasi. Kalau ada yang tidak tertulis di sini, pilih yang paling sederhana.

---

## 1. Arah desain

**Satu kalimat:** alur dan tata letak mengikuti aplikasi **Roamy** (dari video yang kamu kirim), tapi tampilannya hitam dan putih saja dan memakai konten wisata Indonesia.

Satu-satunya referensi visual adalah video Roamy. Pola yang diambil:

| # | Pola di Roamy | Diterapkan di Nusly |
|---|---------------|---------------------|
| 1 | Masuk lewat tombol **Share** di TikTok/Instagram. Roamy muncul sebagai salah satu tujuan | Nusly muncul di menu Share. Layar proses menampilkan "Mendeteksi tempat..." dengan bingkai pindai di tengah, progress bar, dan toast bawah "Tidak mau menunggu? Nusly menyimpan di latar belakang" + tombol "Oke" |
| 2 | Modal **Import Locations**: daftar tempat dengan ikon kategori kecil, nama, keterangan, dan kotak centang; toast "Saved 9 spots"; dua tombol bawah | Modal "Impor tempat": kartu melayang berisi daftar tempat bercentang, toast "Tersimpan 9 spot", tombol sekunder "Tambah ke koleksi" dan tombol utama hitam "Simpan spot" |
| 3 | **Peta penuh** sebagai halaman utama spot tersimpan, dengan bottom sheet berisi ringkasan ("50 Cities, 98 Spots"), chip kota, chip kategori (All, Attractions, Bar, Cafe), dan daftar baris berfoto | Tab **Peta** jadi halaman andalan: peta penuh + bottom sheet "Indonesia, 50 kota · 98 spot", chip kota dengan jumlah, chip kategori (Semua, Atraksi, Kafe, Kuliner), baris spot dengan foto, nama, label kategori + lokasi, deskripsi singkat |
| 4 | Dua tombol mengambang di atas daftar: **Add Spot** dan **Plan Trip** | Tombol mengambang "Tambah spot" (sekunder) dan "Buat trip" (utama hitam) |
| 5 | **Create Trip** sebagai kartu modal melayang: baris "Where" dan "When", grid 2 kolom chip **Preferences** berikon kecil, tautan "Skip, Surprise me", tombol bawah "Clear" dan "Continue" | Kartu modal "Buat trip": baris "Ke mana" dan "Kapan" (misal 4 hari / Kapan saja), grid chip Preferensi berikon (Populer, Museum, Alam, Kuliner, Sejarah, Belanja), tautan "Lewati, kejutkan aku", tombol "Hapus" dan "Lanjut" (hitam) |
| 6 | Sheet kecil **"Starting to plan your trip"** dengan ikon kilau dan langkah yang tercentang satu per satu | Sheet "Nusly sedang menyusun perjalananmu" dengan langkah bertahap |
| 7 | Hasil trip dalam bottom sheet di bawah peta rute: judul "4-Day Bali Trip", "4 days · 28 spots", tombol "Choose dates", tab **Unplanned / Day 1 / Day 2...**, baris bernomor berfoto dengan chip waktu tempuh dan jarak, tombol navigasi bulat | Sheet "Trip 4 hari di Malang", "4 hari · 28 spot", tombol "Pilih tanggal", tab "Belum diatur / Hari 1 / Hari 2...", baris bernomor dengan chip "1 j 22 m · 35,9 km" dan tombol navigasi bulat |

**Ciri tampilan Roamy yang dipertahankan:** sudut sangat membulat, kartu dan sheet melayang di atas peta atau konten, chip berbentuk pil dengan ikon kecil, tombol utama berbentuk pil di bagian bawah, dan banyak ruang putih.

**Yang diganti:** warna biru dan warna kategori di Roamy menjadi **hitam, putih, dan abu**. Kategori dibedakan lewat ikon dan label.

**Prinsip:**
1. **Hitam dan putih saja.** Tidak ada warna lain di antarmuka.
2. **Satu aksi utama per layar.** Tombol hitam penuh hanya satu.
3. **Peta adalah pusat cerita.** Sebagian besar alur berlangsung di peta dan bottom sheet, bukan layar penuh yang berpindah-pindah.
4. **Konten yang bicara.** Foto tempat dan peta adalah satu-satunya hal yang berwarna alami.
5. **Lega dan konsisten.** Komponen sama, jarak sama.

---

## 2. Warna

Hanya putih dan hitam. Abu-abu hanya turunan hitam (hitam dengan transparansi) untuk garis, latar kartu, dan teks sekunder. **Tidak ada warna berhue** (merah, hijau, biru, oranye, dan lainnya).

| Token | Hex | Dipakai untuk |
|-------|-----|---------------|
| `white` | `#FFFFFF` | Latar semua layar, teks di atas hitam |
| `black` | `#000000` | Teks utama, tombol utama, ikon aktif, pin |
| `gray-50` | `#F7F7F7` | Latar kartu, kolom input, chip tidak aktif |
| `gray-100` | `#EFEFEF` | Latar tombol sekunder, track progress |
| `gray-200` | `#E3E3E3` | Garis pemisah dan border |
| `gray-400` | `#A6A6A6` | Placeholder, ikon nonaktif |
| `gray-600` | `#666666` | Teks sekunder, keterangan (kontras 5,7:1 di atas putih) |

**Aturan:**
- Sekitar **90% putih**, 8% abu muda, 2% hitam pekat (tombol, pin, teks judul).
- **Status tanpa warna:** berhasil = ikon centang + teks "Berhasil"; gagal = ikon seru + teks pesan; peringatan = ikon segitiga + teks. Jangan memakai hijau atau merah.
- **Terpilih/aktif** = dibalik: latar hitam, teks dan ikon putih (misalnya chip filter aktif, tab aktif, tombol kategori terpilih).
- **Nonaktif** = abu (`gray-100` latar, `gray-400` teks).
- **Logo Nusly** adalah satu-satunya elemen berwarna di aplikasi (di Splash dan header kecil). Jangan diberi filter hitam-putih.
- **Foto tempat wisata** ditampilkan apa adanya sebagai konten. Placeholder foto memakai `gray-50` dengan ikon gambar abu.

---

## 3. Tipografi

Font: **Poppins** (Google Fonts). Cadangan: sans-serif sistem.

| Gaya | Ukuran | Berat | Tinggi baris | Pemakaian |
|------|--------|-------|--------------|-----------|
| `display` | 32 | 700 | 1.15 | Angka besar (poin, total biaya), judul onboarding |
| `title-1` | 26 | 700 | 1.2 | Judul layar |
| `title-2` | 20 | 600 | 1.25 | Judul kartu besar |
| `section` | 16 | 700 | 1.3 | Judul bagian ("Koleksi kamu") |
| `body` | 15 | 400 | 1.5 | Isi |
| `body-strong` | 15 | 600 | 1.5 | Nama tempat, label penting |
| `caption` | 12 | 400 | 1.4 | Keterangan, waktu, jarak |
| `button` | 15 | 600 | 1 | Teks tombol |

Aturan: maksimal **3 gaya** di satu layar. Judul layar rata kiri. Huruf kapital semua hanya untuk label kecil (misalnya "HARI 1") dengan jarak huruf 1px.

---

## 4. Jarak, sudut, dan bayangan

**Jarak (kelipatan 4):** 4, 8, 12, 16, 20, 24, 32, 48.

- Margin samping layar: **20**.
- Jarak antar bagian: **24**.
- Jarak antar kartu dalam daftar: **12**.
- Padding dalam kartu: **16**.

**Sudut:** kartu 20, tombol dan chip bulat penuh (999), input 16, bottom sheet 28 (hanya sudut atas), gambar dalam kartu 14.

**Bayangan:** tidak dipakai. Pemisah memakai border 1px `gray-200`. Satu-satunya pengecualian: bottom sheet di atas peta (bayangan tipis hitam 8% opasitas, blur 24).

---

## 5. Komponen

### Tombol
| Jenis | Tampilan | Pemakaian |
|-------|----------|-----------|
| **Utama** | Latar `black`, teks `white`, tinggi 52, bulat penuh, lebar penuh | **Satu per layar** |
| **Sekunder** | Latar `white`, border 1.5px `black`, teks `black` | Aksi pendamping |
| **Tersier** | Teks `black` bergaris bawah, tanpa latar | "Edit nama", "Lihat semua" |
| **Nonaktif** | Latar `gray-100`, teks `gray-400` | Belum bisa dipakai |
| **Ikon** | Lingkaran 44, latar `gray-50` | Aksi kecil (tutup, lainnya) |

Saat ditekan: skala 0.97 selama 120ms.

### Chip filter
Pil tinggi 40, padding horizontal 16. Tidak aktif: `gray-50` + teks `black`. Aktif: `black` + teks `white`. Bisa digulir mendatar.

### Kartu
Latar `white` dengan border `gray-200`, atau latar `gray-50` tanpa border. Sudut 20, padding 16. Tidak ada bayangan.

### Input
Tinggi 52, latar `gray-50`, sudut 16, teks 15. Fokus: border 1.5px `black`. Error: border `black` + pesan di bawah dengan ikon seru. Label di atas kolom (`caption`, `gray-600`).

### Bottom navigation
Tinggi 72, latar `white`, garis atas `gray-200`. **4 tab:** Beranda, Peta, Trip, Misi. Ikon garis 24 + label 11. Aktif: ikon dan label `black`, ikon terisi. Tidak aktif: `gray-400`.

### Bottom sheet
Latar `white`, sudut atas 28, handle abu di tengah (40x4). Ada tiga tinggi: kecil (ringkasan), setengah, penuh. Bisa digeser.

### Peta
- Gaya peta **terang dan abu-abu**: latar `#F2F2F2`, jalan putih, air `#E6E6E6`, taman `#EDEDED`, tanpa label berlebihan.
- **Pin:** lingkaran hitam 28 dengan titik putih 10. Pin terpilih: membesar 1.25x dengan border putih 3.
- **Rute:** garis hitam 4px, ujung membulat. Pin bernomor memakai angka putih di dalam lingkaran hitam.
- Pencarian mengambang di atas, putih, sudut bulat penuh.

### Daftar spot dan baris itinerary
Kartu horizontal: foto/ikon 56 di kiri (sudut 14), nama (`body-strong`) dan keterangan (`caption`, `gray-600`) di tengah, aksi di kanan. Di itinerary, jam muncul di kolom kiri (`caption`, `gray-600`), dan antar kartu ada konektor tipis berisi jarak dan waktu tempuh.

### Progress dan toggle
Progress: track `gray-100` tinggi 8, isi `black`. Toggle aktif: `black`, nonaktif: `gray-200`. Checkbox terpilih: kotak `black` dengan centang `white`.

### Lencana dan level
Lingkaran atau kotak membulat berisi ikon garis. Terbuka: hitam dengan ikon putih. Terkunci: `gray-100` dengan ikon `gray-400`.

### Ikon
Gaya garis, tebal 2px, ujung membulat, ukuran 24 (20 di dalam chip). Satu set konsisten, misalnya Lucide atau Phosphor Regular. Tanpa emoji.

---

## 6. Gerak

Gerakan halus dan membal, selaras dengan video promo Nusly.

| Situasi | Durasi | Kurva |
|---------|--------|-------|
| Pindah layar | 300ms | ease-out kubik (geser dari kanan) |
| Kartu muncul dalam daftar | 350ms, jeda 60ms antar item | ease-out + naik 16px |
| Chip/pin muncul | 400ms | pegas ringan (sedikit melampaui lalu kembali) |
| Bottom sheet | 320ms | ease-out kubik, bisa digeser |
| Tombol ditekan | 120ms | skala 0.97 |
| Loading deteksi AI | berulang | cincin progres tipis berputar, teks bertahap |

Hormati pengaturan "kurangi gerakan" di perangkat: matikan efek membal dan pakai pudar saja.

---

## 7. Struktur navigasi

**Bottom bar:** Beranda · Peta · Trip · Misi.
**Profil:** ikon di pojok kanan atas Beranda.

```
Splash → Login → Pilih minat → Beranda
Beranda ─ Simpan dari sosmed → Deteksi → Tempat ditemukan → Koleksi / Peta
Peta ─ Detail spot → Tambah ke trip
Trip ─ Buat trip → AI menyusun → Itinerary per hari
        ├ Rute di peta
        ├ Estimasi biaya
        ├ Pesan (booking)
        ├ Edit itinerary
        ├ Trip bareng (undang, voting)
        └ Bagikan
Misi ─ Misi harian → Check-in/ulasan → Poin → Tukar poin → Riwayat poin
Profil ─ Pengaturan, Notifikasi, Ajak teman
```

---

## 8. Daftar layar dan tata letaknya

### A. Awal
1. **Splash:** latar putih, logo Nusly di tengah (180), kata "Nusly" `title-1` di bawahnya, tagline `caption` `gray-600`: "Simpan spot, rencanakan perjalananmu".
2. **Login:** judul "Masuk ke Nusly", tombol "Lanjutkan dengan Google" (sekunder), pemisah "atau", kolom email dan kata sandi, tombol utama "Masuk", tautan "Belum punya akun? Daftar".
3. **Pilih minat:** judul "Kamu suka liburan seperti apa?", grid chip besar berikon (Kuliner, Wisata alam, Kafe, Belanja, Budaya, Pantai, Gunung, Hidden gem), pilihan terpilih = hitam. Tombol utama "Lanjut" aktif setelah 3 pilihan.

### B. Beranda dan simpan spot
4. **Beranda:** sapaan `caption` + judul besar "Mau liburan ke mana?", ikon profil di kanan. Kartu hitam besar (satu-satunya blok hitam di layar) berisi "Nemu tempat keren di sosmed?" dan tombol putih "Simpan dari sosmed". Bagian "Koleksi kamu" (kartu abu muda yang bisa digulir), bagian "Trip aktif" (kartu dengan progress).
5. **Simpan dari sosmed:** area teks besar "Tempel link atau caption video di sini", tombol sekunder "Tempel dari clipboard", petunjuk kecil tentang fitur *share*, tombol utama "Deteksi tempat".
6. **Mendeteksi tempat (pola Roamy):** sheet putih di atas konten yang dibagikan, logo kecil di bingkai pindai di tengah, "Mendeteksi tempat...", progress bar tipis hitam, dan toast di bagian bawah "Tidak mau menunggu? Nusly menyimpan di latar belakang" dengan tombol "Oke".
7. **Impor tempat (pola Roamy):** kartu modal melayang dengan tombol tutup, judul "Impor tempat", daftar baris (ikon kategori kecil, nama, keterangan, kotak centang hitam), toast "Tersimpan 9 spot", dua tombol bawah: sekunder "Tambah ke koleksi" dan utama "Simpan spot".

### C. Peta dan koleksi
8. **Peta (halaman andalan, pola Roamy):** peta penuh berwarna abu terang dengan banyak pin hitam, tombol kembali bulat di kiri atas, bottom sheet "Indonesia · 50 kota · 98 spot", chip kota dengan jumlah ("Bali 15"), chip kategori (Semua, Atraksi, Kafe, Kuliner) dengan ikon cari di depannya, daftar baris spot (foto, nama, label kategori + lokasi, deskripsi dua baris), dan dua tombol mengambang: "Tambah spot" dan "Buat trip".
9. **Detail spot:** carousel foto, nama, kategori dengan ikon, alamat, jam buka, kolom "Catatan pribadi", tombol sekunder "Arahkan" dan tombol utama "Tambah ke trip".
10. **Koleksi:** grid 2 kolom kartu koleksi (kolase foto 2x2, nama, jumlah spot), tombol "+ Koleksi baru".

### D. Trip dan itinerary
11. **Buat trip (pola Roamy):** kartu modal melayang dengan judul "Buat trip", tombol tutup bulat, baris "Ke mana" (ikon + kota + provinsi), baris "Kapan" (misal "4 hari" / "Kapan saja"), grid 2 kolom chip Preferensi dengan ikon kecil (Populer, Museum, Alam, Kuliner, Sejarah, Belanja), tautan "Lewati, kejutkan aku", dan di bawah "Hapus" (sekunder) serta "Lanjut" (utama hitam).
12. **AI menyusun (pola Roamy):** bottom sheet kecil di atas peta, ikon kilau, judul "Nusly sedang menyusun perjalananmu", dan daftar langkah yang tercentang satu per satu ("Memulai", "Menyusun itinerary", "Memeriksa rute").
13. **Itinerary per hari (pola Roamy):** peta rute di atas, bottom sheet berisi thumbnail dan judul "Trip 4 hari di Malang", "4 hari · 28 spot", tombol "Pilih tanggal"; tab "Belum diatur / Hari 1 / Hari 2..." (aktif = hitam); ringkasan hari ("Batu · 109 km · 8 spot"); daftar baris bernomor dengan foto kecil, nama, kategori, dan chip waktu tempuh ("1 j 22 m · 35,9 km"); tombol navigasi bulat di kanan tiap baris; di bawah "Buat ulang" (sekunder) dan "Bagikan" (utama).
14. **Rute di peta:** peta dengan garis rute hitam dan pin bernomor, carousel kartu spot di bawah.
15. **Estimasi biaya:** total besar (`display`), rincian Makan, Tiket, Transportasi, Penginapan dengan batang proporsi hitam, kolom batas anggaran.
16. **Pesan:** kartu Hotel, Tiket atraksi, Sewa kendaraan dengan harga dan tombol "Pesan", catatan kecil tentang komisi mitra.
17. **Bagikan:** bottom sheet dengan pratinjau itinerary dan opsi Salin link, Simpan gambar, Unduh PDF, Kirim ke WhatsApp.
18. **Tab Trip:** kontrol segmen "Akan datang / Selesai", daftar kartu trip, keadaan kosong.

### E. Misi dan profil
19. **Misi:** kartu poin (latar `gray-50`, angka `display`, level dan progress ke level berikutnya, hitungan hari beruntun), "Misi hari ini" (kartu dengan judul, hadiah poin, progress, tombol "Klaim"), "Pencapaian" (lencana).
20. **Tukar poin:** saldo di atas, grid hadiah (Kuota AI tambahan, Nusly Plus, voucher mitra) dengan tombol "Tukar", keadaan nonaktif jika poin kurang.
21. **Profil:** foto, nama, email, daftar menu (Riwayat trip, Koleksi, Poin dan level, Notifikasi, Tema, Bantuan, Keluar).

### F. Fitur lanjutan
22. **Jelajahi:** pencarian, chip kategori, kartu rekomendasi dengan label kecil "Rekomendasi" (outline hitam, bukan warna) untuk tempat mitra.
23. **Edit itinerary:** pegangan geser di tiap kartu, ikon hapus, kartu putus-putus "+ Tambah tempat", bar atas "Batal / Simpan".
24. **Info cuaca dan jam buka:** baris info cuaca di bawah tab hari, peringatan "Tutup hari Senin" dengan ikon segitiga.
25. **Trip bareng:** avatar bertumpuk, tombol "+ Undang", kolom tautan undangan, daftar "Voting tempat" dengan tombol Setuju / Tidak.
26. **Check-in dan ulasan:** bottom sheet "Sudah sampai di ...?", tombol "Check-in" (+30 poin), bintang 1-5 (terisi = hitam), kolom ulasan.
27. **Ajak teman:** kode referral besar, tombol "Salin kode", progress teman bergabung, tombol bagikan.
28. **Riwayat poin:** total di atas, daftar per tanggal (+ dan − ditandai tanda, bukan warna).
29. **Notifikasi:** daftar dengan ikon; yang belum dibaca memiliki titik hitam kecil.
30. **Pengaturan:** kelompok Akun, Tampilan (Terang / Gelap / Ikuti sistem), Notifikasi (toggle), Bahasa, Tentang, Keluar.
31. **Mode offline:** spanduk abu "Kamu sedang offline. Menampilkan data tersimpan.", tombol AI nonaktif dengan keterangan.
32. **Keadaan kosong dan error:** ikon garis, judul singkat, saran satu kalimat, satu tombol. Contoh: "Belum ada spot", "Tempat tidak ditemukan", "Ada masalah koneksi".

> Mode gelap (opsional, nanti): balik token. `white` ↔ `black`, `gray-50` → `#141414`, `gray-200` → `#2A2A2A`, `gray-600` → `#A6A6A6`.

---

## 9. Gaya tulisan

- Bahasa Indonesia santai tapi sopan ("kamu", bukan "Anda").
- Kalimat pendek. Tombol berisi kata kerja: "Simpan 4 spot", "Buat itinerary".
- Tanpa emoji, tanpa tanda seru berlebihan, tanpa istilah teknis.
- Angka uang: `Rp 450 rb`, `Rp 1.250.000`. Jarak: `35 km`. Waktu: `08.00`, `1 jam 22 menit`.
- Jangan pernah memakai teks contoh palsu (lorem ipsum) atau angka karangan di versi final.

---

## 10. Aksesibilitas

- Area sentuh minimal **48x48**.
- Kontras teks minimal 4.5:1 (teks `gray-600` di atas putih sudah memenuhi).
- Informasi tidak boleh bergantung pada warna saja (status selalu punya ikon dan teks).
- Tombol ikon wajib punya label untuk pembaca layar.
- Dukung ukuran font sistem yang besar tanpa teks terpotong.

---

## 11. Larangan (anti "slop")

Hindari semua ini:
- Warna apa pun selain putih, hitam, dan abu turunannya. Tidak ada ungu, gradasi, atau efek glow.
- Emoji dan ilustrasi 3D yang mengilap.
- Bayangan tebal di setiap kartu.
- Lebih dari satu tombol utama di satu layar.
- Kartu bersarang di dalam kartu.
- Teks rata tengah untuk paragraf panjang.
- Ikon dari set yang berbeda-beda.
- Judul bagian yang sama gayanya dengan isi.
- Layar yang terlalu padat. Kalau ragu, kurangi elemen.

---

## 12. Token untuk Flutter

```dart
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';

class NuslyColors {
  static const white = Color(0xFFFFFFFF);
  static const black = Color(0xFF000000);
  static const gray50 = Color(0xFFF7F7F7);
  static const gray100 = Color(0xFFEFEFEF);
  static const gray200 = Color(0xFFE3E3E3);
  static const gray400 = Color(0xFFA6A6A6);
  static const gray600 = Color(0xFF666666);
}

ThemeData nuslyTheme() {
  final base = ThemeData(
    useMaterial3: true,
    scaffoldBackgroundColor: NuslyColors.white,
    colorScheme: const ColorScheme.light(
      primary: NuslyColors.black,
      onPrimary: NuslyColors.white,
      surface: NuslyColors.white,
      onSurface: NuslyColors.black,
      outline: NuslyColors.gray200,
    ),
  );
  return base.copyWith(
    textTheme: GoogleFonts.poppinsTextTheme(base.textTheme).apply(
      bodyColor: NuslyColors.black,
      displayColor: NuslyColors.black,
    ),
    elevatedButtonTheme: ElevatedButtonThemeData(
      style: ElevatedButton.styleFrom(
        backgroundColor: NuslyColors.black,
        foregroundColor: NuslyColors.white,
        minimumSize: const Size.fromHeight(52),
        shape: const StadiumBorder(),
        elevation: 0,
        textStyle: GoogleFonts.poppins(fontSize: 15, fontWeight: FontWeight.w600),
      ),
    ),
    outlinedButtonTheme: OutlinedButtonThemeData(
      style: OutlinedButton.styleFrom(
        foregroundColor: NuslyColors.black,
        minimumSize: const Size.fromHeight(52),
        shape: const StadiumBorder(),
        side: const BorderSide(color: NuslyColors.black, width: 1.5),
      ),
    ),
    inputDecorationTheme: InputDecorationTheme(
      filled: true,
      fillColor: NuslyColors.gray50,
      border: OutlineInputBorder(
        borderRadius: BorderRadius.circular(16),
        borderSide: BorderSide.none,
      ),
      focusedBorder: OutlineInputBorder(
        borderRadius: BorderRadius.circular(16),
        borderSide: const BorderSide(color: NuslyColors.black, width: 1.5),
      ),
    ),
    cardTheme: CardThemeData(
      color: NuslyColors.white,
      elevation: 0,
      shape: RoundedRectangleBorder(
        borderRadius: BorderRadius.circular(20),
        side: const BorderSide(color: NuslyColors.gray200),
      ),
    ),
  );
}
```

---

## 13. Ringkasan untuk ditempel ke alat AI

```
Desain aplikasi mobile "Nusly" (AI travel planner wisata Indonesia), Android 390x844, semua teks bahasa Indonesia.
Gaya: minimalis, putih dominan. Warna HANYA putih #FFFFFF dan hitam #000000, plus abu turunan hitam (#F7F7F7, #EFEFEF, #E3E3E3, #A6A6A6, #666666). Tanpa warna lain, tanpa gradasi, tanpa emoji, tanpa bayangan (pakai border 1px #E3E3E3).
Font Poppins. Tombol utama: hitam penuh, teks putih, bulat penuh, tinggi 52, hanya satu per layar. Tombol sekunder: outline hitam. Chip: pil, aktif = hitam teks putih, tidak aktif = #F7F7F7. Kartu sudut 20. Ikon garis 2px.
Bottom navigation 4 tab: Beranda, Peta, Trip, Misi (aktif hitam, tidak aktif abu).
Peta gaya abu terang dengan pin hitam dan rute garis hitam. Status ditandai ikon + teks, bukan warna.
Logo Nusly (yang diunggah) adalah satu-satunya elemen berwarna.
Ikuti pola UI aplikasi Roamy (peta penuh + bottom sheet, modal Import Locations, kartu modal Create Trip dengan chip Preferences, tab Day 1/Day 2) tetapi dalam hitam-putih. Ikuti DESIGN.md untuk detail tiap layar.
```
