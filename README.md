# sparta-design-agents

**SPARTA 브랜드 디자인 에이전트 시스템 — 사용 설명서**

SPARTA(팀스파르타/스파르타클럽) 브랜드 가이드라인을 AI가 자동으로 지켜주는 디자인 도우미입니다.
배너, 광고, 피드 이미지 등을 브랜드 규정에 맞게 **제작**하고, 기존 디자인을 **검수**할 수 있습니다.

---

## 이런 분들을 위한 도구입니다

- 브랜드 가이드라인 PDF를 매번 열어보기 번거로운 디자이너
- "이 로고 색상 맞나?", "여백이 충분한가?" 매번 확인하기 힘든 마케터
- SPARTA 브랜드 콘텐츠를 빠르게 만들어야 하는 팀원 누구나

---

## 무엇을 할 수 있나요?

이 시스템은 **4가지 명령어**를 제공합니다:

| 명령어 | 한 줄 설명 | 사용 상황 |
|--------|-----------|----------|
| `/sparta-design` | 브랜드 규정을 지키는 디자인을 새로 만듭니다 | 배너, 광고, 피드 이미지 등을 제작할 때 |
| `/sparta-review` | 만들어진 디자인이 규정에 맞는지 검사합니다 | 디자인 완성 후 브랜드 적합성을 확인할 때 |
| `/sparta-feedback` | 디자인에 대한 의견을 기록합니다 | 수정 요청이나 개선 의견을 남길 때 |
| `/sparta-learn` | 쌓인 피드백을 분석하여 개선점을 찾습니다 | 반복되는 문제를 파악하고 가이드라인을 개선할 때 |

---

## 시작하기 전에 필요한 것

1. **Claude Code** (Anthropic의 CLI 도구)가 설치되어 있어야 합니다
2. **SPARTA 브랜드 가이드라인 PDF 2종** (용량 문제로 이 저장소에 포함되어 있지 않음):
   - `SPARTA_Brand_Basic_Guide_V.1.0_compressed.pdf`
   - `SPARTA_Brand_Application_Guide_V.1.0_compressed.pdf`

---

## 설치 방법 (처음 한 번만 하면 됩니다)

### Step 1. 저장소 다운로드

터미널을 열고 아래 명령어를 입력합니다:

```bash
git clone https://github.com/soonini/sparta-design-agents.git
cd sparta-design-agents
```

> 터미널이 익숙하지 않다면: GitHub 페이지에서 초록색 "Code" 버튼 → "Download ZIP"으로 다운로드한 뒤 압축을 풀어도 됩니다.

### Step 2. Claude Code 설정 폴더에 복사

아래 명령어를 한 줄씩 입력합니다:

```bash
cp agents/*.md ~/.claude/agents/
cp commands/*.md ~/.claude/commands/
cp -r skills/* ~/.claude/skills/
```

> 이 명령어는 에이전트, 명령어, 스킬 파일을 Claude Code가 인식하는 폴더에 복사합니다.
> `~/.claude/` 폴더가 없다면 Claude Code를 한 번 실행하면 자동으로 생성됩니다.

### Step 3. 브랜드 PDF 배치

SPARTA 브랜드 가이드라인 PDF 2종을 다운로드받은 `sparta-design-agents` 폴더 안에 넣어주세요.
에이전트가 디자인 작업 시 이 PDF를 참고합니다.

### 설치 확인

Claude Code를 실행한 뒤 `/sparta-design 테스트`를 입력해 보세요.
에이전트가 브랜드, 콘텐츠 타입 등을 질문하면 정상적으로 설치된 것입니다.

---

## 사용 방법

### 1. 디자인 제작 (`/sparta-design`)

브랜드 가이드라인을 자동으로 지키면서 디자인 시안과 HTML/CSS 코드를 만들어줍니다.

**사용법:**

```
/sparta-design [만들고 싶은 디자인 설명]
```

**실제 사용 예시:**

```
/sparta-design 내일배움캠프 신규 과정 런칭 프로모션 배너
/sparta-design 스파르타클럽 AI 과정 할인 이벤트 스토리 광고
/sparta-design Team Sparta 기업 브랜딩 메시지 피드 이미지
```

**진행 과정:**

1. 에이전트가 요청을 분석하고, 부족한 정보가 있으면 질문합니다
2. 컬러, 레이아웃, 타이포를 결정한 **텍스트 시안**을 먼저 보여줍니다
3. 시안을 확인하고 수정 요청을 할 수 있습니다 (마음에 들 때까지 반복 가능)
4. 승인하면 완성된 **HTML/CSS 파일**을 생성합니다
5. 마지막으로 32개 항목의 **셀프 검수**를 자동으로 수행합니다

> 시안 승인 전에는 코드를 생성하지 않으므로, 편하게 수정 요청하세요.

---

### 2. 디자인 검수 (`/sparta-review`)

이미 만들어진 디자인(이미지 또는 HTML 파일)이 브랜드 가이드라인에 맞는지 검사합니다.

**사용법:**

```
/sparta-review [검수할 파일 경로]
```

**실제 사용 예시:**

```
/sparta-review ./designs/banner-v2.png
/sparta-review ./output/promo-banner.html
/sparta-review ~/Desktop/sparta-feed-image.png
```

**검수 항목 (총 32개):**

| 카테고리 | 항목 수 | 심각도 | 검사 내용 |
|---------|--------|--------|----------|
| 로고 | 7개 | CRITICAL | 로고 크기, 여백, 색상, 금지 변형 등 |
| 컬러 | 5개 | CRITICAL | 브랜드 컬러 정확도, 조합 규칙 등 |
| 타이포그래피 | 6개 | HIGH | 폰트, 크기, 줄간격, 자간 등 |
| 그래픽 | 9개 | HIGH | 아이콘, 일러스트, 사진 규격 등 |
| 레이아웃 | 5개 | MEDIUM | 여백, 정렬, Safe Area 등 |

**판정 결과:**

| 판정 | 의미 |
|------|------|
| **PASS** | CRITICAL 0건, HIGH 0건 — 바로 사용 가능 |
| **조건부 PASS** | CRITICAL 0건, HIGH 1~2건 — 수정 권장 |
| **FAIL** | CRITICAL 1건 이상 또는 HIGH 3건 이상 — 수정 필수 |

> 검수 결과에는 위반 항목별 구체적인 수정 방법도 함께 제시됩니다.

---

### 3. 피드백 기록 (`/sparta-feedback`)

디자인에 대한 의견이나 수정 요청을 기록합니다. 기록된 피드백은 나중에 분석하여 가이드라인 개선에 활용됩니다.

**사용법:**

```
/sparta-feedback [의견 내용]
```

**실제 사용 예시:**

```
/sparta-feedback 내배캠 배너에서 로고 클리어 스페이스가 너무 좁아 보입니다
/sparta-feedback COLOR-02 기준이 모호합니다 — 그레이스케일과 유채색 경계가 불명확
/sparta-feedback ./designs/event-banner.html CTA 버튼 위치가 Safe Area 밖에 있어요
```

**피드백 유형 (자동 분류):**

| 유형 | 설명 | 예시 |
|------|------|------|
| design | 특정 디자인에 대한 의견 | "이 배너 로고가 너무 작아요" |
| review | 검수 결과에 대한 보충 | "LOGO-03은 PASS인데 여백이 아슬아슬해요" |
| general | 가이드라인 자체에 대한 의견 | "COLOR-02 기준이 모호합니다" |

> 피드백은 `feedback/log.jsonl` 파일에 자동 저장됩니다.

---

### 4. 피드백 분석 (`/sparta-learn`)

축적된 피드백을 분석하여 자주 발생하는 문제와 가이드라인 개선점을 찾아줍니다.

**사용법:**

```
/sparta-learn
/sparta-learn 2026년 2월 피드백만 분석해줘
/sparta-learn 미해결 피드백만 보여줘
```

**분석 결과에 포함되는 내용:**

- 가장 많이 위반된 항목 TOP 5
- 월별 FAIL 비율 추이
- 판단이 모호한 영역 (PASS와 FAIL이 혼재되는 항목)
- 아직 해결되지 않은 피드백 목록
- 가이드라인 개선 제안 (초안)

> 개선 제안은 팀 리더가 검토 후 승인/거절을 결정합니다.

---

## 지원 브랜드

이 시스템은 SPARTA의 4개 브랜드를 모두 지원합니다:

| 브랜드 | 주요 용도 |
|--------|----------|
| **Team Sparta** | 기업 브랜딩, 공식 커뮤니케이션 |
| **Sparta Club** | 일반 소비자 대상 교육 서비스 |
| **Sparta Builders** | 개발자/빌더 커뮤니티 |
| **Sparta 기업교육** | B2B 기업 교육 서비스 |

---

## 콘텐츠 타입 가이드

어떤 타입으로 만들지 모르겠다면 아래 표를 참고하세요:

| 타입 | 이름 | 이럴 때 사용 | 예시 |
|------|------|-------------|------|
| TYPE-A | Content-Driven | 정보를 전달할 때 | 과정 소개, 커리큘럼, 수강 후기, 비교표 |
| TYPE-B | Action-Driven | 행동을 유도할 때 | 할인 이벤트, 모집 마감, 수강신청, 프로모션 |
| TYPE-C | Message-Driven | 메시지를 전달할 때 | 브랜드 슬로건, 캠페인, 비전 선언 |

---

## 폴더 구조

```
sparta-design-agents/
├── agents/                          # AI 에이전트 설정 파일
│   ├── sparta-design-creator.md     #   디자인을 만들어주는 에이전트
│   └── sparta-design-reviewer.md    #   디자인을 검수해주는 에이전트
│
├── commands/                        # 슬래시 명령어 파일
│   ├── sparta-design.md             #   /sparta-design 명령어
│   ├── sparta-review.md             #   /sparta-review 명령어
│   ├── sparta-feedback.md           #   /sparta-feedback 명령어
│   └── sparta-learn.md              #   /sparta-learn 명령어
│
├── skills/                          # 브랜드 지식 데이터
│   ├── sparta-brand-components/     #   컬러, 로고, 폰트 등 디자인 토큰
│   │   └── SKILL.md
│   ├── sparta-design-guideline.md   #   디자인 제작 가이드라인
│   ├── sparta-review-checklist.md   #   32개 검수 체크리스트
│   └── sparta-feedback-loop.md      #   피드백 수집/분석 규칙
│
├── feedback/                        # 피드백 저장소
│   ├── log.jsonl                    #   피드백 기록 (자동 누적)
│   └── SUMMARY.md                   #   피드백 분석 요약
│
├── CLAUDE.md                        # 프로젝트 내부 규칙 (개발자용)
├── PLAN.md                          # 구현 계획서
├── HANDOVER.md                      # 작업 인수인계서
├── CONTRIBUTING.md                  # 기여 가이드
└── README.md                        # 이 파일 (사용 설명서)
```

---

## 자주 묻는 질문

### Q. Claude Code가 뭔가요?

Anthropic에서 만든 AI 코딩 도우미입니다. 터미널(명령줄)에서 동작하며, 이 프로젝트의 에이전트들은 Claude Code 위에서 실행됩니다. 설치 방법은 [공식 문서](https://docs.anthropic.com/en/docs/claude-code)를 참고하세요.

### Q. 디자인 툴(피그마 등) 없이도 사용할 수 있나요?

네. 이 시스템은 **HTML/CSS 파일**로 디자인을 생성합니다. 웹 브라우저에서 바로 확인할 수 있고, 스크린샷을 찍어 사용하거나 개발팀에 전달할 수 있습니다.

### Q. 만들 수 있는 디자인 포맷은 어떤 것들이 있나요?

| 포맷 | 비율 | 주요 용도 |
|------|------|----------|
| Mini Banner | 3:2 | 웹 배너, 썸네일 |
| Flex Banner | 가변 | 웹 상단/하단 배너 |
| Story-AD | 1:2 | 인스타그램/페이스북 스토리 광고 |
| Feed / Pop-Up | 4:5 | SNS 피드 이미지, 팝업 |

### Q. 검수만 따로 할 수 있나요?

네. `/sparta-review` 명령어에 이미지 파일(PNG, JPG 등)이나 HTML 파일 경로를 넘기면 됩니다. 이 시스템으로 만들지 않은 디자인도 검수할 수 있습니다.

### Q. 피드백은 어디에 저장되나요?

`feedback/log.jsonl` 파일에 자동으로 쌓입니다. 이 파일은 직접 편집하지 않는 것을 권장합니다. `/sparta-learn` 명령어로 분석 결과를 확인할 수 있습니다.

### Q. 브랜드 가이드라인 PDF가 없으면 사용할 수 없나요?

에이전트는 이미 PDF의 내용을 스킬 파일(`skills/` 폴더)로 변환해 놓았기 때문에 PDF 없이도 기본적인 제작/검수가 가능합니다. 다만, PDF 원본이 있으면 에이전트가 더 정확한 판단을 할 수 있습니다.

---

## 문제가 발생했을 때

| 증상 | 해결 방법 |
|------|----------|
| 명령어 입력 시 반응이 없음 | Claude Code가 실행 중인지 확인. `~/.claude/commands/` 폴더에 파일이 복사되었는지 확인 |
| "파일을 찾을 수 없습니다" 오류 | 검수 시 파일 경로가 정확한지 확인. 경로에 한글이나 공백이 있으면 따옴표로 감싸기 |
| 에이전트가 브랜드를 잘못 판별함 | 명령어에 브랜드명을 명시적으로 포함 (예: "Team Sparta 배너" 또는 "스파르타클럽 광고") |
| 검수 결과가 너무 엄격함 | 가이드라인 기준으로 판정하므로 정상입니다. 기준이 부적절하다면 `/sparta-feedback`으로 의견을 남겨주세요 |

---

## 기여하기

가이드라인 개선 의견, 버그 제보, 새로운 기능 제안은 언제든 환영합니다.
자세한 기여 방법은 [CONTRIBUTING.md](CONTRIBUTING.md)를 참고하세요.

---

## 라이선스

MIT
