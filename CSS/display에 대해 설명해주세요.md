# display에 대해 설명해주세요 🤨

## 정의
display 속성은 화면에 어떻게 드러나게 할지를 결정하는 속성입니다. 속성값에는 `none`, `block`, `inline`, `inline-block` 등이 있습니다. 태그마다 기본값으로 지정되어 있는 display 값이 다르며 기본값이 block 이여도 inline 으로 변경이 됩니다.

## none
화면에서 사라집니다. 크기 자체도 차지하지 않습니다.

## block
항상 새로운 라인에서 시작합니다.
기본적으로 가로 영역을 모두 채우며, width 와 height를 지정할 수 있습니다.
> block 인 태그들  
> `div`, `h1 ~ h6`, `p` 등


## inline
새로운 라인에서 시작하지 않으며, 컨텐츠를 딱 감쌀정도의 크기만을 갖게됩니다. width 와 height를 지정해주어도 크기는 변하지 않습니다.
> inline 인 태그들  
> `span`, `a` 등

## inline-block
`inline` 과 `div`의 특성을 합쳐놓은 속성입니다. `inline` 요소처럼 새로운 라인에서 시작하지 않고 `block`처럼 너비와 높이를 설정할 수 있습니다.

## 차이점
![](https://media.vlpt.us/post-images/chris/00ccfe60-5f8e-11e9-b975-e5b35539d0db/image.png)
`참고자료`  
> [tistory - [CSS] display란? / display 속성 / display 종류](https://programming119.tistory.com/97)  
[TCP SCHOOL - 디스플레이](http://tcpschool.com/css/css_position_display)
