<div align="center">

# VoiceFlow

**Fast, private voice dictation for macOS — powered by on-device AI.**

Type at the speed of thought. VoiceFlow transcribes your speech locally using [whisper.cpp](https://github.com/ggerganov/whisper.cpp) with Metal GPU acceleration — no cloud, no latency, no subscriptions.

[![Latest Release](https://img.shields.io/github/v/release/Sachin1801/voiceflow-releases?style=flat-square&color=blue)](https://github.com/Sachin1801/voiceflow-releases/releases/latest)
[![Platform](https://img.shields.io/badge/platform-macOS%2013%2B-black?style=flat-square&logo=apple&logoColor=white)](https://github.com/Sachin1801/voiceflow-releases/releases/latest)
[![Architecture](https://img.shields.io/badge/Apple%20Silicon-M1%2B-orange?style=flat-square)](https://github.com/Sachin1801/voiceflow-releases/releases/latest)
[![Notarized](https://img.shields.io/badge/Apple%20Notarized-✓-brightgreen?style=flat-square&logo=apple&logoColor=white)](https://support.apple.com/guide/security/app-security-overview-sec35dd877d0/web)
[![Downloads](https://img.shields.io/github/downloads/Sachin1801/voiceflow-releases/total?style=flat-square&color=purple)](https://github.com/Sachin1801/voiceflow-releases/releases)

<!-- Add a hero screenshot or demo GIF here:
![VoiceFlow Demo](screenshots/demo.gif)
-->

[**Download Latest Release**](https://github.com/Sachin1801/voiceflow-releases/releases/latest)

</div>

---

## What is VoiceFlow?

VoiceFlow is a macOS-native voice dictation app that runs entirely on your machine. It uses OpenAI's Whisper model via [whisper.cpp](https://github.com/ggerganov/whisper.cpp) with Apple Metal GPU acceleration to transcribe your speech in real-time and type it directly into any application.

Unlike cloud-based dictation services, VoiceFlow processes everything locally — your audio never leaves your device. Optionally enable AI text enhancement for grammar cleanup using your own API keys.

---

## Features

### Core Dictation
- **Push-to-Talk** — Hold a hotkey to record, release to transcribe and type
- **Hands-Free Mode** — Toggle recording on/off for longer dictations
- **Instant Text Injection** — Transcribed text is typed directly into your focused app
- **Voice Activity Detection** — Silero VAD automatically detects speech boundaries

### Intelligence
- **Local Speech-to-Text** — Whisper Small English model (~466 MB), runs on-device via Metal GPU
- **AI Text Enhancement** — Optional grammar/punctuation cleanup via OpenAI, OpenRouter, or any OpenAI-compatible API
- **Filler Word Removal** — Automatically strips "um", "uh", "you know" and custom filler words
- **Custom Word Replacement** — Define find/replace rules (case-insensitive, word-boundary aware)
- **Custom Dictionary** — Add specialized terms to improve transcription accuracy

### Interface
- **Floating Pill Overlay** — Minimal, always-on-top recording indicator that works in full-screen apps
- **Transcription History** — Browse past transcriptions grouped by date
- **Usage Statistics** — Track days active, total words, and average WPM
- **Glass Morphism UI** — Clean, native-feeling dark interface

### Customization
- **Rebindable Shortcuts** — Customize push-to-talk, hands-free, and cancel hotkeys with visual key recorder
- **20 Languages** — English, Spanish, French, German, Japanese, Chinese, Korean, and more
- **Configurable AI Models** — Choose from 9+ models (free to premium) with cost estimates
- **Custom AI Prompts** — Tailor how AI enhancement processes your text

### System
- **Auto-Updates** — Built-in updater checks for new versions automatically
- **Code Signed & Notarized** — Verified by Apple for safe installation
- **No Telemetry** — Zero analytics, tracking, or data collection

---

## Installation

### Quick Start

1. **Download** the latest `.dmg` from the [Releases page](https://github.com/Sachin1801/voiceflow-releases/releases/latest)
2. **Open** the DMG and drag VoiceFlow to your Applications folder
3. **Launch** VoiceFlow — it will guide you through permissions setup
4. **Grant permissions** when prompted:
   - **Microphone** — Required for audio capture
   - **Accessibility** — Required for keyboard shortcuts and text injection

### System Requirements

| Requirement | Details |
|---|---|
| **OS** | macOS 13 Ventura or later |
| **Chip** | Apple Silicon (M1, M2, M3, M4) |
| **Disk Space** | ~600 MB (includes Whisper model) |
| **RAM** | 4 GB minimum |
| **Permissions** | Microphone + Accessibility |

### Updating

VoiceFlow includes a built-in auto-updater. When a new version is available, you'll see an update notification in the app. You can also manually check for updates in **Settings > Updates**.

---

<!-- Uncomment and add screenshots when available:

## Screenshots

<div align="center">

| Home | Settings | Pill Overlay |
|:---:|:---:|:---:|
| ![Home](screenshots/home.png) | ![Settings](screenshots/settings.png) | ![Pill](screenshots/pill-overlay.png) |

</div>

---

-->

## How It Works

```
Microphone → Voice Activity Detection → Whisper STT → Text Processing → Type into App
              (Silero VAD / ONNX)      (whisper.cpp)   (filler removal,   (enigo)
                                        (Metal GPU)     word replace,
                                                        AI enhance)
```

VoiceFlow runs a multi-threaded pipeline optimized for low latency:

- **Audio thread** captures microphone input via a lock-free ring buffer — no mutex contention
- **Processing thread** runs VAD and Whisper inference on Apple Metal GPU
- **Main thread** handles UI updates and text injection into your active application
- **I/O thread** (lazy) handles optional AI enhancement API calls

All speech processing happens on-device. The only network requests are optional AI text enhancement calls using your own API keys.

---

## Privacy & Security

| | |
|---|---|
| **Local Processing** | All speech recognition runs on your Mac using whisper.cpp — audio never leaves your device |
| **No Cloud Required** | Works fully offline. Cloud features (AI enhancement) are opt-in and use your own API keys |
| **Apple Notarized** | Code signed with a Developer ID certificate and notarized by Apple |
| **No Telemetry** | Zero analytics, crash reporting, or usage tracking |
| **No Account Required** | No sign-up, no login, no email collection |
| **Minimal Permissions** | Only requests Microphone and Accessibility — nothing else |

---

## Roadmap

- [ ] Cloud STT providers (OpenAI Whisper API, Deepgram)
- [ ] Intel Mac support
- [ ] Additional Whisper model sizes (tiny for speed, large for accuracy)
- [ ] Clipboard mode (copy to clipboard instead of typing)
- [ ] Per-app dictation profiles

---

## FAQ

<details>
<summary><strong>Is VoiceFlow free?</strong></summary>
<br>
Yes, VoiceFlow is free to download and use. AI text enhancement requires your own API key from a supported provider.
</details>

<details>
<summary><strong>Does it work offline?</strong></summary>
<br>
Yes. Core voice dictation is fully offline. The only feature that requires internet is optional AI text enhancement.
</details>

<details>
<summary><strong>What about Intel Macs?</strong></summary>
<br>
VoiceFlow currently requires Apple Silicon (M1 or later). Intel Mac support is on the roadmap.
</details>

<details>
<summary><strong>How do I update?</strong></summary>
<br>
VoiceFlow checks for updates automatically. You can also check manually in Settings > Updates. Updates are downloaded and applied in-app.
</details>

<details>
<summary><strong>Why does it need Accessibility permission?</strong></summary>
<br>
Accessibility permission is required for two things: (1) capturing global keyboard shortcuts even when VoiceFlow is in the background, and (2) injecting transcribed text into your currently focused application.
</details>

<details>
<summary><strong>Is my voice data sent anywhere?</strong></summary>
<br>
No. All speech-to-text processing happens locally on your Mac using whisper.cpp. Audio is never transmitted over the network. If you enable AI text enhancement, only the transcribed text (not audio) is sent to your chosen API provider.
</details>

---

## Built With

- [whisper.cpp](https://github.com/ggerganov/whisper.cpp) — Local speech-to-text inference
- [Tauri v2](https://v2.tauri.app) — Native app framework
- [React 19](https://react.dev) — Frontend UI
- [ONNX Runtime](https://onnxruntime.ai) — Silero VAD inference
- [Tailwind CSS](https://tailwindcss.com) — Styling

---

## Feedback & Issues

Found a bug or have a feature request? [Open an issue](https://github.com/Sachin1801/voiceflow-releases/issues/new/choose).

---

## License

Copyright (c) 2026 Sachin Adlakha. All rights reserved.

VoiceFlow is distributed as freeware. You may download and use this software for personal and commercial purposes. Redistribution, modification, or reverse engineering of the software is not permitted without explicit written permission. See [LICENSE](LICENSE) for full terms.
