# Release v2.2.0-r50.1-public-2027

**Nexora** is a separately maintained modified distribution based on the upstream [Chat On Steroids project](https://github.com/totec448-spec/chat-on-steroids) (MIT; Copyright (c) 2026 Chat On Steroids contributors). Nexora modifications and packaging are maintained by [seunghwan1727-art](https://github.com/seunghwan1727-art). The complete upstream MIT notice is included in the Windows ZIP at `resources/LICENSE`. See [CREDITS.md](CREDITS.md) for dependencies and provenance. Nexora is independent of OpenAI.

Release date: 2026-10-15

## Assets

Windows app + Companion 2.0.59 + public fixed-expiry license:

ChatOnSteroids_v2.2.0_r50.1_Companion2.0.59_PUBLIC_FREE_TO_20271231_20261015.zip

SHA-256:

84264136A4B58313042EED53EC2F1B6474A4843B2DE36ADE1CB2F1D47F5391D4

Standalone Chrome Companion:

ChatOnSteroids_Companion_2.0.59_PUBLIC_20261016.zip

SHA-256:

37D14E0D3D6BD1E7C7A9DA420C534A52C2805B37A2C236ABB9060AEBEDE1066F

This standalone Companion ZIP also contains the original project's MIT copyright/license notice and a detailed CREDITS.md with the upstream project URL.

## License

- Public signed license included with the Windows package.
- Expiry: 2028-01-01 00:00 KST, exclusive; usage is free through 2027-12-31.
- Current enforcement checks expiry at app startup, not continuous automatic termination.
- An unrelated developer-only non-expiring license is **not** part of this release.
- The license does not change ChatGPT or Codex subscription/service limits.
- The original upstream MIT license remains applicable to original MIT-covered code; the signed public key governs startup of this packaged binary, not the user's open-source rights.

## Verification completed

- Bundled application and Companion 2.0.59 version parity: PASS.
- Bridge protocol version 13 parity: PASS.
- Base r50.1 offline regression: 21/21 PASS.
- Public license signature / actual verification logic: PASS.
- Expiry boundary and tamper rejection: PASS.
- SHA-256 verification of extracted package files and ZIP payload: PASS.
- Public and developer keys confirmed distinct: PASS.
- Live receiver-PC installation and long-running E2E: NOT RUN.
- Independent final Codex review: deferred to conserve usage quota.

## Known separate issues

- Intermittent request attribution labeled Unattributed.
- Model picker unavailable in some browser states.

## Installation notes

Download and fully extract the Windows ZIP; do not copy only the executable.
Run VERIFY_RELEASE.ps1, launch Chat On Steroids.exe, and install the bundled Chrome extension from resources/extension.
Do not run two COS app versions concurrently. Preserve and back up existing user data.

The public package contains executable binaries and the required Electron/extension JavaScript, not a separate source repository.
