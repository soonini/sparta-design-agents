# 인수인계서 (HANDOVER)

> 마지막 업데이트: 2026-02-20

## 현재 상태: 프로젝트 초기 정리 완료

## 완료된 작업

### 프로젝트 정리
- 원본 오픈소스(affaan-m/everything-claude-code)에서 불필요한 파일 제거:
  - `everything-claude-coding.png` (6.3MB 장식 이미지)
  - `plugins/` (외부 플러그인 목록)
  - `examples/` (예시 설정 템플릿)
  - `mcp-configs/` (플레이스홀더 API 키)
  - `skills/clickhouse-io.md` (ClickHouse 전용)
  - `skills/project-guidelines-example.md` (예시 템플릿)

### 프로젝트명 변경
- everything-claude-code → **sparta-design-agents**
- README.md: 프로젝트 설명, 구조 트리, 설치 방법 전면 재작성
- CLAUDE.md: 협업 규칙(토큰 절약, 인수인계, CLAUDE.md 업데이트) 추가

## 유지된 범용 설정 (활용 가능)

| 폴더 | 파일 수 | 핵심 |
|-------|---------|------|
| agents/ | 9 | planner, architect, tdd-guide, code-reviewer, security-reviewer, build-error-resolver, e2e-runner, refactor-cleaner, doc-updater |
| skills/ | 5 | coding-standards, frontend-patterns, backend-patterns, tdd-workflow/, security-review/ |
| commands/ | 9 | /plan, /tdd, /e2e, /code-review, /build-fix, /refactor-clean, /test-coverage, /update-codemaps, /update-docs |
| rules/ | 8 | security, coding-style, testing, git-workflow, agents, performance, patterns, hooks |
| hooks/ | 1 | hooks.json (PreToolUse 3 + PostToolUse 4 + Stop 1) |

## 진행 중인 작업

- GitHub 원격 레포 연결 (아직 미완료)

## 다음 단계

### 즉시 해야 할 것
1. GitHub 레포 생성 및 push
2. 레퍼런스 스킬 설치 (Phase 0)

### SPARTA 브랜드 시스템 구현 순서
1. `skills/sparta-brand-components/SKILL.md` - PDF → 실무 스펙 변환 (~600줄)
2. `skills/sparta-review-checklist.md` - 검수 체크리스트 (~350줄)
3. `skills/sparta-design-guideline.md` - 통합 가이드라인 (~400줄)
4. `agents/sparta-design-reviewer.md` - 검수 에이전트
5. `agents/sparta-design-creator.md` - 제작 에이전트
6. `commands/sparta-design.md` + `commands/sparta-review.md` - 슬래시 커맨드

### 참고
- 구현 플랜 상세: SPARTA 브랜드 PDF 가이드라인 필요
- 에이전트 프론트매터 형식은 기존 `agents/code-reviewer.md` 참조
- 스킬 디렉토리 형식은 `skills/security-review/SKILL.md` 참조

## 알려진 이슈

- 로컬 폴더명이 아직 `everything-claude-code`로 되어 있음 (GitHub 레포명은 `sparta-design-agents`로 설정 예정)
- SPARTA 브랜드 PDF 가이드라인 파일이 아직 레포에 없음 (Phase 1 시작 시 필요)
