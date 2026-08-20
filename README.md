# Sabaq Classroom Updates

This public repository is the dedicated update channel for the Android app with package `com.foxlabs.sabaqclassroom`.

It is completely separate from Homework Planner. The app reads `update.json`, downloads the referenced APK over HTTPS, verifies its SHA-256 checksum, confirms the package and version code, and then opens Android's installer.

## Publishing a future update

1. Increase `versionCode` and `versionName` in the app's `app/build.gradle.kts`.
2. Build the APK with the same permanent signing identity used for the first production release.
3. Run `scripts/prepare-release.ps1` from the Sabaq Classroom source project.
4. Upload the prepared APK to a matching GitHub release tag.
5. Commit and push the generated `update.json` only after the release APK is publicly downloadable.
6. Install the previous version and test the in-app update end to end before announcing it.

Never publish an APK whose filename, URL, package, version, signing certificate, or checksum differs from the manifest.
