## 여러 커밋(commit) 하나로 합치기

생각없이 커밋을 하다보면 의미없는 내용의 커밋들이 쌓일 떄가 있다.
그럴때 대충 쓴 커밋 메세지를 합쳐서 하나의 의미있는 커밋으로 만들어보자

1. rebase 사용

- 3개의 커밋 메시지를 합쳐줄라면 `git rebase -i HEAD~3`을 실행한다(2개가 있다면 2를 적어주면된다)

```
git rebase -i HEAD~3
```

2. 편집할 커밋 선택

- 제일 최근 커밋한 내용이 제일 위로 온다. 맨위 pick은 놔두고 나머지는 insert mode로 들어가 `pick`을 `s`로 바꿔준 뒤 `:wq`로 저장하고 나온다.

3. 커밋메세지 수정

- 모든 커밋메세지가 합쳐있는 것을 확인할 수 있기에, 원하는대로 지우거나 수정하고 다시 :wq -> 저장,종료해주면 된다.

4. Push 하기

- 강제로 push 하기

```
  git push origin main -f
```

- rebase는 commit history를 정리하는 역할을 한다. 같은 브랜치에서 rebase를 할 때마다 history가 달라질 수 있다.
  수정사항이 추가로 생긴 후 다시 rebase 하면 history가 무조건 달라지게 된다. git은 history가 다른 branch의 push를 허용하지 않는다.
  그렇기에 -f(force)를 사용하여 강제 push를 진행해야한다.
