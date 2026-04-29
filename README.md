 Android app developed for the DAI (Desenvolvimento de Aplicações para Internet) course. It covers the basics of an
  Android project that talks to external services: Firebase for authentication and data, Google Maps for showing the
  device's location, and a small connectivity check on the main screen.

  ## What it does

  - Login and registration screens backed by Firebase Authentication
  - User data stored in Firebase Realtime Database
  - Map screen using Google Maps SDK that requests location permission and centers on the device's current position
  - "No internet" state on the main screen that polls every 5 seconds and re-enables the buttons once the connection is
  back

  ## Tech

  - Java, Android SDK (compileSdk 34, minSdk 26)
  - Firebase BOM 32.8.0 — Auth, Realtime Database, Analytics
  - Google Play Services — Maps
  - Gradle (Kotlin DSL)

  ## Project layout

  app/src/main/java/com/example/myapplication/
  ├── MainActivity.java        # entry point, login/register buttons, connectivity check
  ├── LoginActivity.java
  ├── RegisterActivity.java
  ├── MapaActivity.java        # Google Maps + location
  ├── FirebaseService.java     # Firebase helpers
  ├── NetworkUtils.java        # connectivity helper
  ├── User.java                # user model
  └── teste.java

  ## Build and run

  Open the project in Android Studio (Hedgehog or newer recommended) and let Gradle sync. Then run on an emulator or a
  physical device with API 26+.

  From the command line:

  ```bash
  ./gradlew assembleDebug

  The APK ends up under app/build/outputs/apk/debug/.

  Configuration

  The repo includes an app/google-services.json and the Maps API key is set up in the manifest/resources. If you fork
  this and want to actually run it against your own Firebase project / Maps key:

  1. Replace app/google-services.json with the file from your Firebase console.
  2. Replace the Google Maps API key.
  3. In Firebase, enable Email/Password authentication and create a Realtime Database.
```
  Permissions

  The app requests:

  - ACCESS_FINE_LOCATION — for the map
  - INTERNET and ACCESS_NETWORK_STATE — for Firebase and the connectivity check

  Notes

  - Package name is the default com.example.myapplication from the Android Studio template — never got renamed.
  - Code comments and UI strings are in Portuguese.
  - The Firebase config and Maps key shipped in the repo are tied to the original development project and shouldn't be
  reused.

  Context

  University project.
