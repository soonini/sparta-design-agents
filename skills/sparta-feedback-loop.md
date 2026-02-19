# SPARTA 브랜드 피드백 루프

> 팀 사용자들의 피드백을 수집·분석하여 가이드라인과 체크리스트를 지속 개선하는 학습 시스템.
> `/sparta-feedback`으로 피드백 제출, `/sparta-learn`으로 분석 및 개선 제안.

## 사용 시점

- `/sparta-feedback` 커맨드 실행 시 → 피드백 로깅 규칙 참조
- `/sparta-learn` 커맨드 실행 시 → 분석 알고리즘 및 메트릭 참조
- `/sparta-review` 검수 완료 후 → 검수 결과 자동 로깅
- `/sparta-design` 제작 완료 후 → 제작 결과 수동 피드백 가능

---

## 1. 데이터 저장소

### 1.1 디렉토리 구조

```
feedback/
├── log.jsonl       # 피드백 누적 저장소 (append-only)
└── SUMMARY.md      # 주기적 분석 결과
```

### 1.2 로그 스키마 (`log.jsonl`)

한 줄에 하나의 JSON 객체. **append-only** — 기존 항목을 수정하지 않고 새 항목만 추가한다.

```json
{
  "id": "FB-20260220-001",
  "date": "2026-02-20",
  "type": "review",
  "author": "작성자",
  "asset": "대상 파일명 또는 설명",
  "verdict": "PASS",
  "violations": ["LOGO-03", "COLOR-02"],
  "tags": [],
  "suggestion": "개선 제안 텍스트",
  "resolved": false
}
```

#### 필드 정의

| 필드 | 타입 | 필수 | 설명 |
|------|------|------|------|
| `id` | string | Y | `FB-YYYYMMDD-NNN` 형식. 당일 순번 자동 채번 |
| `date` | string | Y | ISO 날짜 (`YYYY-MM-DD`) |
| `type` | enum | Y | `review` / `design` / `general` |
| `author` | string | Y | 피드백 작성자 이름 또는 ID |
| `asset` | string | Y | 대상 파일 경로 또는 디자인 설명 |
| `verdict` | enum | N | `PASS` / `CONDITIONAL_PASS` / `FAIL` / `N/A`. 검수 결과 연계 시 사용 |
| `violations` | string[] | N | 위반 항목 ID 목록 (예: `["LOGO-03", "COLOR-02"]`) |
| `tags` | string[] | N | `AMBIGUOUS` / `EXEMPTED` / `NEW` / 자유 태그 |
| `suggestion` | string | Y | 개선 제안 또는 코멘트 |
| `resolved` | boolean | Y | 해결 여부. 초기값 `false` |

#### type별 용도

| type | 입력 경로 | 설명 |
|------|-----------|------|
| `review` | `/sparta-review` 완료 후 자동 | 검수 결과 로깅 (verdict, violations 포함) |
| `design` | `/sparta-feedback` 수동 제출 | 제작물에 대한 팀원 피드백 |
| `general` | `/sparta-feedback` 수동 제출 | 가이드라인 자체에 대한 의견, 모호 영역 보고 |

---

## 2. 피드백 수집

### 2.1 자동 수집 (검수 완료 시)

`/sparta-review` 완료 후 검수 결과를 `log.jsonl`에 자동 기록:

1. 검수 리포트에서 verdict, violations 추출
2. 새 로그 엔트리 생성 (`type: "review"`)
3. `feedback/log.jsonl`에 append
4. 사용자에게 로깅 완료 알림

### 2.2 수동 수집 (`/sparta-feedback`)

팀원이 직접 피드백을 제출:

1. 사용자 입력에서 대상(`asset`)과 코멘트(`suggestion`) 추출
2. `type`을 `design` 또는 `general`로 분류
3. 작성자(`author`) 확인 — 미제공 시 질문
4. 새 로그 엔트리 생성
5. `feedback/log.jsonl`에 append
6. 등록 확인 메시지 출력

### 2.3 ID 채번 규칙

```
FB-{YYYYMMDD}-{NNN}
```

- `YYYYMMDD`: 피드백 등록일
- `NNN`: 당일 순번 (001부터 시작)
- 기존 `log.jsonl`에서 동일 날짜의 마지막 ID를 읽어 +1

---

## 3. 피드백 분석 (`/sparta-learn`)

### 3.1 분석 워크플로우

1. **로드**: `feedback/log.jsonl` 전체 읽기
2. **분류**: type별, 날짜별, violation별 그룹핑
3. **메트릭 산출**: 아래 4가지 핵심 메트릭 계산
4. **패턴 식별**: 반복 위반, 모호 영역, 미해결 항목 도출
5. **개선안 생성**: 체크리스트/가이드라인 수정 초안 제시
6. **요약 갱신**: `feedback/SUMMARY.md` 업데이트

### 3.2 핵심 메트릭

| 메트릭 | 산출 방법 | 활용 |
|--------|-----------|------|
| **위반 빈도 TOP 5** | violations 필드에서 항목별 빈도 집계 → 상위 5개 | 체크리스트 강조 대상 식별 |
| **FAIL 비율 추이** | 월별 `(FAIL 건수 / 전체 review 건수) × 100` | 팀 학습 효과 측정 |
| **모호 영역** | 동일 항목에 PASS/FAIL 판정 혼재 비율 > 30% | 가이드라인 명확화 대상 |
| **미해결 피드백** | `resolved: false` 항목 수 | 액션 필요 항목 파악 |

### 3.3 개선안 유형

| 유형 | 트리거 | 대상 파일 |
|------|--------|-----------|
| **체크리스트 항목 추가** | `tags`에 `NEW`가 3건 이상 동일 패턴 | `skills/sparta-review-checklist.md` |
| **체크리스트 항목 강조** | 위반 빈도 TOP 5 항목 | `skills/sparta-review-checklist.md` |
| **가이드라인 명확화** | 모호 영역 메트릭 > 30% 항목 | `skills/sparta-design-guideline.md` |
| **DO/DON'T 보강** | 반복 위반 패턴에서 구체적 사례 도출 | `skills/sparta-design-guideline.md` |
| **컴포넌트 규격 수정** | 실무 적용 불가 피드백 (`general` type) | `skills/sparta-brand-components/SKILL.md` |

### 3.4 개선안 출력 형식

```markdown
# SPARTA 피드백 분석 결과

## 분석 기간
- 기간: YYYY-MM-DD ~ YYYY-MM-DD
- 총 피드백: N건 (review: N / design: N / general: N)

## 핵심 메트릭

### 위반 빈도 TOP 5
| 순위 | 항목 | 빈도 | 심각도 |
|------|------|------|--------|
| 1 | COLOR-02 | 12건 | CRITICAL |
| ... | ... | ... | ... |

### FAIL 비율 추이
| 월 | 전체 | FAIL | 비율 |
|----|------|------|------|
| 2026-01 | 20 | 8 | 40% |
| 2026-02 | 25 | 5 | 20% |

### 모호 영역
| 항목 | PASS | FAIL | 혼재율 |
|------|------|------|--------|
| GFX-02 | 5 | 4 | 44% |

### 미해결 피드백
- 총 N건 (review: N / design: N / general: N)

## 개선 제안

### 1. [체크리스트 항목 추가] 새 항목 제안
- **근거**: NEW 태그 피드백 N건에서 공통 패턴 발견
- **제안 항목**: `GFX-10: 설명...`
- **대상 파일**: `skills/sparta-review-checklist.md`

### 2. [가이드라인 명확화] GFX-02 기준 보강
- **근거**: 모호 영역 (혼재율 44%)
- **현재**: "프레임이 잘리더라도 3면 이상 화면에 보여야 함"
- **제안**: 구체적 수치 또는 예시 추가
- **대상 파일**: `skills/sparta-design-guideline.md`
```

---

## 4. 요약 파일 (`feedback/SUMMARY.md`)

### 4.1 갱신 시점

- `/sparta-learn` 실행 시 자동 갱신
- 수동 갱신 불필요

### 4.2 포함 내용

| 섹션 | 내용 |
|------|------|
| 마지막 분석일 | 분석 실행 날짜 |
| 누적 통계 | 전체/type별 피드백 건수, FAIL 비율 |
| 위반 빈도 TOP 5 | 최근 분석 기준 |
| 학습 포인트 | 팀이 자주 실수하는 영역 요약 |
| 개선 이력 | 과거 개선안 반영 내역 (날짜, 내용, 대상 파일) |
| 미해결 항목 | 아직 처리되지 않은 피드백 수 |

---

## 5. 연계 규칙

### 5.1 검수 체크리스트 연계

`skills/sparta-review-checklist.md` 5.3절 예외 처리에서 정의된 태그:

| 태그 | 발생 시점 | 피드백 루프 동작 |
|------|-----------|-----------------|
| `AMBIGUOUS` | 가이드라인 모호 영역 | `tags: ["AMBIGUOUS"]`로 로깅 → 모호 영역 메트릭에 반영 |
| `EXEMPTED` | 의도적 가이드라인 이탈 | `tags: ["EXEMPTED"]`로 로깅 → 분석에서 제외 |
| `NEW` | 체크리스트에 없는 새 위반 | `tags: ["NEW"]`로 로깅 → 항목 추가 제안 트리거 |

### 5.2 검수 에이전트 연계

`agents/sparta-design-reviewer.md`가 검수 완료 시:

1. 검수 리포트 출력
2. verdict + violations를 피드백 로그에 자동 기록
3. AMBIGUOUS/NEW 태그 항목이 있으면 별도 강조

### 5.3 제작 에이전트 연계

`agents/sparta-design-creator.md`가 셀프 검수에서 FAIL 발견 시:

1. 수정 후 재확인
2. 최종 결과를 피드백 로그에 기록 가능 (선택)

---

## 6. 운영 가이드

### 6.1 피드백 해결 처리

미해결 피드백(`resolved: false`)을 처리할 때:

1. 해당 피드백의 개선안이 반영되었는지 확인
2. 반영 완료 시 새 로그 엔트리 추가 (`resolved: true`는 원본 수정이 아닌 해결 기록 추가로 처리)

```json
{
  "id": "FB-20260220-001-resolved",
  "date": "2026-02-25",
  "type": "general",
  "author": "팀 리더",
  "asset": "FB-20260220-001",
  "verdict": "N/A",
  "violations": [],
  "tags": ["resolved"],
  "suggestion": "COLOR-02 가이드라인에 구체적 예시 추가 완료",
  "resolved": true
}
```

### 6.2 분석 주기

- **권장**: 피드백 10건 이상 축적 시 `/sparta-learn` 실행
- **최소**: 월 1회
- 분석 결과는 팀 리더가 검토 후 승인/거절 결정

### 6.3 개선안 반영 절차

1. `/sparta-learn`이 개선안 초안 생성
2. 팀 리더가 검토
3. 승인된 개선안을 해당 스킬/체크리스트 파일에 직접 반영
4. 반영 이력을 `feedback/SUMMARY.md`에 기록
5. 관련 미해결 피드백을 해결 처리
