# JHJ AI Usage Monitor — 배포판

**JHJ AI 통합 사용량 모니터**의 설치 파일만 올리는 저장소입니다. Claude Code · Codex 의 세션·주간 한도와 일별 비용을 트레이 팝업으로 보여 주는 Windows 앱입니다. 소스는 비공개 저장소에 있습니다.

## 설치

[Releases](https://github.com/HyungJIn-kr-97/JHJ_AI_USAGE_RELEASE/releases/latest) 에서 둘 중 하나를 받아 실행합니다. .NET 설치는 필요 없습니다.

| 파일 | 종류 |
|---|---|
| `JHJ_AI-Usage-Monitor_Setup.exe` | 웹 설치 관리자 — 릴리스 목록에서 버전을 골라 받아 설치합니다(기본은 최신) |
| `JHJ_AI-Usage-Monitor_<버전>_win-x64.exe` | 오프라인 설치 파일 — 그 버전 하나로 설치합니다 |

최신 설치 파일 주소(늘 같은 주소)입니다.

```
https://github.com/HyungJIn-kr-97/JHJ_AI_USAGE_RELEASE/releases/latest/download/JHJ_AI-Usage-Monitor_Setup.exe
```

- 처음 실행할 때 SmartScreen 창이 뜨면 「추가 정보」 → 「실행」을 누릅니다. 코드 서명이 없어서 뜨는 창입니다.
- 설치본은 이 저장소의 최신 릴리스를 보고 스스로 업데이트합니다.
- 파일마다 `.sha256` 이 함께 올라가 있습니다.

## 수집하는 사용 정보

설치 관리자에서 **사용 정보 수집 동의**에 체크해야 「설치」가 눌립니다. 모은 정보는 **어디로도 자동 전송되지 않습니다** — 설정 › 일반 「진단 정보」의 「복사」·「파일로 저장」으로 사용자가 직접 꺼내 [이슈](https://github.com/HyungJIn-kr-97/JHJ_AI_USAGE_RELEASE/issues/new)에 붙입니다.

| 모으는 것 | 쓰임 |
|---|---|
| 앱 버전 · Windows 버전 · .NET · 언어 | 장비마다 다른 동작 재현 |
| 설정값(갱신 주기 · 계정 명칭·유형·요금 · 프로그램 연동표 · 등급 경계) | 설정 조합에 따른 차이 |
| Claude 자리마다 — 로그인 계정 UUID(앞 8자) · 자격 파일 유무 · 플랜·등급·만료 · 로그 파일 수·용량·기간 | 「계정 연동이 안 잡힌다」 「사용량이 비었다」 원인 |
| 프로그램 라우팅 표 · 세션 메타 수 · 에이전트 모드 폴더 | 「어느 프로그램이 어느 계정으로 세졌나」 근거 |
| 이력 파일별 건수·기간·비용·토큰 합계 | 사용량 차트·활용도 계산 검증 |
| 마지막 갱신 상태(계정별 신뢰도·출처·상태 문구·한도·비용) · 이벤트 로그 최근 200줄 | 오류 추적 |

**가리는 것** — 메일은 첫 글자+도메인, UUID 는 앞 8자, 경로의 사용자 폴더는 `%USERPROFILE%`. **넣지 않는 것** — 토큰 · 대화 내용 · 프로젝트 경로.

## 라이선스

MIT 입니다([LICENSE](LICENSE)). [fmdz387/costats](https://github.com/fmdz387/costats) (MIT) 에서 출발했습니다.
