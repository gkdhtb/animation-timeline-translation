# [번역] animation-timeline 
- 원문: https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline

**animation-timeline** CSS 속성은 CSS 애니메이션의 진행 상황을 제어하는 데 사용되는 타임라인을 지정합니다.

animation-timeline을 통해 다음 유형의 타임라인을 설정할 수 있습니다:

- 기본 문서 타임라인은, 문서가 브라우저에 처음 로드된 이후 시간이 지남에 따라 진행됩니다. 이 타임라인은 전통적으로 CSS 애니메이션과 관련된 타임라인으로 자동 값, 또는 animation-timeline 값을 전혀 지정하지 않음으로써 선택됩니다.
- 스크롤 진행 타임라인은, 스크롤 가능한 요소(스크롤러)를 상하(또는 좌우) 사이에서 스크롤해 진행합니다. 스크롤 범위 위치는 시작 0% 끝 100% 진행률의 퍼센트로 변환됩니다. 스크롤 진행 타임라인을 제공하는 요소는 두가지 방법으로 지정할 수 있습니다:

  - 명명된 스크롤 진행 타임라인은 스크롤 진행 타임라인을 제공하는 스크롤러가 scroll-timeline-name 속성(또는 scroll-timeline 축약 속성)을 사용하여 명시적으로 명명한 것입니다. 그 이름은 해당 요소의 `animation-timeline` 속성 값으로 지정하여 애니메이션에 연결합니다.
  - 익명 스크롤 진행 타임라인은 동잘할 요소에 `animation-timeline` 값으로 scroll() 함수를 제공합니다, 이 함수는 전달하는 인수를 기반으로 스크롤 진행 타임라인과 사용할 스크롤 축을 제공하는 스크롤러를 선택합니다.

- 뷰 진행 타임라인은, 스크롤러 내부의 요소(피사체로 알려진)의 가시성의 변화를 기반으로 진행됩니다. 스크롤러 내부 피사체의 가시성은 추적됩니다 - 기본적으로 타임라임은 스크롤의 한쪽 가장자리에 피사체가 처음 보일 때 0%, 반대쪽 가장자리에 도달할때 100%입니다. 스크롤 진행 타임라임과 달리, 스크롤러를 지정할 수 없습니다 - 피사체의 가시성은 항상 가까운 상위 스크롤러 내에서 추적됩니다. 뷰 진행 타임라인을 제공하는 피사체는 두가지 방법으로 지정할 수 있습니다:
