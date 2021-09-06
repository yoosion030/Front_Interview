# npm과 npx의 차이점을 아시나요 👀

### ⭐알아놔야 할 것⭐
- **패키지** : **코드의 배포**를 위해서 사용되는 코드의 묶음
- **패키지 매니저** : 패키지를 관리하는 작업을 자동화, 안전처리 하기위해 사용되는 도구 / 패키지를 다루는 작업을 편리하고 안전하게 수행하기 위해 사용되는 도구
- **패키지 관리** : 패키지를 설치, 업데이트, 수정, 삭제하는 작업
  
## 💻npm ( node package manager )
- node.js를 설치하면 함께 설치되는 **패키지 관리도구**입니다.
- node.js의 자동화 된 의존성과 패키지 관리를 위한 **패키지 매니저**이다.


## 💻npx 
npx 어디서 많이 봤는데? -> 리액트 설치할 때
> npx create-react-app blahblah

npx가 뭐길래?
> npm 5.2.0버전부터 추가된 node.js 패키지를 실행시키는 하나의 도구입니다. 

Node 패키지를 실행시키는 하나의 **도구**이다.


## 결론

npx는 결국 npm을 편리하게 사용하기 위해 나온 도구입니다.

---

업데이트를 할 경우에 npm은 일일이 업데이트를 해줘야하기 때문에 모듈이 많아 업데이트가 잦은 react의 경우 npx를 이용해 설치하는 것을 권장합니다.
> npx create-react-app blahblah



`참고자료`
> [tistory - npm과 npx의 용어정리 및 차이점](https://seizemymoment.tistory.com/106)  
>[ tistory - 패키지 매니저(Package Manager)란?](https://aahc.tistory.com/14)