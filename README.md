# تطبيق الطيبات (AlTayebat)

مشروع Android كامل (Kotlin، بدون مكتبات خارجية). الحد الأدنى Android 6.0 (API 23) والهدف API 36.

## المتطلبات
- JDK 17 أو أحدث
- Android SDK (منصة 36 + build-tools) — أسهل طريقة تثبيت Android Studio
- عند البناء من سطر الأوامر: عرّف `ANDROID_HOME` أو أنشئ ملف `local.properties` فيه `sdk.dir=/path/to/Android/sdk`

## البناء
```bash
./gradlew assembleDebug      # نسخة تجريبية  -> app/build/outputs/apk/debug/
./gradlew assembleRelease    # APK موقّع     -> app/build/outputs/apk/release/app-release.apk
./gradlew bundleRelease      # AAB لـ Google Play -> app/build/outputs/bundle/release/app-release.aab
```
(على ويندوز: `gradlew.bat` بدل `./gradlew`)

## التوقيع
- ملف المفتاح: `altayebat-release.jks` وبياناته في `keystore.properties` (alias: `altayebat`).
- **احتفظ بنسخة احتياطية من الملفين في مكان آمن.** لو ضاع المفتاح لن تستطيع تحديث التطبيق على Google Play بنفس الحساب.
- لا ترفعهما على GitHub (موجودان في `.gitignore`). ولو شاركت المشروع مع غيرك فاحذفهما من النسخة المُشاركة.
- عند الرفع على Google Play يُفضّل تفعيل Play App Signing.

## عند كل تحديث
ارفع `versionCode` (رقم صحيح أكبر من السابق) و`versionName` في `app/build.gradle.kts`.

## ملفات النشر
- `store/play_store_icon_512.png` — أيقونة المتجر 512×512
- `store/STORE_LISTING_AR.md` — نصوص صفحة المتجر
- `store/PRIVACY_POLICY_AR.md` — سياسة الخصوصية (انشرها على رابط عام واكتب الرابط في Play Console)
