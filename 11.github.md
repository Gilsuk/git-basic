github사용법
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
팁
---
로컬에서 어느정도 개발환경을 구축해놓고 푸시를 하는편이 시행착오를 줄이는데 유리하다.