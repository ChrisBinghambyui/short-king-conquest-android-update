# Run Short King Conquest on Your Own Device

This guide gets the game running two ways: in a desktop browser (about one minute) and as an Android app on your phone over USB. The Android build wraps the game's HTML and JavaScript with [Capacitor](https://capacitorjs.com).

## Option 1: Play in a browser

1. Download or clone this repository.
2. Open `www/index.html` in a modern browser such as Chrome, Edge, or Firefox.

No build step or server is needed. Your save lives in the browser's local storage.

## Option 2: Install on an Android phone

### What you need

* [Node.js](https://nodejs.org) 20 or newer
* [Android Studio](https://developer.android.com/studio) (it includes the Android SDK, adb, and a JDK)
* An Android phone and a USB cable that carries data (some cables only charge)

### Step 1: Prepare the phone

1. Open **Settings > About phone** and tap **Build number** seven times to enable Developer options.
2. Open **Settings > System > Developer options** and turn on **USB debugging**.
3. Plug the phone into your computer. When the phone asks, tap **Allow** to trust the computer.

### Step 2: Set up the project

Run these from the project folder (the one that contains `www/`):

```
npm init -y
npm i @capacitor/core @capacitor/cli @capacitor/android
npx cap init "Short King Conquest" com.yourname.shortkingconquest --web-dir www
npx cap add android
npx cap sync
npx cap open android
```

Choose your own package ID in place of `com.yourname.shortkingconquest` before running `cap init`. Use lowercase letters and dots only. If you ever publish to Google Play, the ID is permanent once uploaded.

The last command opens the project in Android Studio. Let it finish its first Gradle sync (a progress bar at the bottom). The first sync can take several minutes.

### Step 3: Two one-time edits in Android Studio

1. In `android/app/build.gradle`, change `proguard-android.txt` to `proguard-android-optimize.txt`.
2. In `android/app/src/main/AndroidManifest.xml`, delete any `android:screenOrientation="..."` attribute. This lets the game work in both portrait and landscape.

### Step 4: Run it

1. In the device dropdown at the top of Android Studio, pick your phone.
2. Press the green **Run** button.

The game installs and launches on your phone. Android Studio can also keep the app running with a debugger attached if you press **Debug** instead.

### Changing the game later

After you edit `www/index.html` or `www/game.js`, run:

```
npx cap sync
```

Then press **Run** again in Android Studio. You can test changes faster by editing and refreshing in a desktop browser first.

## Troubleshooting

* **Phone does not appear in the device dropdown:** Check that USB debugging is on, try a different cable or port, and set the phone's USB mode to File Transfer. You can confirm detection by running `adb devices` (adb is in the Android SDK `platform-tools` folder).
* **Device shows as "unauthorized":** Unplug the phone, plug it back in, and tap **Allow** on the prompt. If no prompt appears, toggle USB debugging off and on, or use **Revoke USB debugging authorizations** in Developer options.
* **Gradle sync fails:** Open **File > Sync Project with Gradle Files** and make sure Android Studio has finished downloading the SDK components it asks for.
* **`npx cap` says it cannot find a config:** Make sure you ran the commands from the folder that contains `www/`, and that `cap init` finished before `cap add android`.
* **Game is blank or shows an old version:** Run `npx cap sync` again, then do a fresh Run from Android Studio.z