## 최댓값과 최솟값

<br>

### Problem

-문자열 s에는 공백으로 구분된 숫자들이 저장되어 있습니다. str에 나타나는 숫자 중 최소값과 최대값을 찾아 이를 "(최소값) (최대값)"형태의 문자열을 반환하는 함수, solution을 완성하세요.
예를들어 s가 "1 2 3 4"라면 "1 4"를 리턴하고, "-1 -2 -3 -4"라면 "-4 -1"을 리턴하면 됩니다.

### Solution

```javascript
function solution(s) {
  let sep = s.split(" ").map(Number);
  console.log(sep);
  let min = sep.reduce((min, val) => (min < val ? min : val));
  let max = sep.reduce((min, val) => (min > val ? min : val));
  return min + " " + max;
}
```

### 풀이

우선 문자열 s를 공백을 기준으로 분리하고, 이를 숫자형 배열로 변환하기 위해 map 함수에 Number를 적용한다. 그리고 이 배열에서 reduce 함수를 사용하여 최소값과 최대값을 찾는다.
(reduce 함수는 배열의 각 요소를 순회하며 누적값을 계산하는 함수) 이 때 min은 현재까지의 최소값을, val은 현재 요소의 값을 나타낸다. 삼항 연산자를 사용하여 최소값과 최대값을 찾은 후, return문을 통해 결과를 반환한다.

### 개념정리

`map(Number)` - 숫자정렬

- map 함수는 배열의 각 요소에 대해 주어진 함수를 실행하고, 그 결과를 새로운 배열로 반환한다. map(Number)를 적용하면 문자열 배열을 숫자 배열로 변환할 수 있다.
