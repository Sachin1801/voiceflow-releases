# Security Policy

## Supported Versions

| Version | Supported |
|---------|-----------|
| 0.1.x   | Yes       |

## Reporting a Vulnerability

If you discover a security vulnerability in VoiceFlow, please report it responsibly.

**Do NOT open a public GitHub issue for security vulnerabilities.**

Instead, please email: **sachin.adlakha18@gmail.com**

Include:
- Description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if any)

You can expect an initial response within 48 hours. We will work with you to understand and address the issue before any public disclosure.

## Security Measures

VoiceFlow implements the following security practices:

- **Code Signing**: All releases are signed with an Apple Developer ID certificate
- **Apple Notarization**: Every release is notarized by Apple's security service
- **Local Processing**: Speech recognition runs entirely on-device — no audio data is transmitted
- **Minimal Permissions**: Only Microphone and Accessibility permissions are requested
- **No Telemetry**: No analytics, crash reporting, or usage data collection
- **Sandboxed Network**: Network access is only used for optional AI text enhancement (user-configured API keys)
