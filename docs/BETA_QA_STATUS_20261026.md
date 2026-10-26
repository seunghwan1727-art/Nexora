# Nexora r52.4-P70 — Beta QA status (2026-10-26)

> **Status: internal QA candidate. No public release has been published for this version.**

Nexora is a modified distribution of [Chat On Steroids](https://github.com/totec448-spec/chat-on-steroids), whose original code is MIT-licensed.

## Target

- Desktop app: `2.3.0-beta.6` (revision `r52.4-P70`)
- Chrome Companion: `2.0.82`
- Existing Windows app identity: `com.chatonsteroids.app`
- Existing per-user data directory: `%APPDATA%\chat-on-steroids`
- Existing local MCP bridge: port `8765`
- The beta is intended as an **update to the existing Nexora installation**, not a separate demo application.

## QA completed

- Public Windows NSIS installer candidate built and its EXE and packaged ASAR digests verified.
- Packaging checksum and public/private license separation checks passed.
- Synthetic Cold/Hot terminal-job preservation and distinct-process reload tests passed.
- Isolated, synthetic installation update and rollback tests passed, including preservation of configuration and job metadata digests.
- A personal-device private beta cutover and file-by-file backup check were reported successful on 2026-10-26. This does not establish that other users' installations upgrade safely.

## Not yet validated for general release

- End-to-end upgrade of a typical existing portable installation to the installer-based edition, including conflict-free rollback.
- Live ChatGPT A/B request-to-chat attribution and `Unattributed` recovery.
- Chrome project-scoped Compact/Resume and existing tunnel continuity across an update.
- Windows code-signing; QA installers are currently unsigned.

**Do not promote this candidate to a general GitHub Release until these deployment risks are assessed.** The stable downloads linked in the repository README are unchanged.

## Publication policy

Only public-edition binaries and their checksums may be uploaded to public releases. Never publish a private-license build, `license.key`, tokens, tunnel credentials, user data, or terminal-job outputs.

This document is a status record and is not an installation authorization.
