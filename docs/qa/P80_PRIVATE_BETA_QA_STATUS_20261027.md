# Nexora P80 — private beta QA checkpoint (2026-10-27)

## Status

**QA package prepared; production and public release remain NO-GO.**

- Code version: `2.3.0-beta.7` (same compiled executable / `app.asar` as the validated P76 core).
- Companion version: `2.0.82`, with a separate P79 build ID for the guarded same-version update pathway.
- P77 synthetic A/B request-id ownership regression: PASS. This is **not** a live two-chat ChatGPT E2E test.
- P79 isolated auto-reload guard regression: PASS (same-build 0; idle changed-build 1; busy/pending 0; replayed attempt 0).
- P80 private local QA candidate created with two 1,166-entry SHA-256 manifests. Manifest comparison: exactly five approved changes, no added/missing paths. Executable, ASAR and P77 fiber manifest hashes match the pinned parent.
- P80 independent post-build runtime verification result: not yet confirmed in this checkpoint.
- Live ChatGPT A/B attribution, `agents` pre-execution authorization, Chrome Companion transition, restart/Compact & Resume: pending.
- The previous private installation, browser and tunnel are preserved; retained Jobs must not be acknowledged, cancelled, deleted or replayed as part of QA.

## Guardrails

This public repository **must not** contain:
- signed private / NO_LIMIT binaries or a private license file;
- userData, credentials, tokens, terminal archives or recorded conversation content;
- an unverified prerelease tagged or presented as production-ready.

Do not merge this QA checkpoint into `main` or publish executable release assets before live A/B authorization and safe-transition verification pass.

## Next gates

1. Prove correct request-to-conversation mapping and no cross-chat ownership in two distinct live ChatGPT chats.
2. Verify browser journal, command ACK outbox, pending page tasks and one-time update custody are safely drained before a controlled transition.
3. Apply the beta through a non-forced single-instance handoff, without restarting Chrome or refreshing tabs.
4. Run post-apply A/B, scoped mutations, `agents`, reconnect, persistence and unread-job preservation checks.
5. Produce a separately sanitized distributable with independent hash, license and security checks; only then approve a public GitHub prerelease.

**Current release gate: NO-GO.**
