# my-homepage

순수 **HTML/CSS/JavaScript**로 만든 개인 홈페이지입니다. 서버/빌드 도구/패키지 매니저 없이 `index.html` 하나로 동작합니다.

## 미리보기

- `index.html`을 브라우저에서 직접 열면 됩니다.
- 로컬에서 정상 동작 확인은 VS Code의 **Live Server** 확장을 권장합니다.

## 실행 방법

### 1) 가장 간단한 방법

1. `index.html` 더블 클릭
2. 브라우저에서 열기

### 2) Live Server (권장)

1. VS Code에서 프로젝트 폴더 열기
2. `index.html` 우클릭 → **Open with Live Server**

## 프로젝트 구조

이 프로젝트는 단일 파일 구조입니다.

- `index.html`: HTML/CSS/JS가 모두 포함된 메인 파일
- `docs/homepage-features.md`: 5가지 기능 기획/설계 문서

## 주요 기능

- **히어로 섹션**: 타이핑 애니메이션, 기술 스택 뱃지, CTA 버튼
- **포트폴리오**: 프로젝트 카드 동적 렌더링 + 카테고리 필터
- **다크/라이트 테마**: 테마 토글 + `localStorage` 저장 + OS 설정 자동 감지
- **블로그/학습 기록**: JS 배열 기반 정적 포스트 목록
- **연락처/SNS 허브**: 이메일 난독화(동적 생성) + 복사 기능

## 데이터 수정(커스터마이징)

`index.html`의 `<script>` 영역에서 아래 항목을 수정합니다.

- **프로젝트 목록**: `projects[]` 배열 편집  
  - `category`는 `'consulting'` / `'si'` / `'operation'` 중 하나
- **블로그 글 목록**: `posts[]` 배열에 `{ date, title, tags, summary }` 추가
- **기술 스택 뱃지**: `#hero` 섹션의 `.tech-badges` 내 배지 텍스트 수정
- **이메일**: `const email = ['앞부분', '도메인'].join('@')` 두 조각 수정

## 외부 의존성(CDN)

- Font Awesome 6.5.0 (아이콘)
- Google Fonts: Noto Sans KR (폰트)

오프라인 환경에서는 아이콘/폰트가 정상 표시되지 않을 수 있습니다.

