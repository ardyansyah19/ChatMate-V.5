# ChatMate V.1
By Ahmad Riko Dyansyah

Aplikasi chatting mobile bergaya **WhatsApp**, dibangun dengan **Flutter/Dart**.
UI/UX (tab Chats–Status–Calls, bubble chat, read receipt, status online, dsb)
dibuat semirip mungkin dengan pengalaman WhatsApp, namun menggunakan nama,
warna, dan aset orisinal (bukan logo/brand resmi WhatsApp/Meta).

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
## 📄 Lisensi

Proyek ini dibuat untuk keperluan belajar/portofolio pribadi. Silakan
dimodifikasi bebas sesuai kebutuhanmu.
