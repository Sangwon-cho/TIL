## 핸드폰 번호 가리기

### Problem

프로그래머스 모바일은 개인정보 보호를 위해 고지서를 보낼 때 고객들의 전화번호의 일부를 가립니다.
전화번호가 문자열 phone_number로 주어졌을 때, 전화번호의 뒷 4자리를 제외한 나머지 숫자를 전부 \*으로 가린 문자열을 리턴하는 함수, solution을 완성해주세요.

### Solution

```
function solution(phone_number) {
    let fourNum = phone_number.substr(phone_number.length-4,phone_number.length)
    let num = phone_number.length - 4;
    return "*".repeat(num)+fourNum
}
```

### 풀이

뒤에 문자열 4개를 구하기 위해 처음에는 substr을 사용하였다. 하지만 후에 찾아보니
substr은 엣날 함수라 쓰지말고 대신 substring 또는 slice을 사용하라고 하는 것을 보았다.
기본적인 사용법은 비슷하지만 slice는 음수를 사용함으로 뒤에서부터 문자열을 자를 수 있게 해주기에
substr을 대신해 사용하면 더 좋을 것 같다.

### Refactoring

```
function solution(phone_number) {
    return "*".repeat(phone_number.length-4)+phone_number.slice(-4)
}
```
