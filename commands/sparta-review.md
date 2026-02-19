---
description: SPARTA 브랜드 가이드라인 기준 디자인 검수 (PASS/FAIL 판정 + 수정 제안)
---

# /sparta-review

SPARTA 브랜드 디자인 검수를 시작한다. 아래 스킬과 에이전트를 참조하여 워크플로우를 진행한다.

## 참조 파일

반드시 아래 파일을 순서대로 로드한다:

1. `skills/sparta-brand-components/SKILL.md` — 디자인 토큰, 로고, 컬러, 타이포, 그래픽 규격
2. `skills/sparta-review-checklist.md` — 32개 체크리스트, 심각도, 판정 기준, 리포트 형식
3. `agents/sparta-design-reviewer.md` — 검수 워크플로우 전체 지침

## 워크플로우

`agents/sparta-design-reviewer.md`의 5단계 워크플로우를 그대로 따른다:

1. **대상 식별** — `$ARGUMENTS`로 전달된 파일(이미지 또는 HTML)을 읽고, 브랜드/콘텐츠 타입/포맷/매체를 식별한다.
2. **CRITICAL 검수** — 로고 7항목(LOGO-01~07) + 컬러 5항목(COLOR-01~05) 전수 검사.
3. **HIGH 검수** — 타이포 6항목(TYPO-01~06) + 그래픽 9항목(GFX-01~09) 전수 검사.
4. **MEDIUM 검수** — 레이아웃 5항목(LAYOUT-01~05) 검사.
5. **판정 및 리포트** — PASS/조건부 PASS/FAIL 판정 후 검수 리포트를 출력한다.

## 판정 기준

| 판정 | 조건 |
|------|------|
| PASS | CRITICAL 0건, HIGH 0건 |
| 조건부 PASS | CRITICAL 0건, HIGH 1~2건 |
| FAIL | CRITICAL 1건 이상 또는 HIGH 3건 이상 |

## 사용 예시

```
/sparta-review ./designs/banner-v2.png
/sparta-review ./output/promo-banner.html
/sparta-review ~/Desktop/sparta-feed-image.png
```
