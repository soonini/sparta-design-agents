# CLAUDE.md

## 프로젝트 개요

**sparta-design-agents** - SPARTA(팀스파르타/스파르타클럽) 브랜드 디자인 에이전트 시스템.
PDF 브랜드 가이드라인을 실무 수준의 상세 스펙으로 변환하고, 이를 기반으로 동작하는 제작/검수 에이전트를 제공한다.

문서/설정 전용 레포지토리 (애플리케이션 코드 없음). 모든 콘텐츠는 Markdown과 JSON.

## 저장소 구조

```
sparta-design-agents/
├── agents/          # 서브에이전트 (YAML frontmatter + 시스템 프롬프트)
├── skills/          # 워크플로우 및 도메인 지식 (.md 또는 디렉토리/SKILL.md)
├── commands/        # 슬래시 커맨드 (YAML frontmatter + 지시사항)
├── rules/           # 항상 로드되는 가이드라인
├── hooks/           # hooks.json (PreToolUse, PostToolUse, Stop)
├── CLAUDE.md        # 이 파일
├── PLAN.md          # 구현 플랜 (팀 공유용)
├── HANDOVER.md      # 인수인계서
├── README.md
└── CONTRIBUTING.md
```

## 파일 컨벤션

- 모든 문서는 한국어로 작성
- 에이전트: YAML frontmatter 필수 (`name`, `description`, `tools`, `model`)
- 커맨드: YAML frontmatter 필수 (`description`)
- 파일명: 소문자 + 하이픈 (`sparta-design-creator.md`)
- 스킬: 단일 `.md` 또는 디렉토리 내 `SKILL.md`

## 협업 규칙 (필수 준수)

### 1. 토큰 절약
- 서브에이전트에 `model: haiku` 우선 사용 (단순 탐색/검색)
- 불필요한 파일 재읽기 금지 - 이미 읽은 내용은 컨텍스트에서 참조
- 병렬 처리 가능한 작업은 반드시 병렬 실행
- 긴 출력보다 핵심만 요약

### 2. CLAUDE.md 업데이트
- 새 파일 추가/제거 시 저장소 구조 섹션 업데이트
- 새 규칙/컨벤션 발생 시 즉시 반영
- 프로젝트 상태 변경 시 진행 상황 섹션 업데이트

### 3. 인수인계
- 모든 세션 종료 시 HANDOVER.md 업데이트
- 포함 내용: 완료된 작업, 진행 중인 작업, 다음 단계, 알려진 이슈
- 다른 작업자가 즉시 이어서 작업 가능한 수준으로 작성

### 4. Git 워크플로우
- 의미 있는 단위로 커밋 (feat/fix/refactor/docs)
- 브랜치 전략: main에서 직접 작업 (설정 레포이므로)
- 커밋 전 변경 내역 확인 필수

## 프로젝트 진행 상황

### 완료
- [x] 프로젝트 정리: 불필요한 파일 제거 (examples, plugins, mcp-configs, clickhouse-io, project-guidelines-example, 이미지)
- [x] 프로젝트명 변경: everything-claude-code → sparta-design-agents
- [x] README.md, CLAUDE.md 업데이트
- [x] 구현 플랜 수립 및 PLAN.md 작성
- [x] 프로젝트 문서/구조 정비 (.gitignore, CONTRIBUTING.md, HANDOVER.md 갱신)

### 다음 단계 (SPARTA 브랜드 시스템)
- [ ] Phase 1: `skills/sparta-brand-components/SKILL.md` (컴포넌트 라이브러리)
- [ ] Phase 2: `skills/sparta-review-checklist.md` (검수 체크리스트)
- [ ] Phase 3: `skills/sparta-design-guideline.md` (통합 가이드라인)
- [ ] Phase 4: `agents/sparta-design-creator.md` + `agents/sparta-design-reviewer.md`
- [ ] Phase 5: `commands/sparta-design.md` + `commands/sparta-review.md`

## 컨텍스트 윈도우 주의

MCP 서버가 너무 많으면 200k → ~70k로 축소됨. 프로젝트당 10개 미만 MCP, 80개 미만 도구 유지.
