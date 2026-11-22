# Angry Dogs vs. Cats — Android app

Offline slingshot game (5 levels, 4 dog breeds, player profiles & leaderboard).
Runs on **Android 5.0 and newer**, phones and tablets, landscape.

## Option A — Let GitHub build the APK (no software to install)

1. Sign in at github.com → **New repository** → name it `angry-dogs-vs-cats` → Create.
2. On the new repo page click **uploading an existing file**, then drag in **everything inside this folder**
   (including the `.github` folder, `gradle` folder, `gradlew`, and `app`). Click **Commit changes**.
   - Tip: if the `.github` folder doesn't upload (hidden on some computers), create it on GitHub:
     **Add file → Create new file**, name it `.github/workflows/build-apk.yml`, and paste in the contents of that file.
3. Open the **Actions** tab. The "Build Android APK" job starts by itself (takes about 4–6 minutes).
   If it doesn't, click **Build Android APK → Run workflow**.
4. When it shows a green tick, open the repo's **Releases** (right-hand side) → **latest** →
   tap **AngryDogsVsCats.apk** on your phone to download it.
5. Open the downloaded file. Android will ask to allow installing from this source (Chrome/Files) → allow → **Install**.

Every time you change a file and commit, a fresh APK is built. New versions install over the old one and keep saved scores.

## Option B — Android Studio (on your PC)

1. Install Android Studio → **Open** this folder → wait for "Gradle sync" to finish.
2. **Build → Build App Bundle(s) / APK(s) → Build APK(s)**.
3. The APK is at `app/build/outputs/apk/debug/app-debug.apk`. Copy it to your phone and install.

## Editing the game

The whole game is one file: `app/src/main/assets/www/index.html` (works offline, no internet needed).
You can also open it in Chrome on a computer to test.

## Notes

- `app/sideload.keystore` signs the APK so updates install cleanly. It's fine for sharing the APK directly.
  For Google Play, create your own private signing key (Android Studio → Build → Generate Signed App Bundle).
- Package name: `com.angrydogsvscats.game`, version 1.1.
