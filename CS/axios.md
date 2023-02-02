## Axios

흔히 백엔드 또는 third-party API에 네트워크 요청이 필요한 애플리케이션을 개발할 때 Axios 및 Fetch와 같은 HTTP 클라이언트를 사용!

- Axios는 브라우저, Node.js를 위한 Promise API를 활용하는 HTTP 비동시 통신 라이브러리이다.(Ajax처럼 API를 이용한 비동기 통신을 할 때 주로 사용한다)
  - Ajax: 브라우저의 XMLHttpRequest객체를 이용하여 화면 전체를 새로고침하지 않고 일부 변경된 데이터만 로드하는 비동기 처리.
- 운영환경에 따라 브라우저의 XMLHttpRequest 객체 또는 Node.js의 HTTP API 사용
  - HTTP(HyperText Transfer Protocol)

    - HyperText : 링크 주소를 참조하는 문서로 전자기기에 있는 데이터
    - Transfer : 전달
    - Protocol : 규약, 규칙

    ⇒ 클라이언트의 요청에 서버가 응답하는 방식, 세부적인 방법을 규약으로 정해놓은 것을 HTTP라고 한다.

### 사용하는 이유

- 대부분의 브라우저를 지원한다.
- JSON 데이터를 자동으로 변환해준다.(stringfy 같은 것 사용안해도된다)
- 다양한 기능들이 있다.(요청을 중간에 취소한다거나, 응답시간 초과 시 어떤 동작을 하게 한다거나)
- 가독성이 좋게 구성되어 있다.
- Promise 기반이다.
- 많은 사람들이 사용하고 있다.

### Fetch API와 비교하여..

→ fetch api를 사용한다면 JSON.stringify()를 사용하여 객체를 문자열로 변환한 뒤 body에 할당해야한다. 반면에 Axios는 자동으로 JSON형태로 변환해주기에 편리하다.

→`Error`와 관련하여 fetch api는 404 에러나 다른 HTTP 에러 응답을 받았다고 해서 promise를 거부하지 않는다.
네트워크 장애가 발생한 경우에만 promise를 거부(reject)한다. 그래서 .then을 사용해 수동으로 HTTP 에러를 처리해야한다. 반면 **axios는 상태코드가 2xx의 범위를 넘어가면 거부(reject)한다!!**
