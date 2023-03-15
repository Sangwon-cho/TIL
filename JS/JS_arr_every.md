# Array.prototype.every()

- every()는 배열 안의 모든 요소가 주어진 판별함수를 통과하는지 테스트한다.
- 즉 모든 요소가 true의 조건을 만족하면 `true`를 return하고 그 외엔 `false`를 리턴한다.

에를 들어 입력된 내용이 모두 숫자인지 확인하는 함수를 만든다고 가정해보자

```Javascript
function isNumber(s) {
   return s.split("").every(ele => !isNaN(s))
}
```

들어온 숫자들을 배열로 만들고 그 배열의 요소 하나하나가 판별함수를 통과하는지 테스트한다. 즉 요소가 숫자이면 isNaN에서 false가 되니 ! \* false가 만나 true를 리턴할 것이다.

이처럼 진실 혹은 거짓과 같은 것을 판별할 때 매우 유용한 메소드이니 기억해두도록 하자!
