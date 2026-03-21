# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build Commands

```bash
./gradlew assembleDebug          # Build debug APK
./gradlew assembleRelease        # Build release APK
./gradlew test                   # Run unit tests
./gradlew testDebugUnitTest      # Run debug unit tests only
./gradlew connectedAndroidTest   # Run instrumentation tests on connected device
./gradlew lint                   # Run lint checks
./gradlew lintFix                # Run lint and apply safe fixes
./gradlew clean                  # Clean build directory
```

## Architecture

Single-activity Jetpack Compose app (`MainActivity.kt`) demonstrating Android notifications with runtime permission handling.

**Key components in `MainActivity.kt`:**
- `showNotification()` — builds and displays a `NotificationCompat` with channel ID `"notification_Channel_id"`
- `createNotificationChannel()` — registers the notification channel (required for Android 8.0+, min SDK is 26 so this always runs)
- `RequestNotificationPermission()` — composable that gates `POST_NOTIFICATIONS` permission (Android 13+) via Accompanist Permissions, using `LaunchedEffect` to prompt on launch

**Theme system** lives in `ui/theme/`: Material 3 with dynamic color support on Android 12+.

## Tech Stack

- **UI:** Jetpack Compose + Material 3
- **Permissions:** `com.google.accompanist:accompanist-permissions:0.31.1-alpha`
- **Compose BOM:** `2024.04.01`
- **Kotlin:** 2.0.0 / AGP: 8.8.1 / Target SDK: 35 / Min SDK: 26
- **Java compatibility:** VERSION_11

## Dependencies

All versions are managed via the version catalog at `gradle/libs.versions.toml`. Add new dependencies there rather than hardcoding versions in `build.gradle.kts`.
