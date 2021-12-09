# Fetch API에 대해 아시나요?

## fetch 사용법

`fetch()`함수는 첫번째 인자로 `URL`, 두번째 인자로 옵션 객체를 받고 `Promise` 타입의 객체를 반환합니다. 반환된 객체는 API호출이 성공했을 경우에는 **응답객체**를 `reslove`하고, 실패했을 경우에는 **예외객체**를 `reject`합니다.

```JS
fetch(url, options)
  .then((response) => console.log("response:", response))
  .catch((error) => console.log("error:", error));
```

## GET 호출

`fetch()`함수는 default로 GET 방식으로 작동하고 GET 방식은 요청 전문을 받지 않기 때문에 옵션인자가 필요없습니다.

```JS
fetch(url, options)
  .then((response) => console.log("response:", response))
  .catch((error) => console.log("error:", error));
```

**결과**

응답 객체를 통해 응답 상태가 `200`인 것을 알 수 있습니다.

```JS
Response {status: 200, ok: true, redirected: false, type: "cors", url: "https://jsonplaceholder.typicode.com/posts/1", …}
```

대부분의 REST API들을 JSON 형태의 데이터를 응답하기 때문에 응답객체는 `json()`메서드를 제공합니다.

```JS
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then((response) => response.json())
  .then((data) => console.log(data));
```

`json()`메서드를 호출하면 응답객체로부터 JSON 포멧의 응답 전문을 자바스크립트 객체로 변환하여 얻을 수 있습니다.

```JS
{
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  "body": "quia et suscipit↵suscipit recusandae consequuntur …strum rerum est autem sunt rem eveniet architecto"
}
```

## POST 호출

POST 호출을 할때에는 `method`옵션을 `POST`로 지정해주어야 합니다. 그리고 `headers`옵션을 통해 JSON 포멧을 사용한다고 알려줘야 하며, 요청 전문을 JSON 포멧으로 직렬화하여 가장 중요한 `body`옵션에 설정해줍니다.

```JS
fetch("https://jsonplaceholder.typicode.com/posts", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    title: "Test",
    body: "I am testing!",
    userId: 1,
  }),
}).then((response) => console.log(response));
```

**결과**
응답 객체를 통해 응답 상태가 `201`인 것을 알 수 있습니다.

```JS
Response {type: "cors", url: "https://jsonplaceholder.typicode.com/posts", redirected: false, status: 201, ok: true, …}
```

`json`메서드를 이용한 호츌

```JS
fetch("https://jsonplaceholder.typicode.com/posts", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    title: "Test",
    body: "I am testing!",
    userId: 1,
  }),
})
  .then((response) => response.json())
  .then((data) => console.log(data));
```

## PUT, DELETE 호출

PUT 방식은 `method`옵션을 `PUT`으로 설정한다는 점 빼고는 POST 방식과 매우 흡사합니다.

```JS
fetch("https://jsonplaceholder.typicode.com/posts/1", {
  method: "PUT",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    title: "Test",
    body: "I am testing!",
    userId: 1,
  }),
})
  .then((response) => response.json())
  .then((data) => console.log(data));
```

DELETE 방식에서는 보낼 테이터가 없기 때문에, `headers`와 `body`옵션이 필요없습니다.
