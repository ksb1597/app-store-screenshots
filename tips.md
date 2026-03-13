# Tips - app-store-screenshots

## 노하우 / 팁

### 스크린샷 캡처 시 주의
- 아이폰 시뮬레이터는 반드시 **6.1인치**로 캡처할 것
- 6.1인치로 찍으면 나중에 이미지 크기 조정할 필요 없음

### 사전 준비물
- 앱 스크린샷 PNG 파일들 (시뮬레이터 6.1인치 캡처)
- 앱 아이콘 PNG 파일
- 브랜드 색상 (배경색, 텍스트색, 강조색)
- 원하는 폰트 이름 (Google Fonts 기준)
- 앱 기능 목록 (중요도 순서대로)
- Node.js 18+ 필요

### 설치 방법
- 권장: `npx skills add ParthJadhav/app-store-screenshots`
- 전역 설치: `npx skills add ParthJadhav/app-store-screenshots -g`
- Claude Code 전용: `npx skills add ParthJadhav/app-store-screenshots -a claude-code`
- 수동: `git clone https://github.com/ParthJadhav/app-store-screenshots ~/.claude/skills/app-store-screenshots`

### 프롬프트 작성 패턴
- 좋은 프롬프트 구성: **앱 종류 + 핵심 가치 + 기능 목록 + 슬라이드 수 + 스타일**
- 앱이 뭘 하는지 한 문장으로 설명
- 핵심 기능 3~5개를 중요한 순서대로 나열
- 비주얼 스타일 지정 (미니멀, 어두운, 밝은, 컬러풀 등)
- 슬라이드 수 명시 (최대 10장)
- 참고할 App Store 앱이 있으면 레퍼런스로 언급

### 샘플 프롬프트
```
습관 추적 앱:
Build App Store screenshots for my habit tracker.
The app helps people stay consistent with simple daily routines.
I want 6 slides, clean/minimal style, warm neutrals, and a calm premium feel.

가계부 앱:
Generate App Store screenshots for my personal finance app.
The app's main strengths are fast expense capture, clear monthly trends, and shared budgets.
I want a sharp, modern style with high contrast and 7 slides.

AI 메모 앱:
Create exportable App Store screenshots for my AI note-taking app.
The core value is turning messy voice notes into clean summaries and action items.
I want bold copy, dark backgrounds, and a polished tech-forward look.

명상 앱:
Build marketing screenshots for my meditation app.
The app focuses on sleep, stress relief, and short guided sessions.
Use a soft, warm, organic style and prioritize emotional outcomes over feature lists.
```

### 핵심 디자인 원칙
- 스크린샷은 광고이지 UI 설명서가 아님 -- 각 슬라이드는 하나의 아이디어만 전달
- 헤드라인은 1초 안에 읽을 수 있어야 함 (App Store 썸네일 크기에서도)
- 연속된 슬라이드가 같은 레이아웃을 반복하면 안 됨
- 색상, 폰트, 스타일은 모두 사용자가 지정 (하드코딩 없음)

### 내보내기 해상도 (Apple 필수 4가지)
- 6.9인치: 1320 x 2868
- 6.5인치: 1284 x 2778
- 6.3인치: 1206 x 2622
- 6.1인치: 1125 x 2436

### 프로젝트 구조
- 전체 생성기가 `page.tsx` 파일 하나로 동작
- `public/mockup.png` -- 아이폰 프레임 이미지 (스킬에 포함)
- `public/screenshots/` -- 앱 스크린샷 넣는 폴더
- 개발서버 실행 후 브라우저에서 클릭하면 PNG로 내보내기

### 패키지 매니저 우선순위
- bun > pnpm > yarn > npm 순서로 자동 감지
