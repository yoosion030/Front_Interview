# JS를 body 맨 밑에 둬야 하는 이유는 무엇인가요😦

##  브라우저의 동작 방식
1. HTML을 읽기 시작합니다.
2. HTML을 파싱합니다.
> 파싱이란 웹 상에서 주어진 정보를 내가 원하는 형태로 가공하여 서버에서 불러들이는 것입니다.
3. DOM 트리를 생성합니다.
4. Render 트리가 생성됩니다.
5. Display에 표시합니다.


script 태그는 다운로드 되고 실행되는 동안 HTML 파싱을 차단합니다.스크립트를 맨 아래에 두면 HTML을 먼저 파싱하여 사용자에게 표시할 수 있습니다.

결론 : body 태그 최하단에 위치하는게 가장 좋다.

`참고자료`
> [velog - \<script> 태그는 어디에 위치해야 할까요?](https://velog.io/@takeknowledge/script-%ED%83%9C%EA%B7%B8%EB%8A%94-%EC%96%B4%EB%94%94%EC%97%90-%EC%9C%84%EC%B9%98%ED%95%B4%EC%95%BC-%ED%95%A0%EA%B9%8C%EC%9A%94)