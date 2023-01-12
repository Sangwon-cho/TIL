## 나누어 떨어지는 숫자 배열

<br>

### Problem

array의 각 element 중 divisor로 나누어 떨어지는 값을 오름차순으로 정렬한 배열을 반환하는 함수, solution을 작성해주세요.
divisor로 나누어 떨어지는 element가 하나도 없다면 배열에 -1을 담아 반환하세요.

### Solution

```
function solution(arr, divisor) {
   const result = arr.filter(ele=> ele%divisor === 0).sort((a,b)=>{return a-b});
  return result.length ? result: [-1]
}
```

### 풀이

filter()함수를 사용하여 함수의 조건을 만족하는 요소들을 모아 새로운 배열을 만들어 result에 담았다.
그 중에서 `sort()` 함수의 사용법을 다시 한번 정리하고 지나가면 크게 문제될 것 같지 않은 문제이다.

### 개념정리

`sort()` - 숫자정렬

- 기본 정렬 순서는 문자열의 유니코드 코드 포인트를 따른다.

유니코드의 포인트를 따르기에 숫자정렬에서 9가 80보다 앞에 오지만 문자열로 변환되면 그 결과는 달라진다.(만일 한자릿수 비교라면 단순히 sort()로도 가능하다. 두자릿수이상의 숫자도 포함되어있다면 꼭 함수 사용해야함!)

그렇기에 sort()내부에서 함수를 사용하여 정렬을 해줘야한다.

```
    const a = [5,2,3,7,19,1];

    const asc = a.sort((a,b)=>(a-b));
    //결과값 : [ 1, 2, 3, 5, 7, 19 ]

    const des = a.sort((a,b)=>(b-a));
    //결과값 : [ 19, 7, 5, 3, 2, 1 ]
```

해당함수는 배열 객체들을 두개씩 받아 비교하고 a-b의 값이 음수인 경우 앞에다 배치하며 +값일수록 뒤에 배치하는 방식이다.
