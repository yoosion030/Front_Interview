# grid가 무엇인지 설명해보시오 💦

## grid 용어

![grid 정리](https://studiomeal.com/wp-content/uploads/2020/01/03-2.jpg)
- 그리드 컨테이너 : `display : grid`를 적용하는 grid의 전체영역
- 그리드 아이템 : grid 컨테이너의 자식요소들
- 그리드 트랙 : grid의 행 또는 열
- 그리드 셀 : grid의 한칸
- 그리드 라인 : grid 셀을 구분하는 선
- 그리드 번호 : grid 라인의 각 번호
- 그리드 갭 : grid 셀 사이의 간격
- 그리드 영역 : grid 라인으로 둘러싸인 사각형 영역으로 그리드 셀의 집합


## display : grid;
grid 컨테이너에 `display : grid;`속성값을 지정해준다.
- 아이템들이 block 요소라면 딱히 변화는 없다.  
- `display : inline-grid;`는 inline-block 처럼 동작한다.

## grid-template-rows, grid-template-columns
컨테이너에 grid 트랙(행과 열)의 크기들을 지정해주는 속성이다.
- row : 행의 배치
- columns : 열의 배치

        grid-template-columns : 1fr 1fr 1fr;
- fr : 숫자의 비율대로 트랙의 크기를 나눔
- **1fr 1fr 1fr** 은 균일하게 **1:1:1 비율**인 3개의 columns을 만들겠다는 의미이다.

## repeat 함수
repeat는 반복되는 값을 자동으로 처리할 수 있는 함수이다.
- **repeat(반복획수, 반복값)**
- ex ) repeat(5, 1fr) = 1fr 1fr 1fr 1fr 1fr
  
## minmax함수
최솟값과 최댓값을 지정할 수 있는 함수이다.
- **minmax(100px, auto)** = 최소한 100px, 최대는 자동으로 늘어나게
- 내용이 적더라도 최소한 100px을 확보, 내용이 많아 100px이 넘어가면 auto로 알아서 늘어나게

## auto-fill, auto-fit
column의 개수를 미리 정하지 않고 설정된 너비가 허용하는 한 최대한 셀을 채움
- auto-fill은 남는 공간이 있을 수 있다.
- auto-fit은 남는 공간을 채운다.


## row-gap, column-gap, gap
그리드 셀 사이의 간격을 설정
- row : 행 사이의 간격
- column : 열 사이의 간격
- gap : 행, 열 사이의 간격



`참고자료`
> [1분코딩 - grid 총정리](https://studiomeal.com/archives/533)