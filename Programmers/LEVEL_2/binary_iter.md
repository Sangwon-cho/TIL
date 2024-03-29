## 이진 변환 반복하기

<br>

### Problem

0과 1로 이루어진 어떤 문자열 x에 대한 이진 변환을 다음과 같이 정의합니다. x의 모든 0을 제거합니다.
x의 길이를 c라고 하면, x를 "c를 2진법으로 표현한 문자열"로 바꿉니다.예를 들어, x = "0111010"이라면, x에 이진 변환을 가하면 x = "0111010" -> "1111" -> "100" 이 됩니다.

0과 1로 이루어진 문자열 s가 매개변수로 주어집니다. s가 "1"이 될 때까지 계속해서 s에 이진 변환을 가했을 때, 이진 변환의 횟수와 변환 과정에서 제거된 모든 0의 개수를 각각 배열에 담아 return 하도록 solution 함수를 완성해주세요.

### Solution

```javascript
function solution(s) {
  let count = 0; // 변환 횟수
  let zero = 0; // 제거된 0의 개수

  while (s !== "1") {
    // "1"이 될 때까지 반복
    let c = s.replaceAll("0", "").length; // 0을 제거한 문자열의 길이
    zero += s.length - c; // 제거된 0의 개수 누적
    s = c.toString(2); // 2진법으로 변환
    count++; // 변환 횟수 증가
  }

  return [count, zero];
}

solution("110010101001");
```

### 풀이

1. while 반복문으로 변환 작업을 수행하면서 "1"이 될 때까지 반복
2. replaceAll("0", "") 메서드를 사용하여 0을 제거한 문자열의 길이를 구한다.
3. zero += s.length - c를 통해 제거된 0의 개수를 누적.
4. toString(2) 메서드를 사용하여 2진법으로 변환한 후 다시 s에 할당
   -> 이진 변환 반복!

<br>

### 개념정리

`toString()` & `parseInt()`

- 십진수를 이진수로 변환하는 방법:
  - Number.toString(2) 메서드를 사용하여 숫자를 2진수 문자열로 변환할 수 있다. 예를 들어, 10.toString(2)는 "1010"을 반환한다.
- 이진수를 십진수로 변환하는 방법:
  - parseInt(binary, 2) 함수를 사용하여 2진수 문자열을 십진수로 변환할 수 있다. 예를 들어, parseInt("1010", 2)는 10을 반환한다.
