# Nexora r51.3 - Chrome Companion Icons Hotfix (2.0.63)

**EXPERIMENTAL PRE-RELEASE - NOT THE STABLE BUILD.**

Release date: October 16, 2026.

## Why this hotfix exists

The earlier [r51.3 experimental attribution beta](https://github.com/seunghwan1727-art/Nexora/releases/tag/v2.2.0-r51.3-attribution-beta-20261016) shipped a Companion 2.0.63 directory whose manifest referenced four icon files that were accidentally **excluded from the packaged ZIP files**. Chrome refused to load the unpacked extension with an error similar to:

> Could not load icon 'icons/icon16.png' specified in 'icons'.

This release restores the four PNGs in **both** the bundled Windows application extension and the separate Companion ZIP:

- icons/icon16.png
- icons/icon32.png
- icons/icon48.png
- icons/icon128.png

The original Companion 2.0.63 icon files are copied byte-for-byte. Their PNG signatures, dimensions, SHA-256 hashes, and all icon references in manifest.json are checked. The application's app.asar SHA-256 and all JavaScript code remain unchanged; no feature rewrite or change to the public license was made.

**Download this icon-hotfix prerelease instead of the original r51.3 beta if Chrome fails to load the extension.** The r50.1 public release remains the recommended baseline for users who do not require the experimental attribution changes.

## Downloads and integrity

**Windows app (Companion 2.0.63 included; public license expires 2028-01-01 00:00 KST):**

Nexora_r51_3_Companion2.0.63_PUBLIC_ICONFIX_20261016.zip

SHA-256: 139F2B50BC39CDF6A63135851731A0A865ECF1C48D0574A18382A500EA38F74C

**Standalone Companion 2.0.63 (icons and original MIT license included):**

Nexora_Companion2.0.63_ICONFIX_20261016.zip

SHA-256: F1DACE6FC75D9AAB83A7677D89212804681DB7D3539E3E955B4C6C83E3B4EA9A

The Windows ZIP contains a signed **public** license only, valid through December 31, 2027 KST. The developer-only NO_LIMIT license, signing private keys and private development sources are **not** part of these public downloads.

## Verification and limitations

| Check | Result |
| --- | --- |
| Previously completed r51.3 offline code regression tests | 24/24 PASS (unchanged code) |
| Original r51.3 independent Codex review | CONDITIONAL, 0 outstanding P0 / 2 outstanding P1 |
| Manifest icon references and actual PNG files (16, 32, 48, 128) | PASS |
| Windows program / Companion expected versions | 2.0.63 / 2.0.63 PASS |
| Public license expiry, public/private separation | PASS |
| Package file hashes, ZIP entire payload and MIT notice | PASS |
| Real recipient-PC end-to-end ChatGPT attribution testing | NOT RUN |

**Two known P1 issues from the earlier r51.3 review are NOT fixed by this packaging-only patch:**

1. A pending tool Activity record can be lost when the app is closed before the 45-second attribution window completes, because the recorder's shutdown flush has a 10-second budget.
2. A late fingerprint arriving after the attribution deadline, but before the queued write, may downgrade an exactly attributed record to Unattributed.

Actual live Chrome MCP card result shapes also remain unverified. This hotfix resolves the **missing extension icons**, not all Unattributed warnings, Core Tunnel 503, picker_unavailable, or an individual failing command. Do not assume those other issues are resolved.

## Install or update

1. Back up COS settings and session data; keep your existing r50.1/r51.3 directory for rollback.
2. Extract the **entire** new Windows ZIP into a short, separate directory. Do not combine old and new program files.
3. Run VERIFY_RELEASE.ps1 in the extracted app folder. Check for VERSION_MATCH_PASS, PUBLIC_LICENSE_EXPIRY_PASS and VERIFY_CANDIDATE_PASS.
4. Stop the **COS application only** before switching the executable. No Chrome restart or ChatGPT-tab closure is necessary. Never run two COS versions simultaneously.
5. In chrome://extensions enable Developer mode. Load the extracted resources/extension folder as an unpacked extension. If the extension is already registered at the same folder, click its Reload control; check that icons exist and Companion 2.0.63 loads successfully.
6. Verify Companion / Bridge connection and test low-risk, read-only tools in separate conversations before depending on the experimental attribution behavior.

If needed, roll back to the unchanged [r50.1 release](https://github.com/seunghwan1727-art/Nexora/releases/tag/v2.2.0-r50.1-public-2027).

## Origin and license

Nexora is based on the original MIT-licensed [Chat On Steroids](https://github.com/totec448-spec/chat-on-steroids) project, not developed independently from scratch, and is not affiliated with OpenAI. Original MIT license and copyright notices are included in the archive. This prerelease does not change the upstream project's MIT rights.
