
# WA Nux App (Flutter)
Satu kode Flutter untuk Android (APK) + Windows (EXE) yang menampilkan https://wa.nux.my.id/

## Cara cepat tanpa install Flutter (pakai GitHub Actions)
1. Buat repo GitHub baru (public/private boleh).
2. Upload semua isi folder ini ke repo (atau upload ZIP lalu `Extract` di GitHub).
3. Buka tab **Actions** di repo Anda, lalu jalankan workflow:
   - **Build Android (APK)**
   - **Build Windows (EXE)**
4. Setelah selesai, unduh hasilnya di **Actions → Artifacts**:
   - `wa_nux_android_apk` → berisi `app-release.apk`
   - `wa_nux_windows_release` → berisi folder Release dengan `.exe`

> Catatan:
> - APK yang dihasilkan **debug-signed** (untuk uji coba/instal manual). Untuk rilis Play Store, tambahkan keystore & signing.
> - EXE Windows membutuhkan **WebView2 Runtime**. Biasanya sudah ada di Windows 10/11. Jika belum, instal Microsoft Edge WebView2 Runtime.

## Build lokal (opsional)
- `flutter create . --platforms=android,windows`
- Tambah permission Internet otomatis oleh workflow; bila build lokal, tambahkan manual ke `android/app/src/main/AndroidManifest.xml`:
  ```xml
  <uses-permission android:name="android.permission.INTERNET"/>
  ```
- `flutter pub get`
- Android: `flutter build apk --release`
- Windows: `flutter build windows --release`
