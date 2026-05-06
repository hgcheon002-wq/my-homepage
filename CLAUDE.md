# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

순수 HTML/CSS/JS로 만든 개인 홈페이지. 서버·빌드 도구·패키지 매니저 없음.
`index.html` 하나를 브라우저에서 직접 열면 동작한다.

## 실행

```
index.html 을 브라우저에서 더블클릭 또는 Live Server(VS Code 확장)로 열기
```

빌드·테스트·린트 명령어 없음 (빌드 도구 미사용).

## 아키텍처

`index.html` 단일 파일에 HTML·CSS·JS가 모두 포함된 구조.

| 영역 | 위치 | 역할 |
|---|---|---|
| CSS 변수 | `<style>` 상단 `:root` / `[data-theme="dark"]` | 라이트·다크 테마 색상 전체 관리 |
| 히어로 섹션 | `#hero` + `typeAnimation()` 함수 | 타이핑 애니메이션, 기술 스택 뱃지, CTA 버튼 |
| 포트폴리오 | `#portfolio` + `projects[]` 배열 + `renderProjects()` | 카드 동적 렌더링, 카테고리 필터(컨설팅/SI/운영) |
| 블로그 기록 | `#blog` + `posts[]` 배열 | JS 배열 기반 정적 포스트 목록 |
| 연락처 | `#contact` + `copyEmail()` | 이메일 난독화(JS 조합), SNS 허브 |
| 테마 토글 | `toggleTheme()` + `localStorage` | OS 설정 자동 감지, 선택값 브라우저에 저장 |

## 데이터 수정 방법

- **프로젝트 추가/수정**: `<script>` 내 `projects[]` 배열 항목 편집. `category` 값은 `'consulting'` / `'si'` / `'operation'` 중 하나.
- **블로그 포스트 추가**: `posts[]` 배열에 `{ date, title, tags, summary }` 객체 추가.
- **기술 스택 뱃지**: `#hero` 내 `.tech-badges` 안의 `<span class="badge">` 직접 편집.
- **이메일 변경**: `const email = ['앞부분', '도메인'].join('@')` 두 조각 수정.

## 외부 의존성 (CDN)

- Font Awesome 6.5.0 — 아이콘
- Google Fonts (Noto Sans KR) — 한국어 폰트

오프라인 환경에서는 아이콘·폰트가 표시되지 않는다.

## 기획 문서

`docs/homepage-features.md` — 5가지 기능의 설계 의도, 트레이드오프, 구현 우선순위 기록.
