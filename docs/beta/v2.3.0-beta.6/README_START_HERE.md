# Nexora Beta 2.3.0-beta.6 — 먼저 읽으세요

**배포 상태: NO-GO (내부 검증용). 현재 이 설치 파일을 실행하거나 타인에게 배포하지 마세요.** 실제 COS 운영 Job 2,048건의 무손실 업그레이드와 Chrome/ChatGPT/Tunnel 실환경 검증이 끝나지 않았습니다.

- 에디션: **PUBLIC (free beta policy)** — No personal license.key is included. Free-use policy through December 31, 2027 KST; ChatGPT and external API fees are separate.
- 프로그램: **Chat On Steroids / Nexora r52.4-P70**, Companion **2.0.82**
- 파일: `Chat-On-Steroids-Setup-x64.exe` (Windows NSIS 설치 후보)
- 기본 정책: 베타는 별도 앱/데모가 아니라 **기존 COS의 버전 업데이트**입니다. 같은 사용자 데이터 `%APPDATA%\chat-on-steroids`, 기존 포트 `8765`, 기존 Chrome Companion 및 OpenAI Tunnel 설정을 유지하도록 설계했습니다.
- Windows 코드 서명: **아직 없음(NotSigned)**. 설치 시 보안 경고를 우회하여 실행하지 마세요.

## 정확한 문서 읽기 및 설치 순서

1. **이 문서 `README_START_HERE.md`** — 현재 배포 승인 여부와 에디션 확인
2. **`SETUP.md`** — *기존 사용자* 또는 *신규 사용자* 중 본인 경로 하나만 선택해 순서대로 진행
3. **`TROUBLESHOOTING.md`** — 오류 발생 시에만 참고. 자동 초기화/재설치를 요구하지 않음
4. **`RELEASE_NOTES.md`** — 이번 버전의 변경 사항 및 미검증 기능 확인
5. **`RELEASE_GATE.json`**에서 `release`가 `GO`로 승인된 **새 배포본**인지 확인. **현재 패키지는 `NO-GO`이므로 여기서 중단**
6. 승인된 정식 배포본에 한해서만 `SHA256SUMS.txt`와 실제 설치 파일 SHA-256 확인 후 `Chat-On-Steroids-Setup-x64.exe` 실행

현재 설치 EXE SHA-256 (대조용, 실행 승인이 아님):

```text
1D0623F9E3C76816E2EDD75268BF2BA84FBAE1807A3F4E799C0BC37A30298D50
```

Windows PowerShell 확인 명령 (압축을 해제한 이 폴더에서):

```powershell
Get-FileHash -LiteralPath ".\Chat-On-Steroids-Setup-x64.exe" -Algorithm SHA256
```

해시가 위 값 또는 `SHA256SUMS.txt`와 다르면 **설치를 중단**하세요.

## 어느 설치 경로를 따라야 하나요?

| 사용자 구분 | 진행할 내용 | 하지 말아야 할 일 |
|---|---|---|
| **기존 COS 사용자** | `SETUP.md`의 **A. 기존 사용자: 버전 업데이트** | Setup Wizard 재실행, API 키/터널 새로 발급, 새 Chrome 프로필/확장 중복 등록 |
| **처음 설치하는 사용자** | `SETUP.md`의 **B. 신규 사용자: 최초 설치와 6단계 Setup** | 이전 사용자 데이터 복사, 불필요한 Cloudflare Named Tunnel 강제 설정 |

기존 COS의 설정·세션·프로젝트·Job·공유 폴더·라이선스는 유지되어야 하며, Chrome 전체 종료/ChatGPT 탭 강제 새로고침도 업데이트 절차가 아닙니다. 이 안전 조건은 **아직 실제 기존 설치에서 검증되지 않았습니다**.

**공개 GitHub에는 개인 무제한판이나 `license.key`를 업로드하면 안 됩니다.** 개인 자격 증명·Tunnel credentials·작업 로그 원문은 지원 요청에 첨부하지 마세요.
