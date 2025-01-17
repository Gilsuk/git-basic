github
===

기존의 로컬 레포가 있을 때
---
github에서 레포를 생성할 때, 초기화(init)명령을 내리지 말고 레포를 생성하여, 주소만 받아온 뒤, 자신의 로컬 레포에서

    git remote add origin https://github.com/account/repo.git
으로 리모트를 연결한 후

    git push origin master
로 깃헙에 푸시한다.

다른 팀 구성원들은 이후에 이 레포를 clone하면 된다.

새로시작하는 프로젝트
---
github에서 레포를 생성할 때, init을 하여 github이 최초의 레포가 되도록 한다.
그리고 이것을 곧바로 clone해서 사용한다.

권한
---
github에서 공개한 프로젝트는 누구나 clone할 수 있지만, 권한은 획득한 멤버들만 push할 수 있다. 따라서 팀원들의 계정에 push권한을 주어야 한다.

브랜치 관리 전략
---
clone이든 push든 일단 레포를 시작하면 master 브랜치만 존재할 것이다.

    git checkout -b develop
    git push -u origin develop
위 커맨드로 develop 브랜치를 만들고 리모트에 푸시하고 추적브랜치를 연결한다.

다른 팀 구성원들은 이것을 clone한 후,

    git checkout develop
으로 develop 브랜치를 checkout 한다. develop 브랜치는 origin/develop을 자동으로 추적하고 있다.

이제 develop 브랜치로부터 각자 자신의 브랜치를 마음껏 생성하여 작업한 후, 주기적으로 develop에 작업 상황을 반영한다.

    git checkout develop
    git fetch
    git merge @{u}
    ---적절한 병합 수행---
    git push
를 통해서 자신의 작업 상황을 리모트에 반영한다.

자신이 작업중인 수많은 브랜치를 모두 push할 필요가 없다. 자신의 작업상황은 develop으로 다 모아서 develop만 push하면 된다.

develop의 기능이 안정화 되었다고 판단할 때 master로 병합한다.

팁
---
로컬에서 어느정도 개발환경을 구축해놓고 푸시를 하는편이 시행착오를 줄이는데 유리하다.

이슈/풀리퀘스트는 협업용 게시판이다. 수정해야할 이슈 등을 등록해놓고 확인하거나 다른 팀원에게 기능 추가/삭제를 요청할 수도 있다.

또한 커밋간 소스코드의 변경사항을 보여주는

    git diff
가 GUI 환경으로 구성되어 더욱 보기 편하다.

소스코드의 blame 메뉴를 통해서 코드의 어떤 부분이 어느 커밋에서 수정되었는지 알아볼 수 있다.

GUI
---
git은 대부분의 코딩용 에디터에 내장되어있거나, 추가 플러그인으로 제공된다. 또한, GUI도구도 여럿 나와있으니 편한대로 쓰면된다.

Eclipse에서 git사용하기
---
이클립스에도 Egit 이라는 이름의 git GUI툴이 내장되어 있다.

    Window -> Perspective -> Open Perspective -> Other -> Git -> Open
왼쪽 메뉴에서, 레포를 불러오거나 clone하여 시작할 수 있다. 인터페이스만 다를 뿐, staging하고 commit하고 브랜치를 생성하는등 기본 원리는 모두 동일하다.
