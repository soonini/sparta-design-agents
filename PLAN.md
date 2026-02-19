# SPARTA 브랜드 디자인 에이전트 시스템 구현 플랜

> 최종 업데이트: 2026-02-20

## 1. 배경

SPARTA(팀스파르타/스파르타클럽)의 브랜드 디자인 가이드라인이 PDF로 존재하지만 컨셉 수준이라 실무에서 직접 활용하기 어렵다. 이를 **실무 수준의 상세 스펙**으로 변환하고, 이를 기반으로 동작하는 **제작 에이전트**와 **검수 에이전트**를 만든다.

**핵심 원칙**: PDF 컨셉 → 컴포넌트 라이브러리 + 상세 가이드라인 수립 → 검수 체크리스트 정의 → 두 에이전트가 이를 참조

## 2. 목표

| 목표 | 설명 |
|------|------|
| 브랜드 스펙 정형화 | PDF 가이드라인을 구조화된 마크다운 스펙으로 변환 |
| 제작 자동화 | AI 에이전트가 가이드라인 준수 디자인 시안 + HTML/CSS 코드 생성 |
| 검수 자동화 | AI 에이전트가 이미지 분석 후 PASS/FAIL 판정 + 수정 제안 |
| 슬래시 커맨드 | `/sparta-design`, `/sparta-review`로 즉시 호출 |

## 3. 산출물 목록

### 스킬 (4개)

| 파일 | 설명 | 예상 분량 |
|------|------|-----------|
| `skills/sparta-brand-components/SKILL.md` | 컴포넌트 라이브러리 (디자인 토큰, 로고, 컬러, 타이포, 그래픽, 레이아웃) | ~600줄 |
| `skills/sparta-review-checklist.md` | 검수 체크리스트 (심각도별 판정 기준) | ~350줄 |
| `skills/sparta-design-guideline.md` | 통합 상세 가이드라인 (콘텐츠 유형별 적용 규칙) | ~400줄 |
| `skills/sparta-feedback-loop.md` | 피드백 수집/분석 규칙, 학습 루프 정의 | ~200줄 |

### 에이전트 (2개)

| 파일 | 설명 | 모델 |
|------|------|------|
| `agents/sparta-design-creator.md` | 제작 에이전트: 시안 제안 + HTML/CSS 코드 생성 | opus |
| `agents/sparta-design-reviewer.md` | 검수 에이전트: 이미지 분석 후 PASS/FAIL 판정 | opus |

### 커맨드 (4개)

| 파일 | 사용법 |
|------|--------|
| `commands/sparta-design.md` | `/sparta-design [설명]` → 제작 에이전트 호출 |
| `commands/sparta-review.md` | `/sparta-review [이미지경로]` → 검수 에이전트 호출 |
| `commands/sparta-feedback.md` | `/sparta-feedback [코멘트]` → 피드백 제출 |
| `commands/sparta-learn.md` | `/sparta-learn` → 축적 피드백 분석 및 개선 제안 |

## 4. 구현 단계

### Phase 0: 사전 준비/ㅊ

레퍼런스 스킬 설치:
- `figma/mcp-server-guide@create-design-system-rules` — Figma MCP 도구 활용법
- `holo00/ideaforge@brand-guidelines` — 컬러 시스템, 타이포 스케일, 컴포넌트 표준 참고

### Phase 1: 컴포넌트 라이브러리

**파일**: `skills/sparta-brand-components/SKILL.md`

PDF 가이드라인에서 추출할 항목:

| 섹션 | 포함 내용 |
|------|-----------|
| 디자인 토큰 | CSS 변수 형태 컬러 팔레트, 타이포 토큰, 스페이싱 토큰 (4px 그리드) |
| 로고 | 4개 브랜드별 변형, 최소 크기, 클리어 스페이스, 배치 유형, 금지사항 9가지 |
| 컬러 시스템 | Accent + Text + Background 조합 규칙, 3색 제한, Primary/Secondary Pairing |
| 타이포그래피 | Pretendard/Sandol Dol, 7단계 위계 테이블, 콘텐츠 유형별 적용 |
| 그래픽 | Potential Cube 모티프, 프레임 타입 (4레이어 구조), 패턴, 태그 |
| 레이아웃 그리드 | 포맷별 규격 (Mini Banner, Web-Flex, Story-AD, Feed/Pop-Up) |
| CSS 변수 템플릿 | 모든 토큰을 CSS Custom Properties로 정의한 복사 가능 코드 블록 |

### Phase 2: 검수 체크리스트

**파일**: `skills/sparta-review-checklist.md`

**심각도 정의:**
- **CRITICAL**: 브랜드 아이덴티티 훼손 → 반드시 수정 후 게시
- **HIGH**: 가이드라인 명시적 위반 → 수정 권장
- **MEDIUM**: 모범 사례 미준수 → 개선 고려

**체크리스트 영역:**

| 영역 | 심각도 | 주요 항목 |
|------|--------|-----------|
| 로고 | CRITICAL | 승인 변형, 최소 크기, 클리어 스페이스, 금지사항, 배경 조합 |
| 컬러 | CRITICAL | 승인 팔레트, 3색 조합 규칙, Pairing 규칙, 가독성 대비 |
| 타이포그래피 | HIGH | 승인 폰트, 위계 구조, weight/size/line-height, 금지사항 |
| 그래픽 | HIGH | 프레임 4레이어, 패턴 규격, 태그 형태 |
| 레이아웃 | MEDIUM | 포맷 비율, 마진 및 안전 영역 |

**판정 기준:**
- **PASS**: CRITICAL 0건, HIGH 0건
- **조건부 PASS**: CRITICAL 0건, HIGH 1~2건
- **FAIL**: CRITICAL 1건 이상 또는 HIGH 3건 이상

### Phase 3: 통합 상세 가이드라인

**파일**: `skills/sparta-design-guideline.md`

| 섹션 | 내용 |
|------|------|
| 콘텐츠 유형별 적용 | Content-Driven / Action-Driven / Message-Driven 별 텍스트 비중, 계층, 이미지 처리 |
| 레이아웃 포맷별 적용 | 각 포맷에서의 텍스트 배치, 그래픽 영역, 로고 위치 |
| 브랜드별 분기 | Team Sparta / Sparta Club / Sparta Builders / 기업교육별 차이 |
| DO / DON'T | PDF의 Incorrect Usage 예시를 텍스트로 기술 |
| HTML/CSS 생성 규칙 | 단일 .html, inline CSS, Pretendard CDN, placeholder div, CSS 변수 참조 |

### Phase 4: 에이전트 구현

#### 제작 에이전트 (`agents/sparta-design-creator.md`)

워크플로우:
1. 요청 분석 (브랜드, 목적, 타겟, 콘텐츠 유형 파악)
2. 스킬 참조하여 텍스트 시안 제안 (레이아웃, 컬러 조합, 타이포, 그래픽 요소)
3. 사용자 확인 대기
4. HTML/CSS 코드 생성 + Figma 스펙 첨부

#### 검수 에이전트 (`agents/sparta-design-reviewer.md`)

워크플로우:
1. 이미지 분석 (콘텐츠 유형, 사용 브랜드 식별)
2. 체크리스트 항목별 순차 검수
3. 검수 리포트 생성 (PASS/조건부 PASS/FAIL + 상세 결과)

검수 리포트 형식:
```
# SPARTA 브랜드 검수 리포트

## 요약
- 판정: PASS / 조건부 PASS / FAIL
- CRITICAL: N건 / HIGH: N건 / MEDIUM: N건

## 상세 결과
### [CRITICAL] 항목명
- 상태: FAIL
- 기준: [규칙 참조]
- 발견: [실제 상태]
- 수정 방안: [구체적 수정 지시]
```

### Phase 5: 슬래시 커맨드

| 커맨드 | 예시 |
|--------|------|
| `/sparta-design` | `/sparta-design 내일배움캠프 신규 과정 런칭 프로모션 배너` |
| `/sparta-review` | `/sparta-review ./designs/banner-v2.png` |

### Phase 6: 피드백 루프

팀 사용자들의 피드백을 수집·분석하여 가이드라인과 체크리스트를 지속 개선하는 학습 시스템.

**디렉토리 구조:**

```
feedback/
├── log.jsonl       # 피드백 누적 저장소 (append-only)
└── SUMMARY.md      # 주기적 분석 결과
```

**산출물:**

| 파일 | 역할 |
|------|------|
| `skills/sparta-feedback-loop.md` | 피드백 수집/분석 규칙, 로그 스키마, 학습 알고리즘 정의 |
| `commands/sparta-feedback.md` | `/sparta-feedback` — 팀원이 제작/검수 결과에 피드백 제출 |
| `commands/sparta-learn.md` | `/sparta-learn` — 축적된 피드백 분석 → 체크리스트/가이드라인 개선 제안 |

**피드백 로그 스키마 (log.jsonl):**

```json
{
  "date": "2026-02-20",
  "type": "review|design|general",
  "author": "작성자",
  "asset": "대상 파일명 또는 설명",
  "verdict": "PASS|CONDITIONAL_PASS|FAIL|N/A",
  "violations": ["위반-항목-id"],
  "suggestion": "개선 제안 텍스트",
  "resolved": false
}
```

**학습 루프 워크플로우:**

1. **수집**: `/sparta-review` 실행 → 검수 결과 자동 로깅 / `/sparta-feedback` → 팀원 수동 피드백 추가
2. **축적**: `feedback/log.jsonl`에 append
3. **분석**: `/sparta-learn` 실행 → 패턴 분석 (반복 위반 항목, 자주 발생하는 질문, 가이드라인 모호 영역 식별)
4. **제안**: 체크리스트 항목 추가/강조, 가이드라인 명확화, DO/DON'T 보강 등 구체적 개선안 초안 생성
5. **검토**: 팀 리더가 개선안 검토 후 승인/거절 결정
6. **반영**: 승인된 개선안을 해당 스킬/체크리스트 파일에 반영
7. **요약**: `feedback/SUMMARY.md` 업데이트 (누적 통계, 학습 포인트, 개선 이력)

**분석 메트릭:**

| 메트릭 | 설명 |
|--------|------|
| 위반 빈도 TOP 5 | 가장 자주 발생하는 위반 항목 → 체크리스트 강조 대상 |
| FAIL 비율 추이 | 시간에 따른 FAIL 비율 변화 → 팀 학습 효과 측정 |
| 모호 영역 | 같은 항목에 PASS/FAIL 판정이 혼재 → 가이드라인 명확화 대상 |
| 미해결 피드백 | resolved=false 항목 → 액션 필요 |

## 5. 빌드 순서 및 의존관계

```
Phase 1                    Phase 2
[컴포넌트 라이브러리] ──→ [검수 체크리스트]
        │                      │
        ▼                      │
     Phase 3                   │
[통합 가이드라인] ◄────────────┘
        │                      │
        ▼                      ▼
     Phase 4a               Phase 4b
[제작 에이전트] ◄──── [검수 에이전트]
        │                      │
        └──────┬───────────────┘
               ▼
            Phase 5
      [슬래시 커맨드 2개]
               │
               ▼
            Phase 6
        [피드백 루프]
  (스킬 1 + 커맨드 2 + feedback/)
```

| 순서 | 파일 | 이유 |
|------|------|------|
| 1 | `skills/sparta-brand-components/SKILL.md` | 모든 파일의 기반. PDF → 실무 스펙 변환 |
| 2 | `skills/sparta-review-checklist.md` | 합격 기준 정의. 가이드라인의 검증 기준 역할 |
| 3 | `skills/sparta-design-guideline.md` | 스펙을 어떻게 적용하는지의 실무 가이드 |
| 4 | `agents/sparta-design-reviewer.md` | 검수가 먼저 있어야 제작물 검증 가능 |
| 5 | `agents/sparta-design-creator.md` | 제작 + 검수 연계 |
| 6 | `commands/sparta-design.md` + `commands/sparta-review.md` | 슬래시 커맨드 래퍼 |
| 7 | `skills/sparta-feedback-loop.md` + `commands/sparta-feedback.md` + `commands/sparta-learn.md` | 피드백 수집·분석·학습 루프 |

## 6. 컨텍스트 윈도우 예산

| 컴포넌트 | 예상 토큰 | 로드 시점 |
|----------|-----------|-----------|
| sparta-brand-components | ~4,000–5,000 | 항상 (두 에이전트 공통) |
| sparta-design-guideline | ~2,500–3,000 | 제작 에이전트 |
| sparta-review-checklist | ~2,500–3,000 | 검수 에이전트 |
| 에이전트 프롬프트 | ~1,500–2,000 | 호출 시 |

- **제작 시 총**: ~8,000–10,000 토큰 → 충분한 여유
- **검수 시 총**: ~8,000–10,000 토큰 → 충분한 여유

## 7. 검증 방법

| 검증 | 방법 |
|------|------|
| 컴포넌트 라이브러리 | PDF 가이드와 대조하여 모든 수치 정확성 확인 |
| 제작 에이전트 | `/sparta-design 스파르타클럽 AI 과정 런칭 배너` 실행 → HTML/CSS 출력 → 브라우저에서 시각 확인 |
| 검수 에이전트 | 생성된 HTML 스크린샷 → `/sparta-review` 실행 → 검수 리포트 확인 |
| 교차 검증 | 의도적 가이드라인 위반 디자인 투입 → 검수 에이전트 정확도 확인 |

## 8. 참조할 기존 패턴

| 대상 | 참고 파일 |
|------|-----------|
| 에이전트 프론트매터 | `agents/code-reviewer.md` |
| 스킬 디렉토리 구조 | `skills/security-review/SKILL.md` |
| 커맨드 형식 | `commands/e2e.md` |
| 검수 리포트 | `agents/code-reviewer.md`의 CRITICAL/HIGH/MEDIUM 형식 |
