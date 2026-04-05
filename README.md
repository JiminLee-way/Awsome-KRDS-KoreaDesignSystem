# Awesome KRDS (Korea Design System)

대한민국 범정부 UI/UX 디자인시스템(KRDS) v1.0.0 기반 Claude Code 플러그인.

디지털 정부서비스의 설계, 구현, 검증을 지원하는 6개 스킬을 제공합니다.

## 설치

Claude Code에서:

```
/plugin marketplace add JiminLee-way/Awsome-KRDS-KoreaDesignSystem-
/plugin install krds@Awsome-KRDS-KoreaDesignSystem-
```

## 스킬 목록

| 스킬 | 트리거 | 역할 |
|------|--------|------|
| **krds-onboarding** | KRDS, 정부, 공공 | npm install 자동화 → 기관 유형 → 적용 기준 |
| **krds-style** | 색상, 폰트, 레이아웃 | KRDS 토큰 기반 스타일 가이드 |
| **krds-components** | 버튼, 입력, 메뉴 등 | 43종 컴포넌트 가이드 + HTML 스니펫 |
| **krds-patterns** | 검색, 로그인, 신청 | 기본 패턴 11종 + 서비스 패턴 5종 |
| **krds-verify** | 검증, 체크리스트 | 311개 체크리스트 P/F/E/N/A 검증 |
| **krds-license** | 배포, 커밋 | 공공누리 제1유형 저작권 검증 |

## 워크플로우

```
krds-onboarding → krds-style → krds-components → krds-patterns → krds-verify → krds-license
```

## 에셋 참조

이 플러그인의 모든 스킬은 `npm install krds-uiux` 패키지의 에셋을 직접 참조합니다:
- HTML 스니펫 74개 (`html/code/*.html`)
- CSS 디자인 토큰 (`resources/css/token/krds_tokens.css`)
- SVG 아이콘 95개 (`resources/img/component/icon/*.svg`)
- PretendardGOV 폰트 (`resources/fonts/`)
- CDN 번들 (`resources/cdn/krds.min.css` + `krds.min.js`)

## KRDS 리소스

| 리소스 | 링크 |
|--------|------|
| KRDS 홈페이지 | [www.krds.go.kr](https://www.krds.go.kr) |
| KRDS GitHub | [github.com/KRDS-uiux/krds-uiux](https://github.com/KRDS-uiux/krds-uiux) |
| KRDS Figma | [figma.com/@krds](https://www.figma.com/@krds) |
| UI/UX 가이드라인 PDF | [디지털 정부서비스 UI/UX 가이드라인 (2025.08)](https://www.krds.go.kr) |
| npm 패키지 | [krds-uiux](https://www.npmjs.com/package/krds-uiux) |

## 저작권

본 저작물은 행정안전부에서 작성하여 공공누리 제1유형으로 개방한
'범정부 UI/UX 디자인시스템(KRDS)'을 이용하였으며,
해당 저작물은 [KRDS 디자인시스템 홈페이지(www.krds.go.kr)](https://www.krds.go.kr)에서
무료로 다운받으실 수 있습니다.
