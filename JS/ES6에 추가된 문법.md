# ES6에 추가된 문법에 대해 5가지 이상 말해주세요.

## 1. 블록스코프 let, const

let과 const가 추가되었습니다. let은 변수이도 cosnt는 상수입니다. 이 키워드로 선언하면 블록레벨의 스코프를 가지고 같은 스코프에선 let으로 변수를 재정의 하는 것이 불가합니다. let, const는 호이스팅이 적용이 안되고 변수선언 이전에 접근이 불가능합니다.

## 2. 화살표함수 (=>)

화살표 함수를 사용하면 기존 함수를 축약할 수 있다.

```js
// ES6
const testFunction = () => ~~~;

function testFunction () ~~~
```

## 3. 비구조화 할당

배열이나 객체의 속성을 해체해서 각각을 변수로 보고 값을 할당해주는 문법입니다.

```js
// ES6
let user = { name: "Sunny", interests: ["Traveling", "Swimming"] };
let { name, interests, tasks } = user;

let name = user.name;
let interests = user.interests;
let tasks = user.tasks;
```

## 4. Promise(프로미스)

비동기란 여러 작업을 한번에 시켜줄 수 있도록 돕는 작업인데, 이때 해야할 작업을 콜백으로 전달합니다.
다만, 콜백을 통해서 작업하면 코드가 중첩 되면서 지저분해집니다.
이를 해결할 수 있는 것이 프로미스입니다.

## 5. 모듈

export를 사용하여 내보낼 수 있고 import를 사용하여 모듈을 가져올 수 있습니다.

## 정리

ES6에서 추가된 문법으론 let, const, 화살표 함수, 비구조화 할당, 프로미스, 모듈 가져오기, 내보내기 등이 있습니다.

`참고자료`

> [tistory - 자바스크립트 ES6에서 추가된 문법](https://way-be-developer.tistory.com/157)
