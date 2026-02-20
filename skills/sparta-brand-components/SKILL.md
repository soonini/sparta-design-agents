---
name: sparta-brand-components
description: SPARTA 브랜드 디자인 토큰(컬러/타이포/스페이싱), 로고 규격, 그래픽 에셋, UI 컴포넌트, CSS 변수 템플릿. 디자인 제작·검수 시 수치 기준으로 참조.
user-invocable: false
---

# SPARTA 브랜드 컴포넌트 라이브러리

> SPARTA Brand Basic Guide V.1.0 + Application Guide V.1.0 기반
> 모든 수치와 규칙은 공식 PDF 가이드라인에서 추출됨

---

## 1. 디자인 토큰

### 1.1 컬러 토큰

#### 메인 컬러

| 토큰명 | HEX | 용도 |
|--------|-----|------|
| `--sparta-red` | `#FA0030` | 브랜드 대표색 |
| `--sparta-deep-red` | `#850028` | 보조 강조색 |
| `--sparta-blue` | `#93E6F5` | 포인트 컬러 |

#### 확장 팔레트 — Red 계열

| 토큰명 | HEX | RGB |
|--------|-----|-----|
| `--red-100` | `#FFAAF0` | 255, 170, 240 |
| `--red-200` | `#FF82D2` | 255, 130, 210 |
| `--red-300` | `#EB2844` | 235, 40, 68 |
| `--red-400` | `#AA002A` | 170, 0, 42 |
| `--red-500` | `#730023` | 115, 0, 35 |

#### 확장 팔레트 — Blue 계열

| 토큰명 | HEX | RGB |
|--------|-----|-----|
| `--blue-100` | `#8CEBFF` | 140, 235, 255 |
| `--blue-200` | `#00D2E6` | 0, 210, 230 |
| `--blue-300` | `#0096EB` | 0, 150, 235 |
| `--blue-400` | `#005F9B` | 0, 95, 155 |
| `--blue-500` | `#003773` | 0, 55, 115 |

#### 확장 팔레트 — Purple 계열

| 토큰명 | HEX | RGB |
|--------|-----|-----|
| `--purple-100` | `#DCA5FF` | 220, 165, 255 |
| `--purple-200` | `#D773FF` | 215, 115, 255 |
| `--purple-300` | `#9646FF` | 150, 70, 255 |
| `--purple-400` | `#6400C3` | 100, 0, 195 |
| `--purple-500` | `#320073` | 50, 0, 115 |

#### Grayscale

| 토큰명 | HEX |
|--------|-----|
| `--gray-white` | `#FFFFFF` |
| `--gray-50` | `#F5F5F5` |
| `--gray-100` | `#E0E0E0` |
| `--gray-300` | `#999999` |
| `--gray-500` | `#666666` |
| `--gray-800` | `#333333` |
| `--gray-black` | `#000000` |

#### 그래픽 에셋 전용 컬러 (아이콘/일러스트레이션 전용, 다른 용도 사용 금지)

**Red 계열** (사용 비율):

| 토큰명 | HEX | 비율 (Category Icon) | 비율 (Illustration) |
|--------|-----|---------------------|---------------------|
| `--asset-red-1` | `#FFAAF0` | 10% | 10% |
| `--asset-red-2` | `#FF82D2` | 30% | 30% |
| `--asset-red-3` | `#EB2844` | 50% | 40% |
| `--asset-red-4` | `#AA002A` | 10% | 10% |
| `--asset-red-5` | `#730023` | — | 10% |

**Purple 계열** (사용 비율):

| 토큰명 | HEX | 비율 (Category Icon) | 비율 (Illustration) |
|--------|-----|---------------------|---------------------|
| `--asset-purple-1` | `#DCA5FF` | 10% | 10% |
| `--asset-purple-2` | `#D773FF` | 30% | 30% |
| `--asset-purple-3` | `#9646FF` | 50% | 40% |
| `--asset-purple-4` | `#6400C3` | 10% | 10% |
| `--asset-purple-5` | `#320073` | — | 10% |

**Blue 계열** (사용 비율):

| 토큰명 | HEX | 비율 (Category Icon) | 비율 (Illustration) |
|--------|-----|---------------------|---------------------|
| `--asset-blue-1` | `#8CEBFF` | 10% | 10% |
| `--asset-blue-2` | `#00D2E6` | 30% | 30% |
| `--asset-blue-3` | `#0096EB` | 50% | 40% |
| `--asset-blue-4` | `#005F9B` | 10% | 10% |
| `--asset-blue-5` | `#003773` | — | 10% |

그래픽 에셋 면 배치: Top=레벨2, Bevel-Bright=레벨1, Bevel-Dark=레벨4(Icon)/레벨5(Illust), Front=레벨3, Side=Black

### 1.2 타이포그래피 토큰

#### 서체

| 토큰명 | 서체 | 용도 |
|--------|------|------|
| `--font-primary` | `Pretendard` | 주 서체 (모든 UI, 마케팅 텍스트) |
| `--font-secondary` | `Sandol Dol` | 보조 서체 (브랜드 메시지 강조) |

#### Weight

| 토큰명 | 값 | 서체 |
|--------|---|------|
| `--weight-extrabold` | `800` | Pretendard |
| `--weight-bold` | `700` | Pretendard, Sandol Dol |
| `--weight-semibold` | `600` | Pretendard |
| `--weight-medium` | `500` | Pretendard, Sandol Dol |
| `--weight-regular` | `400` | Pretendard |

#### 텍스트 위계

기준(Base) 대비 상대 크기. Base size는 매체별로 결정.

| 레벨 | 토큰명 | 크기 | Weight | Line Height |
|------|--------|------|--------|-------------|
| Head | `--text-head` | 150–250% | ExtraBold (800) | 110% |
| Title | `--text-title` | 100–120% | Bold (700) | 130% |
| Label | `--text-label` | 60% | Bold (700) | 130% |
| SubTitle | `--text-subtitle` | 40–60% | Medium (500) | 140% |
| Body | `--text-body` | 20–40% | Regular (400) | 160% |
| Body List | `--text-body-list` | 15–20% | Regular (400) | 160% |
| Caption | `--text-caption` | 10–15% | Regular (400) | 160% |

### 1.3 스페이싱 토큰

4px 그리드 기반:

| 토큰명 | 값 |
|--------|----|
| `--space-1` | `4px` |
| `--space-2` | `8px` |
| `--space-3` | `12px` |
| `--space-4` | `16px` |
| `--space-6` | `24px` |
| `--space-8` | `32px` |
| `--space-10` | `40px` |
| `--space-12` | `48px` |
| `--space-16` | `64px` |

---

## 2. 로고

### 2.1 브랜드별 변형

| 브랜드 | Primary Type (가로형) | Stacked Type (세로형) |
|--------|----------------------|----------------------|
| Team Sparta | O | O |
| Sparta Club | O | O |
| Sparta Builders | O | O |
| Sparta 기업교육 | O | O |

### 2.2 최소 크기

| 브랜드 | Primary 최소 높이 | Stacked 최소 높이 |
|--------|-------------------|-------------------|
| Team Sparta | 22px | 45px |
| Sparta Club | 24px | 56px |
| Sparta Builders | 22px | 45px |
| Sparta 기업교육 | 22px | 45px |

### 2.3 클리어 스페이스

T자 형태 기반의 여백. 로고 주변에 T자 높이만큼의 최소 여백을 확보해야 함.

### 2.4 배치 유형

- **Standard**: 좌상단 또는 우상단
- **Extended**: 중앙, 하단 등 (특별한 경우에 한해 사용)

### 2.5 시그니처 마크

S 아이콘. 독립적으로 사용 가능 (앱 아이콘, 파비콘 등).

### 2.6 파트너십 로고

- **Ongoing (지속적 협력)**: `|`로 구분 — `SPARTA Club | 파트너사`
- **One-Off (일회성 협력)**: `X`로 구분 — `SPARTA Club X 파트너사`

### 2.7 아이덴티티 컬러 적용

| 배경 | 로고 색상 |
|------|----------|
| 흰색/밝은 배경 | Sparta Red (`#FA0030`) |
| Sparta Red 배경 | 흰색 (`#FFFFFF`) |

### 2.8 로고 금지사항 (9가지)

1. 비율 변경 (가로/세로 왜곡)
2. 회전
3. 그림자 효과 추가
4. 아웃라인 처리
5. 지정 외 색상 사용
6. 패턴/텍스처 적용
7. 가독성 부족한 배경 위 배치
8. 로고 요소 분리 또는 재배치
9. 다른 그래픽/텍스트와 결합

---

## 3. 컬러 시스템

### 3.1 컬러 셋 구성

모든 디자인은 **Accent + Text + Background** 3가지 역할로 컬러를 배정.

### 3.2 최대 3색 규칙

한 디자인에 **최대 3색**까지만 사용. 확장 팔레트 내에서 선택.

### 3.3 컬러 페어링

#### Primary Pairing (8가지 — 가장 빈번하게 사용)

메인 컬러 기반의 기본 조합. Sparta Red + White, Sparta Red + Deep Red 등 공식 가이드에 정의된 8가지 조합.

#### Secondary Pairing (4가지)

확장 팔레트 간 보조 조합.

#### Extended Pairing (16가지)

확장 팔레트 전체에서 허용되는 조합.

### 3.4 로고 + 배경 조합

공식 승인된 **16가지** 로고-배경 조합만 사용 가능. 가이드라인에 없는 조합은 금지.

### 3.5 컬러 금지사항

- 지정 팔레트 이외의 색상 사용
- 4색 이상 혼합
- 가독성이 떨어지는 텍스트-배경 조합
- 그라디언트 적용 (특별히 승인되지 않은 경우)

---

## 4. 타이포그래피

### 4.1 서체 규정

- **주 서체**: Pretendard — 모든 UI, 마케팅 텍스트에 사용
  - Weight: ExtraBold (800), Bold (700), SemiBold (600), Medium (500), Regular (400)
- **보조 서체**: Sandol Dol — 브랜드 메시지 강조에 한정 사용
  - Weight: Bold (700), Medium (500)

### 4.2 콘텐츠 타입별 서체 적용

| 콘텐츠 타입 | 주요 서체 | 설명 |
|-------------|----------|------|
| Marketing A | Pretendard | 일반 마케팅 카피 |
| Marketing B | Pretendard | 마케팅 카피 변형 |
| Brand Message A | Sandol Dol + Pretendard | 브랜드 메시지 (제목: Sandol Dol) |
| Brand Message B | Sandol Dol + Pretendard | 브랜드 메시지 변형 |

### 4.3 타이포그래피 금지사항 (9가지)

1. 장평(가로 비율) 변경
2. 과도한 자간 조정
3. 행간 부족 (위계별 최소 line-height 미준수)
4. 지정 외 서체 사용
5. 텍스트에 그라디언트 적용
6. 텍스트에 아웃라인 처리
7. 텍스트에 그림자 효과
8. 배경 대비 색상 대비 부족
9. 과도한 weight 혼합 (한 레이아웃에 너무 많은 굵기)

---

## 5. 키 비주얼 그래픽

### 5.1 그래픽 모티프: Potential Cube

정육면체 아웃라인 기반 **육각형 형태**. Bevel(모서리면)을 추가하여 입체감과 성장 가능성을 시각화.
모든 그래픽 에셋(UI 아이콘, 카테고리 아이콘, 일러스트레이션)에 이 모티프가 적용됨.

### 5.2 Frame Type

이미지와 텍스트를 브랜드 프레임 안에 배치하는 방식.

#### 유형

| 유형 | 설명 |
|------|------|
| Image Masking | 프레임 내부에 이미지를 마스킹 처리 |
| Image Clipping | 프레임 경계에서 이미지를 클리핑 |
| Text | 프레임 내부에 텍스트 배치 |

#### 4-레이어 구조

```
Layer 4 (최상위): Text / Logo
Layer 3:          Image
Layer 2:          Frame (Potential Cube 형태)
Layer 1 (최하위): Background
```

#### 크롭 가이드

| 타입 | 프레임 크기 | 설명 |
|------|-----------|------|
| Basic | 125% | 기본 크롭 |
| Full | 150% | 넓은 크롭 |
| Extended | 프레임 확장 | 프레임이 화면 밖으로 확장 |

#### 규칙

- 프레임의 **최소 3면**이 화면에 노출되어야 함
- 프레임이 잘리더라도 Potential Cube 형태를 인지할 수 있어야 함

### 5.3 Pattern Type

그래픽 모티프를 반복 패턴으로 사용하는 방식.

#### 유형

| 유형 | 설명 |
|------|------|
| Full Pattern | 면이 채워진 패턴 |
| Line Pattern | 아웃라인만 사용하는 패턴 |

#### 3-레이어 구조

```
Layer 3 (최상위): Text / Logo
Layer 2:          Pattern
Layer 1 (최하위): Background
```

#### 방향 및 반복

- **Single**: 단일 패턴
- **Full Horizontal**: 수평 반복
- **Full Vertical**: 수직 반복
- Full 반복 시 **최대 3-4회** 반복
- 톤온톤 컬러 사용 (배경과 유사한 계열)

### 5.4 Tag Type

콘텐츠에 카테고리나 텍스트를 표시하는 태그 요소.

#### 삽입 가능 콘텐츠

- 텍스트 (카테고리명, 라벨 등)
- 카테고리 아이콘

#### 형태

| 형태 | 설명 |
|------|------|
| Square | 사각형 태그 |
| Hexagon | 육각형 태그 (Potential Cube 모티프 기반) |
| Signature | 브랜드 시그니처 형태 |

#### 비례 가이드

X-height(기준 높이)를 기준으로:
- 태그 전체 높이 마진: **0.3X**
- 텍스트 높이: **0.45X**
- 텍스트-태그 경계 간격: **0.15X**

---

## 6. 그래픽 에셋

### 6.1 UI Icon

- **스타일**: 육각형 아웃라인 기반, 단순화된 2D 형태
- **용도**: 하단 내비게이션, 기능 아이콘, 메뉴 아이콘
- **에셋 목록**: 홈, IT취업(내배캠), 강의, 커뮤니티, 좋아요, 스킬업, AI 부업, 프로필, 알림, 열정
- **제작 규칙**: 그리드 준수, 추가 제작 시 유관 부서 협의 필수

**금지사항:**
- 그래픽 요소(장식, 일러스트)로 활용
- 최소 여백 침범
- 복잡한 형태로 구성

### 6.2 Category Icon

- **스타일**: 3D Bevel 적용, 입체감 있는 아이콘
- **용도**: 카테고리 분류, 콘텐츠 태그, 배너 그래픽
- **에셋 목록**: 국비강의, 국비취업, 디자인, 자기개발(커리어), 개발, 데이터, AI·GPT, 자격증
- **컬러**: Blue, Red, Purple 3계열 중 선택
- **각도 규격**: 좌측 하단 경사각 10°, 우측 하단 경사각 35°

**제작 프로세스:**
1. 꼭짓점을 그리드에 맞춤
2. 나머지 변을 직선으로 연결하여 형태 완성
3. 완성된 기본 형태를 기준으로 아이콘 제작
4. 모서리에 Bevel을 적용해 입체감 추가

**태그 내 배치 규칙:**
- 태그 안에서 아이콘이 뛰어나오는 듯한 시각 효과 연출
- 태그와 아이콘 간 시각적 충돌이 발생하면 아이콘을 확장하거나 회전하여 조정

**금지사항:**
- 불규칙한 조명 기준으로 컬러 적용
- Bevel을 과도하게 적용
- 동일한 컬러를 반복적으로 구성

### 6.3 Illustration

- **스타일**: Bevel 적용 입체 스타일, 콘텐츠 메시지 전달 목적
- **에셋 목록**: 강의, 내일배움캠프, 데이터(3종), 앱 아이콘, 폴더, 내일배움카드, 컴퓨터, 노트북, 완주, 축하, 캘린더, 알람, 긴급 알림
- **컬러**: Category Icon과 동일 3계열 (비율 약간 상이: 주요면 40%, 나머지 10%씩)

**제작 프로세스:**
1. 표현하고자 하는 기본 형태를 입체적으로 제작
2. 기본 형태의 모서리에 Bevel 면 추가
3. 핵심 요소를 한층 더 입체화해 강조
4. 빛과 그림자를 추가해 입체감을 강화

**특징:**
- Feature 1: 모서리면 추가 (Bevel)
- Feature 2: 강조 필요한 경우 핵심 요소를 더 입체화

**금지사항:**
- 메시지를 해칠 정도로 Bevel을 과도하게 강조
- 기능적인 역할의 UI 아이콘처럼 사용
- 한 개체에 여러 색상 혼합

### 6.4 Character: 르탄이

- **정체**: 스파르타클럽 공식 캐릭터
- **구성**: 얼굴, 몸통, 투구, 투구 위 장식, 망토
- **얼굴 형태**: 그래픽 모티프(Potential Cube)에서 파생된 육각 프레임
- **투구 장식**: 다양한 감정을 시각적으로 표현하는 역할
- **주요 활용**: 내일배움캠프 서비스에서 사용자 커뮤니케이션

---

## 7. 레이아웃 그리드

### 7.1 배너 포맷

| 포맷명 | 비율 | 용도 |
|--------|------|------|
| 3:2 Mini Banner (Web) | 3:2 | 웹사이트 미니 배너 |
| Banner (Web - Flex) | 가로 확장형 | 웹사이트 플렉스 배너 |
| 1:2 (Instagram Story-AD) | 1:2 | 인스타그램 스토리 광고 |
| 4:5 (Instagram Feed/Pop-Up) | 4:5 | 인스타그램 피드, 팝업 배너 |

### 7.2 영역 구분

| 영역 | 설명 |
|------|------|
| Layout Grid | 전체 배너 레이아웃의 기준이 되는 셀 구조 |
| Margin / Safe Area | 주요 정보가 잘려나가지 않도록 확보된 안전 영역 |
| Text Area | 텍스트 배치 권장 영역 |
| Graphic Area | 그래픽/이미지 배치 영역 |

### 7.3 콘텐츠 타입별 배치

#### Type A: Content-Driven (내용 중심)

| 요소 | 배치 순서 |
|------|----------|
| Tag | 최상단 (S Size) |
| SubTitle | Tag 아래 |
| Title (Head Copy) | 중앙 핵심 |
| Body | Title 아래 |
| CTA | 하단 버튼 |

#### Type B: Action-Driven (액션 중심)

| 요소 | 배치 순서 |
|------|----------|
| Title (Head Copy) | 최상단 대형 |
| SubTitle | Title 아래 (L Size 태그 가능) |
| CTA | 하단 버튼 |

#### Type C: Message-Driven (메시지 중심)

| 요소 | 배치 순서 |
|------|----------|
| SubTitle | 최상단 |
| Title (Head Copy) | 중앙 최대형 |
| Caption | 하단 보조 |

---

## 8. UI 컴포넌트

### 8.1 Infographic

| 컴포넌트 | 스타일 |
|----------|--------|
| Graph (게이지) | 반원 형태, 카테고리 아이콘 중앙 배치, Sparta Red 계열 |
| Charts (바 차트) | Potential Cube 모티프 형태 바, 빨간색 계열 |
| Progress | 빨간색 active 구간 + 회색 inactive 구간 |

### 8.2 Active Button

| 컴포넌트 | Active 상태 |
|----------|------------|
| Carousel Indicator | 붉은 도트 (active), 회색 도트 (inactive) |
| Tab | 빨간 텍스트 + 라운드 배경 (active), 회색 텍스트 (inactive) |
| Calendar | 빨간 육각형 배경 + 흰 텍스트 (today), 기본 텍스트 (other) |

### 8.3 Tag (UI)

- 콘텐츠 카드 위에 배치되는 라벨 태그
- Active: 색상 배경(빨간) + 흰 텍스트
- Inactive: 회색/투명 배경 + 기본 텍스트
- 예: 무료 세미나, 스터디클럽, GPT, 데이터 분석

---

## 9. 웹 배너 가이드

### 9.1 Mini Banner (3:2)

```
┌──────────────────────────┐
│  [TAG]                   │
│  Sub Copy                │
│  Head Copy          [그래│
│  Dummy              픽   │
│                     영역]│
│  [CTA BUTTON]            │
└──────────────────────────┘
```

- Head Copy + Sub Copy는 좌측 텍스트 영역
- 그래픽 요소(일러스트레이션/이미지)는 우측 배치
- CTA 버튼은 좌하단

### 9.2 Flex Banner (가로 확장형)

```
┌─────────────────────────────────────────────┐
│  Head Copy Dummy Text    [그래픽 영역]       │
│  Up to 2 lines                              │
│  Sub copy dummy text                        │
└─────────────────────────────────────────────┘
```

- Head Copy 최대 2줄
- 그래픽 요소는 우측 배치
- 가로로 긴 형태, Extended Area 활용 가능

---

## 10. CSS 변수 템플릿

아래 코드 블록을 HTML 파일 상단에 삽입하여 모든 토큰을 CSS 변수로 사용.

```css
:root {
  /* === 메인 컬러 === */
  --sparta-red: #FA0030;
  --sparta-deep-red: #850028;
  --sparta-blue: #93E6F5;

  /* === 확장 팔레트: Red === */
  --red-100: #FFAAF0;
  --red-200: #FF82D2;
  --red-300: #EB2844;
  --red-400: #AA002A;
  --red-500: #730023;

  /* === 확장 팔레트: Blue === */
  --blue-100: #8CEBFF;
  --blue-200: #00D2E6;
  --blue-300: #0096EB;
  --blue-400: #005F9B;
  --blue-500: #003773;

  /* === 확장 팔레트: Purple === */
  --purple-100: #DCA5FF;
  --purple-200: #D773FF;
  --purple-300: #9646FF;
  --purple-400: #6400C3;
  --purple-500: #320073;

  /* === Grayscale === */
  --gray-white: #FFFFFF;
  --gray-50: #F5F5F5;
  --gray-100: #E0E0E0;
  --gray-300: #999999;
  --gray-500: #666666;
  --gray-800: #333333;
  --gray-black: #000000;

  /* === 타이포그래피 === */
  --font-primary: 'Pretendard', -apple-system, BlinkMacSystemFont, system-ui, sans-serif;
  --font-secondary: 'Sandol Dol', sans-serif;

  --weight-extrabold: 800;
  --weight-bold: 700;
  --weight-semibold: 600;
  --weight-medium: 500;
  --weight-regular: 400;

  /* === 스페이싱 (4px 그리드) === */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;
}
```

### Pretendard CDN

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard/dist/web/static/pretendard.css" />
```
