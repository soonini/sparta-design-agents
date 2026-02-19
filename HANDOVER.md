# 인수인계서 (HANDOVER)

> 마지막 업데이트: 2026-02-20

## 현재 상태: Phase 6 완료 — 전체 Phase 완료

## 완료된 작업

### 프로젝트 초기 정리
- 원본 오픈소스(affaan-m/everything-claude-code)에서 불필요한 파일 제거
- 프로젝트명 변경: everything-claude-code → **sparta-design-agents**

### 범용 설정 제거
- 범용 에이전트 9개, 스킬 5개, 커맨드 9개, 규칙 8개, 훅 1개 전부 제거
- 이유: 애플리케이션 코드가 없는 레포에 개발용 도구 불필요, 글로벌 설정과 중복
- `agents/`, `skills/`, `commands/`는 빈 디렉토리로 유지 (Phase별 산출물 배치용)
- `rules/`, `hooks/`는 디렉토리 자체 삭제

### 문서 정비
- `PLAN.md` 생성 (구현 플랜 팀 공유용)
- `.gitignore` 정리 (IDE, 마켓플레이스 스킬, PDF 제외)
- `CONTRIBUTING.md` SPARTA 프로젝트 맥락으로 재작성
- `CLAUDE.md`, `README.md` 현재 구조에 맞게 동기화

### 레퍼런스 스킬 설치 (Phase 0)
- brand-guidelines, design-system-patterns, create-design-system-rules
- `.agents/skills/`에 설치됨 (gitignore 대상)

### Phase 1: 컴포넌트 라이브러리 완료
- **Basic Guide 전체 (p1-79)** + **Application Guide 핵심 (p80-100)** 읽기 완료
- `skills/sparta-brand-components/SKILL.md` 작성 완료 (~530줄)
- 포함 내용: 디자인 토큰(컬러/타이포/스페이싱), 로고, 컬러 시스템, 타이포그래피, 키 비주얼 그래픽, 그래픽 에셋, 레이아웃 그리드, UI 컴포넌트, 웹 배너 가이드, CSS 변수 템플릿

### Phase 2: 검수 체크리스트 완료
- `skills/sparta-review-checklist.md` 작성 완료 (~180줄)
- 포함 내용:
  - **심각도 3단계**: CRITICAL / HIGH / MEDIUM
  - **판정 기준**: PASS / 조건부 PASS / FAIL
  - **체크리스트 32항목**: 로고 7 + 컬러 5 (CRITICAL) / 타이포 6 + 그래픽 9 (HIGH) / 레이아웃 5 (MEDIUM)
  - **검수 리포트 형식**: 판정 요약 + 항목별 상세 결과 템플릿
  - **검수 프로세스**: 순서, 재검수 규칙, 예외 처리(AMBIGUOUS/EXEMPTED 태그)
  - **피드백 루프 연계**: 모호 영역/새 위반 유형 발견 시 피드백 루프에 보고

### Phase 3: 통합 가이드라인 완료
- `skills/sparta-design-guideline.md` 작성 완료 (~330줄)
- 포함 내용:
  - **콘텐츠 유형별 적용**: TYPE-A/B/C 판별 기준, 텍스트 하이어라키, 서체 매핑
  - **레이아웃 포맷별 적용**: Mini Banner/Flex/Story-AD/Feed 각각의 배치 규칙, ASCII 다이어그램 포함
  - **브랜드별 분기**: 4개 브랜드의 톤, 로고 크기, 콘텐츠 타입, 캐릭터 사용 차이
  - **DO/DON'T**: 로고/컬러/타이포/그래픽/레이아웃 5개 영역 실무 규칙
  - **HTML/CSS 생성 규칙**: 단일 .html, CSS 변수 참조, placeholder, 포맷별 권장 크기
  - **제작 워크플로우**: 5단계 (요청 분석 → 텍스트 시안 → 사용자 확인 → HTML/CSS 생성 → 셀프 검수)
  - **의사결정 플로우차트**: 8단계 빠른 참조

### PLAN.md Phase 6 추가
- 피드백 루프 설계 반영: 로그 스키마, 학습 워크플로우, 분석 메트릭 정의
- 산출물 목록 업데이트: 스킬 3→4개, 커맨드 2→4개
- 의존관계 다이어그램에 Phase 6 추가

### Phase 4: 에이전트 구현 완료
- `agents/sparta-design-reviewer.md` 작성 완료 (~150줄)
  - YAML frontmatter: name, description, tools(Read/Glob/Grep/Bash/WebFetch), model(opus)
  - 5단계 검수 워크플로우: 대상 식별 → CRITICAL → HIGH → MEDIUM → 판정/리포트
  - 32개 체크리스트 항목별 확인 내용 상세 기술
  - 검수 리포트 형식 (판정 요약 + 항목별 PASS/FAIL + 수정 방안)
  - HTML 파일 추가 확인 항목 (CSS 변수, CDN, placeholder, 레이어 주석)
  - 재검수, 예외 처리(AMBIGUOUS/EXEMPTED/NEW 태그) 규칙
- `agents/sparta-design-creator.md` 작성 완료 (~170줄)
  - YAML frontmatter: name, description, tools(Read/Write/Edit/Glob/Grep/Bash), model(opus)
  - 5단계 제작 워크플로우: 요청 분석 → 텍스트 시안 → 사용자 확인 → HTML/CSS 생성 → 셀프 검수
  - 의사결정 플로우차트 8단계 연동
  - HTML/CSS 생성 규칙 (단일 파일, CSS 변수, placeholder, 레이어 주석, 포맷별 크기)
  - 셀프 검수 절차 (CRITICAL → HIGH 순서, FAIL 시 수정 후 재확인)
  - Figma 스펙 요약 출력 형식
  - 참조 스킬: sparta-brand-components, sparta-design-guideline, sparta-review-checklist

### Phase 5: 슬래시 커맨드 완료
- `commands/sparta-design.md` 작성 완료 (~40줄)
  - YAML frontmatter: description
  - 참조 파일 4개 로드 지시 (3 스킬 + 1 에이전트)
  - `agents/sparta-design-creator.md`의 5단계 워크플로우 연동
  - 사용 예시 3가지
- `commands/sparta-review.md` 작성 완료 (~40줄)
  - YAML frontmatter: description
  - 참조 파일 3개 로드 지시 (2 스킬 + 1 에이전트)
  - `agents/sparta-design-reviewer.md`의 5단계 워크플로우 연동
  - 판정 기준 테이블 포함
  - 사용 예시 3가지

### Phase 6: 피드백 루프 완료
- `skills/sparta-feedback-loop.md` 작성 완료 (~180줄)
  - 로그 스키마 (log.jsonl): ID 채번, 필드 정의, type별 용도
  - 피드백 수집: 자동 수집 (검수 완료 시) + 수동 수집 (`/sparta-feedback`)
  - 피드백 분석: 4가지 핵심 메트릭 (위반 빈도 TOP 5, FAIL 비율 추이, 모호 영역, 미해결 피드백)
  - 5가지 개선안 유형 (항목 추가/강조/명확화/DO-DON'T 보강/규격 수정)
  - 검수 체크리스트·에이전트 연계 규칙 (AMBIGUOUS/EXEMPTED/NEW 태그)
  - 운영 가이드: 해결 처리, 분석 주기, 개선안 반영 절차
- `commands/sparta-feedback.md` 작성 완료 (~40줄)
  - YAML frontmatter: description
  - 8단계 워크플로우: 입력 분석 → 분류 → 작성자 확인 → 위반 매핑 → 태그 → 채번 → 저장 → 확인
  - 확인 출력 형식 포함
  - 사용 예시 3가지
- `commands/sparta-learn.md` 작성 완료 (~35줄)
  - YAML frontmatter: description
  - 참조 파일 3개 (피드백 루프 + 체크리스트 + 가이드라인)
  - 6단계 분석 워크플로우 연동
  - 사용 예시 3가지
- `feedback/log.jsonl` 초기 빈 파일 생성
- `feedback/SUMMARY.md` 초기 템플릿 생성 (누적 통계, TOP 5, 학습 포인트, 개선 이력, 미해결 항목)

## 진행 상황 요약

| 순서 | 산출물 | 상태 |
|------|--------|------|
| Phase 1 | `skills/sparta-brand-components/SKILL.md` | **완료** |
| Phase 2 | `skills/sparta-review-checklist.md` | **완료** |
| Phase 3 | `skills/sparta-design-guideline.md` (통합 가이드라인) | **완료** |
| Phase 4 | `agents/sparta-design-reviewer.md` + `agents/sparta-design-creator.md` | **완료** |
| Phase 5 | `commands/sparta-design.md` + `commands/sparta-review.md` | **완료** |
| Phase 6 | `skills/sparta-feedback-loop.md` + `commands/sparta-feedback.md` + `commands/sparta-learn.md` + `feedback/` | **완료** |

## 전체 Phase 완료

모든 계획된 Phase(1~6)가 완료되었습니다. 향후 가능한 작업:
- 실제 제작/검수 테스트 (제작 에이전트로 배너 생성 → 검수 에이전트로 검증)
- 피드백 루프 실전 운영 (피드백 축적 후 `/sparta-learn`으로 분석)
- 가이드라인/체크리스트 개선 (피드백 기반)

## Phase 1 PDF 리딩 요약 (다음 세션에서 참조)

다음 세션에서 SKILL.md 작성 시 아래 요약을 기반으로 작업. PDF를 다시 읽을 필요 없음.

### 1. 로고 (Basic Guide p10-20)
- **4개 브랜드**: Team Sparta, Sparta Club, Sparta Builders, Sparta 기업교육
- **2가지 타입**: Primary Type (가로형) + Stacked Type (세로형)
- **최소 크기**: Primary 22-24px, Stacked 45-56px (브랜드별 상이)
- **여백 규정**: T자 기반 클리어 스페이스
- **배치**: Standard (좌상단/우상단) + Extended (중앙/하단 등)
- **시그니처 마크**: S 아이콘 (독립 사용 가능)
- **파트너십 로고**: Ongoing(|로 구분), One-Off(X로 구분)
- **아이덴티티 컬러**: 흰 배경에 빨간 로고, 빨간 배경에 흰 로고
- **금지 사항 9가지**: 비율 변경, 회전, 그림자, 아웃라인, 색상 변경, 패턴, 배경 위 가독성 부족, 요소 분리, 다른 그래픽 결합

### 2. 컬러 (Basic Guide p21-31)
- **메인 컬러**: Sparta Red `#FA0030`, Deep Red `#850028`, Sparta Blue `#93E6F5`
- **확장 팔레트** (각 5단계):
  - Red: `#FFAAF0` → `#FF82D2` → `#EB2844` → `#AA002A` → `#730023`
  - Blue: `#8CEBFF` → `#00D2E6` → `#0096EB` → `#005F9B` → `#003773`
  - Purple: `#DCA5FF` → `#D773FF` → `#9646FF` → `#6400C3` → `#320073`
  - Grayscale: White `#FFFFFF` → `#F5F5F5` → `#E0E0E0` → `#999999` → `#666666` → `#333333` → Black `#000000`
- **컬러 셋**: Accent + Text + Background 조합
- **최대 3색 규칙**: 한 디자인에 3색 이하 사용
- **Primary Pairing**: 8가지 조합
- **Secondary Pairing**: 4가지 조합
- **Extended Pairing**: 16가지 조합
- **로고+배경 조합**: 16가지 승인된 조합

### 3. 타이포그래피 (Basic Guide p32-37)
- **주 서체**: Pretendard (ExtraBold / Bold / SemiBold / Medium / Regular)
- **보조 서체**: Sandol Dol (Bold / Medium)
- **계층 구조**:
  - Head: 150-250%, ExtraBold, Leading 110%
  - Title: 100-120%, Bold, Leading 130%
  - Label: 60%, Bold, Leading 130%
  - SubTitle: 40-60%, Medium, Leading 140%
  - Body: 20-40%, Regular, Leading 160%
  - Body List: 15-20%, Regular, Leading 160%
  - Caption: 10-15%, Regular, Leading 160%
- **콘텐츠 타입**:
  - Marketing A/B: Pretendard 사용
  - Brand Message A/B: Sandol Dol + Pretendard 조합
- **금지 사항 9가지**: 장평 변경, 자간 과도, 행간 부족, 지정 외 서체, 그라디언트, 아웃라인, 그림자, 색상 대비 부족, 과도한 굵기 혼합

### 4. 키 비주얼 그래픽 (Basic Guide p38-59)

#### 4-1. 그래픽 모티프
- **Potential Cube**: 정육면체 아웃라인 기반 육각형 + Bevel (모서리면)

#### 4-2. Frame Type
- **3가지 유형**: Image Masking / Image Clipping / Text
- **4-레이어 구조**: Background → Frame → Image → Text/Logo
- **크롭 가이드**: Basic 125% / Full 150% / Extended (프레임 확장)
- **최소 3면 노출 규칙**

#### 4-3. Pattern Type
- **2가지 유형**: Full Pattern / Line Pattern
- **3-레이어 구조**: Background → Pattern → Text/Logo
- **방향**: Single / Full (수평/수직)
- **Full 반복 시 최대 3-4회**, 톤온톤 컬러

#### 4-4. Tag Type
- **텍스트/카테고리 아이콘** 삽입 가능
- **3가지 형태**: Square / Hexagon / Signature
- **비례 가이드**: X-height 기준, 태그 높이 마진 0.3X, 텍스트 높이 0.45X, 갭 0.15X

### 5. 그래픽 에셋 (Basic Guide p60-79)

#### 5-1. UI Icon
- 육각형 아웃라인 기반, 단순 형태
- **에셋**: 홈, IT취업(내배캠), 강의, 커뮤니티, 좋아요, 스킬업, AI 부업, 프로필, 알림, 열정
- 그리드 준수, 추가 제작 시 유관 부서 협의
- **금지**: 그래픽 요소화, 최소 여백 침범, 복잡한 형태

#### 5-2. Category Icon
- 3D Bevel 적용, 카테고리 직관 표현
- **에셋**: 국비강의, 국비취업, 디자인, 자기개발(커리어), 개발, 데이터, AI·GPT, 자격증
- **제작 가이드**: 좌측 하단 경사각 10°, 우측 하단 경사각 35°
- **제작 프로세스**: 1) 꼭 변을 그리드에 맞춤 → 2) 직선 연결 → 3) 아이콘 완성 → 4) Bevel 적용
- **컬러**: Blue, Red, Purple 3가지 중 선택
- **컬러 사용 비율**: R1(10%) / R2(30%) / R3(50%) / R4(10%) 또는 동일 비율의 P/B 계열
- **태그 가이드**: 아이콘이 뛰어나오는 듯한 시각 효과, 충돌 시 확장/회전 조정
- **금지**: 불규칙 조명, 과도한 Bevel, 동일 컬러 반복

#### 5-3. Illustration
- Bevel 적용 입체 스타일, 콘텐츠 메시지 전달
- **에셋**: 강의, 내일배움캠프, 데이터1/2/3, 앱 아이콘, 폴더, 내일배움카드, 컴퓨터, 노트북, 완주, 축하, 캘린더, 알람, 긴급 알림
- **Feature 1**: 모서리면 추가 (Bevel)
- **Feature 2**: 강조 필요한 경우 핵심 요소를 더 입체화
- **제작 프로세스**: 1) 기본 형태 입체 → 2) Bevel 면 추가 → 3) 핵심 요소 강조 → 4) 빛과 그림자
- **컬러 가이드**: Category Icon과 동일 비율 (R/P/B 계열, 약간 다른 배분 — R3=40%, R4=10%, R5=10%)
- **금지**: 과도한 Bevel, UI 아이콘처럼 기능적 사용, 한 개체에 여러 색상

#### 5-4. Character (르탄이)
- 스파르타클럽 캐릭터 **르탄이** (Look&Feel)
- 구성: 얼굴, 몸통, 투구, 투구 위 장식, 망토
- 그래픽 모티프에서 파생된 육각 프레임을 얼굴 형태에 적용
- 투구 위 장식은 다양한 감정 표현 역할
- 주로 **내일배움캠프** 서비스에서 사용자 커뮤니케이션에 활용

### 6. 웹 Look & Feel (Application Guide p82-87)
- 메인 페이지: 볼드 타이포그래피 + 그래픽 모티프 활용
- 스크롤 시 잠재력 단어 뒤로 태그 등장 효과
- 내비게이션: 스크롤 시 상단 플로팅 형태로 전환
- 마우스 호버 시 일러스트레이션이 입체적 구성으로 전환
- 모바일 버전: 동일한 디자인 언어를 모바일 환경에 적용

### 7. UI 컴포넌트 (Application Guide p88-92)

#### 7-1. Infographic
- Graph: 게이지형 (반원 + 카테고리 아이콘 중앙)
- Charts: 바 차트 (빨간색 계열, Potential Cube 모티프 형태)
- Progress: 진행률 바 (빨간색 active + 회색 inactive)

#### 7-2. Active Button
- Carousel: 활성화 시 붉은 도트 인디케이터
- Tab: 활성 탭은 빨간 텍스트 + 라운드 배경
- Calendar: 오늘 날짜 = 빨간 육각형 배경 + 흰 텍스트

#### 7-3. Tag
- 콘텐츠 카드 위 태그 (무료 세미나, 스터디클럽, GPT, 데이터 분석 등)
- 활성화 시 색상 적용 (빨간 배경 + 흰 텍스트)

### 8. 브랜드 콘텐츠 (Application Guide p93-100)

#### 8-1. Content Guide
- **3가지 콘텐츠 타입**:
  - Type A (Content-Driven): 정보 제공, 이해 중심 — #명확한, #신뢰 중심, #정보 구조화
  - Type B (Action-Driven): 행동 유도, 전환 촉진 — #간결, #시각 강조, #클릭 유도형
  - Type C (Message-Driven): 브랜드 핵심 메시지 강조 — #Bold, #감정 자극, #인지 우선
- **텍스트 하이어라키**: Type별 요소 구성이 다름
  - Content-Driven: Tag → SubTitle → Title → Body → CTA
  - Action-Driven: Title → SubTitle → CTA
  - Message-Driven: SubTitle → Title → Caption
- **레이아웃 포맷**: Layout Grid + Margin/Safe Area + Text Area
  - 3:2 Mini Banner (Web)
  - Banner (Web - Flex)
  - 1:2 (Instagram Story-AD)
  - 4:5 (Instagram Feed/Pop-Up)

#### 8-2. Web Banner
- Mini Banner: Head Copy + Sub Copy + TAG + CTA Button + Graphic Area
- Flex Banner: Head Copy (최대 2줄) + Sub Copy + Graphic Area
- 텍스트 구조, 그래픽 요소 배치, CTA 구성 원칙 가이드

#### 8-3. SNS
- 모바일 기반 환경에 최적화된 시각 정보 구조
- 브랜드 메시지를 직관적이고 빠르게 전달

## 알려진 이슈

(현재 알려진 이슈 없음)

## 해결된 이슈

- [x] ~~GitHub 원격 레포 연결 미완료~~ → `origin` 연결 완료 + 전체 push 완료 (2026-02-20)
- [x] ~~PDF 공유 방법 미정~~ → README.md "3. 브랜드 PDF 원본" 섹션에 안내 완료
- [x] ~~Application Guide p101-132 미읽음~~ → 전체 읽기 완료 (2026-02-20). Office Item(명함/종이백/봉투) + Goods(유니폼/뱃지/에코백/스티커) — 모두 오프라인/물리 제작물. 디지털 디자인 스킬에 반영할 새 규격 없음

## 참고 자료

- 브랜드 PDF: `SPARTA_Brand_Basic_Guide_V.1.0_compressed.pdf`, `SPARTA_Brand_Application_Guide_V.1.0_compressed.pdf`
- 구현 플랜: `PLAN.md`
- 기여 가이드: `CONTRIBUTING.md`
