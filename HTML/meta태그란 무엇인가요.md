# ⭐\<meta>태그는 무엇인가요?⭐

## 정의
- \<meta/> 태그는 웹 페이지의 **보이지 않는 정보를 제공**하는데 쓰이는 태그입니다.


## 속성
속성에는 **charset, content,http-equiv, name** 이 있습니다.
- charset
- content
- http-equiv
- name

### charset
- 해당 문서의 **문자 인코딩 방식**을 명시합니다.
- HTML5에서는 한글과 영문을 비롯해 모든 언어를 표시할 수 있는 **UTF-8**을 가장 많이 사용합니다.  

```html
    <meta charset="UTF-8">
```

  
### name
- **메타데이터를 위한 이름**을 명시합니다.
- 반드시 **content** 속성과 함께 명시를 해야합니다.
- 속성 값에는 author, description, generator, keywords, **viewport** 가 있다.
- name 은 메타요소가 어떤 정보의 형태를 갖고 있는지 알려주고 content는 실제 메타데이터의 컨텐츠 입니다.
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
- meta viewport는 **반응형 웹 구현을 위해 필요한 메타 태그** 입니다.
- 너비는 보고있는 기기의 넓이이며 그에 맞춰 초기 화면 배율을 1로 지정한다는 의미입니다.


### http-equiv
- content 속성에 명시된 값에 대한 **HTTP 헤더를 제공**합니다.
- 인터넷 익스플로러가 어떤 렌더링 엔진을 사용할지 선택합니다.

```html
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
```
### content
- **name** 속성이나 **http-equiv** 속성과 관련된 값을 명시합니다.
- content는 단독으로 사용할 수 없습니다.

`참고자료`  
> [github - meta 태그를 알아보자](https://junhobaik.github.io/meta-tag/)  
[velog - HTML <meta>태그](https://velog.io/@2seunghye/HTML-meta%ED%83%9C%EA%B7%B8)  
[velog - 그동안 몰랐던 Meta 태그 정리!](https://velog.io/@jellyloveschoco/%EA%B7%B8%EB%8F%99%EC%95%88-%EB%AA%B0%EB%9E%90%EB%8D%98-Meta-%ED%83%9C%EA%B7%B8-%EC%A0%95%EB%A6%AC)
