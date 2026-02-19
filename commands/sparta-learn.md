---
description: SPARTA 브랜드 피드백 분석 및 가이드라인/체크리스트 개선 제안
---

# /sparta-learn

축적된 피드백을 분석하여 가이드라인과 체크리스트의 개선안을 제시한다.

## 참조 파일

반드시 아래 파일을 순서대로 로드한다:

1. `skills/sparta-feedback-loop.md` — 분석 워크플로우, 메트릭 정의, 개선안 유형
2. `skills/sparta-review-checklist.md` — 현재 체크리스트 (개선 대상)
3. `skills/sparta-design-guideline.md` — 현재 가이드라인 (개선 대상)

## 워크플로우

`skills/sparta-feedback-loop.md` 3절의 분석 워크플로우를 따른다:

1. **로드** — `feedback/log.jsonl` 전체를 읽는다. 파일이 비어 있거나 없으면 "분석할 피드백이 없습니다"를 출력하고 종료한다.
2. **분류** — type별, 날짜별, violation별로 그룹핑한다.
3. **메트릭 산출** — 4가지 핵심 메트릭을 계산한다:
   - 위반 빈도 TOP 5
   - FAIL 비율 추이 (월별)
   - 모호 영역 (PASS/FAIL 혼재율 > 30%)
   - 미해결 피드백 수
4. **패턴 식별** — 반복 위반 패턴, 자주 발생하는 질문, 모호 영역을 도출한다.
5. **개선안 생성** — 5가지 유형(항목 추가/강조/명확화/DO-DON'T 보강/규격 수정)에서 해당하는 개선안을 초안으로 작성한다.
6. **요약 갱신** — `feedback/SUMMARY.md`를 최신 분석 결과로 업데이트한다.

## 출력

`skills/sparta-feedback-loop.md` 3.4절의 분석 결과 형식을 그대로 사용한다.

개선 제안은 초안이며, 팀 리더가 검토 후 승인/거절을 결정한다. 승인된 개선안은 해당 스킬 파일에 직접 반영한다.

## 사용 예시

```
/sparta-learn
/sparta-learn 2026년 2월 피드백만 분석해줘
/sparta-learn 미해결 피드백만 보여줘
```
