---
name: krds-style
description: Use when implementing colors, typography, layout, spacing, shapes, elevation, or high-contrast mode for Korean government digital services following KRDS. Triggers on 색상, 폰트, 서체, 타이포, 레이아웃, 그리드, 간격, 래디어스, 엘리베이션, 선명한 화면, 다크모드, 반응형.
---

# KRDS 스타일 가이드

## Overview

KRDS(Korea Design System)는 대한민국 정부 디지털 서비스의 일관된 사용자 경험을 위해 6가지 핵심 스타일 요소를 정의한다.

1. **색상(Color)** — Primary, Secondary, Gray, Danger, Warning, Success, Information, Point, Graphic 팔레트와 접근성 기반 매직넘버 체계
2. **타이포그래피(Typography)** — Pretendard GOV 표준 서체, Display/Heading/Body/Label/Navigation 타입 스케일
3. **형태(Shape)** — Border radius 5단계(xsmall~xlarge), 최대 12px, 컨테이너 높이 기반 계산법
4. **레이아웃(Layout)** — 4단계 반응형 브레이크포인트(small/medium/large/xlarge), 12컬럼 그리드
5. **아이콘(Icon)** — 시스템 색상과 병행 사용, 접근성을 위한 텍스트+아이콘 조합 필수
6. **엘리베이션(Elevation)** — 6단계 레이어 체계(-1 ~ +4), 그림자/색상/딤드/경계선으로 표현

## 에셋 참조

실제 디자인 토큰 값은 아래 CSS 파일에서 확인한다:

```
node_modules/krds-uiux/resources/css/token/krds_tokens.css
```

이 파일에는 PRIMITIVE(원시 색상), MODE-LIGHT(라이트 모드 시맨틱), MODE-HIGH-CONTRAST(선명한 화면 시맨틱), RESPONSIVE-PC/MOBILE(반응형 타이포·간격), SEMANTIC(gap/padding/radius) 토큰이 모두 포함되어 있다.

상세 토큰 목록은 다음 레퍼런스 파일을 참조한다:
- `references/color-tokens.md` — 전체 색상 토큰
- `references/typography.md` — 타입 스케일 토큰
- `references/spacing.md` — 간격·패딩·래디어스 토큰

---

## 색상 적용 가이드

### 60-30-10 비율 원칙

화면 내 색상 면적 비율을 지켜 시각적 안정감을 확보한다.

| 역할 | 비율 | 색상 계열 | 용도 |
|------|------|-----------|------|
| Base | 60% | Gray | 배경, 서피스, 여백 |
| Secondary | 30% | Secondary | 카드, 패널, 보조 영역 |
| Primary | 10% | Primary | CTA 버튼, 링크, 포커스 |
| Accent | 5% 이하 | Point / Danger / Warning / Success | 강조, 알림, 상태 표시 |

### 매직넘버 접근성 체계

색상 단계 번호(5~95)와 명도 대비를 연계한 접근성 지표:

| 매직넘버 | 대비비 | WCAG 레벨 | 용도 |
|----------|--------|-----------|------|
| 40 | 3:1 | AA (대형 텍스트, UI 컴포넌트) | 아이콘, 비활성 테두리, 큰 글자 |
| 50 | 4.5:1 | AA (일반 텍스트) | 본문 텍스트, 레이블, 일반 아이콘 |
| 70 | 7:1 | AAA | 중요 본문, 소형 텍스트 |
| 90 | 15:1 | 선명한 화면 | 고대비 모드 본문 텍스트 |

### 시스템 색상 사용 원칙

시스템 색상(Danger, Warning, Success, Information)은 반드시 **아이콘 + 텍스트를 병행**해야 한다. 색상만으로 상태를 전달하면 색각이상자가 정보를 인지할 수 없다.

### 상태별 색상 변화 패턴

| 요소 유형 | Default | Hover | Pressed |
|-----------|---------|-------|---------|
| Primary 버튼 (fill) | primary-50 | primary-60 | primary-70 |
| Secondary 버튼 (fill) | primary-5 | primary-10 | primary-20 |
| Tertiary 버튼 (fill) | transparent | gray-5 | gray-10 |
| Text 버튼 (fill) | transparent | secondary-5 | secondary-10 |
| Link | primary-50 | primary-60 | primary-70 |

### 색각이상자 대응 8색 팔레트

색각이상(Color Vision Deficiency)을 가진 사용자도 구분할 수 있는 안전한 8색 조합:

| 이름 | Hex 코드 |
|------|----------|
| Black | `#000000` |
| Orange | `#E69F00` |
| Sky blue | `#56B4E9` |
| Bluish green | `#009E73` |
| Yellow | `#F0E442` |
| Blue | `#0072B2` |
| Vermilion | `#D55E00` |
| Reddish purple | `#CC79A7` |

---

## 타이포그래피

### 서체

- **표준형**: Pretendard GOV (KRDS 공식 서체)
- **확장형** (고딕 계열): Noto Sans KR, 나눔고딕, Spoqa Han Sans Neo

### 기본 크기 및 줄 간격

- 기본 본문 크기: **17px** (Pretendard GOV 기준, `--krds-pc-font-size-body-medium: 1.7rem`)
- 최소 본문 크기: **16px** (접근성 권장 하한)
- 줄 간격(line-height): **150% 이상** 필수

### 굵기

- Regular: **400** (`--krds-typo-font-weight-regular: Regular`)
- Bold: **700** (`--krds-typo-font-weight-bold: Bold`)

### Heading-Body 크기 비율

Heading과 Body 텍스트의 크기 차이는 **1.25~1.5배**를 유지한다.

예시: Body medium(17px) 대비 Heading small(19px) = 1.12배, Heading medium(24px) = 1.41배, Heading large(32px) = 1.88배

상세 타입 스케일은 `references/typography.md` 참조.

---

## 레이아웃

### 반응형 브레이크포인트 4단계

| 단계 | 최소 너비 | 컬럼 수 | Gutter | Margin |
|------|-----------|---------|--------|--------|
| small | 360px+ | 4 | 16px | 16px |
| medium | 768px+ | 8 | 16px | 24px |
| large | 1024px+ | 12 | 24px | 24px |
| xlarge | 1280px+ | 12 | 24px | 24px |

### 최대 콘텐츠 너비

**1200px** — xlarge 이상에서 콘텐츠가 이 너비를 초과하지 않는다.

### 서브페이지 레이아웃 구조

```
Header
  └─ Breadcrumb
       └─ [Left Menu] + Main Contents + [Right Menu]
            └─ Footer
```

- Header → Breadcrumb 간격: 24px (PC) / 16px (Mobile)
- Left Menu ↔ Contents 간격: 64px (PC) / 0 (Mobile, 메뉴 숨김)
- Contents ↔ Right Menu 간격: 40px (PC) / 0 (Mobile)
- Contents → Footer 간격: 64px (PC) / 40px (Mobile)
- Breadcrumb → H1 간격: 40px (PC) / 32px (Mobile)

---

## 형태(Shape)

### Border Radius 규칙

- 래디어스 최대값: **12px**
- 계산법: `컨테이너 높이 × 0.125`, 결과가 홀수이면 짝수로 올림

### 5단계 래디어스 스케일

| 단계 | 크기 | CSS 변수 (예시) |
|------|------|-----------------|
| xsmall | 2px (0.2rem) | `--krds-radius-xsmall1`, `--krds-radius-xsmall2`, `--krds-radius-xsmall3` |
| small | 4px (0.4rem) | `--krds-radius-small1`, `--krds-radius-small2`, `--krds-radius-small3` |
| medium | 6~8px (0.6~0.8rem) | `--krds-radius-medium1`~`--krds-radius-medium4` |
| large | 10px (1.0rem) | `--krds-radius-large1`, `--krds-radius-large2` |
| xlarge | 12px (1.2rem) | `--krds-radius-xlarge1`, `--krds-radius-xlarge2` |

---

## 엘리베이션(Elevation)

### 6단계 레이어 체계

| 레벨 | 용도 | 표현 방법 |
|------|------|-----------|
| -1 | 배경 아래 (sunken) | 색상 차이로 구분 |
| 0 | 기본 배경 (base) | 기본 서피스 색상 |
| +1 | 카드, 탭, 약간 떠 있는 요소 | 그림자 shadow1 (`#0000000d`) |
| +2 | 드롭다운, 팝오버 | 그림자 shadow2 (`#00000014`) |
| +3 | 모달, 사이드 패널 | 그림자 shadow3 (`#0000001f`) + 딤드 배경 |
| +4 | 긴급 공지, 최상위 알림 | 강한 그림자 + 딤드 (`alpha-black75`) |

### 표현 수단

- **그림자(Shadow)**: `--krds-light-color-alpha-shadow1/2/3` 사용
- **색상(Color)**: 레벨이 높을수록 서피스 색상 밝게/어둡게 조정
- **딤드(Dimmed)**: 모달 등 +3 이상에서 `--krds-light-color-background-dim` (alpha-black75) 적용
- **경계선(Border)**: `--krds-light-border-width-variable-regular` (0.1rem) 또는 `-medium` (0.2rem)

---

## 선명한 화면 모드 (High Contrast)

### 대비비 요구사항

| 요소 | 필요 대비비 |
|------|------------|
| 본문 텍스트 | 15:1 이상 |
| 헤딩, 레이블 | 7:1 이상 |
| 아이콘 | 4.5:1 이상 |

### 레이어 색상 규칙

선명한 화면에서 레이어가 올라갈수록 **점차 밝아지게** 설정한다:

| 레이어 | Light 모드 | High Contrast 모드 |
|--------|------------|-------------------|
| 기본 배경 | gray-0 (`#ffffff`) | gray-100 (`#000000`) |
| 서피스 subtler | gray-5 (`#f4f5f6`) | gray-95 (`#131416`) |
| 서피스 subtle | gray-10 (`#e6e8ea`) | gray-90 (`#1e2124`) |

### High Contrast Secondary 색상 차이

선명한 화면 모드의 Secondary 색상은 라이트 모드와 **완전히 다른 색상**을 사용한다:

- Light Secondary-50: `#346fb2` (블루 계열)
- High Contrast Secondary-50: `#268097` (틸/시안 계열)

이는 어두운 배경에서 가독성을 확보하기 위한 의도적 설계이다.

### Border 두께 차이

| 모드 | variable-regular | variable-medium |
|------|-----------------|-----------------|
| Light | 0.1rem (1px) | 0.2rem (2px) |
| High Contrast | 0.2rem (2px) | 0.3rem (3px) |

선명한 화면 모드에서는 경계선 두께를 자동으로 증가시켜 요소 구분을 강화한다.
