# SPARTA 브랜드 검수 체크리스트

> 이 스킬은 검수 에이전트가 디자인 산출물을 평가할 때 참조하는 판정 기준이다.
> 모든 항목은 `skills/sparta-brand-components/SKILL.md`의 규칙에서 도출됨.

## 사용 시점

- 검수 에이전트(`agents/sparta-design-reviewer.md`)가 이미지/HTML을 분석할 때
- 디자이너가 셀프 체크할 때
- `/sparta-review` 커맨드 실행 시 자동 참조

---

## 1. 심각도 정의

| 심각도 | 의미 | 조치 |
|--------|------|------|
| **CRITICAL** | 브랜드 아이덴티티 훼손. 외부 공개 시 브랜드 신뢰도 손상 | 반드시 수정 후 게시 |
| **HIGH** | 가이드라인 명시적 위반. 브랜드 일관성 저해 | 수정 강력 권장 |
| **MEDIUM** | 모범 사례 미준수. 품질 개선 여지 | 개선 고려 |

---

## 2. 판정 기준

| 판정 | 조건 |
|------|------|
| **PASS** | CRITICAL 0건 **AND** HIGH 0건 |
| **조건부 PASS** | CRITICAL 0건 **AND** HIGH 1~2건 |
| **FAIL** | CRITICAL 1건 이상 **OR** HIGH 3건 이상 |

MEDIUM 항목은 판정에 영향을 주지 않으나, 검수 리포트에 기록하여 개선을 유도한다.

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

### 3.3 타이포그래피 (HIGH)

| ID | 항목 | 기준 | 위반 예시 |
|----|------|------|-----------|
| `TYPO-01` | 승인 서체 사용 | Pretendard(주 서체) 또는 Sandol Dol(보조 서체)만 허용 | Arial, Noto Sans 등 미승인 서체 |
| `TYPO-02` | 위계 구조 준수 | Head → Title → Label → SubTitle → Body → Body List → Caption 순서 | Title 크기가 Head보다 큰 경우 |
| `TYPO-03` | Weight 규정 준수 | 레벨별 지정 Weight 사용 (Head: 800, Title: 700, SubTitle: 500, Body: 400) | Body 텍스트에 ExtraBold 적용 |
| `TYPO-04` | Line Height 준수 | Head: 110% / Title: 130% / SubTitle: 140% / Body: 160% | Head 텍스트에 160% 행간 |
| `TYPO-05` | 콘텐츠 타입별 서체 | Marketing A/B: Pretendard / Brand Message A/B: Sandol Dol + Pretendard | 마케팅 카피에 Sandol Dol 단독 사용 |
| `TYPO-06` | 금지사항 위반 없음 | 9가지 금지사항 전부 미해당 | 장평 변경, 텍스트 그림자, 아웃라인 처리 |

### 3.4 그래픽 (HIGH)

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

### 3.5 레이아웃 (MEDIUM)

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

## 요약

- **판정**: PASS / 조건부 PASS / FAIL
- **CRITICAL**: N건
- **HIGH**: N건
- **MEDIUM**: N건
- **대상**: [파일명 또는 설명]
- **콘텐츠 타입**: Content-Driven / Action-Driven / Message-Driven
- **검수일**: YYYY-MM-DD

## 상세 결과

### CRITICAL 항목

#### [CRITICAL] LOGO-01: 승인된 변형 사용
- **상태**: PASS / FAIL
- **기준**: 4개 브랜드 × 2개 타입만 허용
- **발견**: [실제 사용된 로고 설명]
- **수정 방안**: [구체적 수정 지시] (FAIL 시에만)

<!-- CRITICAL/HIGH 항목은 모두 나열, PASS 항목도 기록 -->

### HIGH 항목

#### [HIGH] TYPO-01: 승인 서체 사용
- **상태**: PASS / FAIL
- **기준**: Pretendard 또는 Sandol Dol만 허용
- **발견**: [실제 사용된 서체]
- **수정 방안**: [구체적 수정 지시] (FAIL 시에만)

### MEDIUM 항목

#### [MEDIUM] LAYOUT-01: 포맷 비율 준수
- **상태**: PASS / FAIL
- **기준**: 지정 포맷 비율 사용
- **발견**: [실제 비율]
- **개선 제안**: [제안] (FAIL 시에만)
```

---

## 5. 검수 프로세스

### 5.1 순서

1. **식별**: 대상 디자인 메타데이터 파악
   - 사용 브랜드 (Team Sparta / Sparta Club / Sparta Builders / 기업교육)
   - 콘텐츠 타입 (Content-Driven / Action-Driven / Message-Driven)
   - 레이아웃 포맷 (Mini 3:2 / Flex / Story 1:2 / Feed 4:5)
   - 타겟 매체 (Web / Mobile / SNS)
2. **CRITICAL 검수**: 로고(7항목) + 컬러(5항목) — 12항목 우선 검사
3. **HIGH 검수**: 타이포그래피(6항목) + 그래픽(9항목) — 15항목 검사
4. **MEDIUM 검수**: 레이아웃(5항목) — 5항목 검사
5. **판정**: 심각도별 건수 집계 → PASS/조건부 PASS/FAIL 결정
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
| HIGH | `TYPO-01` ~ `TYPO-06` | 타이포그래피 | 6 |
| HIGH | `GFX-01` ~ `GFX-09` | 그래픽 | 9 |
| MEDIUM | `LAYOUT-01` ~ `LAYOUT-05` | 레이아웃 | 5 |
| **합계** | | | **32** |
