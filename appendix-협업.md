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