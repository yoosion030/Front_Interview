# async & await에 대해 설명해주세요!

## async와 await이란?

자바스크립트의 비동기 처리 패턴 중 가장 최근에 나온 문법이자 콜백 함수와 프로미스의 단점을 보완하고 개발자가 읽기 좋은 코드를 작성하게 해주는 문법입니다.

## async & await 예제

**그냥 코드**

```JS
var user = {
  id: 1,
  name: 'Josh'
};

function logName() {
    var user = fetchUser('domain.com/user/1');
    if(user.id === 1) {
        console.log(user.name);
    }
}
```

**async & await을 사용한 코드**

```JS
var user = {
  id: 1,
  name: 'Josh'
};

async function logName() {
    var user = await fetchUser('domain.com/users/1');
    if(user.id === 1) {
        console.log(user.name);
    }
}
```

### async & await 적용된 코드와 그렇지 않은 코드

```JS
var user = {
  id: 1,
  name: 'Josh'
};

function logName() {
    var user = fetchUser('domain.com/user/1');
    if(user.id === 1) {
        console.log(user.name);
    }
}
```

여기서 `fetchUser()`메서드가 데이터를 받아오는 HTTP 통신이라고 가정한다면 자바스크립트의 비동기 처리 코드는 아래와 같이 콜백을 사용해야지 코드의 실행 순서를 보장받을 수 있습니다.

```JS
function logName() {
    var user = fetchUser('domain.com/user/1',function(user){
        if(user.id == 1) {
            console.log(user.name);
        }
    })
}
```

이 외에 간단하게 생각하여 `서버에서 사용자 데이터를 불러와서 변수에 담고, 사용자 아이디가 1이면 사용자 이름을 출력` 하려고 하면 **async await**만 붙이시면 됩니다.

```JS
async function logName() {
    var user = await fetchUser('domain.com/users/1');
    if(user.id === 1) {
        console.log(user.name);
    }
}
```

## async & await 기본 문법

```JS
async function 함수명() {
    await 비동기_처리_메서드명();
}
```

먼저 함수의 앞에 `async`라는 예약어를 붙입니다. 그리고 함수 내부에 있는 비동기 처리 메서트 앞에 `await`을 붙입니다. 여기서 주의할 점은 비동기 처리 메서드가 꼭 프로미스 객체를 반환해야 `await`이 의도한 대로 동작합니다.

일반적으로 `await`의 대상이 되는 비동기 처리 코드는 `Axios`등 프로미스를 반환하는 API 호출 함수입니다.

## async & await 예제

```JS
function fetchItems() {
    return new Promise(function(resolve, reject) {
        var item = [1, 2, 3];
        resolve(items);
    });
}

async function logItems() {
    var resultItems = await fetchItems();
    console.log(resultItems); // [1, 2, 3]
}
```

`Promise`는 자바스트립트 비동기 처리를 위한 객체입니다. `fetchItems()` 함수를 실행하면 프로미스가 **이행(resolved)** 결과 값은 `items`배열이 됩니다.

`logItems()`함수를 실행하면 `fetchItems()`함수의 결과 값은 `items` 배열이 `resultItems`변수에 담깁니다. 따라서 콘솔에는 `[1, 2, 3]`이 출력됩니다.

`await`을 사용하지 않았다면 데이터를 받아온 시점에 콘솔을 출력할 수 있게 콜백 함수나 `.then()`등을 사용해야 했을 겁니다. 하지만 `async & await`문법 덕에 비동기에 대한 사고를 하지 않아도 되는 것입니다.

### 실용 예제

```JS
function fetchUser() {
    var url = 'https://jsonplaceholder.typicode.com/users/1'
    return fetch(url).then(function(response){
        return response.json();
    });
}

function fetchTodo() {
    var url = 'https://jsonplaceholder.typicode.com/todos/1'
    return fetch(url).then(function(response){
        return response.json();
    });
}


```

위의 코드와 같이 각각 사용자와 할일 목록을 받아오는 HTTP통신 코드가 있다고 가정하겠습니다. 위 함수들을 실행하면 각각 사용자 정보와 할 일 정보가 담긴 프로미스 객체가 반환됩니다.

아래의 코드의 로직은 다음과 같습니다.

1. `fetchUser()`를 이용하여 사용자 정보 호출
2. 받아온 사용자 아이디가 1이면 할 일 정보 호출
3. 받아온 할 일 정보의 제목을 콘솔에 출력

```JS
// json
//{
//   "userId": 1,
//   "id": 1,
//   "title": "delectus aut autem",
//   "completed": false
// }
async function logTodoTitle() {
    var user = await fetchUser();
    if(user.id === 1) {
        var todo = await fetchTodo();
        console.log(todo.title)
    }
}
```

`logTodoTitle()`를 실행하면 todo의 제목인 delectus aut autem가 출력될 것입니다. 위 비동기 처리 코드를 콜백이나 프로미스로 하였다면 코드가 더 길어졌을 것이고 인덴팅 뿐만 아니라 가독성도 좋지 않았을 것입니다. 이처럼 **async & await**문법을 이용하면 기존의 비동기 처리 코드 방식으로 사고하지 않아도 되는 강점이 생깁니다.

### 예외 처리

async & await에서 예외를 처리하는 방법은 바로 **try catch**입니다. 프로미스에서 에러 처리를 위해 `.catch()`를 사용했던 것처럼 async에서는 `catch{}`를 사용하면 됩니다.

```Js
async function logTodoTitle() {
    try {
        var user = await fetchUser();
        if(user.id === 1) {
            var todo = await fetchTodo();
            console.log(todo.title);
        }
    } catch(error) {
        console.log(error);
    }
}
```

위의 코드를 실행하다가 발생한 네트워크 통신 오류 뿐만 아니라 간단한 타입 오류 등의 일반적인 오류까지도 `catch`로 잡아낼 수 있습니다. 발견된 에러는 `error`객체에 담기기 때문에 에러의 유형에 맞게 에러 코드를 처리하면 됩니다.
