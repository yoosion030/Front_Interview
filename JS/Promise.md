# Promise에 대해 설명해 주세요

Promise란 비동기적 처리의 성공/실패 여부와 그 결과값을 대표하는 object입니다.

## Promise가 왜 필요할까?

프로미스는 주로 서버에서 받아온 데이터를 화면에 표시할 때 사용합니다. 서버에서 데이터를 요청하고 받아오기 위해 아래와 같은 API를 사용합니다.

```JS
$.get('url 주소/products/1', function(response) {
  // ...
});
```

위 API가 실행되면 서버에다가 '데이터 하나 보내주세요'라는 요청을 보냅니다. 그런데 여기서 데이터를 받아오기도 전에 데이터를 다 받아온 것 마냥 화면에 데이터를 표시하려고 하면 오류가 발생하거나 빈 화면이 뜹니다. 이와 같은 문제점을 해결하기 위한 방법 중 하나가 **프로미스** 입니다.

## Promise 기초

**ajax 통신코드**

```JS
function getData(callbackFunc) {
  $.get('url 주소/products/1', function(response) {
    callbackFunc(response); // 서버에서 받은 데이터 response를 callbackFunc() 함수에 넘겨줌
  });
}

getData(function(tableData) {
  console.log(tableData); // $.get()의 response 값이 tableData에 전달됨
});
```

위 코드는 제이쿼리의 ajax 통신 API를 이용하여 지정된 url에서 1번 상품 데이터를 받아오는 코드입니다. 위 코드에 promise를 적용하면 아래와 같은 코드가 됩니다.

```JS
unction getData(callback) {
  // new Promise() 추가
  return new Promise(function(resolve, reject) {
    $.get('url 주소/products/1', function(response) {
      // 데이터를 받으면 resolve() 호출
      resolve(response);
    });
  });
}

// getData()의 실행이 끝나면 호출되는 then()
getData().then(function(tableData) {
  // resolve()의 결과 값이 여기로 전달됨
  console.log(tableData); // $.get()의 reponse 값이 tableData에 전달됨
});
```

## Promise의 3가지 상태

Promise의 상태 = Promise의 처리과정  
`new Promise()`로 프로미스를 생성하고 종료될 때까지 3가지 상태를 갖습니다.

- Pending(대기) : 비동기 처리 로직이 아직 **완료되지 않은** 상태
- Fulfilled(이행) : 비동기 처리가 **완료**되어 프로미스가 결과 값을 반환해준 상태
- Rejected(실패) : 비동기 처리가 **실패**하거나 오류가 **발생**한 상태

### 1. Pending(대기)

아래와 같이 메서드를 호출하면 Promise는 대기상태가 됩니다.

```JS
new Promise()
```

new Promise() 메서드를 호출할 때 콜백 함수를 선언할 수 있고, 콜백 함수의 인자는 `resolve`,`reject`입니다.

```JS
new Promise(function(resolve, reject) {
  // ...
});
```

### 2. Fulfilled(이행)

콜백 함수의 인자 `resolve`를 아래와 같이 실행하면 이행상태가 됩니다.

```JS
new Promise(function(resolve, reject){
    resolve();
});
```

이행 상태가 되면 아래와 같이 `then()`을 이용하여 처리 결과값을 받을 수 있습니다.

```JS
function getData() {
    return new Promise(function(resolve, reject) {
        var data = 100;
        resolve(data);
    });
}

getData().then(function(resolvedDate) {
    console.log(resolvedData); // 100
})
```

### 3. Rejected(실패)

`new Promise()`로 프로미스 객체를 생성 후 `reject`를 아래와 같이 호출하게되면 실패상태가 됩니다.

```JS
new Promise(function(resolve,reject) {
    reject();
});
```

실패 상태가 되면 실패한 이유(실패 처리의 결과 값)를 `catch()`로 받을 수 있습니다.

```JS
function getData(){
    return new Promise(function(resolve, reject){
        reject(new Error("Request is failed"));
    });
}

// reject()의 결과값 Error를 err에 대입
getData().then().catch(function(err){
    console.log(err); // Error: Request is failed
})
```

**프로미스 처리 흐름**
![](https://joshua1988.github.io/images/posts/web/javascript/promise.svg)

### 기초 예제

```JS
function getData() {
    return new Promise(function(resolve, reject){
        $.get('url 주소/products/1', function(response) {
            if(response) {
                resolve(response);
            }
            reject(new Error("Request is failed"));
        });
    });
}

// $.get() 호출 결과에 따라 'response' 또는 'Error' 출력
getData().then(function(data){
    cosole.log(data);
}).catch(function(err){
    console.log(err);
})
```

완료 상태 => response 출력  
실패 상태 => err 출력

### 여러 개의 프로미스 연결하기

`then()`메서드를 호풀하고 나면 새로운 프로미스 객체가 반환됩니다. 따라서 아래와 같이 프로미스를 연결할 수 있습니다.

```JS
function getData(){
    return new Promise({

    });
}

// then()으로 여러개의 프로미스를 연결한 방식
getData()
    .then(function(data){

    })
    .then(function(){

    })
    ~~~
```

### 연결 프로미스 예제

비동기 처리 예제에서 가장 흔하게 사용되는 `setTimeout()` API를 사용하였습니다.

```JS
new Promise(function(resolve, reject){
    setTimeout(function(){
        resolve(1);
    }, 2000);
})
    .then(function(result){
        cosole.log(result); // 1
        return result + 10;
    })

    .then(function(result){
        cosole.log(result); // 11
        return result + 20;
    })
    .then(function(result){
        cosole.log(result); // 31
    })

```

프로미스 객체를 하나 생성한 후 `setTimeout()`을 이용하여 2초 후에 `resolve()`를 호출합니다. `resolve()`가 호출되면 프로미스가 대기상태에서 이행상태로 넘어가기 때문에 첫 번째 `.then()`로직으로 넘어갑니다. 첫번째 `.then()`안에 있는 코드를 실행 후 return 을 하게해주어 다음 `.then()`으로 넘어가면서 최종적으로는 31을 출력하는 그런 코드입니다.
