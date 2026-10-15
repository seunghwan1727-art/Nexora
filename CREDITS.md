# Project origins, credits and licenses

## Original project — Chat On Steroids

Nexora's Windows distribution is a modified build based on:

**[Chat On Steroids](https://github.com/totec448-spec/chat-on-steroids)**  
Repository: https://github.com/totec448-spec/chat-on-steroids  
Original contributors and copyright: **Copyright (c) 2026 Chat On Steroids contributors**  
License: **MIT** — https://github.com/totec448-spec/chat-on-steroids/blob/main/LICENSE

This project and its community are the foundation of Nexora. Nexora is an independent downstream distribution and is **not** the official upstream project.

The original MIT license copyright notice and license text are included in the downloadable application under **`resources/LICENSE`**. The upstream MIT grant continues to apply to the original code and derivatives to the extent covered by that license.

## Nexora modifications and distribution

**Maintained by:** [seunghwan1727-art](https://github.com/seunghwan1727-art)  
**Public release repository:** [seunghwan1727-art/Nexora](https://github.com/seunghwan1727-art/Nexora)

This distribution contains additional Windows-focused engineering and packaging, including work relating to:

- Terminal / Jobs integration and long-running command handling
- Session history, continuity, handoff and release stability
- Companion version synchronization and browser integration
- Optional Local AI / Codex-based development workflows
- Binary release verification, public signed license and Windows deployment

Not every feature listed above is necessarily new relative to the upstream project; this list describes areas worked on in the Nexora version and does not claim original authorship of all related concepts.

## Technology and third-party acknowledgements

| Project | Usage / relationship |
| --- | --- |
| [Electron](https://github.com/electron/electron) and [Chromium](https://www.chromium.org/) | Desktop application runtime |
| [Node.js](https://nodejs.org/) | JavaScript runtime |
| [Chrome Extensions (Manifest V3)](https://developer.chrome.com/docs/extensions/develop) | ChatGPT browser companion |
| [Model Context Protocol](https://modelcontextprotocol.io/) and [its SDK](https://github.com/modelcontextprotocol) | Tool and local bridge protocol |
| [Cloudflare cloudflared](https://github.com/cloudflare/cloudflared) | Tunnel networking |
| [node-pty](https://github.com/microsoft/node-pty) | Windows terminal / ConPTY support |
| [Tree-sitter](https://github.com/tree-sitter/tree-sitter) and Tree-sitter Bash grammar | Command syntax parsing |
| [sharp](https://github.com/lovell/sharp) | Image decoding and transforms |
| [ws](https://github.com/websockets/ws) | WebSocket support |
| [Zod](https://github.com/colinhacks/zod) | Input and configuration validation |
| [Marked](https://github.com/markedjs/marked) | Markdown rendering |
| [ripgrep](https://github.com/BurntSushi/ripgrep) | File and text search |
| [Codex CLI](https://github.com/openai/codex) | Optional external development/review tool |
| [llama.cpp](https://github.com/ggml-org/llama.cpp) | Optional external local-model runtime |

Individual components have their **own** license obligations. Consult the included ZIP files **`LICENSE.electron.txt`**, **`LICENSES.chromium.html`**, **`resources/LICENSE`**, **`resources/tunnel/LICENSE`**, **`resources/tunnel/NOTICE`**, and licenses under bundled dependencies. These notices have not been replaced by a Nexora-specific license.

## Public license and upstream MIT rights

The public Nexora build contains a signature-verified **license.key** expiring at **2028-01-01 00:00 KST**. Its runtime gate determines whether that particular executable starts after the deadline. It is **not** a cancellation of the original project's MIT permission to use, study, modify and redistribute the MIT-covered source code.

The separate Nexora development-source tree and developer-only NO_LIMIT signing credentials are not published. The Electron ASAR and Chrome Companion nevertheless contain executable JavaScript that users can inspect.

ChatGPT and Codex are provided by OpenAI. **Nexora is not affiliated with, sponsored, endorsed or operated by OpenAI.** Follow the terms of connected services; no license grants additional provider quota.

---

## 원본 프로젝트 및 출처 (한국어)

Nexora는 처음부터 독자적으로 만들어진 프로그램이 아니라 **[Chat On Steroids 원본 저장소](https://github.com/totec448-spec/chat-on-steroids)를 기반으로 수정·확장한 별도 Windows 배포판**입니다.

- **원본 프로젝트:** Chat On Steroids / `totec448-spec` 및 기여자
- **원본 저작권:** Copyright (c) 2026 Chat On Steroids contributors
- **원본 라이선스:** MIT (공개 배포 ZIP의 `resources/LICENSE`에 전문 보존)
- **Nexora 수정·개발·배포:** [seunghwan1727-art](https://github.com/seunghwan1727-art)
- **사용 기반 기술:** Electron, Chromium, Node.js, Chrome Manifest V3, MCP, cloudflared, node-pty, Tree-sitter, sharp, ws, Zod, Marked, ripgrep
- **선택 연동:** Codex CLI, llama.cpp

**무료 키의 만료일은 Nexora 배포 실행 파일의 시작 시 검사 조건**이며, **원본 MIT 라이선스가 부여한 권리를 무효화하는 조건은 아닙니다.** 원본 프로젝트와 제3자 오픈소스 제작자에게 감사를 표합니다.
