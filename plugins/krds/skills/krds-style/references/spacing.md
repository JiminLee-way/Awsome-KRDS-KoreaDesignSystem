# KRDS 간격(Spacing) 토큰 레퍼런스

> 출처: `node_modules/krds-uiux/resources/css/token/krds_tokens.css`
> 생성일: Mon, Dec 9, 2024, 10:32:10 AM GMT+9

---

## Number Scale (기본 단위)

모든 Gap, Padding, Radius, Size 토큰은 Number Scale을 참조한다.

| CSS Variable | rem | px (1rem=10px) |
|-------------|-----|----------------|
| `--krds-number-0` | 0rem | 0px |
| `--krds-number-1` | 0.1rem | 1px |
| `--krds-number-2` | 0.2rem | 2px |
| `--krds-number-3` | 0.4rem | 4px |
| `--krds-number-4` | 0.6rem | 6px |
| `--krds-number-5` | 0.8rem | 8px |
| `--krds-number-6` | 1rem | 10px |
| `--krds-number-7` | 1.2rem | 12px |
| `--krds-number-8` | 1.6rem | 16px |
| `--krds-number-9` | 2rem | 20px |
| `--krds-number-10` | 2.4rem | 24px |
| `--krds-number-11` | 2.8rem | 28px |
| `--krds-number-12` | 3.2rem | 32px |
| `--krds-number-13` | 3.6rem | 36px |
| `--krds-number-14` | 4rem | 40px |
| `--krds-number-15` | 4.4rem | 44px |
| `--krds-number-16` | 4.8rem | 48px |
| `--krds-number-17` | 5.6rem | 56px |
| `--krds-number-18` | 6.4rem | 64px |
| `--krds-number-19` | 7.2rem | 72px |
| `--krds-number-20` | 8rem | 80px |
| `--krds-number-21` | 9.6rem | 96px |
| `--krds-number-max` | 100rem | 1000px |

---

## Gap (간격)

| CSS Variable | 참조 Number | rem | px |
|-------------|-------------|-----|-----|
| `--krds-gap-1` | number-2 | 0.2rem | 2px |
| `--krds-gap-2` | number-3 | 0.4rem | 4px |
| `--krds-gap-3` | number-5 | 0.8rem | 8px |
| `--krds-gap-4` | number-7 | 1.2rem | 12px |
| `--krds-gap-5` | number-8 | 1.6rem | 16px |
| `--krds-gap-6` | number-9 | 2rem | 20px |
| `--krds-gap-7` | number-10 | 2.4rem | 24px |
| `--krds-gap-8` | number-12 | 3.2rem | 32px |
| `--krds-gap-9` | number-14 | 4rem | 40px |
| `--krds-gap-10` | number-16 | 4.8rem | 48px |
| `--krds-gap-11` | number-18 | 6.4rem | 64px |
| `--krds-gap-12` | number-20 | 8rem | 80px |

---

## Padding (패딩)

| CSS Variable | 참조 Number | rem | px |
|-------------|-------------|-----|-----|
| `--krds-padding-1` | number-2 | 0.2rem | 2px |
| `--krds-padding-2` | number-3 | 0.4rem | 4px |
| `--krds-padding-3` | number-5 | 0.8rem | 8px |
| `--krds-padding-4` | number-6 | 1rem | 10px |
| `--krds-padding-5` | number-7 | 1.2rem | 12px |
| `--krds-padding-6` | number-8 | 1.6rem | 16px |
| `--krds-padding-7` | number-9 | 2rem | 20px |
| `--krds-padding-8` | number-10 | 2.4rem | 24px |
| `--krds-padding-9` | number-12 | 3.2rem | 32px |
| `--krds-padding-10` | number-14 | 4rem | 40px |

---

## Card Padding

### PC

| 크기 | CSS Variable | 참조 Number | rem | px |
|------|-------------|-------------|-----|-----|
| Large | `--krds-pc-padding-card-large` | number-14 | 4rem | 40px |
| Medium | `--krds-pc-padding-card-medium` | number-12 | 3.2rem | 32px |
| Small | `--krds-pc-padding-card-small` | number-10 | 2.4rem | 24px |
| XSmall | `--krds-pc-padding-card-xsmall` | number-8 | 1.6rem | 16px |

### Mobile

| 크기 | CSS Variable | 참조 Number | rem | px |
|------|-------------|-------------|-----|-----|
| Large | `--krds-mobile-padding-card-large` | number-10 | 2.4rem | 24px |
| Medium | `--krds-mobile-padding-card-medium` | number-10 | 2.4rem | 24px |
| Small | `--krds-mobile-padding-card-small` | number-9 | 2rem | 20px |
| XSmall | `--krds-mobile-padding-card-xsmall` | number-7 | 1.2rem | 12px |

### PC vs Mobile 비교

| 크기 | PC | Mobile | 축소 |
|------|-----|--------|------|
| Large | 40px | 24px | 60% |
| Medium | 32px | 24px | 75% |
| Small | 24px | 20px | 83% |
| XSmall | 16px | 12px | 75% |

---

## Layout Spacing (레이아웃 간격)

### PC 레이아웃 간격

| 위치 | CSS Variable | 참조 Number | rem | px |
|------|-------------|-------------|-----|-----|
| Header → Breadcrumb | `--krds-pc-gap-layout-header-breadcrumb` | number-10 | 2.4rem | 24px |
| Left menu ↔ Contents | `--krds-pc-gap-layout-left-contents` | number-18 | 6.4rem | 64px |
| Contents ↔ Right menu | `--krds-pc-gap-layout-contents-right` | number-14 | 4rem | 40px |
| Contents → Footer | `--krds-pc-gap-layout-contents-footer` | number-18 | 6.4rem | 64px |
| Breadcrumb → H1 | `--krds-pc-gap-layout-breadcrumb-h1` | number-14 | 4rem | 40px |

### Mobile 레이아웃 간격

| 위치 | CSS Variable | 참조 Number | rem | px |
|------|-------------|-------------|-----|-----|
| Header → Breadcrumb | `--krds-mobile-gap-layout-header-breadcrumb` | number-8 | 1.6rem | 16px |
| Left menu ↔ Contents | `--krds-mobile-gap-layout-left-contents` | - | 0rem | 0px |
| Contents ↔ Right menu | `--krds-mobile-gap-layout-contents-right` | - | 0rem | 0px |
| Contents → Footer | `--krds-mobile-gap-layout-contents-footer` | number-14 | 4rem | 40px |
| Breadcrumb → H1 | `--krds-mobile-gap-layout-breadcrumb-h1` | number-12 | 3.2rem | 32px |

---

## Text Hierarchy Spacing (텍스트 계층 간격)

### PC 텍스트 계층 간격

| 관계 | CSS Variable | 참조 Number | rem | px |
|------|-------------|-------------|-----|-----|
| H1 → H2 | `--krds-pc-gap-layout-h1-h2` | number-16 | 4.8rem | 48px |
| H2 → H2 | `--krds-pc-gap-layout-h2-h2` | number-20 | 8rem | 80px |
| H2 → H3 | `--krds-pc-gap-layout-h2-h3` | number-14 | 4rem | 40px |
| H3 → H3 | `--krds-pc-gap-layout-h3-h3` | number-18 | 6.4rem | 64px |
| H3 → H4 | `--krds-pc-gap-layout-h3-h4` | number-10 | 2.4rem | 24px |
| H4 → H4 | `--krds-pc-gap-layout-h4-h4` | number-14 | 4rem | 40px |
| H4 → H5 | `--krds-pc-gap-layout-h4-h5` | number-8 | 1.6rem | 16px |
| H5 → H5 | `--krds-pc-gap-layout-h5-h5` | number-12 | 3.2rem | 32px |
| Title → Body (small) | `--krds-pc-gap-layout-title-body-small` | number-8 | 1.6rem | 16px |
| Title → Body (medium) | `--krds-pc-gap-layout-title-body-medium` | number-9 | 2rem | 20px |
| Title → Body (large) | `--krds-pc-gap-layout-title-body-large` | number-10 | 2.4rem | 24px |

### Mobile 텍스트 계층 간격

| 관계 | CSS Variable | 참조 Number | rem | px |
|------|-------------|-------------|-----|-----|
| H1 → H2 | `--krds-mobile-gap-layout-h1-h2` | number-12 | 3.2rem | 32px |
| H2 → H2 | `--krds-mobile-gap-layout-h2-h2` | number-14 | 4rem | 40px |
| H2 → H3 | `--krds-mobile-gap-layout-h2-h3` | number-10 | 2.4rem | 24px |
| H3 → H3 | `--krds-mobile-gap-layout-h3-h3` | number-12 | 3.2rem | 32px |
| H3 → H4 | `--krds-mobile-gap-layout-h3-h4` | number-8 | 1.6rem | 16px |
| H4 → H4 | `--krds-mobile-gap-layout-h4-h4` | number-10 | 2.4rem | 24px |
| H4 → H5 | `--krds-mobile-gap-layout-h4-h5` | number-7 | 1.2rem | 12px |
| H5 → H5 | `--krds-mobile-gap-layout-h5-h5` | number-8 | 1.6rem | 16px |
| Title → Body (small) | `--krds-mobile-gap-layout-title-body-small` | number-5 | 0.8rem | 8px |
| Title → Body (medium) | `--krds-mobile-gap-layout-title-body-medium` | number-7 | 1.2rem | 12px |
| Title → Body (large) | `--krds-mobile-gap-layout-title-body-large` | number-9 | 2rem | 20px |

---

## Text-Text / Image-Text Spacing

### PC

| 관계 | CSS Variable | 참조 Number | rem | px |
|------|-------------|-------------|-----|-----|
| Text ↔ Text (large) | `--krds-pc-gap-layout-text-text-large` | number-9 | 2rem | 20px |
| Text ↔ Text (medium) | `--krds-pc-gap-layout-text-text-medium` | number-8 | 1.6rem | 16px |
| Text ↔ Text (small) | `--krds-pc-gap-layout-text-text-small` | number-7 | 1.2rem | 12px |
| Image ↔ Text (large) | `--krds-pc-gap-layout-image-text-large` | number-12 | 3.2rem | 32px |
| Image ↔ Text (medium) | `--krds-pc-gap-layout-image-text-medium` | number-10 | 2.4rem | 24px |
| Image ↔ Text (small) | `--krds-pc-gap-layout-image-text-small` | number-9 | 2rem | 20px |

### Mobile

| 관계 | CSS Variable | 참조 Number | rem | px |
|------|-------------|-------------|-----|-----|
| Text ↔ Text (large) | `--krds-mobile-gap-layout-text-text-large` | number-8 | 1.6rem | 16px |
| Text ↔ Text (medium) | `--krds-mobile-gap-layout-text-text-medium` | number-7 | 1.2rem | 12px |
| Text ↔ Text (small) | `--krds-mobile-gap-layout-text-text-small` | number-6 | 1rem | 10px |
| Image ↔ Text (large) | `--krds-mobile-gap-layout-image-text-large` | number-10 | 2.4rem | 24px |
| Image ↔ Text (medium) | `--krds-mobile-gap-layout-image-text-medium` | number-9 | 2rem | 20px |
| Image ↔ Text (small) | `--krds-mobile-gap-layout-image-text-small` | number-8 | 1.6rem | 16px |

---

## Size Height (높이)

| CSS Variable | 참조 Number | rem | px |
|-------------|-------------|-----|-----|
| `--krds-size-height-1` | number-5 | 0.8rem | 8px |
| `--krds-size-height-2` | number-8 | 1.6rem | 16px |
| `--krds-size-height-3` | number-9 | 2rem | 20px |
| `--krds-size-height-4` | number-10 | 2.4rem | 24px |
| `--krds-size-height-5` | number-12 | 3.2rem | 32px |
| `--krds-size-height-6` | number-14 | 4rem | 40px |
| `--krds-size-height-7` | number-16 | 4.8rem | 48px |
| `--krds-size-height-8` | number-17 | 5.6rem | 56px |
| `--krds-size-height-9` | number-18 | 6.4rem | 64px |
| `--krds-size-height-10` | number-19 | 7.2rem | 72px |
| `--krds-size-height-11` | number-20 | 8rem | 80px |

---

## Border Radius (래디어스)

| CSS Variable | 참조 Number | rem | px | Shape 단계 |
|-------------|-------------|-----|-----|-----------|
| `--krds-radius-xsmall1` | number-2 | 0.2rem | 2px | xsmall |
| `--krds-radius-xsmall2` | number-2 | 0.2rem | 2px | xsmall |
| `--krds-radius-xsmall3` | number-2 | 0.2rem | 2px | xsmall |
| `--krds-radius-small1` | number-3 | 0.4rem | 4px | small |
| `--krds-radius-small2` | number-3 | 0.4rem | 4px | small |
| `--krds-radius-small3` | number-3 | 0.4rem | 4px | small |
| `--krds-radius-medium1` | number-4 | 0.6rem | 6px | medium |
| `--krds-radius-medium2` | number-4 | 0.6rem | 6px | medium |
| `--krds-radius-medium3` | number-5 | 0.8rem | 8px | medium |
| `--krds-radius-medium4` | number-5 | 0.8rem | 8px | medium |
| `--krds-radius-large1` | number-6 | 1rem | 10px | large |
| `--krds-radius-large2` | number-6 | 1rem | 10px | large |
| `--krds-radius-xlarge1` | number-7 | 1.2rem | 12px | xlarge |
| `--krds-radius-xlarge2` | number-7 | 1.2rem | 12px | xlarge |
| `--krds-radius-max` | number-max | 100rem | 1000px | max (원형) |

### Radius 계산 규칙

1. **계산식**: `컨테이너 높이 × 0.125`
2. 결과가 홀수이면 **짝수로 올림** (예: 5px → 6px)
3. **최대값 12px** 초과 불가 (`--krds-radius-xlarge` = 12px)
4. 완전 원형이 필요한 경우 `--krds-radius-max` (100rem) 사용

### 높이 기반 Radius 적용 가이드

| 컨테이너 높이 | 계산 (×0.125) | 적용 Radius | 사용 변수 |
|-------------|-------------|------------|----------|
| 16px | 2px | 2px | `--krds-radius-xsmall` |
| 24px | 3px → 4px (올림) | 4px | `--krds-radius-small` |
| 32px | 4px | 4px | `--krds-radius-small` |
| 40px | 5px → 6px (올림) | 6px | `--krds-radius-medium` |
| 48px | 6px | 6px | `--krds-radius-medium` |
| 56px | 7px → 8px (올림) | 8px | `--krds-radius-medium` |
| 64px | 8px | 8px | `--krds-radius-medium` |
| 80px | 10px | 10px | `--krds-radius-large` |
| 96px+ | 12px (최대) | 12px | `--krds-radius-xlarge` |
