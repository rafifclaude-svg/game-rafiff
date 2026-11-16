# EDIGIDAW – proyek APK

Game sudah dibundel offline (three.js dan font ada di folder `www/`).

## Cara paling mudah: GitHub Actions (tanpa install apa pun)
1. Buat repo baru di github.com, lalu upload SEMUA isi folder ini
   (termasuk folder tersembunyi `.github`).
2. Buka tab **Actions** → **Build APK** → **Run workflow**.
3. Tunggu ±5 menit, lalu unduh **EDIGIDAW-apk** di bagian *Artifacts*.
4. Ekstrak zip-nya → `app-debug.apk` → pasang di HP
   (izinkan "Instal dari sumber tidak dikenal").

## Cara lokal (Android Studio / JDK 17 + Android SDK)
```
npm install
npx cap add android
npx cap sync android
# tambahkan android:screenOrientation="sensorLandscape" pada <activity> di AndroidManifest.xml
cd android && ./gradlew assembleDebug
```
APK ada di `android/app/build/outputs/apk/debug/app-debug.apk`.

Catatan: ini APK debug (cukup untuk dipasang sendiri). Untuk Play Store perlu APK/AAB yang ditandatangani (`./gradlew bundleRelease` + keystore).
