# Nexora Beta 2.3.0-beta.6 — PUBLIC (free beta policy) 릴리스 노트

**상태: QA 후보 / NO-GO — 아직 설치 및 공개 배포 금지.**

제품: Chat On Steroids, 리비전 **r52.4-P70**, Companion **2.0.82**, 기존 제품 ID **com.chatonsteroids.app**.

## 변경 사항

- 별도 베타 앱/데모가 아닌 **기존 COS에 이어지는 버전 업데이트** 구조 반영. 사용자 데이터 `%APPDATA%\chat-on-steroids`, Bridge 포트 **8765** 유지하도록 구성.
- P53~P56 Cold/Hot Job 저장·소유권·Compact/Resume·Tunnel 관련 코드 통합. 실제 모든 기능의 완전한 실환경 E2E를 의미하지는 않습니다.
- Windows 출력 확정 단계 `EPERM` 대응과 Cold/Hot Job 보관 증빙 수정.
- Nexora GitHub Beta 업데이트 채널과 버전 비교 로직 포함. 안정판 사용자를 자동으로 Beta로 이전하지 않도록 설계.
- 전체 Windows NSIS 후보 제작. 기존 설치 ID 및 per-user 설치 방식 유지. Windows 코드 서명은 **없음(NotSigned)**.
- **에디션: PUBLIC (free beta policy). No personal license.key is included. Free-use policy through December 31, 2027 KST; ChatGPT and external API fees are separate.**

## 통과한 QA

- 개인/공개 Windows NSIS 설치 EXE 생성, 원본 P70 EXE·ASAR 및 Companion 버전 확인
- 합성 Job 2,105개 중 미확인 Cold 2,048개 보존, 신규 Hot 저장, 별도 Windows 프로세스에서 소유권·출력 재로딩 및 중복 거부
- **격리된 가상 설치본**의 업데이트·롤백과 설정·라이선스·Job SHA 불변
- 배포 후보 ZIP 내부 모든 파일의 SHA 검증 및 공개/개인 라이선스 분리

## 출시 전 차단 항목

운영 2,048개 미확인 Job의 실제 무손실 Cutover/롤백, ChatGPT A/B 실요청 귀속, Chrome 프로젝트별 Compact/Resume, 기존 Tunnel의 업데이트 전후 연속성, 설치 프로그램 서명, 최종 독립 검토 승인이 남았습니다. 따라서 **현재 파일을 설치하거나 외부 배포하지 마세요**.

사용자용 순서: [README_START_HERE.md](README_START_HERE.md) → [SETUP.md](SETUP.md) → 문제 발생 시 [TROUBLESHOOTING.md](TROUBLESHOOTING.md).

공개 저장소: https://github.com/seunghwan1727-art/Nexora · 원저작물 MIT: https://github.com/totec448-spec/chat-on-steroids
