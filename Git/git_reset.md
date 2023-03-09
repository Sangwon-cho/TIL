# Git 되돌리기 - git reset

깃으로 이력을 관리하다보면 commit한 내용을 되돌려야할 때가 종종 있는 것 같다.
그때마다 구글에 git reset을 검색해서 사용했었는데 이번 기회에 간단하게 정리하여 내것으로 만들어보려고 한다.

여러방법이 있겠지만 이번에는 git reset을 통해 git의 이력을 되돌리는 방법을 선택하였다.

1. soft

```
git reset --soft HEAD~
```

- 가장 많이 사용했던 것 같다. --soft 옵션을 사용하면 commit전으로 돌아오고 그 변경된 내용이 staged된 상태로 보존되어있다.
- 쉽게 말하면 `git add .`을 이미 실행한 상태로 되돌려진다

<br>

2. hard

```
git reset --hard HEAD~
```

- soft가 있었으면 hard도 있을 것이다. 단어만 봐도 단단하고 엄격할 것 같은 느낌이든다.
- 말 그대로 commit전으로 돌아오지만 그때의 working directory에 작업되었던 것들까지 싹 날라간다.
- 즉, git add를 하려고해도 그 기록들이 없는 상태로 되돌려진다.

<br>

3. mixed

```
git reset --mixed HEAD~
```

- 극단적인 두개의 옵션이 합쳐져서 하나씩 기능을 빼온 것 같다.
- commit전으로 돌아오고 working directory의 기록도 함께 있지만 unstaged된 상태로 보존되어있다.
- 즉 아직 git add가 되어있지 않은 상태로 커밋을 하려면 add를 해주고 진행해야되는 상태로 되돌려진다.

<br>

---

<br>

- `HEAD~` 뒤에는 몇개의 커밋을 되돌리고 싶은지 적을 수 있다.

```
git reset --mixed HEAD~1
```

최종 HEAD에서 한개 전의 commit을 되돌리는 것이다.

- 만일 특정 commit을 되돌리고 싶다면 숫자와 영문자의 조합으로 되어있는 commit id를 옵션 뒤에 적으면 된다.

```
git reset --mixed "commit id"
```

## Github에 push한 commit 되돌리기!

앞에서 사용한 것과 같이 git reset을 통해 commit을 되돌리고 `-f`를 사용하여 github에 업데이트 해주면 된다.
예를 들어 메인에서 push 한 커밋을 지우려면(되돌리려면)

```
git push -f origin main
```

을 사용하여 업데이트 해주면 된다.
