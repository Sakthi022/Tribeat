# TriBeat Android — v0.1 prototype

TriBeat is a personal, offline-first three-lane rhythm-game starter for Android.

## What is included
- Android app project using Kotlin + Jetpack Compose.
- Import a local audio file using Android's document picker.
- Play/pause the imported track.
- Enter BPM and generate a three-lane beat-grid chart.
- Tap the three lanes for timing-based hit judgments, score and combo.
- GitHub Actions workflow that builds and uploads a debug APK.

## Important charting limitation
This first build is a playable prototype, not yet a Beatstar-quality automatic charting engine. Its chart generator uses a BPM grid and deterministic lane patterns. It does **not** yet analyse waveform/onsets, isolate kick/snare/vocals, or infer musical phrases from the audio. Those are the next engineering milestones; claiming otherwise would be misleading.

## Build the APK in GitHub Actions
1. Create a new empty GitHub repository.
2. Upload/push the contents of this project to the repository's `main` branch.
3. Open the repository's **Actions** tab.
4. Select **Build TriBeat APK** and run it, or let the push trigger it.
5. Open the successful workflow run and download the `TriBeat-debug-apk` artifact.
6. Extract `app-debug.apk` and install it on your Android phone. If prompted, allow installation from that source.

## Local build
Requires JDK 17 and Gradle 8.9:
```bash
gradle assembleDebug
```

Package: `com.sakthi.tribeat`
Minimum Android: 8.0 (API 26)
Target SDK: 35

## Next milestones
1. Decode imported audio into analysis frames.
2. Multi-resolution spectral-flux onset detection and adaptive thresholds.
3. Beat tracking with confidence scoring and beat-grid correction.
4. Separate percussive/harmonic feature streams and event classification.
5. Phrase-aware three-lane assignment with repetition and hand-balance constraints.
6. Editable chart timeline, difficulty tiers, hold/swipe notes, calibration and latency compensation.
