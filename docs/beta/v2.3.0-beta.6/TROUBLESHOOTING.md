# Nexora 문제 해결 및 안전한 복구 절차

버전: 2.3.0-beta.6 / r52.4-P70 · **현재 후보는 NO-GO: 설치하지 마세요.**

먼저 [README_START_HERE.md](README_START_HERE.md), [SETUP.md](SETUP.md)를 확인하세요. 기존 COS 업데이트는 데이터를 보존하는 것이 최우선입니다.

| 현상 | 우선 확인할 내용 | 하면 안 되는 조치 |
|---|---|---|
| 설치 파일 해시 불일치 | Windows PowerShell `Get-FileHash` 결과가 `SHA256SUMS.txt`와 같은지 확인 | 손상된 설치 EXE 실행 |
| Windows에서 '게시자를 확인할 수 없음' | 현재 QA 후보는 **코드 서명 미적용(NotSigned)**. 검증된 서명/릴리스가 나올 때까지 설치 보류 | 보안 경고를 무조건 무시 |
| 기존 COS에서 설정이나 폴더가 사라짐 | `%APPDATA%\chat-on-steroids`가 그대로인지, 잘못된 Windows 계정·프로필로 실행했는지 확인. 변경하기 전에 기록 | `config.json`/AppData 삭제, 새 Setup으로 덮어쓰기 |
| API 키 또는 Tunnel 오류 | 기존 연결 종류(OpenAI/Quick/Manual), Tunnel ID 존재 및 Workspace가 맞는지만 확인 | 키를 채팅에 공개하거나 무조건 재발급 |
| `Unattributed` / 다른 채팅 귀속 | 실제 채팅의 요청 ID 및 Companion 연결 상태를 확인하고 오류를 기록 | 쓰기 명령 재실행, 임의 `thread_bind`로 우회 |
| Chrome Companion이 연결되지 않음 | `chrome://extensions`와 기존 확장 ID/폴더 경로를 확인 | Chrome 전체 종료·재시작, ChatGPT 탭 강제 종료, 중복 확장 설치 |
| Compact/Resume 이후 다른 프로젝트에 채팅이 표시됨 | 프로젝트 ID 및 원래 채팅 화면을 보존하고 재현 로그만 기록 | 프로젝트 밖으로 옮기거나 대화를 임의 삭제 |
| Terminal Job 2,048건이 미확인 상태 | Job 수·소유권·출력 보관 상태를 *읽기 전용*으로 확인 | ACK·취소·재실행·자동 마이그레이션 강제 |
| 업데이트/롤백 도중 종료 | 설치 시도 중단, 기존 데이터와 이전 정상판을 보존. 승인된 롤백·백업 자료를 가진 담당자에게 문의 | 새 설치를 연속 실행하거나 임의 백업 파일 덮어쓰기 |
| Cloudflare 도메인 없음 | 기본 OpenAI Secure MCP Tunnel을 사용. Named Tunnel은 선택 | 필요 없는 계정·도메인을 신규 구매 |

## 안전한 문제 제보

오류가 발생하면 다음 **비밀정보가 아닌 내용만** 전달하세요: 앱 버전, 공개/개인 에디션, 발생 단계 번호, 오류 시간, 실패 화면의 비밀정보를 가린 설명, 읽기 전용 상태 및 파일 SHA-256. API 키, 개인 라이선스 원문, Tunnel credentials JSON, 사용자 폴더의 개인정보, 실제 Job 출력은 첨부하지 마세요.

**해결되지 않은 실환경 검증:** 운영 COS의 완전한 업그레이드·롤백, ChatGPT A/B 요청 소유권, 프로젝트별 Compact/Resume, 기존 Tunnel 연속성. 이 네 가지가 검증되기 전에 `RELEASE_GATE.json`을 임의로 `GO`로 바꾸거나 공개 배포하지 마세요.
