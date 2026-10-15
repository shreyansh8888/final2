# Codemagic build notes

This package preserves the app source and features. Only Android CI/build configuration was adjusted:
- Android Gradle Plugin set to 8.10.1 and Gradle wrapper to 8.11.1 (API 36 capable toolchain).
- Kotlin Android plugin explicitly applied to the app module.
- Removed an AGP-internal `BaseExtension` compileSdk override that can break builds; app compileSdk remains 36.
- Dart analysis is diagnostic in Codemagic; `flutter build apk --release --split-per-abi` remains the required build step.

Firebase configuration is preserved. Firebase Phone OTP requires the signing certificate SHA-1/SHA-256 registered in the Firebase console.
