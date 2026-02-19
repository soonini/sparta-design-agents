# sparta-design-agents

**SPARTA 브랜드 디자인 에이전트 시스템**

SPARTA(팀스파르타/스파르타클럽) 브랜드 가이드라인 PDF를 실무 수준의 상세 스펙으로 변환하고, 이를 기반으로 동작하는 디자인 제작 및 검수 에이전트를 제공합니다.

---

## 프로젝트 현황

Phase 1 완료, Phase 2부터 순차 구현 예정. 상세 내용은 [PLAN.md](PLAN.md) 참조.

| Phase | 산출물 | 상태 |
|-------|--------|------|
| 1 | `skills/sparta-brand-components/SKILL.md` — 컴포넌트 라이브러리 | **완료** |
| 2 | `skills/sparta-review-checklist.md` — 검수 체크리스트 | 대기 |
| 3 | `skills/sparta-design-guideline.md` — 통합 가이드라인 | 대기 |
| 4 | `agents/sparta-design-creator.md` + `agents/sparta-design-reviewer.md` | 대기 |
| 5 | `commands/sparta-design.md` + `commands/sparta-review.md` | 대기 |

---

## 저장소 구성

```
sparta-design-agents/
|-- agents/          # SPARTA 디자인 에이전트 (Phase 4)
|-- skills/
|   |-- sparta-brand-components/SKILL.md  # 컴포넌트 라이브러리 (완료)
|-- commands/        # 슬래시 커맨드 (Phase 5)
|-- CLAUDE.md        # 프로젝트 지침 및 협업 규칙
|-- PLAN.md          # 구현 플랜 (팀 공유용)
|-- HANDOVER.md      # 인수인계서
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
cp commands/*.md ~/.claude/commands/
cp -r skills/* ~/.claude/skills/
```

### 3. 브랜드 PDF 원본

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
