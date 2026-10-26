# Nexora v2.3.0-beta.6 — GitHub Release 준비 명세

**현재 상태: QA / NO-GO — 공개 게시 금지.** 이 문서는 릴리스 업로드 준비용이며 배포 승인이 아닙니다. `main` 브랜치와 기존 안정판 릴리스는 변경하지 않습니다.

## Release에 설정할 값 (승인 이후)

| 필드 | 값 |
|---|---|
| Repository | `seunghwan1727-art/Nexora` |
| Tag | `v2.3.0-beta.6` |
| Release title | `Nexora 2.3.0-beta.6 (r52.4-P70) — Windows Beta` |
| Target | 검토 완료된 `beta/r524-p70-qa-20261026` 또는 승인된 병합 커밋 |
| Type | **Pre-release** |
| 초기 상태 | **Draft** (검증 완료 전 Publish 금지) |
| 기존 안정판 | 유지. 이 버전을 Latest/Stable로 지정하지 않음 |

업데이트 코드가 이 버전을 인식하려면 게시된 릴리스에서 다음을 만족해야 합니다.
`tag_name = v2.3.0-beta.6`, `prerelease = true`, `draft = false`,
`Chat-On-Steroids-Setup-x64.exe` 및 `SHA256SUMS.txt` Asset 존재.
**현재는 이 조건을 만족하는 공개 릴리스를 만들지 않습니다.**

## 검증된 PUBLIC 후보 설치 Asset

| 파일명 | 크기(바이트) | SHA-256 |
|---|---:|---|
| `Chat-On-Steroids-Setup-x64.exe` | `150297715` | `1D0623F9E3C76816E2EDD75268BF2BA84FBAE1807A3F4E799C0BC37A30298D50` |
| `Chat-On-Steroids-Setup-x64.exe.blockmap` | 배포 전 검증 | `CF203F108E7D354B858B49E8517E5F7FBDA21BBA0A45D0594C01A39EC3323C3A` |
| `SHA256SUMS.txt` | 두 파일의 정확한 체크섬 | GitHub에 업로드한 파일과 동일해야 함 |

내부 검증 ZIP `Nexora_v2.3.0-beta.6_PUBLIC_GUIDED_QA_NO_GO.zip`의 SHA-256:
`CC824A2E6004CDC373E16DE63245D3F52DB4381B5A92A1F5AF01CF5743B49E4D`.
이 ZIP에는 **NO-GO 안내와 릴리스 게이트**가 포함되어 있으므로 그대로 실사용자에게 공개하지 않습니다. 승인 후 설치 설명서/게이트를 재검증한 사용자용 ZIP으로 교체합니다.

**개인 무제한판의 ZIP, 설치 EXE, 서명 라이선스, API 키, Tunnel credentials, 사용자 데이터, Terminal Job 출력은 GitHub에 올리지 않습니다.**

## 설치 설명서 공개 순서

1. [README_START_HERE.md](README_START_HERE.md) — 첫 번째
2. [SETUP.md](SETUP.md) — 기존 사용자/신규 사용자 구분 및 실제 6단계 Setup
3. [TROUBLESHOOTING.md](TROUBLESHOOTING.md)
4. [RELEASE_NOTES.md](RELEASE_NOTES.md)
5. [SHA256SUMS.txt](SHA256SUMS.txt), [RELEASE_GATE.json](RELEASE_GATE.json)

## 출시 전 확인 사항

- [x] GitHub 연결 권한 확인 및 QA 브랜치 커밋 성공
- [x] 공개판 NSIS 설치 EXE, ASAR, Companion 2.0.82 및 SHA-256 확인
- [x] 내부 합성 업데이트/롤백·Cold/Hot Job 복원 검증
- [x] 개인 라이선스와 공개 설치 파일 분리 확인
- [x] 사용자 문서 및 설치 순서 준비
- [ ] 다양한 기존 포터블 사용자의 무손실 업데이트·롤백 검증
- [ ] 기존 Chrome Companion·Tunnel·ChatGPT 채팅 소유권 E2E 검증
- [ ] 베타 릴리스의 미검증 사항과 서명되지 않은 설치 파일 위험 고지 확정
- [ ] 최종 공개용 문서에서 NO-GO 해제 근거 및 정확한 해시 재검증
- [ ] 공개 승인 후 **Draft → Pre-release Publish** 실행
- [ ] 게시 직후 GitHub API 자산명, 다운로드 및 SHA-256 재검증

## Release 본문 초안

> **Nexora r52.4 / 2.3.0-beta.6 — Windows Beta**
>
> 기존 Chat On Steroids / Nexora 설치와 이어지는 베타 업데이트입니다.
> 기존 `%APPDATA%\\chat-on-steroids`, 포트 8765 및 Companion 2.0.82를 유지하도록 설계했습니다.
>
> 기존 사용자: `README_START_HERE.md` → `SETUP.md`의 기존 사용자 항목.
> 신규 사용자: 최초 설치 후 Setup 6단계 진행.
>
> Known limitations: 일부 ChatGPT 요청 소유권(`Unattributed`), Chrome Compact/Resume 및
> 기존 포터블 설치의 자동 업그레이드/복원 경로에 대한 실환경 검증이 필요합니다.
> Windows 설치 프로그램은 코드 서명되지 않았습니다.
>
> 현재 내부 QA 단계입니다. **Release가 승인되기 전에는 다운로드 및 설치하지 마세요.**

저장소의 기존 `main` README와 안정판 링크는 변경하지 않습니다.
