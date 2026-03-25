# Changelog

All notable changes to VoiceFlow are documented here.

## [0.1.9] - 2026-03-25

### Changed
- Simplified pill idle state to a subtle 3px translucent line — no hover text or icons
- Added CI concurrency group to prevent parallel build collisions

## [0.1.8] - 2026-03-25

### Fixed
- Version display in Settings and Updates now reads dynamically from app config
- Pill overlay position and app close behavior
- CI tag annotations now appear correctly in release notes

## [0.1.7] - 2026-03-25

### Added
- Three-state pill UI with idle, recording, and processing transitions
- NSPanel-based overlay for full-screen macOS Spaces visibility
- Structured JSON logging with file output
- Crash diagnostics IPC command
- Input monitoring permission detection and diagnostic logging
- Hallucination filtering for improved speech detection

### Fixed
- Pill overlay now visible in full-screen apps

## [0.1.6] - 2026-03-24

### Added
- Fully rebindable shortcuts: push-to-talk, hands-free mode, cancel
- Inline key recorder: press any key combo to assign a shortcut
- Conflict detection against other shortcuts and macOS system keys
- Cancel dictation (Esc) discards transcript instead of injecting
- Push-to-talk key also stops hands-free mode
- Shortcuts persist across app restarts
- Releases published to public repo for direct downloads

### Fixed
- Updater ACL permissions

## [0.1.5] - 2026-03-24

### Added
- Updater and process permissions for auto-update support
- Public release repo for direct downloads

## [0.1.4] - 2026-03-24

### Added
- Configurable keyboard shortcuts with visual key recorder
- Shortcut conflict detection

## [0.1.3] - 2026-03-24

### Added
- Relaunch flow for accessibility permission granting

## [0.1.2] - 2026-03-24

### Fixed
- Bundle identifier correction
- Cache invalidation

## [0.1.1] - 2026-03-24

### Fixed
- Microphone permission detection using AVFoundation

### Added
- In-app auto-updater

## [0.1.0] - 2026-03-22

### Added
- Initial release
- Local voice dictation with whisper.cpp
- Push-to-talk and hands-free recording modes
- Text injection into focused applications
- AI text enhancement (OpenAI-compatible APIs)
- Custom dictionary and word replacement
- Filler word removal
- 20 language support
- Transcription history with statistics
- Glass morphism UI
- DMG packaging with drag-to-install
