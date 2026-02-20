---
name: sparta-review-checklist
description: SPARTA 브랜드 검수 36항목(CRITICAL/HIGH/MEDIUM), 항목별 PASS/FAIL → 신호등 등급(🔴🟡🟢) 산출. 😎은 리더 별도 판단.
user-invocable: false
---

# SPARTA 브랜드 검수 체크리스트

> 모든 항목은 PASS/FAIL로 판정하고, 심각도별 집계로 신호등 등급을 산출한다.
> 항목은 sparta-brand-components 스킬의 규칙에서 도출됨.

---

## 1. 심각도 정의

| 심각도 | 의미 | 조치 |
|--------|------|------|
| **CRITICAL** | 브랜드 아이덴티티 훼손. 외부 공개 시 브랜드 신뢰도 손상 | 반드시 수정 후 게시 |
| **HIGH** | 가이드라인 명시적 위반. 브랜드 일관성 저해 | 수정 강력 권장 |
| **MEDIUM** | 모범 사례 미준수. 품질 개선 여지 | 개선 고려 |

---

## 2. 신호등 등급 (최종 판정)

| 등급 | 조건 | 설명 |
|------|------|------|
| 🔴 **미달** | CRITICAL 1건 이상 FAIL | 게시 불가. 수정 필수 |
| 🟡 **기본** | CRITICAL 0건, HIGH 1건 이상 FAIL | 게시 가능하나 개선 권장 |
| 🟢 **우수** | CRITICAL + HIGH 전부 PASS | 브랜드 품질 기준 충족 |

> 😎 **미침(p)** 등급은 리더가 별도 판단합니다 (혁신성·지표 개선·생산성 등).

MEDIUM 항목은 등급에 영향을 주지 않으나, 리포트에 기록하여 개선을 유도한다.

---

## 3. 체크리스트

### 3.1 로고 (CRITICAL)

| ID | 항목 | 기준 | 위반 예시 |
|----|------|------|-----------|
| `LOGO-01` | 승인된 변형 사용 | 4개 브랜드(Team Sparta, Sparta Club, Sparta Builders, Sparta 기업교육) × 2개 타입(Primary, Stacked)만 허용 | 비공식 로고 변형, 로고 요소 임의 재배치 |
| `LOGO-02` | 최소 크기 준수 | Primary: 22-24px / Stacked: 45-56px (브랜드별 상이) | Primary 로고를 15px로 축소 |
| `LOGO-03` | 클리어 스페이스 확보 | T자 높이 기준 최소 여백 유지 | 로고 바로 옆에 텍스트나 그래픽 배치 |
| `LOGO-04` | 금지사항 위반 없음 | 9가지 금지사항 전부 미해당 | 로고 회전, 그림자, 아웃라인, 색상 변경 등 |
| `LOGO-05` | 아이덴티티 컬러 준수 | 밝은 배경 → Sparta Red 로고 / Sparta Red 배경 → 흰색 로고 | 파란 배경에 빨간 로고 |
| `LOGO-06` | 로고-배경 승인 조합 | 공식 16가지 로고-배경 조합만 허용 | 미승인 컬러 배경에 로고 배치 |
| `LOGO-07` | 파트너십 로고 형식 | Ongoing: `|` 구분 / One-Off: `X` 구분 | 구분자 없이 두 로고 나란히 배치 |

### 3.2 컬러 (CRITICAL)

| ID | 항목 | 기준 | 위반 예시 |
|----|------|------|-----------|
| `COLOR-01` | 승인 팔레트 사용 | 메인 3색 + 확장 팔레트(Red/Blue/Purple 각 5단계) + Grayscale만 허용 | `#FF6600` 같은 미승인 색상 사용 |
| `COLOR-02` | 최대 3색 규칙 | 한 디자인에 Grayscale 제외 최대 3색 | 4가지 이상 유채색 혼합 |
| `COLOR-03` | 컬러 페어링 준수 | Primary(8가지) / Secondary(4가지) / Extended(16가지) 승인 조합만 사용 | 미승인 색상 조합 |
| `COLOR-04` | 텍스트-배경 가독성 | 충분한 명도 대비 확보 (밝은 텍스트-어두운 배경 또는 반대) | 연분홍 배경에 밝은 빨간 텍스트 |
| `COLOR-05` | 그라디언트 미사용 | 특별히 승인되지 않은 그라디언트 사용 금지 | 로고나 텍스트에 그라디언트 적용 |

### 3.3 가독성·접근성 (CRITICAL)

| ID | 항목 | 기준 | 위반 예시 |
|----|------|------|-----------|
| `QUAL-01` | 본문 최소 폰트 | Body ≥ 14px, Caption ≥ 11px, Head ≥ 24px, Title ≥ 18px | Body를 11px로 설정 |
| `QUAL-02` | 텍스트-배경 명도 대비 | 본문 ≥ 4.5:1, 대형(18px+) ≥ 3:1 (WCAG AA) | 연분홍 배경에 밝은 빨간 텍스트 (2.1:1) |
| `QUAL-03` | CTA 터치 영역 | 모바일 타겟 시 ≥ 44×44px | CTA 버튼 30×30px |
| `QUAL-04` | 핵심 콘텐츠 Safe Area | 로고·타이틀·CTA가 Safe Area 100% 내 배치 | CTA가 Safe Area 밖에 위치 |

> QUAL-01~04 중 1건이라도 FAIL이면 해당 항목이 CRITICAL FAIL로 집계된다.

### 3.4 레이아웃 완성도 (CRITICAL)

| ID | 항목 | 기준 | 위반 예시 |
|----|------|------|-----------|
| `QUAL-05` | 4px 그리드 정렬 | 모든 요소의 margin/padding이 4px 배수 | 간격 13px 사용 |
| `QUAL-06` | 요소 간격 일관성 | 동일 레벨 요소 간격 편차 ≤ 4px | 같은 레벨 요소 간격이 16px / 28px 혼재 |
| `QUAL-07` | 타이포 위계 크기 순서 | Head > Title > SubTitle > Body > Caption | Title이 Head보다 큰 경우 |
| `QUAL-08` | 좌우 여백 균형 | 좌우 마진 차이 ≤ 8px (의도적 비대칭 제외) | 좌 16px / 우 32px |
| `QUAL-09` | 요소 정렬 | 텍스트 요소가 동일 기준선(좌측 또는 중앙)에 정렬 | 텍스트 블록마다 정렬 기준 다름 |

> QUAL-05~09 중 1건이라도 FAIL이면 해당 항목이 CRITICAL FAIL로 집계된다.

### 3.5 타이포그래피 (HIGH)

| ID | 항목 | 기준 | 위반 예시 |
|----|------|------|-----------|
| `TYPO-01` | 승인 서체 사용 | Pretendard(주 서체) 또는 Sandol Dol(보조 서체)만 허용 | Arial, Noto Sans 등 미승인 서체 |
| `TYPO-02` | 위계 구조 준수 | Head → Title → Label → SubTitle → Body → Body List → Caption 순서 | Title 크기가 Head보다 큰 경우 |
| `TYPO-03` | Weight 규정 준수 | 레벨별 지정 Weight 사용 (Head: 800, Title: 700, SubTitle: 500, Body: 400) | Body 텍스트에 ExtraBold 적용 |
| `TYPO-04` | Line Height 준수 | Head: 110% / Title: 130% / SubTitle: 140% / Body: 160% | Head 텍스트에 160% 행간 |
| `TYPO-05` | 콘텐츠 타입별 서체 | Marketing A/B: Pretendard / Brand Message A/B: Sandol Dol + Pretendard | 마케팅 카피에 Sandol Dol 단독 사용 |
| `TYPO-06` | 금지사항 위반 없음 | 9가지 금지사항 전부 미해당 | 장평 변경, 텍스트 그림자, 아웃라인 처리 |

### 3.6 그래픽 (HIGH)

| ID | 항목 | 기준 | 위반 예시 |
|----|------|------|-----------|
| `GFX-01` | Frame 4-레이어 구조 | Background → Frame → Image → Text/Logo 순서 유지 | 프레임 위에 배경 레이어 배치 |
| `GFX-02` | 프레임 최소 3면 노출 | Potential Cube 프레임이 잘리더라도 3면 이상 화면에 보여야 함 | 프레임 2면만 노출 |
| `GFX-03` | 크롭 가이드 준수 | Basic 125% / Full 150% / Extended(확장) 규격 | 90%로 과도하게 크롭 |
| `GFX-04` | 패턴 반복 제한 | Full 반복 시 최대 3-4회, 톤온톤 컬러 | 패턴 6회 이상 반복, 대비 강한 패턴 컬러 |
| `GFX-05` | 태그 비례 가이드 | 마진 0.3X / 텍스트 높이 0.45X / 간격 0.15X (X = X-height) | 태그 내 텍스트가 경계에 붙어 있음 |
| `GFX-06` | UI Icon 규정 | 육각형 아웃라인, 단순 형태, 최소 여백 확보 | 아이콘을 장식/일러스트로 사용 |
| `GFX-07` | Category Icon 규정 | 3D Bevel, 좌측 10°/우측 35° 경사, 3계열 컬러 | 불규칙 조명, 과도한 Bevel |
| `GFX-08` | Illustration 규정 | Bevel 입체 스타일, 한 개체 단일 컬러 계열 | 한 일러스트에 Red + Blue 혼합 |
| `GFX-09` | 에셋 컬러 비율 | Category Icon: 10/30/50/10 / Illustration: 10/30/40/10/10 | 비율 무시한 균등 배분 |

### 3.7 콘텐츠 몰입도 (HIGH)

| ID | 항목 | 기준 | 위반 예시 |
|----|------|------|-----------|
| `QUAL-10` | 시각적 진입점 | 가장 큰 텍스트/그래픽이 화면 상위 60% 내 배치 | 핵심 메시지가 하단에 위치 |
| `QUAL-11` | 핵심 메시지 가중치 | Title이 모든 텍스트 중 최대 font-size × font-weight | SubTitle이 Title보다 시각적으로 강함 |
| `QUAL-12` | 텍스트-그래픽 분리 | 텍스트 위에 그래픽 직접 겹침 없음 (Frame Type 제외) | 로고 위에 패턴 겹침 |
| `QUAL-13` | 정보 밀도 | TYPE-A: ≤ 6개 텍스트 요소 / TYPE-B: ≤ 4개 / TYPE-C: ≤ 3개 | Action-Driven에 텍스트 블록 6개 |
| `QUAL-14` | CTA 즉시 식별 | CTA 배경색이 주변과 ≥ 3:1 대비 (TYPE-A/B만) | CTA 버튼이 배경과 구분 안 됨 |

> QUAL-10~14 중 4개 이상 PASS 시 이 영역 PASS. TYPE-C는 QUAL-14 자동 PASS.

### 3.8 브랜드 일관성 (HIGH)

| ID | 항목 | 기준 | 위반 예시 |
|----|------|------|-----------|
| `BRAND-01` | 톤앤매너 부합 | 브랜드 정의 톤과 일치 (Team Sparta=공식·신뢰, Club=활기·도전, Builders=전문·협력, 기업교육=신뢰·효율) | 기업교육 콘텐츠에 캐주얼한 톤 사용 |
| `BRAND-02` | 컬러 팔레트 일관 | 동일 캠페인 내 동일 Pairing 계열 사용 | 같은 캠페인에서 Red 계열과 Purple 계열 혼용 |
| `BRAND-03` | 타이포 패턴 일관 | Head/Title/Body 서체·Weight·크기가 동일 채널 기존 콘텐츠와 일치 | 같은 채널에서 갑자기 다른 크기 체계 사용 |
| `BRAND-04` | 그래픽 스타일 통일 | 단일 디자인 내 Frame/Pattern/Tag 유형 혼용 없음 | 한 배너에 Frame Type + Pattern Type 동시 사용 |

> BRAND-01~04 중 3개 이상 PASS 시 이 영역 PASS. 비교 대상 없는 첫 콘텐츠는 BRAND-03 자동 PASS.

### 3.9 레이아웃 (MEDIUM)

| ID | 항목 | 기준 | 위반 예시 |
|----|------|------|-----------|
| `LAYOUT-01` | 포맷 비율 준수 | 3:2(Mini) / Flex(가로확장) / 1:2(Story) / 4:5(Feed) | 1:1 비율로 Mini Banner 제작 |
| `LAYOUT-02` | Safe Area 준수 | 주요 정보가 Margin/Safe Area 안에 배치 | 로고나 CTA가 잘림 영역에 위치 |
| `LAYOUT-03` | 텍스트 영역 준수 | 텍스트가 지정된 Text Area 내에 배치 | 텍스트가 Graphic Area를 침범 |
| `LAYOUT-04` | 콘텐츠 타입별 배치 | Type A: Tag→SubTitle→Title→Body→CTA / Type B: Title→SubTitle→CTA / Type C: SubTitle→Title→Caption | Action-Driven에 Body 텍스트 포함 |
| `LAYOUT-05` | 배너 텍스트 구조 | Mini: Head+Sub+TAG+CTA / Flex: Head(최대 2줄)+Sub | Flex Banner에 3줄 이상 Head Copy |

---

## 4. 검수 리포트 형식

```markdown
# SPARTA 브랜드 검수 리포트

## 최종 등급: [🔴/🟡/🟢]

## 요약
- **CRITICAL**: N건 FAIL / 21항목
- **HIGH**: N건 FAIL / 24항목
- **MEDIUM**: N건 FAIL / 5항목
- **대상**: [파일명 또는 설명]
- **브랜드**: [식별된 브랜드]
- **콘텐츠 타입**: [TYPE-A / TYPE-B / TYPE-C]
- **레이아웃 포맷**: [Mini / Flex / Story / Feed]
- **검수일**: YYYY-MM-DD

## 왜 [등급]인가?
- CRITICAL: [N]건 FAIL → [🔴 원인 / ✓]
- HIGH: [N]건 FAIL → [🟡 원인 / ✓]
- MEDIUM: [N]건 FAIL (등급 미영향)

## 상세 결과

### CRITICAL 항목 (로고 · 컬러 · 가독성 · 레이아웃 완성도)

#### [CRITICAL] LOGO-01: 승인된 변형 사용
- **상태**: PASS / FAIL
- **기준**: 4개 브랜드 × 2개 타입만 허용
- **발견**: [실제 상태]
- **수정 방안**: [구체적 지시] (FAIL 시에만)

<!-- 모든 CRITICAL 항목 나열. PASS 항목도 기록 -->

### HIGH 항목 (타이포 · 그래픽 · 몰입도 · 브랜드 일관성)

#### [HIGH] TYPO-01: 승인 서체 사용
- **상태**: PASS / FAIL
- **기준**: Pretendard 또는 Sandol Dol만 허용
- **발견**: [실제 상태]
- **수정 방안**: [구체적 지시] (FAIL 시에만)

### MEDIUM 항목 (레이아웃)

#### [MEDIUM] LAYOUT-01: 포맷 비율 준수
- **상태**: PASS / FAIL
- **기준**: 지정 포맷 비율 사용
- **발견**: [실제 비율]
- **개선 제안**: [제안] (FAIL 시에만)

> 😎 미침(p) 등급은 리더가 별도 판단합니다.
```

---

## 5. 검수 프로세스

### 5.1 순서

1. **식별**: 대상 디자인 메타데이터 파악
   - 사용 브랜드 (Team Sparta / Sparta Club / Sparta Builders / 기업교육)
   - 콘텐츠 타입 (Content-Driven / Action-Driven / Message-Driven)
   - 레이아웃 포맷 (Mini 3:2 / Flex / Story 1:2 / Feed 4:5)
   - 타겟 매체 (Web / Mobile / SNS)
2. **CRITICAL 검수**: 로고(7) + 컬러(5) + 가독성(4) + 레이아웃 완성도(5) — 21항목 우선 검사
3. **HIGH 검수**: 타이포(6) + 그래픽(9) + 몰입도(5) + 브랜드 일관성(4) — 24항목 검사
4. **MEDIUM 검수**: 레이아웃(5) — 5항목 검사
5. **등급 산출**: 심각도별 FAIL 건수 집계 → 🔴/🟡/🟢 결정
6. **리포트 생성**: 위 형식에 따라 상세 결과 작성

### 5.2 FAIL 항목 수정 후 재검수

- FAIL 판정 시 수정 방안에 따라 수정 후 재검수 요청 가능
- 재검수 시 이전 리포트의 FAIL 항목만 재확인 (PASS 항목은 생략 가능)
- 재검수 리포트에 이전 판정과 현재 판정을 병기

### 5.3 예외 처리

- 체크리스트에 없는 새로운 유형의 위반 발견 시 → MEDIUM으로 기록 + 피드백 루프에 보고
- 가이드라인 모호 영역 → 판정 보류, `[AMBIGUOUS]` 태그 + 피드백 루프에 보고
- 의도적 가이드라인 이탈 (크리에이티브 디렉터 승인) → `[EXEMPTED]` 태그 + 사유 기록

---

## 6. 항목 ID 참조표

빠른 검색을 위한 전체 항목 요약.

| 심각도 | ID 범위 | 영역 | 항목 수 |
|--------|---------|------|---------|
| CRITICAL | `LOGO-01` ~ `LOGO-07` | 로고 | 7 |
| CRITICAL | `COLOR-01` ~ `COLOR-05` | 컬러 | 5 |
| CRITICAL | `QUAL-01` ~ `QUAL-04` | 가독성·접근성 | 4 |
| CRITICAL | `QUAL-05` ~ `QUAL-09` | 레이아웃 완성도 | 5 |
| HIGH | `TYPO-01` ~ `TYPO-06` | 타이포그래피 | 6 |
| HIGH | `GFX-01` ~ `GFX-09` | 그래픽 | 9 |
| HIGH | `QUAL-10` ~ `QUAL-14` | 콘텐츠 몰입도 | 5 |
| HIGH | `BRAND-01` ~ `BRAND-04` | 브랜드 일관성 | 4 |
| MEDIUM | `LAYOUT-01` ~ `LAYOUT-05` | 레이아웃 | 5 |
| **합계** | | | **50** |
