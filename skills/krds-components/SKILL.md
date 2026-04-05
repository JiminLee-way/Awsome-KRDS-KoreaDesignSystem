---
name: krds-components
description: Use when implementing UI components (buttons, inputs, menus, modals, tables, cards, etc.) for Korean government digital services following KRDS. Triggers on 버튼, 입력, 메뉴, 헤더, 푸터, 모달, 탭, 테이블, 체크박스, 라디오, 셀렉트, 아코디언, 배지, 캐러셀, 페이지네이션, 컴포넌트.
---

# KRDS 컴포넌트 가이드

## Overview

KRDS(Korea Design System)는 대한민국 정부 디지털 서비스의 일관된 사용자 경험을 위해 10개 카테고리, 43개 이상의 UI 컴포넌트를 정의한다. 모든 컴포넌트의 CSS 클래스는 `krds-` 접두사를 사용한다.

1. **Identity** — 헤더, 푸터, 공식 배너, 운영기관 식별자
2. **Navigation** — 메인 메뉴, 사이드 메뉴, 브레드크럼, 탭, 페이지네이션, 건너뛰기 링크, 콘텐츠 내 탐색
3. **Action** — 버튼, 링크
4. **Input** — 텍스트 입력, 텍스트 영역, 날짜 입력, 파일 업로드, 셀렉트
5. **Selection** — 체크박스, 라디오 버튼, 토글 스위치, 태그
6. **Data Display** — 테이블, 구조화 목록, 텍스트 목록, 배지
7. **Overlay** — 모달, 툴팁
8. **Feedback** — 스피너, 단계 표시기, 긴급 공지
9. **Help** — 도움 패널, 따라하기 패널, 맥락적 도움말, 코치마크
10. **Etc** — 아코디언, 캐러셀, 달력, 디스클로저, 언어 전환, TTS, 리사이즈

---

## Iron Law

> **KRDS에 정의된 컴포넌트가 있으면 커스텀 컴포넌트를 만들지 마세요. html/code/ 파일을 먼저 확인하세요.**

---

## Component Implementation Flow

```
사용자가 컴포넌트 요청
→ Read node_modules/krds-uiux/html/code/{name}.html
→ 정확한 마크업 제공
→ 변형 필요 시 {name}_{variant}.html 추가 Read
→ 커스텀 필요 시 Read resources/scss/component/_{name}.scss
→ JS 필요 시 Read resources/js/component/ui-script.js 관련 부분
→ 아이콘 필요 시 Glob resources/img/component/icon/ 확인
```

---

## HTML Snippet Mapping Table (74 files)

모든 HTML 스니펫은 `node_modules/krds-uiux/html/code/` 에 위치한다.

| Category | Files |
|---|---|
| **Buttons** | `button.html`, `button_size.html`, `button_hierarchy.html`, `button_icon.html`, `button_text.html`, `button_with_icon.html` |
| **Text Input** | `text_input.html`, `text_input_icon.html`, `text_input_size.html`, `text_input_state.html` |
| **Select** | `select.html`, `select_size.html`, `select_sorting.html`, `select_state.html` |
| **Checkbox** | `checkbox.html`, `checkbox_chip.html`, `checkbox_size.html` |
| **Radio** | `radio_button.html`, `radio_chip.html`, `radio_size.html` |
| **Toggle** | `toggle_switch.html`, `toggle_switch_size.html` |
| **Identity** | `header.html`, `footer.html`, `masthead.html`, `identifier.html` |
| **Navigation** | `main_menu_pc.html`, `main_menu_mobile.html`, `side_navigation.html`, `breadcrumb.html`, `pagination.html`, `skip_link.html`, `tab.html`, `in_page_navigation.html` |
| **Overlay** | `modal.html`, `modal_sample.html`, `tooltip.html`, `tooltip_box.html`, `tooltip_vertical.html` |
| **Accordion** | `accordion.html`, `accordion_line.html` |
| **Data** | `table.html`, `structured_list.html`, `structured_list_table.html`, `text_list.html`, `text_list_ordered.html` |
| **Badge/Tag** | `badge.html`, `badge_number.html`, `badge_size.html`, `tag.html`, `tag_link.html` |
| **Media** | `carousel.html`, `carousel_banner.html`, `calendar.html`, `calendar_range.html` |
| **Input** | `date_input.html`, `textarea.html`, `file_upload.html` |
| **Feedback** | `spinner.html`, `step_indicator.html` |
| **Help** | `help_panel.html`, `tutorial_panel.html`, `contextual_help.html`, `coach_mark.html` |
| **Alert** | `critical_alerts.html` |
| **Settings** | `language_switcher.html`, `language_switcher_page.html`, `resize.html` |
| **Accessibility** | `tts.html`, `tts_icon.html`, `tts_size.html` |
| **Other** | `disclosure.html`, `link.html`, `favicon.html` |

---

## Common Rules

### Border Radius 5단계

컴포넌트 래디어스는 컨테이너 높이에 비례하며, 최대 12px이다.

| 단계 | 크기 |
|------|------|
| xsmall | 2px |
| small | 4px |
| medium | 6~8px |
| large | 10px |
| xlarge | 12px |

### 상태 색상 패턴

| 상태 | Primary Fill | Secondary Fill | Tertiary Fill |
|------|-------------|----------------|---------------|
| Default | primary-50 | primary-5 | transparent |
| Hover | primary-60 | primary-10 | gray-5 |
| Pressed | primary-70 | primary-20 | gray-10 |
| Disabled | gray-20 | gray-5 | gray-5 |

### 접근성 필수 속성

모든 대화형 컴포넌트에는 다음 ARIA 속성을 적절히 적용한다:

- `aria-label` — 시각적 레이블이 없는 요소에 대체 텍스트 제공
- `aria-expanded` — 아코디언, 드롭다운 등 펼침/접힘 상태 표시
- `aria-selected` — 탭, 목록 등 선택 상태 표시
- `role` — 시맨틱 HTML로 표현할 수 없는 역할 명시

### 키보드 상호작용 원칙

| 키 | 동작 |
|----|------|
| `Tab` | 포커스 이동 (다음 대화형 요소) |
| `Shift+Tab` | 포커스 이동 (이전 대화형 요소) |
| `Enter` | 활성화 / 실행 |
| `Space` | 활성화 / 토글 |
| `Esc` | 닫기 / 취소 |
| `Arrow` | 목록/탭/메뉴 내 항목 이동 |

### 포커스 링

포커스 링은 모든 대화형 요소에 표시되어야 하며, `outline` 속성으로 구현한다. 포커스 링을 제거하거나 숨기지 않는다.

---

## Icon Guide

### 위치

아이콘 SVG 파일은 `node_modules/krds-uiux/resources/img/component/icon/` 에 91개 존재한다.

### 주요 아이콘 목록

| 아이콘 | 파일명 | 용도 |
|--------|--------|------|
| 이동 | `ico_go.svg` | 외부 링크, 바로가기 |
| 닫기 | `ico_close.svg` | 모달, 패널 닫기 |
| 화살표 | `ico_angle.svg` | 드롭다운, 아코디언, 페이지네이션 |
| 달력 | `ico_calendar.svg` | 날짜 입력 |
| 검색 | `ico_sch.svg` | 검색 입력 |
| 다운로드 | `ico_download.svg` | 파일 다운로드 |
| 업로드 | `ico_upload.svg` | 파일 업로드 |
| 삭제 | `ico_delete.svg` | 항목 삭제 |
| 도움말 | `ico_help.svg` | 도움말 트리거 |
| 정보 | `ico_information.svg` | 정보 메시지 |
| 홈 | `ico_bread_home.svg` | 브레드크럼 홈 |
| 더보기 | `ico_more.svg` | 추가 동작 |
| 필터 | `ico_filter.svg` | 필터 동작 |
| 확장 | `ico_expand.svg` | 영역 확장 |
| 볼륨 | `ico_volume.svg` | TTS 음성 |

### 사용 방법

```html
<!-- img 태그 방식 -->
<img src="resources/img/component/icon/ico_go.svg" alt="바로가기" />

<!-- 인라인 SVG 방식 (색상 제어 가능) -->
<svg class="krds-icon" aria-hidden="true">
  <use xlink:href="#ico_go"></use>
</svg>
```

아이콘은 반드시 텍스트 레이블과 함께 사용해야 한다. 아이콘만 단독으로 사용할 경우 `aria-label`을 제공한다.

---

## JS Guide

### JS가 필요한 19개 컴포넌트

다음 컴포넌트는 JavaScript 동작이 필수이며, 모든 스크립트는 `resources/js/component/ui-script.js`에서 관리된다.

| 컴포넌트 | JS 동작 |
|----------|---------|
| accordion | 패널 펼침/접힘, aria-expanded 토글 |
| tab | 탭 전환, aria-selected 토글, Arrow 키 탐색 |
| modal | 열기/닫기, 포커스 트랩, inert 관리 |
| calendar | 월/연 이동, 날짜 선택, 범위 선택 |
| tooltip | 호버/포커스 시 표시, 위치 계산 |
| contextual_help | 인라인 도움말 토글 |
| main_menu | 서브메뉴 확장/축소, 모바일 토글 |
| side_navigation | 하위 메뉴 확장/축소 |
| help_panel | 슬라이드 열기/닫기 |
| tutorial_panel | 단계 이동, 진행률 표시 |
| disclosure | 콘텐츠 펼침/접힘 |
| file_upload | 파일 선택, 목록 관리, 삭제 |
| toggle_switch | 토글 상태 전환 |
| tts | 텍스트 음성 변환 제어 |
| in_page_navigation | 스크롤 연동, 현재 섹션 강조 |
| carousel | 슬라이드 이동, 자동재생 제어 |
| dropdown | 드롭다운 열기/닫기 |
| resize | 텍스트 크기 조절 |
| coach_mark | 순차 안내, 단계 이동 |

### 참조 방법

```javascript
// ui-script.js 내 관련 함수를 Read로 확인
Read resources/js/component/ui-script.js
// 컴포넌트명으로 검색하여 해당 초기화 및 이벤트 바인딩 코드 확인
```

---

## 레퍼런스 파일

각 컴포넌트 카테고리별 상세 가이드라인은 다음 레퍼런스 파일을 참조한다:

- `references/identity.md` — 헤더, 푸터, 공식 배너, 운영기관 식별자
- `references/navigation.md` — 메인 메뉴, 사이드 메뉴, 브레드크럼, 탭, 페이지네이션, 건너뛰기 링크, 콘텐츠 내 탐색
- `references/action-input.md` — 버튼, 링크, 텍스트 입력, 텍스트 영역, 날짜 입력, 파일 업로드
- `references/selection.md` — 라디오 버튼, 셀렉트, 체크박스, 태그
- `references/layout.md` — 모달, 아코디언, 탭, 테이블, 배지, 캐러셀 등 레이아웃/표시 컴포넌트
