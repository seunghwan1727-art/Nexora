# Nexora

**Nexora is a separately maintained, modified distribution based on the open-source [Chat On Steroids](https://github.com/totec448-spec/chat-on-steroids) project.** The downloadable application currently retains its original **Chat On Steroids** executable name.

**Original project:** [totec448-spec/chat-on-steroids](https://github.com/totec448-spec/chat-on-steroids) and its contributors — **MIT License**.

**Nexora modifications, packaging and distribution:** [seunghwan1727-art](https://github.com/seunghwan1727-art).

**Windows companion application for ChatGPT workflows**, with a Chrome extension, local MCP bridge, session tooling, and optional development / local-AI integrations.

## Public Free Edition

**Free to use through December 31, 2027 (Korea Standard Time).**

The public release includes a signed license valid until **2028-01-01 00:00 KST (2027-12-31 15:00 UTC)**. The program currently checks the license on startup; it does not automatically terminate an already-running process at the expiry instant.

The Nexora repository distributes **Windows application binaries, a Chrome Companion extension and documentation only**. No separate Nexora development-source repository is provided. The upstream project's [MIT license](https://github.com/totec448-spec/chat-on-steroids/blob/main/LICENSE) continues to apply to the original MIT-covered code. Electron applications and Chrome extensions necessarily contain executable JavaScript, so shipping binaries only does not make implementation details impossible to inspect.

## Download

Download from the **Releases** section of this repository when a release has been published:

- **Windows app + public free license + bundled Companion 2.0.59:** ChatOnSteroids_v2.2.0_r50.1_Companion2.0.59_PUBLIC_FREE_TO_20271231_20261015.zip
- **Companion 2.0.59 (standalone, MIT notice included):** ChatOnSteroids_Companion_2.0.59_PUBLIC_20261016.zip

Until a release is published, no downloads are available from this repository.

## Installation

1. Download and fully extract the Windows ZIP to a writable, dedicated folder.
2. In PowerShell, run the included VERIFY_RELEASE.ps1. Confirm PUBLIC_LICENSE_EXPIRY_PASS, VERSION_MATCH_PASS, and VERIFY_RELEASE_PASS.
3. Keep license.key next to Chat On Steroids.exe. Launch the EXE.
4. In Chrome, visit chrome://extensions, enable Developer mode, choose **Load unpacked**, and select the extracted resources/extension folder.
5. Confirm the COS bridge/tunnel and Companion 2.0.59 connect successfully.
6. Do not run old and new COS installations simultaneously. Back up your existing session data before migrating.

The ZIP contains no bundled LLM model weights. End users do not need Python or WSL to run the base application. Some optional integrations require their own dependencies or accounts.

## Origins and technology

Nexora is **not a project written from scratch**. It is based on the original [Chat On Steroids repository](https://github.com/totec448-spec/chat-on-steroids), with additional work on the Windows build, session handling, terminal jobs, Companion integration, local-agent options and release verification. These additions are part of the Nexora-maintained distribution and should not be mistaken for features or commitments of the original project.

| Component | Role in this distribution |
| --- | --- |
| [Chat On Steroids](https://github.com/totec448-spec/chat-on-steroids) | Original open-source project on which Nexora is based (MIT) |
| [Electron](https://github.com/electron/electron) / [Chromium](https://www.chromium.org/) / Node.js | Windows desktop runtime and UI |
| Chrome Extensions (Manifest V3) | Browser-side Companion integration |
| [Model Context Protocol](https://modelcontextprotocol.io/) and its SDK | Bridge/tool protocol connecting local capabilities |
| [cloudflared](https://github.com/cloudflare/cloudflared) | Tunnel transport |
| [node-pty](https://github.com/microsoft/node-pty) | Terminal/PTY integration |
| [Tree-sitter](https://github.com/tree-sitter/tree-sitter), [sharp](https://github.com/lovell/sharp), [ws](https://github.com/websockets/ws), [Zod](https://github.com/colinhacks/zod), [Marked](https://github.com/markedjs/marked) | Bash parsing, image handling, sockets, validation and Markdown processing |
| [ripgrep](https://github.com/BurntSushi/ripgrep) | Text and project search |
| [Codex CLI](https://github.com/openai/codex), [llama.cpp](https://github.com/ggml-org/llama.cpp) | Optional external code-review and local-model integrations; not included as a model bundle |

**Original copyright notice:** Copyright (c) 2026 Chat On Steroids contributors. The original MIT license text is preserved in the Windows ZIP at **`resources/LICENSE`**.

Further attribution, original license text and links are in [CREDITS.md](CREDITS.md). Electron/Chromium and included third-party license notices remain in the release ZIP (`LICENSE.electron.txt`, `LICENSES.chromium.html`, and dependency LICENSE/NOTICE files).

The public signed COS **license.key** determines whether this particular packaged executable accepts startup through December 2027. It does **not** revoke or supersede the original MIT license or its redistribution/modification permissions. This project is independent and **not developed, endorsed or operated by OpenAI**.

## Usage and security

The Companion extension requests access to ChatGPT pages and communicates with a locally running COS service. COS can also perform filesystem and terminal operations when authorized. Install only from a trusted release and review application and extension permissions.

ChatGPT, Codex, model-provider plans, API charges, and rate limits are **not** made unlimited by this public COS license.

This is an independent project and is not an official OpenAI application. Third-party notices are included in the ZIP.

## Release status

The public package is based on COS v2.2.0 r50.1 / Companion 2.0.59. The version-compatibility fix and offline regression checks passed. **Real-world installation / integration testing on other PCs is not yet complete.** The separate Unattributed tool attribution warning and picker_unavailable model-selection issue remain under investigation.

For the release SHA-256 values and detailed notes, see [Release notes](RELEASE_NOTES_v2.2.0-r50.1-public-2027.md).

## 한국어 안내

**원본 출처:** [totec448-spec/chat-on-steroids](https://github.com/totec448-spec/chat-on-steroids) 및 원본 기여자들. 원본 프로젝트는 **MIT 라이선스**이며, Nexora는 이 프로젝트를 기반으로 수정·확장한 별도 배포판입니다.

**Nexora 추가 개발 및 배포 관리:** [seunghwan1727-art](https://github.com/seunghwan1727-art). GitHub 프로젝트 이름은 **Nexora**이고, 현재 실행 파일 이름은 **Chat On Steroids**입니다. 원본 MIT 저작권 고지와 라이선스는 ZIP의 **`resources/LICENSE`**에 유지됩니다. 자세한 기반 기술과 출처는 [CREDITS.md](CREDITS.md)를 참조하세요. OpenAI의 공식 제품이 아닙니다.

**이 배포판은 2027년 12월 31일까지 무료로 실행**할 수 있도록 서명된 공개 키를 포함합니다. 이는 해당 실행 파일의 시작 시 유효성을 판단하는 키이며, **원본 MIT 오픈소스 권리를 소멸시키지 않습니다.** 개발자 무기한 키는 포함되지 않습니다.

설치 시 ZIP을 전체 압축 해제하고 VERIFY_RELEASE.ps1을 실행한 뒤, Chat On Steroids.exe를 실행하세요. Chrome 확장 프로그램은 resources/extension 폴더를 압축 해제된 확장으로 등록하면 됩니다.

사용자 기기의 실제 E2E 테스트는 완료되지 않았으므로, 기존 환경의 Sessions와 설정을 백업한 뒤 사용하시기 바랍니다.
