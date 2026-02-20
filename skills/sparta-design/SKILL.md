---
name: sparta-design
description: SPARTA 브랜드 가이드라인 준수 디자인 시안 + HTML/CSS 코드 생성
argument-hint: "[디자인 요청 내용]"
disable-model-invocation: true
---

# /sparta-design

SPARTA 브랜드 디자인 제작을 시작한다. 아래 스킬과 에이전트를 참조하여 워크플로우를 진행한다.

## 참조 파일

반드시 아래 파일을 순서대로 로드한다:

1. `skills/sparta-brand-components/SKILL.md` — 디자인 토큰, 로고, 컬러, 타이포, 그래픽, CSS 변수
2. `skills/sparta-design-guideline/SKILL.md` — 콘텐츠 유형별 적용, 포맷별 레이아웃, DO/DON'T, HTML/CSS 규칙
3. `skills/sparta-review-checklist/SKILL.md` — 셀프 검수용 50개 체크리스트 → 신호등 등급
4. `agents/sparta-design-creator.md` — 제작 워크플로우 전체 지침

## 워크플로우

`agents/sparta-design-creator.md`의 5단계 워크플로우를 그대로 따른다:

1. **요청 분석** — 사용자 입력 `$ARGUMENTS`에서 브랜드, 콘텐츠 타입, 포맷, 핵심 메시지, CTA를 추출한다. 누락 정보가 있으면 질문한다.
2. **텍스트 시안** — 의사결정 플로우차트(8단계)에 따라 컬러 조합, 레이아웃, 타이포 위계를 결정하고 텍스트 시안을 제시한다.
3. **사용자 확인** — 시안 승인을 받을 때까지 수정-재제시를 반복한다. 승인 전 코드 생성 금지.
4. **HTML/CSS 생성** — 단일 `.html` 파일, CSS 변수 전용, Pretendard CDN, 레이어 주석, placeholder 이미지 포함.
5. **셀프 검수** — CRITICAL(21항목) → HIGH(24항목) 순서로 전체 50항목 확인. FAIL 시 수정 후 재확인. 예상 신호등 등급 보고.

## 사용 예시

```
/sparta-design 내일배움캠프 신규 과정 런칭 프로모션 배너
/sparta-design 스파르타클럽 AI 과정 할인 이벤트 스토리 광고
/sparta-design Team Sparta 기업 브랜딩 메시지 피드 이미지
```
