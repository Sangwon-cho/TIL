## 같은 숫자는 싫어

<br>

### Problem

- 배열 arr가 주어집니다. 배열 arr의 각 원소는 숫자 0부터 9까지로 이루어져 있습니다. 이때, 배열 arr에서 연속적으로 나타나는 숫자는 하나만 남기고 전부 제거하려고 합니다. 단, 제거된 후 남은 수들을 반환할 때는 배열 arr의 원소들의 순서를 유지해야 합니다. 예를 들면,

- arr = [1, 1, 3, 3, 0, 1, 1] 이면 [1, 3, 0, 1] 을 return 합니다.
  arr = [4, 4, 4, 3, 3] 이면 [4, 3] 을 return 합니다.
  배열 arr에서 연속적으로 나타나는 숫자는 제거하고 남은 수들을 return 하는 solution 함수를 완성해 주세요.

- 제한사항
  - 배열 arr의 크기 : 1,000,000 이하의 자연수
  - 배열 arr의 원소의 크기 : 0보다 크거나 같고 9보다 작거나 같은 정수

### Solution

```javascript
function solution(arr) {
  let stack = [];

  for (let i = 0; i < arr.length; i++) {
    let ele = arr[i];
    if (stack.length !== 0 && arr[i - 1] === ele) {
      continue;
    } else stack.push(ele);
  }
  return stack;
}
```

### 풀이

stack이라는 빈 배열을 선언합니다. 이 배열은 남은 숫자들을 저장할 용도로 사용됩니다.

1. for 반복문을 사용하여 배열 arr을 순회,
2. stack이 비어있지 않고, 바로 이전의 원소와 현재 원소가 동일한 경우, 중복된 숫자이므로 continue를 사용하여 반복문의 다음 단계로 건너뛴다.
3. 그렇지 않은 경우, 중복되지 않은 숫자이므로 stack 배열에 현재 원소인 ele를 추가한다.
4. 반복문이 끝나면, stack 배열에는 연속적으로 나타나는 숫자가 제거된 남은 숫자들이 저장되어 있게된다.

<br>

### 다른 풀이

```javascript
function solution(arr) {
  return arr.filter((num, index) => num !== arr[index + 1]);
}
```

filter() 함수의 콜백 함수에서는 현재 원소 num과 다음 원소인 arr[index + 1]을 비교하여 연속적으로 나타나는 숫자를 제거.
-> 필터링된 결과가 새로운 배열로 반환

- 그전의 스택 관련 문제를 풀때 filter함수를 이용해 문제를 푸는 것을 자주 보았다. 한동안 안쓰다 filter라는 것을 보니 다시 한번 까먹지 않게 정리하고 넘어가면 좋을 것 같다.

<br>

### 개념정리

`filter()`

- filter() 함수는 주어진 배열에서 특정 조건을 만족하는 원소들로 구성된 새로운 배열을 생성하는 메서드입니다. 콜백 함수를 인자로 받아 각 원소를 순회하면서 조건을 평가하고, *조건을 만족하는 원소들만 필터링하여 반환*합니다.

```
arr.filter(callback(element, index, array), thisArg)
```

- callback: 각 원소를 평가하는 함수로, 세 개의 매개변수 (element, index, array)를 받습니다.
  - element: 현재 평가되는 원소
  - index: 현재 원소의 인덱스
  - array: 원본 배열
- thisArg (선택 사항): 콜백 함수 내에서 this로 참조할 객체
