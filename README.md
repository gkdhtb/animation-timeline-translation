# [번역] animation-timeline 
- 원문: https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline

**animation-timeline** CSS 속성은 CSS 애니메이션의 진행 상황을 제어하는 데 사용되는 타임라인을 지정합니다.

animation-timeline을 통해 다음 유형의 타임라인을 설정할 수 있습니다:

- 기본 문서 타임라인은, 문서가 브라우저에 처음 로드된 이후 시간이 지남에 따라 진행됩니다. 이 타임라인은 전통적으로 CSS 애니메이션과 관련된 타임라인으로 자동 속성값, 또는 animation-timeline 속성값을 전혀 지정하지 않음으로써 선택됩니다.
- 스크롤 진행 타임라인은, 스크롤 가능한 요소(스크롤러)를 상하(또는 좌우) 사이에서 스크롤해 진행합니다. 스크롤 범위 위치는 시작 0% 끝 100% 진행률의 퍼센트로 변환됩니다. 스크롤 진행 타임라인을 제공하는 요소는 두가지 방법으로 지정할 수 있습니다:

  -
