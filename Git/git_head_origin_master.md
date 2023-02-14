## HEAD -> main, origin/main

- `git log --online`을 입력하면 아래와 같은 내용을 확인할 수 있다.

![image!](/image/log-1.png)

- main: 메인

- HEAD: 현재 자신의 작업공간을 나타낸다.

- origin: 원격 저장소의 default 경로이름(git clone시 자동생성)

- HEAD -> main : 로컬 저장소의 최종 커밋

- origin/main: 원격 저장소의 메인 브랜치

- origin/HEAD: 원격 저장소의 default 브랜치의 HEAD

그 다음, 새로운 내용을 commit은 하고 원격저장소의 push 하기 전 상태를 보여준다

<br>

![image2](/image/log-2.png)

- 로컬저장소의 최종 커밋은 HEAD -> main 이 가리키고 있지만 아직 원격 저장소에 push가 되어있지 않기에 그 전 커밋을 원격저장소의 최종커밋으로 보고 있는 것이다.
