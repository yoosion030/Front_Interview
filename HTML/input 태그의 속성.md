# input태그의 타입 속성에 대해서 알고 계신가요 🙋‍♂️

## type 특성
- text : 한줄의 텍스트 필드 ( 기본값 ) ⭐
- password : 값이 가려지는 텍스트 필드
- radio : 같은 name 값을 가진 여러개의 선택중에서 하나의 값을 선택하게 하는 라디오 버튼 ⭐
- checkbox : 체크박스 ⭐
- button : 기본 행동을 가지지 않으며 value을 레이블로 사용하는 푸시 버튼 ⭐
- submit : 양식을 전송하는 버튼 ⭐
- image : src 특성에 지정한 이미지로 나타내는 시각적 제출버튼
- file : 파일을 지정할 수 있는 컨트롤
- color : 색을 지정하 수 있는 컨트롤
- email : 이메일 주소를 편집할 수 있는 필드
- url : URL을 입력하는 필드
- tel : 전화번호를 입력하는 컨트롤
- search : 검색문자열을 입력하는 한줄 텍스트 필드
- range : 값이 가려진 숫자를 입력하는 컨트롤 ⭐
- time :  시간값을 입력하는 콘트롤
- date : 날짜를 지정할 수 있는 컨트롤, 시간대는 지정 x
- month : 연과 월을 지정할 수 있는 컨트롤, 시간대는 지정 x


## 중요속성
- alt - image : 이미지 유형에 대한 대체 속성
- checked - radio, checkbox : 체크 되었는지의 여부 
- autocomplete - all : 폼이나 입력필드가 자동완성 기능을 지원할 지 여부를 지정
- placeholder - password, search, tel, text, url : 양식 컨트롤에 나타나는 내용
- min/max - number, range, date, month, time : \<input> 요소의 최소와 최대 값을 지정

`참고자료`
> [MDN - \<input>: 입력 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/Input)  
> [HTML Input 속성들(Attributes)](http://jun.hansung.ac.kr/CWP/htmls/HTML%20Input%20Attributes.html)