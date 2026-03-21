# ComposeNotification

An Android sample app demonstrating how to send local notifications using Jetpack Compose, with runtime permission handling for Android 13+.

## Features

- Requests `POST_NOTIFICATIONS` permission at launch (Android 13+)
- Creates a notification channel on startup (required for Android 8.0+)
- Displays a local notification via a button tap using `NotificationCompat`
- Built with Material 3 and edge-to-edge display

## Requirements

- Android Studio Hedgehog or later
- Android SDK 26+ (min SDK)
- A device or emulator running Android 8.0 (API 26) or higher

## Getting Started

1. Clone the repository
2. Open the project in Android Studio
3. Sync Gradle and run the app on a device or emulator

## Build

```bash
./gradlew assembleDebug       # Debug APK
./gradlew assembleRelease     # Release APK
./gradlew test                # Unit tests
./gradlew connectedAndroidTest  # Instrumented tests (requires connected device)
./gradlew lint                # Lint checks
```

## Tech Stack

| Component | Version |
|---|---|
| Kotlin | 2.0.0 |
| Android Gradle Plugin | 8.8.1 |
| Jetpack Compose BOM | 2024.04.01 |
| Material 3 | via BOM |
| Accompanist Permissions | 0.31.1-alpha |
| Min SDK | 26 (Android 8.0) |
| Target SDK | 35 (Android 15) |

## Project Structure

```
app/src/main/java/com/example/composenotification/
├── MainActivity.kt          # App entry point, notification logic, permission handling
└── ui/theme/
    ├── Color.kt             # Material 3 color palette
    ├── Theme.kt             # App theme with dynamic color support (Android 12+)
    └── Type.kt              # Typography
```

## How It Works

1. On launch, `createNotificationChannel()` registers a channel with ID `notification_Channel_id`.
2. If the device runs Android 13+, the app requests `POST_NOTIFICATIONS` permission via Accompanist Permissions.
3. Tapping **Show Notification** calls `showNotification()`, which builds and posts a `NotificationCompat` with high priority.
