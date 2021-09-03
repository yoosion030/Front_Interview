# 왜 CSS의 link태그를 head태그 사이에 위치시킬까 🙄

css link 태그를 head 태그 안에 넣는 것은 최적화된 웹사이트를 구출할 때 적절한 명세의 일부입니다.  
 페이지가 처음 로드되면, HTML과 CSS가 동시에 파싱되는데, HTML은 DOM( Document Object Model )을 만들고, CSS는 CSSOM ( CSS Object Model ) 을 만듭니다. 두 가지 모두 웹사이트에서 시각적인 부분을 만드는데 필요하므로, 빠른 "first meaningful paint"를 가능하게 합니다.

>  first meaningful paint : 사용자에게 의미 있는 콘텐츠가 그려지기 시작하는 첫 순간 

  만약 HTML 문서가 10만줄이 넘는 긴 내용이고 브라우저 엔진이 느린데 css가 하단에 선언이 되어있다면 css가 나중에 적용이 될 수도 있습니다. 😥



### 결론 : css는 무조건 HTML의 상단에 정의 해야합니다! 왜냐하면 HTML DOM 요소가 화면에 보일때 원하는 디자인이 적용된 형태로 나타나기 때문입니다.


>참고자료
>   - https://sub0709.tistory.com/73
>   - https://velog.io/@dea8307/%EC%99%9C-%EC%9D%BC%EB%B0%98%EC%A0%81%EC%9C%BC%EB%A1%9C-CSS-link-%ED%83%9C%EA%B7%B8%EB%A5%BC-headhead-%ED%83%9C%EA%B7%B8-%EC%82%AC%EC%9D%B4%EC%97%90-%EC%9C%84%EC%B9%98%EC%8B%9C%ED%82%A4%EA%B3%A0-JS-script-%ED%83%9C%EA%B7%B8%EB%A5%BC-body-%EC%A7%81%EC%A0%84%EC%97%90-%EC%9C%84%EC%B9%98%EC%8B%9C%ED%82%A4%EB%8A%94-%EA%B2%83%EC%9D%B8%EC%A7%80
