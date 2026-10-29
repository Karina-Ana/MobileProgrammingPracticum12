# Akses Lokasi GPS – Flutter

## 📝 Deskripsi Singkat

Akses Lokasi GPS merupakan aplikasi berbasis Flutter yang menggunakan paket **Geolocator** dan **Geocoding** untuk mengambil lokasi perangkat dan menampilkan informasi alamat. Aplikasi ini memungkinkan pengguna mengetahui informasi kecamatan dan kota berdasarkan koordinat GPS perangkat.

Aplikasi menggunakan `StatefulWidget` dan `setState()` untuk memperbarui tampilan sesuai kondisi yang sedang berlangsung. Informasi yang ditampilkan meliputi status proses pengambilan lokasi, hasil lokasi, dan pesan error jika terjadi masalah.

## ✨ Fitur Utama

- **Akses Lokasi GPS:** Mengambil koordinat latitude dan longitude perangkat.
- **Informasi Alamat:** Mengubah koordinat GPS menjadi informasi kecamatan dan kota menggunakan reverse geocoding.
- **Pengecekan GPS:** Memeriksa apakah layanan lokasi perangkat sedang aktif.
- **Penanganan Izin Lokasi:** Memeriksa dan meminta izin akses lokasi kepada pengguna.
- **Indikator Loading:** Menampilkan indikator saat aplikasi sedang mengambil lokasi.
- **Penanganan Error:** Menampilkan pesan jika GPS tidak aktif, izin lokasi ditolak, atau informasi alamat tidak ditemukan.
- **Pembaruan Tampilan:** Memperbarui informasi secara otomatis menggunakan `setState()`.

## 🛠️ Teknologi yang Digunakan

- **Flutter & Dart** – Pengembangan aplikasi.
- **Geolocator (`geolocator`)** – Memeriksa layanan lokasi, menangani izin, dan mengambil koordinat GPS perangkat.
- **Geocoding (`geocoding`)** – Mengubah koordinat menjadi informasi alamat.
- **Google Fonts (`google_fonts`)** – Menggunakan font Poppins pada tampilan aplikasi.

## 📂 Struktur Proyek

```text
lokasi_flutter/
├── android/
│   └── app/
│       └── src/
│           └── main/
│               └── AndroidManifest.xml
├── ios/
├── lib/
│   └── main.dart
├── pubspec.yaml
└── README.md
```

## ⚙️ Cara Kerja Aplikasi

1. Aplikasi menampilkan halaman **Lokasi Saya** dengan tombol untuk mengambil lokasi.
2. Pengguna menekan tombol **TAMPILKAN LOKASI SAAT INI**.
3. Fungsi `_getLocation()` memeriksa apakah GPS aktif dan izin lokasi telah diberikan.
4. Jika izin tersedia, aplikasi mengambil koordinat perangkat menggunakan `Geolocator.getCurrentPosition()`.
5. Koordinat latitude dan longitude diubah menjadi informasi alamat menggunakan `placemarkFromCoordinates()`.
6. Informasi kecamatan dan kota disimpan dalam variabel `_kecamatan` dan `_kota`.
7. `setState()` memperbarui tampilan agar hasil lokasi ditampilkan pada layar.
8. Jika terjadi kesalahan, aplikasi menampilkan pesan melalui variabel `_errorMessage`.

## 📚 Konsep Flutter yang Dipelajari

- **StatefulWidget:** Membuat tampilan yang dapat berubah sesuai kondisi aplikasi.
- **Geolocator:** Mengakses lokasi perangkat dan memeriksa status layanan GPS.
- **Geocoding:** Mengubah koordinat geografis menjadi informasi alamat yang dapat dibaca.
- **Permission Handling:** Memeriksa dan meminta izin akses lokasi kepada pengguna.
- **Async dan Await:** Menjalankan proses pengambilan lokasi yang membutuhkan waktu.
- **setState():** Memperbarui tampilan ketika nilai variabel berubah.
- **Penanganan Error:** Menggunakan `try-catch-finally` untuk menangani kesalahan dan menghentikan indikator loading.
- **Conditional UI:** Menampilkan indikator loading, pesan error, instruksi awal, atau informasi lokasi sesuai kondisi aplikasi.

## 🚀 Cara Menjalankan

1. Pastikan Flutter SDK dan editor kode seperti VS Code atau Android Studio telah terpasang.
2. Buka proyek `lokasi_flutter` melalui editor kode.
3. Tambahkan dependency berikut pada bagian `dependencies` di file `pubspec.yaml`:

   ```yaml
   dependencies:
     flutter:
       sdk: flutter
     google_fonts: ^6.1.0
     geolocator: ^7.7.0
     geocoding: ^3.0.0
   ```

4. Tambahkan izin lokasi pada file `android/app/src/main/AndroidManifest.xml`, di dalam tag `<manifest>` dan sebelum tag `<application>`:

   ```xml
   <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
   <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
   ```

5. Jalankan perintah berikut pada terminal untuk mengunduh dependency:

   ```bash
   flutter pub get
   ```

6. Pastikan GPS pada perangkat aktif dan jalankan aplikasi menggunakan perintah:

   ```bash
   flutter run
   ```

7. Berikan izin lokasi saat diminta oleh aplikasi, kemudian tekan tombol **TAMPILKAN LOKASI SAAT INI** untuk melihat informasi lokasi perangkat.

## 📌 Kesimpulan

Aplikasi Akses Lokasi GPS menerapkan paket Geolocator dan Geocoding untuk mengambil lokasi perangkat dan menampilkan informasi alamat. Penggunaan `setState()` memungkinkan tampilan diperbarui sesuai hasil pengambilan lokasi. Aplikasi juga menangani izin akses lokasi, status loading, dan pesan error agar pengguna dapat mengetahui kondisi proses pengambilan lokasi.
