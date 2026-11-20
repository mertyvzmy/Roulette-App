# Roulette – Android APK

Veriler uygulamanın kendi depolamasında (Capacitor Preferences / SharedPreferences) tutulur.

## Yol 1 – GitHub Actions (bilgisayara bir şey kurmadan)
1. Bu klasörü yeni bir GitHub deposuna yükleyin (`git init && git add . && git commit -m ilk && git push`).
2. Depoda **Actions → APK derle → Run workflow**.
3. İş bitince sayfanın altındaki **roulette-apk** dosyasını indirip zip'ten çıkarın, `app-debug.apk` dosyasını telefona atıp kurun
   (telefonda "bilinmeyen kaynaklardan yüklemeye izin ver" gerekir).

## Yol 2 – Kendi bilgisayarında (Node 18+, JDK 17, Android Studio)
```
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug      # Windows: gradlew.bat assembleDebug
```
APK: `android/app/build/outputs/apk/debug/app-debug.apk`
(Android Studio için: `npx cap open android`)

## Not
Bu bir debug APK'dır; kişisel kurulum için yeterlidir. Play Store için imzalı release derlemesi gerekir.

## Çark paylaşma
Çarklarım → **Paylaş**: çarkın adı ve seçenekleri `.json` dosyası olarak WhatsApp vb. ile gönderilir (kullanıcılar gitmez).
Alan kişi: Çarklarım → **İçe aktar** → dosyayı seçer ya da metni yapıştırır.
Paylaşım için `@capacitor/share` ve `@capacitor/filesystem` eklentileri kullanılır (`npm install` ile otomatik gelir).
