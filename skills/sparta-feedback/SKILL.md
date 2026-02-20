---
name: sparta-feedback
description: SPARTA 브랜드 디자인 피드백 제출 (검수/제작 결과에 대한 의견 기록)
argument-hint: "[피드백 내용]"
disable-model-invocation: true
---

# /sparta-feedback

SPARTA 브랜드 디자인에 대한 피드백을 기록한다. 아래 스킬을 참조하여 피드백을 수집·저장한다.

## 참조 파일

반드시 아래 파일을 로드한다:

1. `skills/sparta-feedback-loop/SKILL.md` — 로그 스키마, 수집 규칙, ID 채번
2. `skills/sparta-review-checklist/SKILL.md` — 위반 항목 ID 참조 (violations 필드 작성 시)

## 워크플로우

1. **입력 분석** — `$ARGUMENTS`에서 대상(`asset`)과 코멘트(`suggestion`)를 추출한다.
2. **분류** — 피드백 유형을 판별한다:
   - 특정 제작물에 대한 의견 → `type: "design"`
   - 가이드라인/체크리스트 자체에 대한 의견 → `type: "general"`
   - 검수 결과에 대한 보충 → `type: "review"`
3. **작성자 확인** — `author`가 누락되면 사용자에게 질문한다.
4. **위반 항목 매핑** — 피드백 내용이 특정 체크리스트 항목과 관련되면 `violations`에 항목 ID를 기록한다.
5. **태그 부여** — 해당되는 경우 `AMBIGUOUS` / `NEW` / 자유 태그를 추가한다.
6. **ID 채번** — `feedback/log.jsonl`에서 당일 마지막 ID를 확인하고 +1한다.
7. **로그 저장** — 새 엔트리를 `feedback/log.jsonl`에 append한다.
8. **확인 출력** — 등록된 피드백 요약을 사용자에게 보여준다.

## 확인 출력 형식

```
피드백이 등록되었습니다.

- ID: FB-2026MMDD-NNN
- 유형: design / general / review
- 대상: [asset]
- 관련 항목: [violations] (있는 경우)
- 코멘트: [suggestion 요약]
```

## 사용 예시

```
/sparta-feedback 내배캠 배너에서 로고 클리어 스페이스가 너무 좁아 보입니다
/sparta-feedback COLOR-02 기준이 모호합니다 — 그레이스케일과 유채색 경계가 불명확
/sparta-feedback ./designs/event-banner.html CTA 버튼 위치가 Safe Area 밖에 있어요
```
