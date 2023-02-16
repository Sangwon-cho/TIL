## String.prototype,trim()

- trim() 메서드는 문자열 양 끝의 공백을 제거하고 원본 문자열 수정을 하지 않고 새로운 문자열을 반환한다.

```javascript
const name = "    Joe    ";

console.log(name);
console.log(name.trim());

//expected result:  '    Joe    '
//expected result:  'Joe'
```

크롤링을 하거나 parsing을 할 때 원하지 않는 빈 공백이 함께 오는 경우가 있을 수 있다.
그럴 때 간단하게 trim()을 써서 정리할 수 있다.
