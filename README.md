# DeepFocus - Android Study & Focus Application

Personal Android study and focus application built with Kotlin and Jetpack Compose.
Optimized for deep academic work, distraction elimination, and heavy reading (handling up to 500 MB PDF textbooks and synced flashcards).

## Architecture Highlights
- **WakeLock & Screen Management:** `FLAG_KEEP_SCREEN_ON` applied to the main Window, with `WindowInsetsControllerCompat` for Immersive Mode.
- **Intelligent Notification Interceptor:** `StudyNotificationListener.kt` suppresses social/chat notifications during focus while allowing Emergency Cellular & VoIP calls to pass through (`Notification.CATEGORY_CALL`).
- **Pomodoro Focus Engine:** `PomodoroViewModel.kt` uses start-timestamp background persistence so the timer remains accurate across device rotations and backgrounding.
- **3D Flip Reader & Engine:** `PdfReaderScreen.kt` uses native Android `PdfRenderer` on a background IO dispatcher with an LRU Bitmap cache and 3D `graphicsLayer` rotation.
- **Hybrid Cloud Sync:** `CloudSyncRepository.kt` connects to Telegram Bot API for notes/flashcards and leverages Android `DownloadManager` for heavy 500MB Google Drive PDFs.
