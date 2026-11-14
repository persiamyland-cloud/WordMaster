# WordMaster — Android project

A lightweight Android-first English–Persian vocabulary app. The Android shell is a native Kotlin Activity with a bundled offline HTML/CSS/JavaScript interface in a local WebView. No network permission, account, ads, or payments are included.

## Included in this prototype
- Home dashboard, daily word, categories and CEFR level filters (A1–C2)
- Flashcards with US/UK IPA, Persian meaning, definition and bilingual example
- Separate US and UK audio controls visibly marked **not connected**
- Searchable dictionary, multiple-choice quiz, favorites and progress
- Favorites, learned words and quiz history stored locally using WebView local storage
- Bundled sample vocabulary dataset; data model is ready to expand

## Build the APK

### Android Studio
1. Install Android Studio (JDK 17 and Android SDK Platform 35).
2. Open this `WordMaster` folder as a project.
3. Let Gradle sync, then choose **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
4. The debug APK is created at `app/build/outputs/apk/debug/app-debug.apk`.

### GitHub Actions (no local Android SDK required)
1. Create a GitHub repository and upload the contents of this folder.
2. Open the repository's **Actions** tab.
3. Run **Build WordMaster APK** (or push to `main`).
4. Download the `WordMaster-debug-apk` artifact from the completed workflow run.

## Vocabulary data schema
Each entry in `app/src/main/assets/index.html` uses:
`word`, `us`, `uk`, `fa`, `def`, `pos`, `level`, `cat`, `ex`, `exfa`.
The requested `americanAudioRef` and `britishAudioRef` fields are intentionally not populated until real licensed audio files/URLs are integrated. The UI does not claim playback works.

## Notes
- This is a functional prototype, not a finished production release.
- Audio is not implemented; the two controls are disabled placeholders.
- The initial sample dataset is small. Add records to `words` and consider moving the dataset to a versioned JSON asset or Room database for thousands of entries.
- A release APK should be signed with your own private signing key before distribution.
