---
name: krds-onboarding
description: Use when starting any project involving Korean government digital services, public sector websites, or KRDS (Korea Design System). Triggers on mentions of 정부, 공공, 행정, KRDS, 디지털 정부서비스, 정부24, 공공기관 웹사이트.
---

## Overview

- **KRDS (KoRea Design System)**는 대한민국 정부의 디지털 서비스 UI/UX 일관성과 접근성을 위한 범정부 디자인 시스템입니다.
- 행정안전부/NIA(한국지능정보사회진흥원)에서 발행하며, **WCAG 2.1 AA** 수준을 준수합니다.
- 이 스킬은 KRDS 기반 프로젝트의 **진입점(Entry Point)**으로, 환경 설정부터 기관 유형 분류, 후속 스킬 안내까지 담당합니다.
- 공식 사이트: [www.krds.go.kr](https://www.krds.go.kr)
- GitHub: [github.com/KRDS-uiux/krds-uiux](https://github.com/KRDS-uiux/krds-uiux)

## Iron Law

```
NO KRDS WORK WITHOUT krds-uiux PACKAGE INSTALLED FIRST
```

모든 스킬은 `node_modules/krds-uiux/`의 에셋(HTML 스니펫, CSS 토큰, SVG 아이콘)을 참조합니다.
패키지가 설치되어 있지 않으면 어떤 KRDS 작업도 진행하지 마세요.

## Step 1: 자동 환경 설정 (무조건 첫 번째, 질문 없이 실행)

사용자가 KRDS 관련 작업을 요청하면, **질문 없이 아래 명령을 즉시 실행**하세요:

```bash
# package.json 없으면 생성
if [ ! -f package.json ]; then npm init -y; fi

# krds-uiux 설치 (이미 있으면 스킵)
if [ ! -d node_modules/krds-uiux ]; then npm install krds-uiux; fi

# 설치 확인
ls node_modules/krds-uiux/resources/css/token/krds_tokens.css
```

### CDN 방식 사용법

프로젝트에 KRDS를 CDN 번들로 로딩하려면:

```html
<link rel="stylesheet" href="node_modules/krds-uiux/resources/cdn/krds.min.css">
<script src="node_modules/krds-uiux/resources/cdn/krds.min.js"></script>
```

### 개별 로딩 방식

필요한 리소스만 선택적으로 로딩하려면:

```html
<link rel="stylesheet" href="node_modules/krds-uiux/resources/css/token/krds_tokens.css">
<link rel="stylesheet" href="node_modules/krds-uiux/resources/css/common/common.css">
<link rel="stylesheet" href="node_modules/krds-uiux/resources/css/component/component.css">
<script src="node_modules/krds-uiux/resources/js/component/ui-script.js"></script>
```

### 폰트 설정

KRDS 공식 폰트인 Pretendard GOV를 적용하세요:

```css
@font-face {
  font-family: 'Pretendard GOV';
  src: url('node_modules/krds-uiux/resources/fonts/PretendardGOV-Regular.subset.woff2') format('woff2');
  font-weight: 400;
}
```

## Step 2: 기관 유형 질문

환경 설정이 완료되면, 사용자에게 물어보세요:

> "정부 기관에서 사용하는 용도인가요? (Y/N)"

### Y인 경우 (정부/공공기관)

후속 질문을 진행하세요:

> "어떤 유형에 해당하나요?"
> 1. **중앙행정기관 (대표)** -- 정부 상징 로고를 사용하는 부/처/청 대표 웹사이트
> 2. **중앙행정기관 (운영 서비스/시스템)** -- 독자적 로고를 사용하는 서비스/시스템/포털
> 3. **공공기관** -- 공공기관 대표/운영 웹사이트
> 4. **지방자치단체** -- 지자체 대표/운영 웹사이트

### N인 경우 (비정부)

KRDS를 참고 수준으로 활용하여 사용자 요청에 따라 자유 설계합니다.
필수 요소 없이 베스트 프랙티스로 안내하세요.

## Step 3: 적용 기준 분기

기관 유형에 따라 적용 기준이 다릅니다:

| 요소 | 중앙행정(대표) | 중앙행정(운영) | 공공기관 | 지자체 |
|------|--------------|--------------|---------|--------|
| 공식 배너 | **필수** | **필수** | 선택 | **필수** |
| 헤더/푸터 스타일 | **필수** | 배치만 필수 | 배치만 필수 | 배치만 필수 |
| 운영기관 식별자 | - | 선택 | 선택 | 선택 |
| 스타일 가이드 | **표준형 필수** | 규칙 준수 | 규칙 준수 | 규칙 준수 |
| 컴포넌트/패턴 | **필수** | **필수** | **필수** | **필수** |

### 표준형 vs 확장형

- **표준형**: 정부 상징 로고를 사용하는 기관에 적용됩니다. KRDS의 색상/서체/형태/배치를 그대로 사용해야 합니다.
- **확장형**: 독자적 로고를 사용하는 기관에 적용됩니다. KRDS 규칙을 준수하되 기관 특성을 반영할 수 있습니다.

## Step 4: 적용 수준 안내

서비스 패턴의 사용성 가이드라인은 3단계로 구분됩니다:

| 수준 | 설명 | 예시 |
|------|------|------|
| **필수(Do)** | 미준수 시 작업 실패 직결. 사용자가 스스로 작업 완료 불가 | 입력폼에 레이블 제공 |
| **권장(Better)** | 미준수 시 작업 난도 상승하나 실패까지는 아님 | 자동완성 기능 제공 |
| **우수(Best)** | 준수 시 만족도 대폭 향상 (매력적 경험) | 관련 서비스 추천 |

필수 항목을 우선 준수하고, 서비스 상황에 맞게 **권장 -> 우수** 순으로 확장하세요.

## Step 5: 후속 스킬 안내

작업 목적에 따라 적절한 스킬을 사용하세요:

| 작업 | 사용할 스킬 |
|------|-----------|
| 색상, 폰트, 레이아웃, 간격, 형태 설계 | **krds-style** |
| 버튼, 입력, 메뉴, 모달 등 컴포넌트 구현 | **krds-components** |
| 검색, 로그인, 신청 등 페이지 패턴 설계 | **krds-patterns** |
| 완성된 서비스의 가이드라인 준수 검증 | **krds-verify** |
| 배포/커밋 전 저작권 출처 표기 확인 | **krds-license** |

## 에셋 참조 규칙 (전 스킬 공통)

```
BASE = node_modules/krds-uiux
```

| 필요한 것 | 참조 경로 | 방법 |
|----------|----------|------|
| 색상/간격/타이포 토큰 | `{BASE}/resources/css/token/krds_tokens.css` | Read |
| 컴포넌트 HTML | `{BASE}/html/code/{component}.html` | Read |
| 컴포넌트 SCSS | `{BASE}/resources/scss/component/_{component}.scss` | Read |
| JS 인터랙션 | `{BASE}/resources/js/component/ui-script.js` | Read |
| 아이콘 SVG | `{BASE}/resources/img/component/icon/*.svg` | Glob + Read |
| 파비콘 | `{BASE}/resources/img/component/favicon/*` | 복사 |
| 폰트 | `{BASE}/resources/fonts/PretendardGOV-*` | 경로 안내 |
| CDN 번들 | `{BASE}/resources/cdn/krds.min.css` + `.js` | 링크 삽입 |

**절대로 KRDS 토큰값이나 HTML 마크업을 기억에 의존해서 생성하지 마세요. 반드시 에셋 파일을 Read하세요.**
