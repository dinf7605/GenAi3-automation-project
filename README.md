# 노코드 자동화 워크플로우 구축

Make · Zapier 등 노코드 자동화 도구를 사용해 Trigger–Action–조건 분기 기반의 워크플로우를 직접 설계·구현한 과제 저장소입니다.

## 목표

- Trigger(시작 이벤트)와 Action(처리 동작)의 작동 원리 이해
- 조건 분기(Filter/Router)의 역할 이해
- 서로 다른 자동화 도구의 특징 비교
- 업무에 적합한 도구를 선정하고 근거 설명

## 구성

| 프로젝트 | 내용 | 사용 도구 |
|----------|------|-----------|
| [프로젝트 1](./project1-tool-comparison) | 동일 워크플로우를 2개 도구로 구현·비교 | Make, Zapier |
| [프로젝트 2](./project2-weather) | 자유 주제 자동화 설계·구현 (날씨 알림) | Make |

## 공통 워크플로우 요구사항

- Trigger 1개 이상
- Action 2개 이상
- 조건 분기(Filter/Router) 1개 이상
- 각 분기 경로가 실제로 1회 이상 실행된 결과 확인

## 보안 유의사항

모든 스크린샷 및 문서에서 API Key, 토큰, Webhook URL, 비밀번호, 계정 이메일 등 민감정보는 마스킹(`***`) 처리했습니다.

## 이미지 폴더 (`images/`)

모든 캡처 이미지는 최상위 `images/` 폴더에서 통합 관리합니다. 각 프로젝트 README는 이 폴더를 참조합니다.

**프로젝트 1**
- `make-scenario.png`, `make-discord.png`, `make-log-sheet.png`
- `zapier-zap.png`, `zapier-discord.png`, `zapier-filtered.png`, `zapier-trial.png`

**프로젝트 2**
- `weather-scenario.png`, `weather-discord-rain.png`, `weather-discord-clear.png`, `weather-datastore.png`, `weather-schedule.png`
