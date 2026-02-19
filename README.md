# sparta-design-agents

**SPARTA 브랜드 디자인 에이전트 시스템**

SPARTA(팀스파르타/스파르타클럽) 브랜드 가이드라인 기반의 디자인 제작 및 검수 에이전트 시스템. 범용 Claude Code 설정(에이전트, 스킬, 훅, 커맨드, 규칙)과 SPARTA 브랜드 전용 에이전트를 함께 제공합니다.

> 범용 설정 원본: [affaan-m/everything-claude-code](https://github.com/affaan-m/everything-claude-code)

---

## 프로젝트 현황

구현 플랜 수립 완료, Phase 1부터 순차 구현 예정. 상세 내용은 [PLAN.md](PLAN.md) 참조.

| Phase | 산출물 | 상태 |
|-------|--------|------|
| 1 | 컴포넌트 라이브러리 (스킬) | 대기 |
| 2 | 검수 체크리스트 (스킬) | 대기 |
| 3 | 통합 가이드라인 (스킬) | 대기 |
| 4 | 제작/검수 에이전트 | 대기 |
| 5 | 슬래시 커맨드 | 대기 |

---

## 저장소 구성

```
sparta-design-agents/
|-- agents/           # 전문 서브에이전트
|   |-- planner.md           # 기능 구현 계획
|   |-- architect.md         # 시스템 설계 결정
|   |-- tdd-guide.md         # 테스트 주도 개발
|   |-- code-reviewer.md     # 품질 및 보안 검토
|   |-- security-reviewer.md # 취약점 분석
|   |-- build-error-resolver.md
|   |-- e2e-runner.md        # Playwright E2E 테스트
|   |-- refactor-cleaner.md  # 불필요한 코드 정리
|   |-- doc-updater.md       # 문서 동기화
|
|-- skills/           # 워크플로우 정의 및 도메인 지식
|   |-- coding-standards.md         # 언어 모범 사례
|   |-- backend-patterns.md         # API, 데이터베이스, 캐싱 패턴
|   |-- frontend-patterns.md        # React, Next.js 패턴
|   |-- tdd-workflow/               # TDD 방법론
|   |-- security-review/            # 보안 체크리스트
|
|-- commands/         # 슬래시 커맨드
|   |-- tdd.md              # /tdd - 테스트 주도 개발
|   |-- plan.md             # /plan - 구현 계획
|   |-- e2e.md              # /e2e - E2E 테스트 생성
|   |-- code-review.md      # /code-review - 품질 검토
|   |-- build-fix.md        # /build-fix - 빌드 오류 수정
|   |-- refactor-clean.md   # /refactor-clean - 불필요한 코드 제거
|   |-- test-coverage.md    # /test-coverage - 커버리지 분석
|   |-- update-codemaps.md  # /update-codemaps - 문서 갱신
|   |-- update-docs.md      # /update-docs - 문서 동기화
|
|-- rules/            # 항상 따라야 하는 가이드라인
|   |-- security.md         # 필수 보안 점검
|   |-- coding-style.md     # 불변성, 파일 구성
|   |-- testing.md          # TDD, 80% 커버리지 요구사항
|   |-- git-workflow.md     # 커밋 형식, PR 프로세스
|   |-- agents.md           # 서브에이전트에 위임할 시점
|   |-- performance.md      # 모델 선택, 컨텍스트 관리
|   |-- patterns.md         # API 응답 형식, 훅
|   |-- hooks.md            # 훅 문서
|
|-- hooks/            # 트리거 기반 자동화
|   |-- hooks.json          # PreToolUse, PostToolUse, Stop 훅
|
|-- CLAUDE.md         # 프로젝트 지침 및 협업 규칙
|-- PLAN.md           # 구현 플랜 (팀 공유용)
|-- HANDOVER.md       # 인수인계서
|-- README.md
|-- CONTRIBUTING.md
```

---

## 빠른 시작

### 1. 클론

```bash
git clone https://github.com/soonini/sparta-design-agents.git
cd sparta-design-agents
```

### 2. Claude Code 설정에 복사

```bash
cp agents/*.md ~/.claude/agents/
cp rules/*.md ~/.claude/rules/
cp commands/*.md ~/.claude/commands/
cp -r skills/* ~/.claude/skills/
```

### 3. hooks 설정

`hooks/hooks.json`의 훅을 `~/.claude/settings.json`에 병합하세요.

### 4. 브랜드 PDF 원본

SPARTA 브랜드 가이드라인 PDF 2종이 필요합니다 (용량 문제로 Git에 포함하지 않음):
- `SPARTA_Brand_Basic_Guide_V.1.0_compressed.pdf`
- `SPARTA_Brand_Application_Guide_V.1.0_compressed.pdf`

프로젝트 루트에 배치하면 에이전트가 참조합니다.

---

## 기여하기

기여 가이드라인은 [CONTRIBUTING.md](CONTRIBUTING.md)를 참조하세요.

---

## 라이선스

MIT

---

## 크레딧

- 범용 설정 원본: [affaan-m/everything-claude-code](https://github.com/affaan-m/everything-claude-code)
