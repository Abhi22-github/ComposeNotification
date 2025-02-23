# compose-notification
This project demonstrates how to implement notifications in Jetpack Compose while properly handling runtime permission requests for Android 13 (API 33) and above. Since Android 13 introduced the POST_NOTIFICATIONS permission, apps must request and manage this permission before displaying notifications.

This project includes:
✔ Creating a Notification Channel (Required for Android 8+)
✔ Displaying a Notification using NotificationManager
✔ Requesting Notification Permission at Runtime (Android 13+)
✔ Handling User Responses (Granted or Denied)
