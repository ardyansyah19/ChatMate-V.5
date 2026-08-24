# ChatMate 💬

Aplikasi chatting mobile bergaya **WhatsApp**, dibangun dengan **Flutter/Dart**.
UI/UX (tab Chats–Status–Calls, bubble chat, read receipt, status online, dsb)
dibuat semirip mungkin dengan pengalaman WhatsApp, namun menggunakan nama,
warna, dan aset orisinal (bukan logo/brand resmi WhatsApp/Meta).

> Catatan: aplikasi ini adalah **demo/prototipe fungsional** tanpa backend
> server sungguhan. Semua "lawan chat" adalah simulasi lokal (auto-reply)
> agar interaksi terasa hidup — cocok untuk dipakai sebagai portofolio,
> tugas kuliah, atau starting point untuk dikembangkan ke backend nyata
> (Firebase, WebSocket, dsb).

## ✨ Fitur

- **Tab Chats** — daftar percakapan dengan foto profil (avatar inisial),
  pesan terakhir, waktu, badge jumlah pesan belum dibaca, sematkan chat,
  bisukan notifikasi, dan hapus chat (swipe).
- **Chat Detail** — bubble chat kiri/kanan, timestamp, centang status
  kirim (mengirim/terkirim/sampai/dibaca ✓✓ biru), indikator
  **"sedang mengetik..."**, auto-reply simulasi.
- **Tab Status** — daftar pembaruan status ala Stories, avatar dengan ring hijau.
- **Tab Calls** — riwayat panggilan (masuk/keluar/tidak terjawab, suara/video).
- **Kontak Baru** — mulai chat dari daftar kontak, pencarian kontak.
- **Pencarian chat** langsung dari halaman utama.
- **Mode Gelap/Terang** yang tersimpan otomatis.
- **Penyimpanan lokal** — semua chat & preferensi tema disimpan di perangkat
  (`shared_preferences`), jadi tetap ada walau aplikasi ditutup/dibuka lagi.

## 🧱 Struktur Proyek

```
chatmate/
├── lib/
│   ├── main.dart                 # Entry point, setup provider & tema
│   ├── theme.dart                # Warna & ThemeData (light/dark)
│   ├── models/                   # Message, ChatModel, Contact
│   ├── data/mock_data.dart       # Kontak & data awal (mock)
│   ├── services/storage_service.dart  # Simpan/muat data via shared_preferences
│   ├── providers/
│   │   ├── chat_provider.dart    # Logika chat: kirim pesan, auto-reply, dsb
│   │   └── theme_provider.dart   # Logika dark mode
│   ├── widgets/
│   │   ├── chat_tile.dart        # Item daftar chat
│   │   └── message_bubble.dart   # Bubble pesan
│   └── screens/
│       ├── home_screen.dart      # Scaffold + TabBar (Chats/Status/Calls)
│       ├── chats_list_screen.dart
│       ├── chat_detail_screen.dart
│       ├── status_screen.dart
│       ├── calls_screen.dart
│       └── contacts_screen.dart
├── pubspec.yaml
└── analysis_options.yaml
```

## 🚀 Cara Menjalankan

Karena arsip ini hanya berisi **kode sumber Dart/Flutter** (folder `lib/` dan
`pubspec.yaml`), kamu perlu men-generate boilerplate platform
(Android/iOS/dll) di komputermu sendiri menggunakan Flutter SDK. Langkahnya:

### 1. Prasyarat
- Install [Flutter SDK](https://docs.flutter.dev/get-started/install) (stable channel).
- Pastikan `flutter doctor` sudah OK (Android Studio / Xcode / emulator terpasang).

### 2. Ekstrak & siapkan proyek
```bash
unzip chatmate.zip
cd chatmate

# Generate folder platform (android/, ios/, dll) — jalankan sekali saja
flutter create .
```
Perintah `flutter create .` akan membuat folder `android/`, `ios/`, `web/`, dll
di dalam folder yang sudah berisi kode ini. Flutter tidak akan menimpa
`lib/` dan `pubspec.yaml` yang sudah ada — tapi jika pubspec ikut ditimpa,
cukup pulihkan dari isi yang sudah disediakan di README/arsip ini.

### 3. Install dependencies
```bash
flutter pub get
```

### 4. Jalankan aplikasi
```bash
flutter run
```
Pilih device/emulator yang tersedia (Android, iOS, atau Chrome untuk versi web).

## 🎨 Kustomisasi

- **Warna tema**: ubah di `lib/theme.dart` (`AppColors`).
- **Kontak & data awal**: ubah di `lib/data/mock_data.dart`.
- **Balasan otomatis**: tambah/edit list `autoReplies` di `mock_data.dart`.
- **Logo/nama aplikasi**: ubah judul di `main.dart` (`MaterialApp.title`) dan
  ikon aplikasi lewat `flutter_launcher_icons` (tambahkan sendiri bila perlu).

## 🔮 Pengembangan Selanjutnya (saran)

- Hubungkan ke backend nyata (Firebase Firestore + Cloud Messaging, atau
  WebSocket/Socket.IO custom) untuk chat real-time antar pengguna sungguhan.
- Autentikasi nomor HP (OTP) seperti WhatsApp asli.
- Kirim gambar/video/dokumen (saat ini tombol lampiran masih placeholder).
- Panggilan suara/video sungguhan (mis. pakai Agora/WebRTC).
- End-to-end encryption untuk keamanan pesan.

## 📄 Lisensi

Proyek ini dibuat untuk keperluan belajar/portofolio pribadi. Silakan
dimodifikasi bebas sesuai kebutuhanmu.
