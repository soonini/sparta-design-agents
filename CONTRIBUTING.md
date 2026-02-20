# 기여 가이드

SPARTA 브랜드 디자인 에이전트 시스템에 기여해 주셔서 감사합니다.

---

## 저장소 구조 이해

이 저장소는 애플리케이션 코드가 없는 **문서/설정 전용 레포**입니다.

| 폴더 | 내용 | 형식 |
|------|------|------|
| `agents/` | SPARTA 디자인 에이전트 시스템 프롬프트 | YAML frontmatter + Markdown |
| `skills/` | 브랜드 스펙, 가이드라인, 슬래시 커맨드 | 디렉토리 내 `SKILL.md` + YAML frontmatter |

---

## 기여 방법

### 1. 브랜치 생성

```bash
git checkout -b feat/my-contribution
```

### 2. 파일 추가/수정

적절한 디렉토리에 파일을 배치합니다.

### 3. 형식 준수

**에이전트** (`agents/*.md`):

```markdown
---
name: agent-name
description: 하는 일
tools: Read, Grep, Glob, Bash
model: sonnet
---

시스템 프롬프트 지시사항...
```

**참조 스킬** (`skills/*/SKILL.md`):

```markdown
---
name: sparta-brand-components
description: 브랜드 컴포넌트 라이브러리
user-invocable: false
---

# 스킬 이름
...
```

**액션 스킬 (슬래시 커맨드)** (`skills/*/SKILL.md`):

```markdown
---
name: sparta-design
description: SPARTA 브랜드 디자인 제작
disable-model-invocation: true
argument-hint: "[디자인 설명]"
---

# 커맨드 이름
...
```

### 4. 문서 동기화

파일을 추가/제거했다면:
- `CLAUDE.md` 저장소 구조 섹션 업데이트
- `README.md` 구조 트리 업데이트

### 5. 커밋 및 PR

```bash
git add .
git commit -m "feat: SPARTA 검수 체크리스트 추가"
git push origin feat/my-contribution
```

커밋 메시지는 [Conventional Commits](https://www.conventionalcommits.org/) 형식을 따릅니다:
`feat`, `fix`, `refactor`, `docs`, `test`, `chore`

---

## 파일 네이밍 규칙

- 소문자 + 하이픈: `sparta-design-creator.md`
- 설명적으로: `sparta-review-checklist.md` > `checklist.md`
- 에이전트/스킬 이름과 파일명 일치

---

## 가이드라인

### 해야 할 것

- 모든 문서는 한국어로 작성
- 기존 패턴을 따르기 (`PLAN.md`의 형식 참조)
- 제출 전 Claude Code에서 동작 확인
- 변경 내역을 `CLAUDE.md`에 반영

### 하지 말아야 할 것

- 민감한 데이터 포함 (API 키, 토큰, 비밀번호)
- 테스트하지 않은 설정 제출
- 중복 기능 생성

---

## 크레딧

범용 에이전트/스킬/커맨드 원본: [affaan-m/everything-claude-code](https://github.com/affaan-m/everything-claude-code)
