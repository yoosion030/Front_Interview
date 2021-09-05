# box-sizing은 무엇인가요 🤔

## 정의
box-sizing은 박스 너비와 높이를 계산하는 기준을 정하는 속성입니다.
box-sizing 속성은 두가지 값을 가집니다.
- content-box ( 기본값 )
- border-box

## content-box
개발자가 지정한 크기가 요소만의 크기가 됩니다. (padding, border, margin 제외)
- width = content width
- heithg = content height

## border-box
개발자가 지정한 크기가 요소 + padding + border 의 크기가 됩니다. ( margin 제외 )
- width = content width + padding + border
- height = contetn height + padding + border

## 차이점
![](https://s3-ap-northeast-2.amazonaws.com/opentutorials-user-file/module/2367/4707.jpeg)  

첫번째 박스는 box-sizing 값이 content-box이고, 두번째 박스는 border-box입니다. 둘다 똑같이 `width : 50px`, `border-width : 50px;`로 주었는데 왜 크기가 다를까요?   
첫번째 박스는 요소의 너비는 500px이고 테두리 너비는 개별적으로 지정이 되었기때문에 테두리를 포함한 너비가 500px보다 커지는 것입니다.  
두번째 박스에는 `border-box` 값을 주었기 때문에 테두리를 지정해주어도 테두리값를 포함해 500px를 유지하게 하도록 하기 때문입니다. `box-sizing` 속성을 `border-box`로 지정하면  테두리를 포함한 크기를 지정할 수 있기 때문에 예측하기가 더 쉽습니다. 



`참고자료`
> [생활코딩 - box-sizing](https://opentutorials.org/course/2418/13405)  
[tistory - box-sizing 속성 / 테두리도 크기에 포함시키기](https://codingbroker.tistory.com/116)