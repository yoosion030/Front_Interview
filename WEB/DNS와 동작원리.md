# DNS와 동작원리가 무엇인가요?

## DNS( Domain Name System )란?

우리는 인터넷을 이용하여 검색이나 웹 서핑, 이메일 등을 사용할 때 도메인 이름( EX www. naver. com )을 웹 브라우저의 주소창에 입력하고 접속하게 됩니다. 즉 실제 naver.com 서버는 숫자로 구성된 IP주소로 통신하지만, 기억하기 쉬운 도메인 이름을 사용하는 것이 필요합니다. 그럼 입력한 도메인 주소를 IP주소로 변환하는 과정이 필요한데 이것을 담당하는 시스템이 DNS입니다.

## DNS를 사용하는 이유
만약 네이버를 접속하려고 할 때 네이버 IP주소를 입력하여 접속하려는 사람은 아마 없을겁니다. 있다고 해도 길고 복잡한 IP 주소를 외울수가 없기 때문에 문자 주소로 바꿔주기 위해 DNS를 사용하게 됩니다.

## 구성 요소 및 동작 원리
**1. 도메인 네임 스페이스 (Domain Name Space)**
최상위 루트에 DNS 서버가 존재하고, 그 하위로 인터넷에 연결된 모든 노드가 연속해서 이어진 계층구조로 구성

**2. 네임 서버 (Name Server)**
주소를 변환 시키기 위해 도메인 네임 스페이스의 트리구조에 대한 정보가 필요한데 이 정보를 가진 서버 도메인 이름을 IP 주소로 변환하는 것

**3. 리졸버 (Resolver)**
DNS클라이언트의 요청을 네임 서버로 전달하고 네임 서버로부터 도메인이름과 IP주소를 받아 클라이언트에게 제공하는 기능을 수행


![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcgbNqc%2Fbtq1uuMDN4D%2Fcfifchk6rOn14ZyP9LB8O0%2Fimg.jpg)



`참고자료`
> [tistory - DNS개념 및 동작 원리](https://ja-gamma.tistory.com/entry/DNS%EA%B0%9C%EB%85%90%EB%8F%99%EC%9E%91%EC%9B%90%EB%A6%AC)