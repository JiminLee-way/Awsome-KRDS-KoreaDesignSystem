# KRDS 타이포그래피 토큰 레퍼런스

> 출처: `node_modules/krds-uiux/resources/css/token/krds_tokens.css`
> 생성일: Mon, Dec 9, 2024, 10:32:10 AM GMT+9

---

## 기본 설정

| 속성 | CSS Variable | 값 |
|------|-------------|-----|
| 서체 | `--krds-typo-font-type` | `Pretendard GOV` |
| 굵기 Regular | `--krds-typo-font-weight-regular` | `Regular` (400) |
| 굵기 Bold | `--krds-typo-font-weight-bold` | `Bold` (700) |
| 자간 0 | `--krds-typo-letter-spacing-0` | `0rem` |
| 자간 1 | `--krds-typo-letter-spacing-1` | `0.1rem` |

---

## rem 변환표

KRDS는 `1rem = 10px` 기반으로 설계되어 있다. `html { font-size: 62.5%; }` 설정이 필요하다.

| rem | px | 용도 예시 |
|-----|-----|----------|
| 1.3rem | 13px | Body xsmall, Label xsmall |
| 1.5rem | 15px | Body small, Label small, Heading xxsmall |
| 1.7rem | 17px | Body medium (기본), Label medium, Heading xsmall |
| 1.9rem | 19px | Body large, Label large, Heading small |
| 2.2rem | 22px | Mobile Heading medium, Mobile Navigation title-medium |
| 2.4rem | 24px | PC Heading medium, PC Navigation title-medium |
| 2.8rem | 28px | Mobile Display small, Mobile Heading xlarge |
| 3.2rem | 32px | PC Heading large, Mobile Display medium |
| 3.6rem | 36px | PC Display small |
| 4.0rem | 40px | PC Heading xlarge |
| 4.4rem | 44px | PC Display medium, Mobile Display large |
| 6.0rem | 60px | PC Display large |

---

## Display 타입 스케일

| 스케일 | PC CSS Variable | PC 크기 | Mobile CSS Variable | Mobile 크기 | 굵기 | 줄 간격 |
|--------|----------------|---------|--------------------|-----------|----|--------|
| Display Large | `--krds-pc-font-size-display-large` | 6.0rem (60px) | `--krds-mobile-font-size-display-large` | 4.4rem (44px) | Bold (700) | 150%+ |
| Display Medium | `--krds-pc-font-size-display-medium` | 4.4rem (44px) | `--krds-mobile-font-size-display-medium` | 3.2rem (32px) | Bold (700) | 150%+ |
| Display Small | `--krds-pc-font-size-display-small` | 3.6rem (36px) | `--krds-mobile-font-size-display-small` | 2.8rem (28px) | Bold (700) | 150%+ |

---

## Heading 타입 스케일

| 스케일 | PC CSS Variable | PC 크기 | Mobile CSS Variable | Mobile 크기 | 굵기 | 줄 간격 |
|--------|----------------|---------|--------------------|-----------|----|--------|
| Heading XLarge (H1) | `--krds-pc-font-size-heading-xlarge` | 4.0rem (40px) | `--krds-mobile-font-size-heading-xlarge` | 2.8rem (28px) | Bold (700) | 150%+ |
| Heading Large (H2) | `--krds-pc-font-size-heading-large` | 3.2rem (32px) | `--krds-mobile-font-size-heading-large` | 2.4rem (24px) | Bold (700) | 150%+ |
| Heading Medium (H3) | `--krds-pc-font-size-heading-medium` | 2.4rem (24px) | `--krds-mobile-font-size-heading-medium` | 2.2rem (22px) | Bold (700) | 150%+ |
| Heading Small (H4) | `--krds-pc-font-size-heading-small` | 1.9rem (19px) | `--krds-mobile-font-size-heading-small` | 1.9rem (19px) | Bold (700) | 150%+ |
| Heading XSmall (H5) | `--krds-pc-font-size-heading-xsmall` | 1.7rem (17px) | `--krds-mobile-font-size-heading-xsmall` | 1.7rem (17px) | Bold (700) | 150%+ |
| Heading XXSmall | `--krds-pc-font-size-heading-xxsmall` | 1.5rem (15px) | `--krds-mobile-font-size-heading-xxsmall` | 1.5rem (15px) | Bold (700) | 150%+ |

---

## Body 타입 스케일

| 스케일 | PC CSS Variable | PC 크기 | Mobile CSS Variable | Mobile 크기 | 굵기 | 줄 간격 |
|--------|----------------|---------|--------------------|-----------|----|--------|
| Body Large | `--krds-pc-font-size-body-large` | 1.9rem (19px) | `--krds-mobile-font-size-body-large` | 1.9rem (19px) | Regular (400) | 150%+ |
| Body Large Bold | (동일 변수) | 1.9rem (19px) | (동일 변수) | 1.9rem (19px) | Bold (700) | 150%+ |
| Body Medium | `--krds-pc-font-size-body-medium` | 1.7rem (17px) | `--krds-mobile-font-size-body-medium` | 1.7rem (17px) | Regular (400) | 150%+ |
| Body Medium Bold | (동일 변수) | 1.7rem (17px) | (동일 변수) | 1.7rem (17px) | Bold (700) | 150%+ |
| Body Small | `--krds-pc-font-size-body-small` | 1.5rem (15px) | `--krds-mobile-font-size-body-small` | 1.5rem (15px) | Regular (400) | 150%+ |
| Body Small Bold | (동일 변수) | 1.5rem (15px) | (동일 변수) | 1.5rem (15px) | Bold (700) | 150%+ |
| Body XSmall | `--krds-pc-font-size-body-xsmall` | 1.3rem (13px) | `--krds-mobile-font-size-body-xsmall` | 1.3rem (13px) | Regular (400) | 150%+ |
| Body XSmall Bold | (동일 변수) | 1.3rem (13px) | (동일 변수) | 1.3rem (13px) | Bold (700) | 150%+ |

> Body 크기는 PC와 Mobile에서 동일하다. Bold 변형은 동일한 CSS 변수에 `font-weight: 700`을 적용한다.

---

## Label 타입 스케일

| 스케일 | PC CSS Variable | PC 크기 | Mobile CSS Variable | Mobile 크기 | 굵기 | 줄 간격 |
|--------|----------------|---------|--------------------|-----------|----|--------|
| Label Large | `--krds-pc-font-size-label-large` | 1.9rem (19px) | `--krds-mobile-font-size-label-large` | 1.9rem (19px) | Bold (700) | 150%+ |
| Label Medium | `--krds-pc-font-size-label-medium` | 1.7rem (17px) | `--krds-mobile-font-size-label-medium` | 1.7rem (17px) | Bold (700) | 150%+ |
| Label Small | `--krds-pc-font-size-label-small` | 1.5rem (15px) | `--krds-mobile-font-size-label-small` | 1.5rem (15px) | Bold (700) | 150%+ |
| Label XSmall | `--krds-pc-font-size-label-xsmall` | 1.3rem (13px) | `--krds-mobile-font-size-label-xsmall` | 1.3rem (13px) | Bold (700) | 150%+ |

> Label 크기는 PC와 Mobile에서 동일하다. Label은 항상 Bold(700) 굵기를 사용한다.

---

## Navigation 타입 스케일

| 스케일 | PC CSS Variable | PC 크기 | Mobile CSS Variable | Mobile 크기 | 굵기 |
|--------|----------------|---------|--------------------|-----------|----|
| Navigation Title Medium | `--krds-pc-font-size-navigation-title-medium` | 2.4rem (24px) | `--krds-mobile-font-size-navigation-title-medium` | 2.2rem (22px) | Bold (700) |
| Navigation Title Small | `--krds-pc-font-size-navigation-title-small` | 1.9rem (19px) | `--krds-mobile-font-size-navigation-title-small` | 1.9rem (19px) | Bold (700) |
| Navigation Depth Medium Bold | `--krds-pc-font-size-navigation-depth-medium-bold` | 1.7rem (17px) | `--krds-mobile-font-size-navigation-depth-medium-bold` | 1.7rem (17px) | Bold (700) |
| Navigation Depth Medium | `--krds-pc-font-size-navigation-depth-medium` | 1.7rem (17px) | `--krds-mobile-font-size-navigation-depth-medium` | 1.7rem (17px) | Regular (400) |
| Navigation Depth Small Bold | `--krds-pc-font-size-navigation-depth-small-bold` | 1.5rem (15px) | `--krds-mobile-font-size-navigation-depth-small-bold` | 1.5rem (15px) | Bold (700) |
| Navigation Depth Small | `--krds-pc-font-size-navigation-depth-small` | 1.5rem (15px) | `--krds-mobile-font-size-navigation-depth-small` | 1.5rem (15px) | Regular (400) |

> Navigation Title Medium은 PC(24px)와 Mobile(22px)에서 크기가 다르다. 나머지 Navigation 스케일은 PC/Mobile 동일하다.

---

## PC vs Mobile 크기 비교 요약

아래 표는 PC와 Mobile에서 크기가 **다른** 스케일만 나열한다 (나머지는 모두 PC = Mobile).

| 스케일 | PC | Mobile | 축소 비율 |
|--------|-----|--------|----------|
| Display Large | 60px | 44px | 73% |
| Display Medium | 44px | 32px | 73% |
| Display Small | 36px | 28px | 78% |
| Heading XLarge | 40px | 28px | 70% |
| Heading Large | 32px | 24px | 75% |
| Heading Medium | 24px | 22px | 92% |
| Navigation Title Medium | 24px | 22px | 92% |

> Heading Small(19px) 이하, Body, Label, Navigation Depth는 PC/Mobile 동일하다.

---

## 사용 예시

```css
/* 기본 본문 스타일 */
body {
  font-family: var(--krds-typo-font-type), 'Pretendard', -apple-system, sans-serif;
  font-size: var(--krds-pc-font-size-body-medium); /* 1.7rem = 17px */
  font-weight: 400;
  line-height: 1.5; /* 150% 이상 */
  letter-spacing: var(--krds-typo-letter-spacing-0); /* 0rem */
}

/* H1 스타일 */
h1 {
  font-size: var(--krds-pc-font-size-heading-xlarge); /* 4.0rem = 40px */
  font-weight: 700;
}

/* 반응형 (Mobile) */
@media (max-width: 1023px) {
  h1 {
    font-size: var(--krds-mobile-font-size-heading-xlarge); /* 2.8rem = 28px */
  }
}
```
