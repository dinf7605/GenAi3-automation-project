# 프로젝트 1 · 자동화 도구 비교 구현 (Make vs Zapier)

동일한 워크플로우를 **Make**와 **Zapier**로 각각 구현하고 비교 분석한 프로젝트입니다.
상세 비교 분석은 [REPORT.md](./REPORT.md)를 참고하세요.

## 워크플로우

고객 문의 자동 분류 및 알림

```
[Trigger]  Google Sheets - 새 행 추가 감지
      │
   [조건 분기]  문의유형 판별 (긴급 / 일반)
      │
      ├─ 긴급 → Discord 알림 → 로그 시트 기록
      └─ 일반 → Discord 알림 → 로그 시트 기록
```

- **Trigger**: Google Sheets 새 행 추가
- **조건 분기**: 문의유형 (긴급 / 일반)
- **Action 1**: Discord 알림
- **Action 2**: 로그 시트 기록

## 구현 결과

### Make (Router · 양방향 분기)

**워크플로우 구성 및 실행 로그**

![Make 워크플로우 구성](../images/make-scenario.png)

**실행 결과 - Discord 알림**

![Make Discord 결과](../images/make-discord.png)

**실행 결과 - 로그 시트**

![Make 로그 시트](../images/make-log-sheet.png)

### Zapier (Filter · 단방향 통과)

**워크플로우 구성**

![Zapier 워크플로우 구성](../images/zapier-zap.png)

**실행 결과 (긴급 통과) - Discord 알림**

![Zapier Discord 결과](../images/zapier-discord.png)

**실행 결과 (일반 중단) - Filter 중단 로그**

![Zapier Filter 중단](../images/zapier-filtered.png)

**요금제 (트라이얼 사용 근거)**

![Zapier 트라이얼](../images/zapier-trial.png)

## 요구사항 충족 체크

| 항목 | Make | Zapier |
|------|------|--------|
| Trigger 1개 이상 | ✅ | ✅ |
| Action 2개 이상 | ✅ (Discord + 로그) | ✅ (Discord + 로그) |
| 조건 분기 1개 이상 | ✅ (Router) | ✅ (Filter) |
| 각 경로 1회 이상 실행 | ✅ 긴급/일반 모두 실행 | ✅ 긴급 통과 + 일반 중단 |

## 이미지 파일 안내

최상위 `images/` 폴더에 아래 파일명으로 캡처를 넣어주세요:

- `make-scenario.png` — Make 시나리오 전체 구성 + 실행 로그
- `make-discord.png` — Make Discord 메시지(긴급/일반)
- `make-log-sheet.png` — Make 로그 시트 기록
- `zapier-zap.png` — Zapier 4단계 Zap 구성
- `zapier-discord.png` — Zapier Discord 긴급 메시지
- `zapier-filtered.png` — Zapier Filter 중단(`stopped your run`) 로그
- `zapier-trial.png` — Zapier `14 TRIAL DAYS LEFT` 배지

> ※ 모든 캡처에서 Webhook URL·봇 토큰·계정 이메일은 마스킹(`***`) 처리하세요.
