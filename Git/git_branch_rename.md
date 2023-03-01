# Git branch 이름 변경하기

- 해당하는 브랜치로 이동한 후 `git branch -m` 사용하여 변경!

```javascript

   git branch -m 새로운브랜치명

```

<br>

- 이동하지 않고 아무 branch에서 변경하는 방법!

```javascript

   git branch -m 기존브랜치명 새로운 브랜치명

```

## branch 이름 정할 때 주의사항!

    - 만일 a라는 브랜치가 존재한다면, a/anything과 같은 브랜치명을 가진 브랜치는 생성되지 않고 생성되더라도 github에 push할때 에러가 발생한다!

    - 만일 dev/a 라는 브랜치가 존재한다면 dev/a/b와 같은 브랜치명도 사용해서는 안된다!
