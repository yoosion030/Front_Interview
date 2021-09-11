# z-index에 관해 설명해주세요 😴

## 정의
위치 지정 요소와 그 자손 또는 하위 플렉스 아이템의 Z축 순서를 지정합니다. 
> 쉽게 말하자면 객체를 배치할 때 겹칠 때가 있는데 어느 객체가 앞으로 나오고, 뒤에 나올지 배치 순서를 결정하는 속성입니다.

⭐z-index는 position속성이 적용된 요소에서만 작동합니다.⭐  
⭐z-index 속성을 지정하지 않으면 0값을 기본값으로 가지게 됩니다.⭐  
⭐더 큰 z-index 값을 가진 요소가 작은 값의 요소 위를 덮습니다.⭐  

### 예제

```html
<button style="width:100px; height:100px; position:relative; "></button>
<button style="width:100px; height:100px; position:absolute; left : 0; background-color : red;"></button>
```

<button style="width:100px; height:100px; position:relative; z-index:1;"></button>
<button style="width:100px; height:100px; position:absolute; left : 0; background-color : red;"></button>

> 둘다 z-index 값이 0 이기 때문에 흰색 요소가 먼저 보임
### 예제
```html
<button style="width:100px; height:100px; position:relative; "></button>
<button style="width:100px; height:100px; position:absolute; left : 0; z-index:1; background-color : red;"></button>
```

<button style="width:100px; height:100px; position:relative; z-index:1;"></button>
<button style="width:100px; height:100px; position:absolute; left : 0; z-index:1; background-color : red;"></button>

> 겹쳐있지만 빨간색 상자의 z-index값이 1이기 때문에 흰색 상자보다 위에 배치됨

`참고자료`
> [tistory - z-index 속성으로 배치 순서 결정하기](https://aboooks.tistory.com/83)