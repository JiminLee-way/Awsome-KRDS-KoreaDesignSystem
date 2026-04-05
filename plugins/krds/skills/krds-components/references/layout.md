# Layout & Display 컴포넌트

## 모달 (Modal)

### 용도

사용자의 주의를 집중시키는 대화상자. 확인, 경고, 폼 입력 등 중요한 상호작용에 사용한다.

### HTML 스니펫

```
html/code/modal.html
html/code/modal_sample.html
```

### 구조

- 딤드 배경 (`krds-modal-backdrop`)
- 모달 컨테이너 (`krds-modal`)
  - 헤더 (제목 + 닫기 버튼)
  - 본문 (콘텐츠)
  - 푸터 (액션 버튼)

### 가이드라인

1. **포커스 트랩**: 모달이 열리면 포커스가 모달 내부에 갇혀야 한다. Tab 키로 모달 외부 요소에 도달할 수 없어야 한다.
2. **inert**: 모달이 열리면 모달 외부의 모든 요소에 `inert` 속성을 적용하여 보조 기기의 접근을 차단한다.
3. **딤드 배경**: 모달 외부를 `--krds-light-color-background-dim` (alpha-black75)으로 어둡게 처리한다.
4. **닫기 필수**: 닫기 버튼(`X`)과 Esc 키를 모두 제공한다. 딤드 배경 클릭으로도 닫을 수 있다.
5. **다중 파일 업로드 금지**: 모달 내에서 다중 파일 업로드를 사용하지 않는다. 단일 파일만 허용한다.
6. `role="dialog"`, `aria-modal="true"`, `aria-labelledby`를 적용한다.
7. 모달 닫힘 시 포커스를 모달을 열었던 요소로 복귀시킨다.
8. KWCAG 2.2 / WCAG 2.1 준수: 2.1.2 No Keyboard Trap (역설적으로 포커스 트랩이지만 Esc로 탈출 보장)

---

## 아코디언 (Accordion)

### 용도

관련 콘텐츠를 접기/펼치기 형태로 구조화하여 제공한다. 긴 콘텐츠를 계층적으로 정리할 때 사용한다.

### HTML 스니펫

```
html/code/accordion.html
html/code/accordion_line.html
```

### 구조

- 아코디언 컨테이너 (`krds-accordion`)
  - 아코디언 항목
    - 헤더 (제목 + 토글 버튼)
    - 패널 (콘텐츠)

### 가이드라인

1. 토글 버튼에 `aria-expanded="true|false"` 속성을 적용한다. 열림/닫힘 상태를 명확히 전달한다.
2. 계층적으로 구조화하여 관련 콘텐츠를 그룹화한다.
3. 헤더 텍스트만으로 내부 콘텐츠를 예상할 수 있도록 명확한 제목을 사용한다.
4. 패널에 `role="region"`과 `aria-labelledby`를 적용한다.
5. Enter/Space 키로 펼침/접힘을 토글한다.
6. 초기 상태에서 모든 패널을 접어 놓거나, 첫 번째 패널만 펼쳐 놓는다.
7. 한 번에 하나만 열리는 모드(exclusive)와 여러 개 열리는 모드(non-exclusive) 모두 지원한다.
8. KWCAG 2.2 / WCAG 2.1 준수: 4.1.2 Name, Role, Value

---

## 탭 (Tab)

### 용도

동일 영역 내에서 여러 패널의 콘텐츠를 전환하여 표시한다. 관련 콘텐츠를 카테고리별로 분류할 때 사용한다.

### HTML 스니펫

```
html/code/tab.html
```

### 구조

- 탭 컨테이너 (`krds-tab`)
  - 탭 리스트 (`role="tablist"`)
    - 탭 버튼 (`role="tab"`)
  - 탭 패널 (`role="tabpanel"`)

### 가이드라인

1. 선택된 탭에 `aria-selected="true"`를 적용한다. 나머지 탭은 `aria-selected="false"`.
2. Arrow Left/Right 키로 탭 간 이동을 지원한다.
3. 탭 버튼에 `aria-controls`로 대응하는 패널을 연결한다.
4. 패널에 `aria-labelledby`로 대응하는 탭 버튼을 연결한다.
5. 선택되지 않은 탭은 `tabindex="-1"`로 설정하여 Tab 키로 건너뛴다.
6. 탭이 많을 경우 가로 스크롤 또는 "더보기" 드롭다운을 제공한다.
7. KWCAG 2.2 / WCAG 2.1 준수: 4.1.2 Name, Role, Value

---

## 표 (Table)

### 용도

구조화된 데이터를 행과 열로 표시한다. 비교, 정렬, 필터링이 필요한 데이터에 적합하다.

### HTML 스니펫

```
html/code/table.html
```

### 구조

- 테이블 컨테이너
  - 테이블 (`<table>`)
    - 테이블 헤더 (`<thead>`)
      - 헤더 행 (`<tr>`)
        - 헤더 셀 (`<th>`)
    - 테이블 바디 (`<tbody>`)
      - 데이터 행 (`<tr>`)
        - 데이터 셀 (`<td>`)
    - 테이블 캡션 (`<caption>`)

### 가이드라인

1. **반응형 스크롤**: 모바일에서 테이블이 화면 너비를 초과하면 가로 스크롤을 제공한다. 테이블을 `overflow-x: auto` 컨테이너로 감싼다.
2. **헤더 고정**: 긴 테이블에서 스크롤 시 헤더 행을 상단에 고정한다 (`position: sticky; top: 0`).
3. **scope 속성**: 모든 `<th>` 요소에 `scope="col"` 또는 `scope="row"`를 적용한다.
4. `<caption>` 태그로 테이블의 목적을 설명한다.
5. 복잡한 헤더 구조에는 `headers` 속성을 사용한다.
6. 빈 셀에는 "-" 또는 "해당 없음"을 표시한다 (비워두지 않는다).
7. KWCAG 2.2 / WCAG 2.1 준수: 1.3.1 Info and Relationships

---

## 배지 (Badge)

### 용도

상태, 카운트, 분류 등을 간결하게 표시하는 작은 레이블 요소. 텍스트 배지와 숫자 배지로 구분한다.

### HTML 스니펫

```
html/code/badge.html
html/code/badge_number.html
html/code/badge_size.html
```

### 구조

- 배지 요소 (`krds-badge`)
  - 텍스트 또는 숫자

### 가이드라인

1. **변형**: outline(테두리만), bg(배경 채움), light(연한 배경) 3가지 스타일을 제공한다. 문맥에 맞는 스타일을 선택한다.
2. **숫자 배지** (`badge_number.html`): 알림 카운트 등에 사용한다. 99를 초과하면 "99+"로 표시한다.
3. 배지 텍스트는 간결하게 유지한다 (1~2단어).
4. 배지는 장식 요소이므로 `aria-label`로 의미를 전달하거나, 연관 요소에 `aria-describedby`로 연결한다.
5. 색상만으로 상태를 구분하지 않는다. 텍스트로 상태를 명시한다.

---

## 캐러셀 (Carousel)

### 용도

여러 콘텐츠(이미지, 카드 등)를 수평으로 슬라이드하며 순차적으로 표시한다.

### HTML 스니펫

```
html/code/carousel.html
html/code/carousel_banner.html
```

### 구조

- 캐러셀 컨테이너 (`krds-carousel`)
  - 슬라이드 목록
    - 슬라이드 항목
  - 이전/다음 버튼
  - 인디케이터 (점, 번호)
  - 재생/정지 버튼

### 가이드라인

1. **Swiper.js**: KRDS 캐러셀은 Swiper.js 라이브러리를 기반으로 구현한다.
2. **자동재생 제어**: 자동재생 캐러셀에는 반드시 재생/정지 버튼을 제공한다. 사용자가 자동 전환을 중지할 수 있어야 한다.
3. 이전/다음 버튼에 `aria-label`을 제공한다.
4. 현재 슬라이드 위치를 인디케이터로 표시한다 ("2/5" 등).
5. 자동재생 시 충분한 표시 시간을 확보한다 (최소 5초).
6. 모바일에서는 스와이프 제스처를 지원한다.
7. KWCAG 2.2 / WCAG 2.1 준수: 2.2.2 Pause, Stop, Hide

### 추천 패턴: 뉴스/주요소식 Fade 슬라이드쇼

텍스트 좌측 + 이미지 우측 분리 레이아웃에 fade 전환 효과를 적용하는 패턴.
공공기관 메인 화면의 주요소식 영역에 적합하다.

**핵심 특징:**
- `swiper-fade` 효과: 슬라이드가 겹쳐서 opacity로 전환 (좌우 이동이 아님)
- 텍스트와 이미지가 분리된 레이아웃 (좌: 제목+본문+링크, 우: 배경이미지)
- 이미지는 `<img>` 태그 대신 `background-image`로 처리하여 비율 유지

**HTML 구조:**
```html
<section class="main-sect news">
  <div class="inner">
    <h2 class="sr-only">주요소식</h2>

    <!-- Swiper: fade 효과 사용 -->
    <div class="news-swiper swiper-container swiper-fade">
      <ul class="news-list swiper-wrapper" aria-live="off">

        <!-- 슬라이드 1 -->
        <li class="news-item swiper-slide" role="group" aria-label="1 / 5">
          <div class="news-text">
            <p class="text-title">슬라이드 제목</p>
            <p class="text-cont">슬라이드 본문 설명 텍스트.
두 줄까지 표시 가능합니다.</p>
          </div>
          <div class="news-img" style="background-image: url('/path/to/image.png');">
            <span class="sr-only">이미지 설명</span>
          </div>
          <a href="/detail" class="news-more">자세히 보러가기</a>
        </li>

        <!-- 슬라이드 2 -->
        <li class="news-item swiper-slide" role="group" aria-label="2 / 5">
          <div class="news-text">
            <p class="text-title">두 번째 슬라이드 제목</p>
            <p class="text-cont">두 번째 슬라이드 설명</p>
          </div>
          <div class="news-img" style="background-image: url('/path/to/image2.png');">
            <span class="sr-only">이미지 설명</span>
          </div>
          <a href="/detail2" class="news-more">자세히 보러가기</a>
        </li>

        <!-- 슬라이드 3~5 동일 구조 -->

      </ul>
      <span class="swiper-notification" aria-live="assertive" aria-atomic="true"></span>
    </div>

    <!-- 인디케이터 (슬라이더 외부에 배치) -->
    <div class="swiper-indicator">
      <div class="swiper-pagination"></div>
      <div class="swiper-controller">
        <button type="button" class="swiper-button-play" style="display: none;">
          <span class="sr-only">주요소식 슬라이드 재생</span>
        </button>
        <button type="button" class="swiper-button-stop">
          <span class="sr-only">주요소식 슬라이드 멈춤</span>
        </button>
      </div>
      <div class="swiper-navigation">
        <button type="button" class="swiper-button-prev" aria-label="Previous slide">
          <span class="sr-only">이전 주요소식으로 이동</span>
        </button>
        <button type="button" class="swiper-button-next" aria-label="Next slide">
          <span class="sr-only">다음 주요소식으로 이동</span>
        </button>
      </div>
    </div>
  </div>
</section>
```

**CSS (KRDS 토큰 기반):**
```css
.main-sect.news {
  position: relative;
  overflow: hidden;
}

.main-sect.news .inner {
  max-width: 1200px;      /* KRDS 최대 콘텐츠 너비 */
  margin: 0 auto;
  padding: 0 var(--krds-padding-8); /* 24px */
}

.news-item {
  display: flex;
  align-items: center;
  gap: var(--krds-gap-10); /* 48px */
  min-height: 400px;
}

/* 텍스트 영역 (좌측) */
.news-text {
  flex: 1;
  min-width: 0;
}

.news-text .text-title {
  font-size: var(--krds-pc-font-size-heading-large); /* 3.2rem (32px) */
  font-weight: 700;
  line-height: 150%;
  color: var(--krds-color-light-gray-90);
  margin-bottom: var(--krds-gap-5); /* 16px */
}

.news-text .text-cont {
  font-size: var(--krds-pc-font-size-body-large); /* 1.9rem (19px) */
  font-weight: 400;
  line-height: 150%;
  color: var(--krds-color-light-gray-60);
  white-space: pre-wrap;     /* 줄바꿈 유지 */
  margin-bottom: var(--krds-gap-7); /* 24px */
}

.news-more {
  display: inline-flex;
  align-items: center;
  font-size: var(--krds-pc-font-size-body-medium); /* 1.7rem */
  color: var(--krds-color-light-primary-50);
  text-decoration: underline;
}

/* 이미지 영역 (우측) */
.news-img {
  flex: 0 0 480px;
  height: 360px;
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;
  border-radius: var(--krds-radius-xlarge); /* 12px */
}

/* 반응형: 모바일에서 세로 배치 */
@media (max-width: 767px) {
  .news-item {
    flex-direction: column-reverse; /* 이미지 위, 텍스트 아래 */
    gap: var(--krds-gap-7); /* 24px */
    min-height: auto;
  }

  .news-img {
    flex: none;
    width: 100%;
    height: 200px;
  }

  .news-text .text-title {
    font-size: var(--krds-mobile-font-size-heading-large); /* 2.4rem */
  }
}
```

**JS 초기화 (fade 효과 + autoplay):**
```javascript
const newsSwiper = new Swiper('.news-swiper', {
  effect: 'fade',             // 핵심: fade 전환 효과
  fadeEffect: { crossFade: true },
  slidesPerView: 1,
  loop: true,
  speed: 400,
  watchSlidesProgress: true,
  autoplay: {
    delay: 4000,              // 4초 (최소 5초 권장이나 뉴스 특성상 4초)
    disableOnInteraction: false,
    pauseOnMouseEnter: true,
  },
  pagination: {
    el: '.swiper-pagination',
    clickable: true,
  },
  navigation: {
    nextEl: '.swiper-button-next',
    prevEl: '.swiper-button-prev',
  },
});

// 재생/멈춤 토글
const $play = document.querySelector('.swiper-button-play');
const $stop = document.querySelector('.swiper-button-stop');
$play.style.display = 'none';

$play.addEventListener('click', () => {
  newsSwiper.autoplay.start();
  $stop.style.display = '';
  $play.style.display = 'none';
});

$stop.addEventListener('click', () => {
  newsSwiper.autoplay.stop();
  $stop.style.display = 'none';
  $play.style.display = '';
});
```

**주의사항:**
- `effect: 'fade'`를 사용하려면 반드시 `swiper-bundle.min.css`와 `.js`를 로드해야 함
- 이미지는 `<img>` 대신 `background-image`로 처리해야 fade 전환 시 깜빡임이 없음
- `background-size: contain`으로 이미지 비율을 유지 (이미지가 잘리지 않음)
- 슬라이드 내부에 `<a class="news-more">`를 넣어 각 슬라이드별 링크 제공
- `aria-live="off"`를 wrapper에 설정하여 자동 재생 중 스크린 리더가 매번 읽지 않도록 함
- `role="group"` + `aria-label="1 / N"`으로 현재 슬라이드 위치 접근성 제공

---

## 달력 (Calendar)

### 용도

날짜를 시각적으로 선택하는 피커 컴포넌트. 단일 날짜 또는 날짜 범위를 선택한다.

### HTML 스니펫

```
html/code/calendar.html
html/code/calendar_range.html
```

### 구조

- 달력 컨테이너 (`krds-calendar`)
  - 헤더 (월/연 표시 + 이동 버튼)
  - 요일 헤더
  - 날짜 그리드
  - 오늘 표시
  - 선택 범위 표시 (범위 선택 시)

### 가이드라인

1. **월/연 이동**: 이전/다음 월 버튼과 연도 이동 기능을 제공한다.
2. **범위 선택** (`calendar_range.html`): 시작일과 종료일을 선택하면 그 사이의 날짜가 시각적으로 강조된다.
3. 오늘 날짜를 시각적으로 구분한다.
4. 선택 불가능한 날짜는 비활성 상태로 표시한다.
5. `role="grid"`, 날짜 셀에 `role="gridcell"`을 적용한다.
6. Arrow 키로 날짜 간 이동을 지원한다.
7. KWCAG 2.2 / WCAG 2.1 준수: 4.1.2 Name, Role, Value

---

## 디스클로저 (Disclosure)

### 용도

콘텐츠의 펼침/접기를 제어하는 간단한 토글 컴포넌트. 아코디언과 유사하지만 단일 항목에 사용한다.

### HTML 스니펫

```
html/code/disclosure.html
```

### 가이드라인

1. `<details>`와 `<summary>` 태그를 사용하거나, `aria-expanded` 속성으로 구현한다.
2. 토글 버튼에 펼침/접힘 상태를 시각적으로 표시한다 (화살표 아이콘 회전 등).
3. Enter/Space 키로 토글한다.
4. 초기 상태는 접힌 상태를 기본으로 한다.

---

## 구조화 목록 (Structured List)

### 용도

키-값 쌍 형태의 정보를 구조화하여 표시한다. 상세 정보, 프로필 데이터 등에 적합하다.

### HTML 스니펫

```
html/code/structured_list.html
html/code/structured_list_table.html
```

### 가이드라인

1. **키-값 쌍**: 항목명(키)과 값을 명확하게 구분하여 표시한다.
2. **테이블형** (`structured_list_table.html`): `<table>` 마크업으로 더 정형화된 형태를 제공한다.
3. `<dl>`, `<dt>`, `<dd>` 태그를 사용하여 시맨틱하게 마크업한다 (비테이블형).
4. 테이블형은 `scope` 속성을 적용한다.
5. 빈 값에는 "-" 또는 "없음"을 표시한다.

---

## 이미지 (Image)

### 가이드라인

1. **반응형**: `max-width: 100%`로 컨테이너 너비에 맞게 조절한다.
2. **alt 텍스트 필수**: 모든 `<img>` 태그에 의미 있는 `alt` 텍스트를 제공한다. 장식용 이미지는 `alt=""`로 설정한다.
3. `<figure>`와 `<figcaption>`을 사용하여 이미지에 설명을 제공한다.
4. 로딩 지연 시 적절한 `width`/`height` 속성으로 레이아웃 이동(CLS)을 방지한다.
5. KWCAG 2.2 / WCAG 2.1 준수: 1.1.1 Non-text Content

---

## 긴급 공지 (Critical Alerts)

### 용도

시스템 장애, 보안 경고 등 긴급한 정보를 사용자에게 즉시 전달하는 배너.

### HTML 스니펫

```
html/code/critical_alerts.html
```

### 가이드라인

1. **최상위 엘리베이션**: 다른 모든 콘텐츠 위에 표시한다 (z-index 최상위, Elevation +4).
2. **시스템 색상**: Danger(위험), Warning(경고), Information(정보) 시스템 색상을 사용한다.
3. `role="alert"` 또는 `role="status"`를 적용하여 스크린 리더가 즉시 읽도록 한다.
4. 닫기 버튼을 제공한다 (닫을 수 있는 경우).
5. 아이콘과 텍스트를 함께 사용하여 색상만으로 상태를 전달하지 않는다.

---

## 단계 표시기 (Step Indicator)

### 용도

다단계 프로세스에서 현재 진행 단계를 표시한다. 회원가입, 주문 과정 등에 사용한다.

### HTML 스니펫

```
html/code/step_indicator.html
```

### 가이드라인

1. **현재/완료/미완료 상태 구분**: 각 단계를 현재(active), 완료(completed), 미완료(pending) 3가지 상태로 시각적으로 구분한다.
2. 현재 단계에 `aria-current="step"`을 적용한다.
3. 완료된 단계에 체크 아이콘(`ico_step_done.svg`)을 표시한다.
4. 단계 수는 3~7개가 적절하다.
5. 각 단계에 명확한 레이블을 제공한다.
6. 모바일에서는 현재 단계와 전체 진행률만 간략하게 표시할 수 있다.

---

## 스피너 (Spinner)

### 용도

데이터 로딩 등 처리 중 상태를 시각적으로 표시한다.

### HTML 스니펫

```
html/code/spinner.html
```

### 가이드라인

1. **로딩 상태**: 스피너가 표시되는 동안 해당 영역의 콘텐츠가 로딩 중임을 나타낸다.
2. **aria-busy**: 로딩 중인 영역에 `aria-busy="true"`를 적용하고, 로딩 완료 시 `aria-busy="false"`로 변경한다.
3. 스피너에 `role="status"`와 `aria-label="로딩 중"`을 적용한다.
4. 전체 페이지 로딩 시 화면 중앙에, 부분 로딩 시 해당 영역 중앙에 배치한다.
5. 로딩이 오래 걸리는 경우 진행률 표시를 고려한다.

---

## 도움 패널 (Help Panel)

### 용도

상세한 도움말 콘텐츠를 화면 우측에서 슬라이드 형태로 제공한다. 현재 화면의 맥락에 맞는 안내를 표시한다.

### HTML 스니펫

```
html/code/help_panel.html
```

### 가이드라인

1. **우측 슬라이드**: 화면 우측에서 슬라이드인 형태로 열린다.
2. **컨텍스트별**: 현재 페이지/기능에 맞는 도움말 콘텐츠를 표시한다.
3. 닫기 버튼을 제공한다.
4. 열림 시 본문 콘텐츠와 겹치지 않도록 레이아웃을 조정하거나 오버레이 처리한다.
5. `aria-label="도움말 패널"`을 적용한다.
6. 포커스 관리: 열림 시 패널 내부로 포커스 이동, 닫힘 시 트리거 요소로 포커스 복귀.

---

## 따라하기 패널 (Tutorial Panel)

### 용도

특정 기능의 사용법을 단계별로 안내하는 가이드 패널.

### HTML 스니펫

```
html/code/tutorial_panel.html
```

### 가이드라인

1. **단계별 가이드**: 각 단계를 순차적으로 표시하고, 이전/다음 버튼으로 이동한다.
2. 현재 단계와 전체 단계 수를 표시한다 ("2/5 단계").
3. 각 단계에 제목과 설명 텍스트를 제공한다.
4. 스크린샷이나 애니메이션으로 시각적 안내를 보강한다.
5. "다시 보지 않기" 옵션을 제공한다.
6. 닫기 버튼을 항상 표시한다.

---

## 맥락적 도움말 (Contextual Help)

### 용도

특정 UI 요소에 대한 간단한 설명을 인라인으로 제공한다. 물음표(?) 아이콘을 클릭하면 도움말이 표시된다.

### HTML 스니펫

```
html/code/contextual_help.html
```

### 가이드라인

1. **인라인 물음표 아이콘**: 도움이 필요한 UI 요소 옆에 물음표 아이콘(`ico_help.svg`)을 배치한다.
2. 아이콘 클릭 시 인라인 도움말 텍스트가 표시/숨김 전환된다.
3. `aria-expanded` 속성으로 도움말 표시 상태를 전달한다.
4. 도움말 텍스트는 간결하게 작성한다 (1~2문장).
5. 아이콘 버튼에 `aria-label="도움말"`을 제공한다.

---

## 코치마크 (Coach Mark)

### 용도

첫 사용자를 대상으로 주요 UI 요소를 순차적으로 안내하는 온보딩 가이드.

### HTML 스니펫

```
html/code/coach_mark.html
```

### 가이드라인

1. **첫 사용자 온보딩**: 사용자가 처음 방문할 때만 표시한다. 재방문 시에는 표시하지 않는다.
2. **순차 안내**: 주요 UI 요소를 하나씩 하이라이트하며 설명을 제공한다. 이전/다음 버튼으로 이동한다.
3. 대상 요소를 스포트라이트(하이라이트)로 강조하고, 나머지 영역은 딤드 처리한다.
4. 각 단계에 제목, 설명, 진행 표시(3/5)를 포함한다.
5. "건너뛰기" 버튼으로 가이드를 종료할 수 있다.
6. 닫기 후 설정에서 다시 볼 수 있는 방법을 제공한다.
7. 포커스를 현재 안내 중인 코치마크 팝오버에 유지한다.
