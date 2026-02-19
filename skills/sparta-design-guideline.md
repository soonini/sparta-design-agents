# SPARTA 브랜드 통합 디자인 가이드라인

> 제작 에이전트가 디자인을 생성할 때 참조하는 실무 적용 규칙.
> 컴포넌트 라이브러리(`sparta-brand-components/SKILL.md`)의 토큰과 규칙을 **어떻게** 조합하는지를 정의한다.

## 사용 시점

- 제작 에이전트(`agents/sparta-design-creator.md`)가 시안을 구성할 때
- HTML/CSS 코드를 생성할 때 구조와 규칙 참조
- 콘텐츠 타입·포맷·브랜드에 따른 분기 판단이 필요할 때

---

## 1. 콘텐츠 유형별 적용

### 1.1 콘텐츠 타입 분류

요청을 받으면 **가장 먼저** 콘텐츠 타입을 판별한다.

| 타입 | 코드 | 목적 | 키워드 |
|------|------|------|--------|
| Content-Driven | `TYPE-A` | 정보 제공, 이해 중심 | #명확한 #신뢰중심 #정보구조화 |
| Action-Driven | `TYPE-B` | 행동 유도, 전환 촉진 | #간결 #시각강조 #클릭유도형 |
| Message-Driven | `TYPE-C` | 브랜드 핵심 메시지 강조 | #Bold #감정자극 #인지우선 |

**판별 기준:**
- 과정 소개, 커리큘럼, 수강 후기, 비교표 → `TYPE-A`
- 할인, 모집 마감, 수강신청 CTA, 프로모션 → `TYPE-B`
- 브랜드 슬로건, 캠페인, 비전 선언 → `TYPE-C`

### 1.2 텍스트 하이어라키

각 타입은 사용하는 텍스트 요소와 배치 순서가 다르다.

#### TYPE-A: Content-Driven

```
Tag (S size)        ← 카테고리 라벨
SubTitle            ← 보조 설명
Title (Head Copy)   ← 핵심 정보 (1-2줄)
Body                ← 상세 설명
CTA Button          ← 행동 유도
```

- **텍스트 비중**: 높음 (Body 텍스트 포함)
- **서체**: Pretendard 전용 (Marketing A/B)
- **Head Weight**: ExtraBold (800)
- **이미지 처리**: 텍스트 보조 역할, 우측 또는 하단 배치

#### TYPE-B: Action-Driven

```
Title (Head Copy)   ← 핵심 메시지 (최대 2줄, 대형)
SubTitle            ← 보조 정보 또는 L-size 태그
CTA Button          ← 즉시 행동 유도 (강조)
```

- **텍스트 비중**: 낮음 (간결한 카피)
- **서체**: Pretendard 전용 (Marketing A/B)
- **Head Weight**: ExtraBold (800)
- **이미지 처리**: 시각 강조 역할, 넓은 Graphic Area 할당
- **CTA**: 가장 눈에 띄게 — Sparta Red 배경 + 흰 텍스트

#### TYPE-C: Message-Driven

```
SubTitle            ← 맥락 제공
Title (Head Copy)   ← 브랜드 메시지 (최대형, 화면 중앙)
Caption             ← 부가 정보
```

- **텍스트 비중**: 중간 (큰 텍스트, 적은 줄 수)
- **서체**: Sandol Dol(제목) + Pretendard(나머지) (Brand Message A/B)
- **Head Weight**: Sandol Dol Bold (700)
- **이미지 처리**: 텍스트가 주인공, 이미지는 배경 또는 최소화
- **CTA**: 없음 (인지·감정 목적)

### 1.3 콘텐츠 타입별 서체 매핑

| 콘텐츠 타입 | Title 서체 | SubTitle·Body 서체 | 비고 |
|-------------|-----------|-------------------|------|
| TYPE-A | Pretendard ExtraBold | Pretendard Medium/Regular | Marketing A/B |
| TYPE-B | Pretendard ExtraBold | Pretendard Medium | Marketing A/B |
| TYPE-C | Sandol Dol Bold | Pretendard Medium/Regular | Brand Message A/B |

---

## 2. 레이아웃 포맷별 적용

### 2.1 포맷 선택 기준

| 포맷 | 비율 | 최적 매체 | 적합한 콘텐츠 타입 |
|------|------|-----------|-------------------|
| Mini Banner | 3:2 | 웹사이트 (메인/서브) | TYPE-A, TYPE-B |
| Flex Banner | 가로 확장형 | 웹사이트 (상단 띠) | TYPE-B, TYPE-C |
| Story-AD | 1:2 | 인스타그램 스토리 | TYPE-B |
| Feed/Pop-Up | 4:5 | 인스타그램 피드, 팝업 | TYPE-A, TYPE-C |

### 2.2 Mini Banner (3:2)

```
┌──────────────────────────────────┐
│ [로고: 좌상단]                    │
│                                  │
│ [TAG]                            │
│ Sub Copy                   ┌────┐│
│ Head Copy (1-2줄)          │ 그 ││
│ Body (TYPE-A만)            │ 래 ││
│                            │ 픽 ││
│ [CTA BUTTON]               └────┘│
└──────────────────────────────────┘
```

**규칙:**
- 로고: Standard 배치 (좌상단), Primary Type
- 텍스트: 좌측 Text Area (전체 폭의 약 60%)
- 그래픽: 우측 Graphic Area (전체 폭의 약 40%)
- CTA: 좌하단, Sparta Red 배경 + 흰 텍스트
- Safe Area: 상하좌우 마진 확보

### 2.3 Flex Banner (가로 확장형)

```
┌──────────────────────────────────────────────────────┐
│ [로고: 좌상단]     Head Copy (최대 2줄)    [그래픽]    │
│                    Sub Copy                          │
└──────────────────────────────────────────────────────┘
```

**규칙:**
- 로고: Standard 배치 (좌상단), Primary Type
- Head Copy: 최대 2줄 제한 (초과 시 폰트 크기 축소보다 카피 수정)
- 그래픽: 우측, Extended Area까지 확장 가능
- 높이가 낮으므로 Body 텍스트 미사용
- TYPE-C일 경우 그래픽 생략하고 텍스트 중앙 배치 가능

### 2.4 Story-AD (1:2)

```
┌──────────────┐
│ [로고: 상단]  │
│              │
│ [TAG]        │
│              │
│ Head Copy    │
│ (대형, 중앙) │
│              │
│ [그래픽]      │
│              │
│ [CTA]        │
│              │
│ [스와이프↑]   │
└──────────────┘
```

**규칙:**
- 세로 비율이 크므로 요소 간 충분한 여백 확보
- 로고: 상단 중앙 또는 좌상단
- CTA: 하단, "스와이프" 인터랙션 고려
- 하단 20% 영역에 핵심 정보 배치 금지 (인스타그램 UI 영역)

### 2.5 Feed/Pop-Up (4:5)

```
┌──────────────────┐
│ [로고: 좌상단]    │
│                  │
│ SubTitle         │
│ Head Copy        │
│ (대형)           │
│                  │
│ [그래픽/이미지]   │
│                  │
│ Caption          │
└──────────────────┘
```

**규칙:**
- TYPE-A: 정보 밀도 높게, 태그 + 본문 포함 가능
- TYPE-C: 텍스트 중심, 그래픽 최소화
- 로고: Standard 배치 (좌상단)
- 하단 캡션 영역 활용

### 2.6 공통 레이아웃 규칙

- **로고 위치**: Standard(좌상단/우상단) 기본. Extended(중앙/하단)는 TYPE-C에서만 허용
- **Safe Area**: 모든 포맷에서 Margin 확보 필수. 주요 정보가 잘림 영역에 위치하면 안 됨
- **Text Area와 Graphic Area 분리**: 텍스트가 그래픽 위에 직접 겹치는 것은 Frame Type 사용 시에만 허용
- **4px 그리드**: 모든 간격은 스페이싱 토큰 기반 (`--space-*`)

---

## 3. 브랜드별 분기

### 3.1 4개 브랜드 개요

| 브랜드 | 대상 | 주요 서비스 | 톤 |
|--------|------|-----------|-----|
| Team Sparta | 기업 (모회사) | 전체 통괄 | 공식적, 신뢰 |
| Sparta Club | 개인 학습자 | 강의, 커뮤니티, 내일배움캠프 | 에너지, 성장 |
| Sparta Builders | 기업 파트너 | 기업 교육 솔루션 | 전문적, 파트너십 |
| Sparta 기업교육 | 기업 HR | 기업 교육 프로그램 | 신뢰, 성과 |

### 3.2 브랜드별 적용 차이

| 항목 | Team Sparta | Sparta Club | Sparta Builders | 기업교육 |
|------|------------|-------------|-----------------|---------|
| 로고 Primary 최소 높이 | 22px | 24px | 22px | 22px |
| 로고 Stacked 최소 높이 | 45px | 56px | 45px | 45px |
| 주요 콘텐츠 타입 | TYPE-C | TYPE-A, TYPE-B | TYPE-A | TYPE-A |
| 캐릭터(르탄이) 사용 | X | O (내배캠) | X | X |
| 카테고리 아이콘 사용 | 제한적 | O | 제한적 | 제한적 |
| 톤 & 무드 | 안정적, 공식 | 활기, 도전 | 전문적, 협력 | 신뢰, 효율 |

### 3.3 브랜드 혼용 금지

- 한 디자인에 **하나의 브랜드 로고만** 사용
- 예외: 파트너십 로고 (Ongoing `|` / One-Off `X` 구분자 사용)
- Team Sparta 로고는 그룹사 차원 콘텐츠에서만 사용
- Sparta Club ↔ Sparta Builders 교차 사용 금지

---

## 4. DO / DON'T

### 4.1 로고

| DO | DON'T |
|----|-------|
| 승인된 8가지 변형(4 브랜드 × 2 타입) 사용 | 로고 요소를 분리하거나 재배치 |
| T자 기준 클리어 스페이스 확보 | 로고 주변에 다른 요소를 밀착 배치 |
| 밝은 배경 → Sparta Red 로고 | 로고에 그림자, 아웃라인, 패턴 적용 |
| Sparta Red 배경 → 흰색 로고 | 로고를 회전하거나 비율 왜곡 |
| 공식 16가지 로고-배경 조합 사용 | 가독성 떨어지는 복잡한 배경 위 배치 |

### 4.2 컬러

| DO | DON'T |
|----|-------|
| 승인 팔레트(메인 3색 + 확장 15색 + Grayscale)에서 선택 | 미승인 색상(`#FF6600` 등) 사용 |
| 한 디자인에 최대 3색(Grayscale 제외) | 4색 이상 유채색 혼합 |
| Primary/Secondary/Extended Pairing 조합 준수 | 임의의 색상 조합 생성 |
| 텍스트-배경 간 충분한 명도 대비 | 유사 밝기의 텍스트-배경 조합 |
| 단색 배경 또는 톤온톤 패턴 | 그라디언트 (특별 승인 없는 한) |

### 4.3 타이포그래피

| DO | DON'T |
|----|-------|
| Pretendard 또는 Sandol Dol만 사용 | Arial, Noto Sans 등 미승인 서체 |
| 레벨별 지정 Weight 준수 (Head: 800, Title: 700 등) | Body에 ExtraBold, Head에 Regular |
| 레벨별 최소 Line Height 준수 | Head에 160% 행간, Body에 110% 행간 |
| Brand Message에만 Sandol Dol 사용 | Marketing 카피에 Sandol Dol 단독 사용 |
| 텍스트 위계를 시각적으로 명확히 구분 | 장평 변경, 과도한 자간, 텍스트 그림자 |

### 4.4 그래픽

| DO | DON'T |
|----|-------|
| Frame Type: 4-레이어 구조 유지 | 레이어 순서 뒤바꿈 |
| 프레임 최소 3면 노출 | 프레임 2면 이하만 노출 |
| 패턴 반복 최대 3-4회 + 톤온톤 | 패턴 6회 이상, 대비 강한 패턴 컬러 |
| 태그 비례 (마진 0.3X, 텍스트 0.45X) | 태그 내 텍스트가 경계에 붙음 |
| Category Icon: 단일 컬러 계열(R/P/B) | 한 아이콘에 여러 컬러 계열 혼합 |
| Illustration: Bevel 입체 + 단일 계열 | 과도한 Bevel, UI 아이콘처럼 기능적 사용 |

### 4.5 레이아웃

| DO | DON'T |
|----|-------|
| 지정 포맷 비율 준수 (3:2, Flex, 1:2, 4:5) | 임의 비율로 변형 |
| Safe Area 안에 핵심 정보 배치 | 로고나 CTA가 잘림 위험 영역에 위치 |
| 콘텐츠 타입별 요소 순서 준수 | Action-Driven에 Body 텍스트 포함 |
| Text Area와 Graphic Area 명확 분리 | 텍스트가 그래픽 위에 무분별하게 겹침 |

---

## 5. HTML/CSS 생성 규칙

### 5.1 파일 구조

- **단일 `.html` 파일**로 생성 (외부 CSS/JS 파일 분리 금지)
- `<style>` 태그로 CSS 포함 (inline attribute 방식은 지양, `<style>` 블록 사용)
- 이미지는 **placeholder `<div>`** 로 대체 (실제 이미지 삽입 불가)

### 5.2 필수 포함 요소

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard/dist/web/static/pretendard.css" />
  <style>
    :root {
      /* sparta-brand-components/SKILL.md의 CSS 변수 템플릿 전체 삽입 */
    }
    /* 레이아웃 및 컴포넌트 스타일 */
  </style>
</head>
<body>
  <!-- 배너 콘텐츠 -->
</body>
</html>
```

### 5.3 CSS 변수 참조

- 모든 색상값은 **CSS 변수**로 참조 (`var(--sparta-red)`, `var(--gray-800)`)
- HEX 직접 사용 금지 — 반드시 `sparta-brand-components/SKILL.md`의 CSS 변수 템플릿 참조
- 서체도 CSS 변수 사용 (`var(--font-primary)`, `var(--font-secondary)`)
- 간격은 스페이싱 토큰 사용 (`var(--space-4)`, `var(--space-8)`)

### 5.4 이미지 placeholder

이미지/일러스트레이션 영역은 실제 이미지 대신 placeholder로 표현:

```html
<div class="graphic-placeholder" style="
  background-color: var(--gray-50);
  border: 2px dashed var(--gray-300);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--gray-500);
  font-family: var(--font-primary);
  font-size: 14px;
">
  [일러스트레이션: 노트북과 코드 에디터]
</div>
```

- placeholder 내부에 **어떤 이미지가 들어갈지 설명** 텍스트 포함
- 회색 점선 테두리 + 중앙 정렬 텍스트

### 5.5 반응형 고려

- 배너는 **고정 크기**로 생성 (비율 유지)
- `width`와 `height`를 명시적으로 지정
- 포맷별 권장 크기:

| 포맷 | 권장 크기 (px) |
|------|---------------|
| Mini Banner (3:2) | 600 × 400 |
| Flex Banner | 1200 × 200 |
| Story-AD (1:2) | 540 × 1080 |
| Feed/Pop-Up (4:5) | 540 × 675 |

### 5.6 코드 품질 규칙

- `class` 이름은 역할 기반 (`.banner-title`, `.cta-button`, `.graphic-area`)
- 시맨틱 HTML 사용 (`<header>`, `<main>`, `<footer>` 등)
- 접근성: `alt` 텍스트(placeholder에도), `lang="ko"`, 충분한 색상 대비 (본문 ≥ 4.5:1, 대형 텍스트 ≥ 3:1 — WCAG AA)
- 주석으로 레이어 구조 표시:

```html
<!-- Layer 1: Background -->
<div class="banner-bg">
  <!-- Layer 2: Frame/Pattern (해당 시) -->
  <!-- Layer 3: Image/Graphic -->
  <div class="graphic-area">...</div>
  <!-- Layer 4: Text/Logo -->
  <div class="text-area">...</div>
</div>
```

---

## 6. 제작 워크플로우

제작 에이전트가 디자인 요청을 처리하는 순서:

### Step 1: 요청 분석

사용자 요청에서 다음을 추출:

| 항목 | 질문 | 기본값 |
|------|------|--------|
| 브랜드 | 어떤 브랜드? | Sparta Club |
| 콘텐츠 타입 | TYPE-A / B / C? | 요청 맥락에서 판별 |
| 포맷 | 어떤 레이아웃? | Mini Banner (3:2) |
| 핵심 메시지 | 전달할 내용? | 사용자 입력 필수 |
| CTA | 어떤 행동 유도? | TYPE-A/B: "자세히 보기" |

- 누락 정보가 있으면 **사용자에게 질문** (추측하여 진행하지 않음)
- 단, 브랜드와 포맷은 기본값 제시 후 확인 요청

### Step 2: 텍스트 시안

분석 결과를 바탕으로 텍스트 시안 제안:

```
## 시안

- **브랜드**: Sparta Club
- **콘텐츠 타입**: TYPE-B (Action-Driven)
- **포맷**: Mini Banner (3:2) — 600×400px
- **컬러 조합**: Sparta Red 배경 + White 텍스트 + Deep Red 악센트
- **레이아웃**:
  - 로고: 좌상단, Primary Type, White
  - Title: "AI 개발자로 전향하는 가장 빠른 방법" (ExtraBold, --text-head)
  - SubTitle: "내일배움캠프 4기 모집 중" (Medium, --text-subtitle)
  - CTA: "지금 신청하기" (White bg + Sparta Red text)
  - 그래픽: 우측, 노트북 일러스트레이션 placeholder
```

### Step 3: 사용자 확인

- 시안을 사용자에게 보여주고 **확인 또는 수정 요청** 대기
- 확인 전 HTML/CSS 코드를 생성하지 않음

### Step 4: HTML/CSS 생성

확인 후 코드 생성:
- 5.1~5.6의 HTML/CSS 생성 규칙 준수
- CSS 변수 템플릿 전체 삽입
- 레이어 구조 주석 포함
- placeholder로 이미지 영역 표현

### Step 5: 셀프 검수

생성된 코드를 `sparta-review-checklist.md` 기준으로 셀프 체크:

**기술 검수 (32항목):**
- CRITICAL 항목 (로고 + 컬러) 전수 확인
- HIGH 항목 (타이포 + 그래픽) 확인
- FAIL 항목 발견 시 코드 수정 후 재확인

**사내 평가 필수 항목 (3항목):**
- `QUAL-01` 가독성: 폰트 크기(Body ≥ 14px, Head ≥ 24px), 명도 대비(본문 ≥ 4.5:1), CTA 터치 영역(≥ 44×44px)
- `QUAL-02` 레이아웃 완성도: 4px 그리드, 간격 일관성(편차 ≤ 4px), 여백 균형(좌우 차이 ≤ 8px)
- `BRAND-01` 가이드라인 준수: 기술 검수 FAIL이 아닐 것

사내 평가 필수 항목이 FAIL이면 🔴 미달 등급이므로 반드시 수정한다.

---

## 7. 키 비주얼 적용 가이드

### 7.1 Frame Type 적용 시

| 결정 사항 | 선택지 | 적용 기준 |
|----------|--------|----------|
| 프레임 유형 | Image Masking / Image Clipping / Text | 이미지 있으면 Masking/Clipping, 텍스트만이면 Text |
| 크롭 레벨 | Basic 125% / Full 150% / Extended | 기본 Basic, 강조 시 Full, 풀블리드 시 Extended |
| 배치 | 최소 3면 노출 확인 | 프레임이 잘려도 Potential Cube 인지 가능해야 함 |

### 7.2 Pattern Type 적용 시

| 결정 사항 | 선택지 | 적용 기준 |
|----------|--------|----------|
| 패턴 유형 | Full Pattern / Line Pattern | 면적 넓으면 Full, 섬세하면 Line |
| 방향 | Single / Full Horizontal / Full Vertical | 배너 방향에 맞춰 선택 |
| 반복 | 최대 3-4회 | 초과 금지 |
| 컬러 | 톤온톤 (배경과 유사 계열) | 대비 강한 컬러 사용 금지 |

### 7.3 Tag Type 적용 시

| 결정 사항 | 선택지 | 적용 기준 |
|----------|--------|----------|
| 형태 | Square / Hexagon / Signature | 기본 Square, 브랜드 강조 시 Hexagon/Signature |
| 내용 | 텍스트 / 카테고리 아이콘 | 카테고리 분류 시 아이콘, 라벨 시 텍스트 |
| 비례 | X-height 기준 0.3X 마진, 0.45X 텍스트 | 비례 가이드 필수 준수 |

---

## 8. 빠른 참조: 의사결정 플로우차트

```
요청 수신
    │
    ▼
[1] 브랜드 식별
    │ Team Sparta / Sparta Club / Sparta Builders / 기업교육
    ▼
[2] 콘텐츠 타입 판별
    │ TYPE-A (정보) / TYPE-B (액션) / TYPE-C (메시지)
    ▼
[3] 포맷 선택
    │ Mini 3:2 / Flex / Story 1:2 / Feed 4:5
    ▼
[4] 서체 결정
    │ TYPE-A/B → Pretendard 전용
    │ TYPE-C   → Sandol Dol(Title) + Pretendard(나머지)
    ▼
[5] 컬러 조합 결정
    │ Primary/Secondary/Extended Pairing에서 최대 3색 선택
    │ 로고-배경 조합 16가지 중 선택
    ▼
[6] 텍스트 하이어라키 구성
    │ 타입별 요소 순서 적용
    ▼
[7] 그래픽 요소 결정
    │ Frame / Pattern / Tag 중 선택
    │ 레이어 구조 설정
    ▼
[8] 시안 제시 → 사용자 확인 → HTML/CSS 생성 → 셀프 검수
```
