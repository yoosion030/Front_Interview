# 이벤트 버블링

## 먼저 이벤트 등록에 대해 알고가자!

이벤트 등록이란 웹 애플리케이션에서 사용자의 입력을 받기 위해 필요한 기능을 말합니다. 아래와 같은 코드를 의미합니다.

```HTML
<button>add one item</button>
```

```JS
var button = document.querySelector('button');
button.addEventListener('click',addItem);

function addItem(event) {
    console.log(event);
}
```

버튼을 클릭하면 `addItem` 함수가 실행되고 `addItem`함수에 `event`인자가 넘어옵니다. `event`인자를 콘솔에 출력해보면 이벤트와 관련된 정보를 확인할 수 있습니다.

이처럼 `addEventListener()` 웹 API는 웹 개발자들이 화면에 동적인 기능을 추가하기 위해 자연스럽게 접하게 되는 기본적인 기능입니다. 사용자의 입력에 따라 추가 동작을 구현할 수 있는 방법입니다.

**여기서 브라우저는 어떻게 이벤트의 발생을 감지했을까요?**

## 1. 이벤트 버블링 (Event Bubbling)

이벤트 버블링은 특정 화면 요소에서 이벤트가 발생했을 때**해당 이벤트가 더 상위의 화면 요소들로 전달되어가는 특성**을 의미합니다.

![](https://joshua1988.github.io/images/posts/web/javascript/event/event-bubble.png)

**위에 그림 코드**

```HTML
<body>
	<div class="one">
		<div class="two">
			<div class="three">
			</div>
		</div>
	</div>
</body>
```

```JS
var divs = document.querySelectorAll('div');
divs.forEach(function(div) {
    div.addEventListener('click',logEvent);
});

function logEvent(event) {
    console.log(event.currentTarget.className);
}
```

위 코드는 세개의 div태그에 모두 이벤트를 등록하고, 클릭했을 때 `logEvent`함수를 실행시키는 코드입니다.

**결과**

> `one`을 눌렀을 때

    one

> `two`를 눌렀을 때

    two
    one

> `three`를 눌렀을 때

    three
    two
    one

**three**를 눌렀을 때 왜 3개의 이벤트가 발생되는 걸까요? 그 이유는 브라우저가 이벤트를 감지하는 방식 때문입니다.

브라우저는 특정 화면 요소에서 이벤트가 발생했을 때 그 이벤트를 최상위에 있는 화면 요소까지 이벤트를 전파시킵니다. 따라서 **three**를 눌렀을 때 three -> two -> one 순서로 div 태그에 등록된 이벤트들이 실행됩니다.

여기서 주의해야 할 점은 각 태그마다 이벤트가 등록되어 있기 때문에 상위 요소로 이벤트가 전달되는 것을 확인할 수 있습니다. 만약 이벤트가 특정 div태그에만 달려 있다면 위와 같은 결과는 나오지 않습니다.

이와 같이 하위에서 상위요소로의 이벤트 전파 방식을 **이벤트 버블링**이라고 합니다.

## 2. 이벤트 캡쳐 (Event Capture)

이베트 캡쳐는 **이벤트 버블링과 반대 방향**으로 진행되는 이벤트 전파 방식입니다.
![](https://joshua1988.github.io/images/posts/web/javascript/event/event-capture.png)

특정 이벤트가 발생했을 때 최상위 요소인 body 태그에서 해당 태그를 찾아 내려갑니다.

**위에 그림 코드**

```HTML
<body>
	<div class="one">
		<div class="two">
			<div class="three">
			</div>
		</div>
	</div>
</body>
```

```JS
var divs = document.querySelectorAll('div');
divs.forEach(function(div) {
    div.addEventListener('click',logEvent, {
        capture: true; // default 값은 false
    });
});

function logEvent(event) {
    console.log(event.currentTarget.className);
}
```

`addEventListener()`APU에서 옵션 객체에 `capture: true`를 설정해주면 이벤트 캡쳐 방식으로 탐색합니다.

**결과**

> `one`을 눌렀을 때

    one

> `two`를 눌렀을 때

    one
    two

> `three`를 눌렀을 때

    one
    two
    three
