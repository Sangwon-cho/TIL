## 최빈값 구하기

### Problem

최빈값은 주어진 값 중에서 가장 자주 나오는 값을 의미합니다. 정수 배열 array가 매개변수로 주어질 때, 최빈값을 return 하도록 solution 함수를 완성해보세요.
최빈값이 여러 개면 -1을 return 합니다.

### Solution

```javascript
function solution(array) {
  let obj = {};
  array.map((ele) => {
    obj[ele] ? (obj[ele] = obj[ele] + 1) : (obj[ele] = 1);
  });
  let editedObj = Object.values(obj);
  let frequentNum = Math.max(...editedObj);
  if (editedObj.indexOf(frequentNum) != editedObj.lastIndexOf(frequentNum)) {
    return -1;
  }
  let result = getKeyByValue(obj, frequentNum);
  return +result;
}

function getKeyByValue(object, value) {
  return Object.keys(object).find((key) => object[key] === value);
}
```

### 풀이

먼저 배열에 있는 숫자들이 몇번씩 반복되는지를 확인하기 위해 map을 사용하여
값이 존재하지 않으면 값을 1로 지정하고 그 값이 이미 존재하면 그 값에 1을 더해준다.
그렇게하면 배열안에 숫자가 몇번씩 나오는지 객체의 key:value 형태로 확인할 수 있다.
그리고 Object.values()를 사용하여 객체의 value값(반복되는 횟수)만 빼서 배열로 만든다.
그 배열을 spread 연산자를 사용해 배열을 개별 요소로 분리하고 Math.max()를 통해 최댓값을 찾아낸다.
(즉, 최빈값을 찾아내기 위한 과정이었다.)

그 후 indexOf, lastIndexOf를 사용해 그 최빈값이 반복되는 것이 확인되면 -1을 리턴하고
그렇지 않고 유일한 값이라면 그 값을 이용해 그 값을 가지고 있는 key값을 리턴하면 된다.
(문자로 리턴이 되기에 +를 사용하여 숫자로 변경)

### 개념정리

> `value값으로 객체 key값 찾기`

객체의 key값만 알면 value값은 알 수 있다. 그렇기에 객체의 key값을 사용해 객체의 value와 찾고 싶은 value값을
비교하면 그 key값이 무엇인지 알 수 있는 것이다. 그리하여 객체와 찾는 값을 인자로 받아 value로 객체의 key값을 찾는 함수를 외부에서 만들었다.

```javascript
function getKeyByValue(object, value) {
  return Object.keys(object).find((key) => object[key] === value);
}
```
