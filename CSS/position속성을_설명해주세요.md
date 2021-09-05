# position 속성에 대해 설명해주세요 🧐

## 정의
position 속성은 웹 문서 안 요소들을 어떻게 배치할 지 정하는 속성입니다.
속성값에는 static, relative, absolute, fixed, sticky 등이  있습니다.
좌표를 지정 해주기 위해서는 **left, right, top, bottom** 속성과 함께 사용합니다.

## static
position 속성의 **기본값**이며, 요소를 문서 흐름에 맞추어 배치합니다. left, right, top, bottom 속성값에 영향을 받지 않습니다.


## relative ( 상대적인 )
**원래 있어야 할 자리( static값 )를 기준**으로 상대적으로 위치 변경이 일어납니다.

## absolute ( 절대적 )
**부모요소가 있는 자리를 기준**으로 위치 변경이 일어납니다. 자신을 감싸고 있는 부모 요소들 중에서 포지션 값이 static이 아닌 요소를 찾고 그 엘리먼트를 기준으로 이동합니다. 상위 요소가 없다면 body태그를 기준으로 위치 변경이 일어납니다.

## fixed 
해당 요소의 위치를 **사용자의 브라우저를 기준**으로 위치 변경이 일어납니다. 스크롤을 내려도 항상 같은 곳에 뒤치하게 됩니다. 웹 페이지에서 항상 따라다니는 광고나 헤더들은 position : fixed 속성값을 갖습니다.

## sticky
relative 처럼 작동하다가 스크롤 시 설정된 top, left 값 위치 도달 시 fixed 처럼 위치가 고정됩니다. 웹 페이지에서 스크롤 상단 고정 메뉴를 만들 때 사용됩니다.


`참고자료` 
> [드림코딩 by 엘리 - CSS 레이아웃 정리 display, position 완성](https://www.youtube.com/watch?v=jWh3IbgMUPI&t=2s&ab_channel=%EB%93%9C%EB%A6%BC%EC%BD%94%EB%94%A9by%EC%97%98%EB%A6%AC)  
[tistory - position 속성으로 정렬하기 ](https://aboooks.tistory.com/82)