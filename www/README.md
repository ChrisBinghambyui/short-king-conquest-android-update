# Short King Conquest: Android build

Run from this folder (Node 20+ and Android Studio installed):

    npm init -y
    npm i @capacitor/core @capacitor/cli @capacitor/android
    npx cap init "Short King Conquest" com.yourname.shortkingconquest --web-dir www
    npx cap add android
    npx cap sync
    npx cap open android

Pick the package ID before `cap init`. It is permanent once uploaded to Play.

Two one-time edits in Android Studio:
- android/app/build.gradle: change `proguard-android.txt` to `proguard-android-optimize.txt`.
- android/app/src/main/AndroidManifest.xml: delete any `android:screenOrientation="..."` attribute so both portrait and landscape work.

After editing www/index.html or www/game.js: `npx cap sync`, then press Run.
