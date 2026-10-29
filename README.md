# Mic Equalizer APK

## Build in the cloud (no Android Studio)
1. Create a free GitHub account and a new repository.
2. Upload everything in this folder (including the hidden `.github` folder) to the repo.
3. Open the repo's **Actions** tab. The "Build APK" workflow runs on upload (or press "Run workflow").
4. When it turns green (about 5 minutes), open the run and download **mic-equalizer-apk** under Artifacts. Unzip it to get `app-debug.apk`.
5. Copy the APK to your phone, open it, and allow "Install unknown apps" when asked.
6. On first Start, allow microphone access.

## Build locally instead
Needs Node 20+, JDK 21, Android Studio/SDK:
    npm install
    npx cap add android
    (add RECORD_AUDIO and MODIFY_AUDIO_SETTINGS uses-permission lines to android/app/src/main/AndroidManifest.xml)
    npx cap sync android
    cd android && ./gradlew assembleDebug
APK: android/app/build/outputs/apk/debug/app-debug.apk

## Updating the app
Edit `www/index.html`, push to GitHub, download the new APK.
