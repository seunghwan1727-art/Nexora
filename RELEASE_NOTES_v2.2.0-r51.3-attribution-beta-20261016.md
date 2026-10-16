# Nexora / COS v2.2.0 r51.3 - Attribution Beta (Companion 2.0.63)

**SUPERSEDED INSTALLER NOTICE:** This original beta ZIP mistakenly omitted the 16, 32, 48 and 128 pixel Companion PNG icons. For fresh installations use the [r51.3 Icon Hotfix prerelease](https://github.com/seunghwan1727-art/Nexora/releases/tag/v2.2.0-r51.3-iconfix-beta-20261016), which includes them in both public downloads. The original assets are retained for release history.

**EXPERIMENTAL PRE-RELEASE. NOT THE RECOMMENDED STABLE BUILD.**

Release date: October 16, 2026.

Nexora is independently maintained and based on the [original MIT-licensed Chat On Steroids project](https://github.com/totec448-spec/chat-on-steroids). The full upstream MIT notice, third-party notices and the signed public license are preserved. See [CREDITS.md](CREDITS.md).

## Downloads and SHA-256

**Windows app + Chrome Companion 2.0.63 + fixed-expiry public license:**

Nexora_r51_3_Companion2.0.63_PUBLIC_FREE_TO_20271231_CODEX_CONDITIONAL_PRERELEASE_20261016.zip

SHA-256: 7CCA972C78C29DAE845228CE783B43E606371AC837CF14915DD2D70F46629760

**Standalone Chrome Companion 2.0.63:**

Nexora_Companion2.0.63_PRERELEASE_20261016.zip

SHA-256: 404E78F4FAA06DDB4093801E9C0422A6A3A798BBCFD9C54A3BDAB1FD66AF462D

The Companion-only ZIP includes the original MIT notice. No developer-only NO_LIMIT license, signing keys, license issuer or development source code is published.

## Experimental improvements

- Improves potential Unattributed activity handling through single-use tool/arguments or tool/complete-single-text-result fingerprints when ChatGPT's public MCP card exposes them.
- Waits for a bounded evidence window before attributing calls. Conflicting conversation or session proof fails closed to Unattributed instead of guessing.
- Disables elevation of a public MCP card's native callId to a permanent HTTP request owner: those IDs are not reliably identical.
- Rejects historical tool cards observed on the extension's first accepted scan as new ownership proof.
- Retains exact HTTP request-ID attribution, Worker/Pack & Resume safeguards and previous app functionality.

## Verification

| Check | Status |
| --- | --- |
| Offline regression suite | 24/24 PASS |
| Source unchanged during test run | PASS |
| App / Companion version | 2.0.63 / 2.0.63 PASS |
| Bridge protocol | 13 PASS |
| Public license expiry and private-license separation | PASS |
| Full ZIP integrity and original MIT copyright inclusion | PASS |
| Independent Codex read-only review | CONDITIONAL: 0 open P0, 2 open P1 |
| Real Chrome renderer / recipient-PC Live E2E | NOT RUN |

## Known P1 limitations - read before testing

1. **Potential local Activity loss during shutdown.** A call pending in the 45-second attribution window may still be waiting when the application begins its 10-second recorder flush. Shutting down immediately after tool execution may drop its local Activity record. Back up sessions and avoid closing COS immediately after using tools.
2. **Post-deadline evidence may downgrade the Activity destination.** An auxiliary fingerprint arriving after the attribution proof deadline, but before the serialized record write, may conflict with an exact request owner and leave the record Unattributed.

The live browser renderer's actual argument/result object shape remains unverified. **The beta is not guaranteed to eliminate Unattributed warnings.** The separate Core Tunnel 503, picker_unavailable and individual PowerShell exit-code errors are not claimed fixed.

## Installation and rollback

1. Keep the [r50.1 release](https://github.com/seunghwan1727-art/Nexora/releases/tag/v2.2.0-r50.1-public-2027), and back up COS session data and settings.
2. Fully unpack the beta ZIP to a separate, short Windows path (for example D:\COS_Beta). Never combine r50.1 and r51.3 files.
3. Run VERIFY_RELEASE.ps1 in PowerShell. Require VERSION_MATCH_PASS, PUBLIC_LICENSE_EXPIRY_PASS and VERIFY_CANDIDATE_PASS.
4. Close the existing COS application only. Do not close ChatGPT tabs or restart Chrome. Do not run two COS installations simultaneously.
5. Run the beta application and load its own unpacked Chrome extension from resources\extension; confirm Companion 2.0.63.
6. In two independent conversations, execute low-risk read-only COS tools and check that Activity records belong to the correct conversations. Report only sanitized diagnostics if any warnings persist.
7. Roll back by exiting beta COS and returning to the original r50.1 app and Companion 2.0.59.

Never share license.key contents, personal access tokens, session cookies, private prompts or user files as diagnostic output.

## License and provenance

The public license allows starting this packaged binary until December 31, 2027 KST, expiring January 1, 2028 00:00 KST. It does not revoke the original MIT rights. Nexora is not affiliated with OpenAI. End users do not need Python or WSL for the base Windows application.
