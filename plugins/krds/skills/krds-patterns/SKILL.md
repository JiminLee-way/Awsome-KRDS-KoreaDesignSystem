---
name: krds-patterns
description: Use when designing page-level patterns for Korean government digital services — search flows, login, application forms, policy pages, list browsing, filtering, error handling. Triggers on 검색, 로그인, 신청, 입력폼, 목록, 필터링, 정렬, 첨부파일, 동의, 오류, 정책 정보, 서비스 패턴, 기본 패턴.
---

# KRDS 패턴 시스템

## Overview

KRDS 패턴은 기본 패턴(Global) 11종과 서비스 패턴(Service) 5종, 총 16종으로 구성됩니다.

| 구분 | 종류 | 수량 |
|------|------|------|
| 기본 패턴 (Global) | 목록 탐색, 필터링/정렬, 상세 정보, 첨부파일, 개인 식별 정보 입력, 입력폼, 동의, 도움, 사용자 피드백, 오류, 확인 | 11종 |
| 서비스 패턴 (Service) | 방문, 검색, 로그인, 신청, 정책 정보 확인 | 5종 |

## Iron Law

> 서비스 패턴의 '필수' 항목을 건너뛰지 마세요. 권장/우수는 단계적으로 확장하되, 필수는 반드시 먼저 구현하세요.

## Pattern System

### 기본 패턴 (Global Patterns)

페이지 유형에 관계없이 공통으로 적용되는 패턴입니다. 목록 탐색, 필터링/정렬, 입력폼, 첨부파일 등 어떤 서비스에서든 반복적으로 등장하는 UI 구조와 상호작용을 다룹니다.

- 참조: `references/global-patterns.md`

### 서비스 패턴 (Service Patterns)

특정 과업 흐름 전체를 다루는 패턴입니다. 사용자가 서비스에 방문하여 검색하고, 로그인하고, 신청서를 작성하고, 정책 정보를 확인하는 등 종단 간(end-to-end) 시나리오를 설계할 때 사용합니다.

- 참조: `references/service-patterns.md`

## 적용 수준

패턴의 각 가이드라인은 아래 3단계 수준으로 구분됩니다.

| 수준 | 표기 | 의미 |
|------|------|------|
| **필수** | Do | 미준수 시 사용자가 과업을 완료하지 못하거나 심각한 문제가 발생합니다. |
| **권장** | Better | 미준수 시 과업 수행 난도가 상승하고 사용자 경험이 저하됩니다. |
| **우수** | Best | 준수 시 사용자 만족도가 대폭 향상됩니다. |

## 패턴 탐색 분기

사용자 과업에 따라 아래와 같이 참조 파일을 안내합니다.

| 사용자 과업 | 참조 파일 |
|------------|----------|
| 목록을 보여주고 싶다 / 필터링·정렬이 필요하다 | `references/global-patterns.md` |
| 입력폼을 설계한다 / 첨부파일을 다룬다 | `references/global-patterns.md` |
| 동의 화면, 오류 처리, 확인 단계가 필요하다 | `references/global-patterns.md` |
| 도움말·피드백 화면을 구성한다 | `references/global-patterns.md` |
| 검색 흐름 전체를 설계한다 | `references/service-patterns.md` |
| 로그인 흐름을 설계한다 | `references/service-patterns.md` |
| 신청·접수 프로세스를 설계한다 | `references/service-patterns.md` |
| 방문(메인 화면)을 구성한다 | `references/service-patterns.md` |
| 정책 정보 페이지를 만든다 | `references/service-patterns.md` |

## 추천 메인 페이지 레이아웃 (공정거래위원회 참조)

공정위(ftc.go.kr)는 KRDS 가이드라인을 적용한 성공 사례 중 하나입니다. 아래는 공정위 수준의 메인 페이지를 구현하기 위한 추천 레이아웃 패턴입니다.

### 페이지 섹션 구조 (6단)

```
1. 공식 배너 — "이 누리집은 대한민국 공식 전자정부 누리집입니다."
2. 헤더 — 로고 + 유틸리티 링크 + 통합검색 + 메인 메뉴 (6~7개 1depth)
─── main 시작 ───
3. 주요소식 슬라이드쇼 — Swiper fade, 텍스트 좌 + 이미지 우 (높이 406px)
4. 자주찾는 서비스 — 아이콘 그리드 퀵메뉴 (6~9개)
5. 소식 탭 — 탭 전환형 뉴스 목록 (보도자료/공지/채용 등 3~7개 탭)
6. 알림판 + SNS + 배너 — 알림판(캐러셀) + SNS 탭(유튜브/인스타/블로그) + 배너
─── main 끝 ───
7. 푸터 — 관련 사이트 드롭다운 + 기관 로고 + 연락처 + 정책 링크 + 저작권
```

### 섹션 3: 주요소식 슬라이드쇼 상세 스펙

실제 공정위 사이트의 측정값 기준:

| 요소 | 값 |
|------|-----|
| 섹션 클래스 | `.main-sect.news` |
| 전체 높이 | 406px |
| 최대 너비 | 콘텐츠 영역 1200px 내 |
| 텍스트 영역 | 좌측 약 43% (493px), `padding-top: 60px` |
| 이미지 영역 | 우측 약 56% (640px), `height: 406px` |
| 이미지 처리 | `background-image` + `background-size: cover` + `border-radius: 12px` |
| 전환 효과 | **Swiper fade** (`effect: 'fade'`, `crossFade: true`) |
| 전환 속도 | 400ms |
| 자동 재생 | 4000ms 간격, `pauseOnMouseEnter: true` |
| 인디케이터 | bullets(점) + 재생/멈춤 + 이전/다음 |
| 슬라이드 수 | 5~7개 권장 |

**텍스트 타이포그래피:**
- 제목 (`.text-title`): Heading large (32px), bold, `gray-90`
- 본문 (`.text-cont`): Body large (19px), regular, `gray-60`, `white-space: pre-wrap`
- 링크 (`.news-more`): Body medium (17px), primary 색상, 밑줄

**반응형 (768px 이하):**
- flex-direction: column-reverse (이미지 위, 텍스트 아래)
- 이미지 높이: 200px, 너비 100%
- 텍스트 제목: Heading large mobile (24px)

상세 HTML/CSS/JS 코드는 `references/layout.md`의 캐러셀 > 추천 패턴: 뉴스/주요소식 Fade 슬라이드쇼 참조.

### 섹션 4: 자주찾는 서비스 퀵메뉴

```html
<section class="main-sect service">
  <div class="inner">
    <h2 class="sr-only">자주찾는 서비스</h2>
    <ul class="service-list">
      <li>
        <a href="/url">
          <span class="ico"><i class="svg-icon ico-name"></i></span>
          <span class="txt">서비스명</span>
        </a>
      </li>
      <!-- 6~9개 반복 -->
    </ul>
  </div>
</section>
```

**스펙:**
- 가로 한 줄 배치 (flex, `justify-content: center`, `gap: 24px`)
- 각 아이콘: 48~64px SVG, 텍스트 아래 배치
- 모바일: 2열 그리드로 전환

### 섹션 5: 소식 탭

```html
<section class="main-sect notice">
  <div class="inner">
    <h2>소식 제목</h2>
    <!-- KRDS 탭 컴포넌트 사용 -->
    <div class="krds-tab-area">
      <ul class="tab-list" role="tablist">
        <li role="presentation">
          <button role="tab" aria-selected="true">보도자료</button>
        </li>
        <li role="presentation">
          <button role="tab" aria-selected="false">공지사항</button>
        </li>
        <li role="presentation">
          <button role="tab" aria-selected="false">채용·입찰</button>
        </li>
      </ul>
      <div role="tabpanel">
        <ul class="news-list">
          <li>
            <a href="/detail">
              <span class="title">게시물 제목</span>
              <span class="date">2026.04.05</span>
            </a>
          </li>
          <!-- 4~5개 반복 -->
        </ul>
        <a href="/list" class="more">더보기</a>
      </div>
    </div>
  </div>
</section>
```

**스펙:**
- KRDS 탭 컴포넌트 (`html/code/tab.html`) 사용
- 탭 3~7개, 각 탭 패널에 게시물 4~5개
- 게시물: 제목 + 날짜 (1행)
- "더보기" 링크로 전체 목록 이동

### 섹션 6: 알림판 + SNS

**알림판:**
- KRDS 캐러셀 (`carousel_banner.html`) 사용
- 이미지 배너 2~4개, 자동 슬라이드

**SNS 탭:**
- 탭: 유튜브 / 인스타그램 / 블로그
- 각 탭에 최신 게시물 3개 (썸네일 + 제목)
- SNS 바로가기 아이콘 (페이스북, X 등)

### 전체 CSS 구조 가이드

```css
/* 메인 페이지 섹션 간격 */
.main-sect { padding: 64px 0; }          /* PC: gap-11 (64px) */
.main-sect + .main-sect { padding-top: 48px; }

/* 콘텐츠 래퍼 */
.inner { max-width: 1200px; margin: 0 auto; padding: 0 24px; }

/* 모바일 */
@media (max-width: 767px) {
  .main-sect { padding: 40px 0; }
  .inner { padding: 0 16px; }
}
```

---

## 에셋 참조

패턴 구현 시 필요한 컴포넌트(버튼, 입력 필드, 페이지네이션, 배지 등)는 **krds-components** 스킬로 위임합니다. 패턴은 "무엇을, 어떤 순서로" 배치할지를 정의하고, 컴포넌트는 "어떻게 생겼고, 어떤 속성이 있는지"를 정의합니다.
