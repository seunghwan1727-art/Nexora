# Nexora 설치 및 초기 설정 — 순서대로 따라하기

버전: **2.3.0-beta.6 / r52.4-P70**, 에디션 **PUBLIC (free beta policy)**, Companion **2.0.82**.

**중요:** 이 파일이 들어 있는 배포 후보는 `NO-GO`입니다. 아래 설치 단계는 **출시 검증이 끝나 GO 승인된 배포본을 받은 이후의 절차**입니다. 현재 파일로 실제 설치하거나 기존 COS를 종료하지 마세요.

먼저 [README_START_HERE.md](README_START_HERE.md)를 읽으세요. 설치 파일은 같은 폴더의 `Chat-On-Steroids-Setup-x64.exe`이며 Windows만 대상으로 합니다. 최종 사용자는 Python이나 WSL을 별도로 설치할 필요가 없습니다.

## A. 기존 사용자 — 기존 COS에 그대로 업데이트

**기존 설치 사용자에게 최초 Setup Wizard를 다시 진행시키지 않습니다.** 베타는 이름만 베타인 기존 COS의 다음 버전입니다.

1. **버전/배포 승인 확인:** `README_START_HERE.md`와 `RELEASE_GATE.json`을 확인합니다. `NO-GO`라면 중단. 설치할 새 릴리스가 기존 제품 ID `com.chatonsteroids.app`인 것도 확인합니다.
2. **현재 환경 기록:** 본인이 쓰던 COS 버전, 연결 상태, 기존 공유 폴더 목록, OpenAI Tunnel ID가 존재하는지, Companion 버전, 미확인 Terminal Job의 수를 *읽기 전용*으로 확인합니다. API 키/라이선스 값은 메모하거나 복사하지 않습니다.
3. **안전한 백업과 승인:** 운영 Job·출력·소유권을 포함해 일관된 백업/롤백을 검증한 **승인된 업데이트 절차**를 사용합니다. 현재 패키지에서는 이 단계가 아직 검증되지 않았으므로 **설치 금지**입니다. Windows 탐색기로 실행 중인 Job 저장소를 임의 복사한 파일을 무손실 백업으로 간주하지 않습니다.
4. **승인된 업데이터로 패치:** 정상 실행 중인 작업이 없는지 확인한 뒤, *사용자가 승인하는 시점*에만 COS의 정상 종료/업데이트 인계를 진행합니다. Chrome 전체 재시작, 탭 종료, 강제 새로고침, 작업 강제 취소/ACK는 금지입니다. 설치 위치 및 동일 사용자 데이터는 유지합니다.
5. **기존 설정 그대로 확인:** 동일 Windows 사용자로 새 COS를 실행하여 기존 `%APPDATA%\chat-on-steroids`, 공유 폴더·권한, API 키 저장 상태, OpenAI Tunnel, 연결된 ChatGPT 앱, Companion, 세션/프로젝트 및 미확인 Job 수를 확인합니다. **설정이 남아 있다면 Setup을 다시 진행하지 않습니다.**
6. **읽기 전용 연결 검증:** ChatGPT에서 이미 연결한 도구를 한 번만 읽기 전용으로 확인합니다. 요청 ID가 `Unattributed`라면 쓰기/명령을 반복 실행하거나 수동 Thread 연결로 우회하지 않습니다.
7. **문제 발생 시:** 작업을 중단하고 [TROUBLESHOOTING.md](TROUBLESHOOTING.md)를 확인합니다. 기존 데이터 삭제/초기화나 성급한 재설치는 금지합니다. 승인된 롤백 절차가 없으면 운영을 복구할 수 있다고 주장하지 않습니다.

**유지 대상:** `config.json`, `secrets.bin`, `terminal-jobs.json`과 관련 출력 증빙, 개인 `license.key`, 기존 확장 프로그램의 안정된 경로/ID, 공유 폴더, Tunnel 설정. 별도 `Nexora-Beta-*` 데이터 디렉터리나 포트 19765/19766을 만드는 예전 P59 방식은 이 업데이트가 아닙니다.

## B. 신규 사용자 — 처음 설치한 경우의 6단계 Setup

1. **다운로드·무결성 확인:** `README_START_HERE.md`의 배포 승인과 SHA-256 검사부터 진행합니다. 공개판은 개인 `license.key`가 필요 없으며, 개인판은 외부 공유하지 않습니다.
2. **정상 Windows 설치:** 승인이 난 설치 파일 `Chat-On-Steroids-Setup-x64.exe`을 실행해 일반 사용자(per-user) 설치를 완료합니다. 보안 경고를 우회하거나 검증되지 않은 EXE를 관리자 권한으로 실행하지 마세요.
3. **COS 실행 → 왼쪽 `Setup` 탭:** 앱 화면에는 아래 **6단계**가 표시됩니다. 단계 이름과 버튼 이름은 현재 소스 UI 기준입니다.

| 단계 | 화면에 표시되는 제목 | 사용자가 해야 할 일 |
|---|---|---|
| **1** | **Pick a folder to share** | `Choose folder`로 필요한 폴더만 공유. 나중에 `Manage folders`로 관리. 접근시키지 않을 폴더는 추가하지 마세요. |
| **2** | **Create a tunnel** | 권장되는 **OpenAI Secure MCP Tunnel** 방식은 화면의 `Open Tunnels`에서 **ChatGPT와 동일한 Workspace**에 Tunnel을 만든 후 `Tunnel ID — Core connector`에 ID를 넣습니다. Desktop 기능을 별도로 쓰는 경우에만 `Tunnel ID — Desktop connector` 추가. |
| **3** | **Create an API key** | `Open API keys`에서 **Restricted** 키를 만들고 권한을 `Tunnels: Read`, `Tunnels: Use`로 최소화한 뒤 `Tunnel API key`에 입력합니다. 키는 다시 표시되지 않을 수 있으니 안전하게 관리하고 채팅/로그에 붙여넣지 마세요. |
| **4** | **Start the tunnel** | `Connect` 선택. 화면의 연결 상태가 정상인지 확인합니다. 연결되지 않으면 다음 단계로 진행하지 말고 오류 확인. |
| **5** | **Add it in ChatGPT** | ChatGPT 웹에서 `Settings → Apps → Advanced settings`의 Developer mode 및 사용자에게 허용된 Custom App 기능 확인. COS의 **connector card에 표시된 이름·설명·MCP 주소를 그대로** 사용해 앱을 추가합니다. 화면 안내의 인증 옵션은 `No authentication`이며, 이 경우 주소 자체가 비밀이므로 외부에 공유하지 마세요. 권한 승인은 신뢰 수준에 맞게 선택합니다. |
| **6** | **Add the Chrome extension** | `chrome://extensions`에서 **Developer mode** → **Load unpacked**. COS 화면의 `Open extension folder` 버튼이 열어주는 **안정된 실제 확장 폴더**를 선택합니다. 연결 상태 및 Companion **2.0.82**를 확인합니다. 별도 pairing code를 입력하는 절차는 없습니다. |

4. **읽기 전용 최종 확인:** 앱과 ChatGPT 앱이 연결돼 보이는지, Companion이 현재 ChatGPT 채팅의 귀속을 확인하는지 검증합니다. `Unattributed`가 뜨면 명령 실행/쓰기 작업을 반복하지 말고 문제를 기록합니다.
5. **선택 기능은 나중에:** `Setup → Advanced → Method`의 기본값은 `OpenAI Secure MCP Tunnel (recommended)`입니다. `Cloudflare quick tunnel` 또는 `Local only`로 변경할 수 있으나 **Cloudflare 계정·개인 도메인·Named Tunnel은 기본 필수 조건이 아닙니다**. 고정 호스트명이 필요한 사람만 별도의 승인된 Named Tunnel 절차를 사용합니다.

### 신규 사용자 확인 체크리스트

- [ ] 승인된 다운로드 및 SHA-256 확인
- [ ] 공유할 폴더만 선택하고 불필요한 권한 미허용
- [ ] ChatGPT와 OpenAI Tunnel Workspace 일치
- [ ] Restricted Tunnel API 키를 앱에만 등록
- [ ] `Connect` 상태 확인
- [ ] ChatGPT 앱에서 정확한 connector card 정보로 연결
- [ ] Chrome Companion 확장 연결 확인
- [ ] 쓰기/명령 이전에 읽기 전용 요청의 채팅 소유권 확인

## 자주 묻는 질문

**Q. 베타는 따로 설치하는 두 번째 COS인가요?** 아닙니다. 기존 COS 업데이트로 설계했습니다. 예전 P59의 별도 베타 AppData/포트 방식은 폐기했습니다.

**Q. 기존 사용자도 OpenAI Tunnel이나 Chrome 확장을 새로 등록하나요?** 정상 업데이트라면 아닙니다. 이전 설정이 나타나지 않으면 임의 재설정보다 먼저 업그레이드 실패 여부를 점검해야 합니다.

**Q. Cloudflare 계정/도메인이 있어야 하나요?** 아닙니다. 기본 Setup은 OpenAI Secure MCP Tunnel입니다. Named Tunnel은 선택 기능입니다.

**Q. 프로그램을 껐다 켜면 Job이 초기화되나요?** 보존돼야 하지만 이 후보는 운영 미확인 2,048건의 실제 업데이트·롤백이 검증되지 않았습니다. 따라서 현 설치 파일을 실행하지 마세요.

문제 해결: [TROUBLESHOOTING.md](TROUBLESHOOTING.md). 변경 내역: [RELEASE_NOTES.md](RELEASE_NOTES.md).
