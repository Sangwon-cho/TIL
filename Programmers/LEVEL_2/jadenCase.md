## JadenCase 문자열 만들기

<br>

### Problem

- JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자인 문자열입니다. 단, 첫 문자가 알파벳이 아닐 때에는 이어지는 알파벳은 소문자로 쓰면 됩니다. (첫 번째 입출력 예 참고)
  문자열 s가 주어졌을 때, s를 JadenCase로 바꾼 문자열을 리턴하는 함수, solution을 완성해주세요.

### Solution

```javascript
function solution(s) {
  let words = s.toLowerCase().split(" ");
  for (let i = 0; i < words.length; i++) {
    if (words[i] !== "") {
      if (isNaN(words[i][0])) {
        words[i] = words[i][0].toUpperCase() + words[i].slice(1);
      } else {
        words[i] = words[i][0] + words[i].slice(1);
      }
    }
  }
  return words.join(" ");
}
```

### 풀이

1. 입력 문자열 s를 모두 소문자로 변환한 후, 공백을 기준으로 단어들을 나눈다.
2. 나눠진 단어들을 순회하면서 첫 번째 문자가 숫자인지 검사한다.
3. 첫 번째 문자가 숫자라면, 단어를 그대로 유지하고 첫 번째 문자가 숫자가 아니라면, 첫 문자를 대문자로 변환하고 나머지 문자들은 그대로 유지한다.
4. 변환된 단어들을 다시 공백으로 연결하여 JadenCase로 변환된 문자열을 반환한다.

### 개념정리

`isNan()`

```
isNan(VALUE)
```

value가 숫자일 경우 false, 숫자가 아닐 경우 true를 리턴함으로 value라는 문자열이 숫자인지 체크하는 함수이다.

### Check Point!

- 어렵다기 보다 놓쳤던 부분이 있다. 제일 처음 split으로 나눌때 소문자로 바꿔야하는 것을 생각하지 못했다.
  앞의 문자만 대문자로 바꾸면 된다고 생각했지 뒤의 문자들이 소문자인지 대문자인지 생각하지 못했었다. heLlO와 같은 단어가 들어왔을 때를 위해
  제일 처음 소문자로 바꿔야했다.
