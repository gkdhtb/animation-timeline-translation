# [번역] animation-timeline 
- 원문: https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline

**animation-timeline** CSS 속성은 CSS 애니메이션의 진행 상황을 제어하는 데 사용되는 타임라인을 지정합니다.

animation-timeline을 통해 다음 유형의 타임라인을 설정할 수 있습니다:

- 기본 문서 타임라인은, 문서가 브라우저에 처음 로드된 이후 시간이 지남에 따라 진행됩니다. 이 타임라인은 전통적으로 CSS 애니메이션과 관련된 타임라인으로 자동 값, 또는 animation-timeline 값을 전혀 지정하지 않음으로써 선택됩니다.
- 스크롤 진행 타임라인은, 스크롤 가능한 요소(스크롤러)를 상하(또는 좌우) 사이에서 스크롤해 진행합니다. 스크롤 범위 위치는 시작 0% 끝 100% 진행률의 퍼센트로 변환됩니다. 스크롤 진행 타임라인을 제공하는 요소는 두가지 방법으로 지정할 수 있습니다:

  - 명명된 스크롤 진행 타임라인은 스크롤 진행 타임라인을 제공하는 스크롤러가 `scroll-timeline-name` 속성(또는 `scroll-timeline` 축약 속성)을 사용하여 명시적으로 명명됩니다. 그 이름은 해당 요소의 `animation-timeline` 속성 값으로 지정하여 애니메이션에 연결합니다.
  - 익명 스크롤 진행 타임라인은 동작할 요소에 `animation-timeline` 값으로 scroll() 함수가 제공됩니다, 이 함수는 전달하는 인수를 기반으로 스크롤 진행 타임라인과 사용할 스크롤 축을 제공하는 스크롤러를 선택합니다.

- 뷰 진행 타임라인은, 스크롤러 내부의 요소(피사체로 알려진)의 가시성의 변화를 기반으로 진행됩니다. 스크롤러 내부 피사체의 가시성은 추적됩니다 - 기본적으로 타임라임은 스크롤의 한쪽 가장자리에 피사체가 처음 보일 때 0%, 반대쪽 가장자리에 도달할때 100%입니다. 스크롤 진행 타임라임과 달리, 스크롤러를 지정할 수 없습니다 - 피사체의 가시성은 항상 가까운 상위 스크롤러 내에서 추적됩니다. 뷰 진행 타임라인을 제공하는 피사체는 두가지 방법으로 지정할 수 있습니다:

  - 명명된 뷰 진행 타임라인은 피사체가 `view-timeline-name` 속성(또는 view-timeline 축약 속성)을 사용하여 명시적으로 명명됩니다. 그 이름은 해당 요소의 `animation-timeline` 속성 값으로 지정하여 애니메이션에 연결합니다. 이것이 핵심 포인트입니다 - 이름이 지정된 뷰 진행 타임라인은, 움직일 요소와 같은 피사체를 가질 필요 없습니다.
  - 익명 뷰 진행 타임라인은 피사체에 `animation-timeline` 값으로 view() 함수가 제공됩니다, 이 함수는 가장 가까운 부모 스크롤러 내부의 위치 기준으로 애니메이션화됩니다.
 
> **NOTE:** `animation-timeline`은 재설정 전용 값으로 `animation` 축약에 포함되어있습니다. 이것은 `animation`은 미리 선언된 `animation-timeline`값을 `auto`로 리셋하지만, 특정한 값을 `animation`을 통해 설정할 수 없습니다. CSS 스크롤 기반 애니메이션을 만들 때, `animation` 축약을 선언한 후 `animation-timeline`선언해야 효과가 나타납니다.

## 문법

```CSS
/* 키워드 */
animation-timeline: none;
animation-timeline: auto;

/* 명명된 timeline 단일 애니메이션 */
animation-timeline: --timeline_name;

/* 익명 스크롤 진행 타임라인 단일 애니메이션 */
animation-timeline: scroll();
animation-timeline: scroll(scroller axis);

/* 익명 뷰 진행 타임라인 단일 애니메이션 */
animation-timeline: view();
animation-timeline: view(axis inset);

/* 다중 애니메이션 */
animation-timeline: --progressBarTimeline, --carouselTimeline;
animation-timeline: none, --slidingTimeline;

/* Global values */
animation-timeline: inherit;
animation-timeline: initial;
animation-timeline: revert;
animation-timeline: revert-layer;
animation-timeline: unset;
```

### 속성 값
`none`

애니메이션이 타임라인과 연결되어 있지 않습니다.

`auto`

애니메이션의 타임라인은 문서의 기본 DocumentTimeline(문서 타임라인)입니다.

`scroll()`

익명 스크롤 타임라인은 현재 요소의 상위 스크롤러에서 제공됩니다. 함수 매개 변수를 사용하여 스크롤러를 선택하고 타임라인을 따라 측정할 스크롤 축을 선택할 수 있습니다.
자세한 내용은 [scroll()](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline/scroll)을 참조하세요.

`view()`

익명 뷰 타임라인은 `animation-timeline: view();`가 설정된 피사체에서 제공됩니다. 함수 매개 변수를 사용하여 타임라인 진행을 추적할 스크롤바 축과 피사체가 보이는 것으로 간주되는 상자의 위치를 조절하는 inset을 선택할 수 있습니다.
자세한 내용은 [view()](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline/view)을 참조하세요.

`<dashed-ident>`

[<dashed-ident>](https://developer.mozilla.org/en-US/docs/Web/CSS/dashed-ident)은 `scroll-timeline-name`또는 `view-timeline-name`속성(`scroll-timeline`또는 `view-timeline` 축약 속성)으로 이전에 선언된 명명된 타임라인을 식별합니다.
> **NOTE:** 두 개 이상의 타임라인이 동일한 이름을 공유하는 경우, 캐스케이드 내에서 마지막으로 선언된 것이 사용됩니다. 또한, 지정된 이름과 일치하는 타임라인을 찾지 못하면, 애니메이션이 타임라인과 연결되지 않습니다.
> **NOTE:** `<dashed-ident>`값은 반드시 `--`로 시작해야합니다. 이것은 CSS 키워드와의 이름 충돌을 방지할 수 있습니다.

## 공식 정의
<table>
  <tr>
    <td>초기 값</td>
    <td>auto</td>
  </tr>
  <tr>
    <td>적용 대상</td>
    <td>모든 요소</td>
  </tr>
  <tr>
    <td>상속</td>
    <td>X</td>
  </tr>
  <tr>
    <td>계산 값</td>
    <td>목록, 각 항목은 대소문자 구분 CSS 식별자 또는 'none', 'auto' 키워드 </td>
  </tr>
    <tr>
    <td>애니메이션 유형</td>
    <td>애니메이션 불가</td>
  </tr>
</table>
