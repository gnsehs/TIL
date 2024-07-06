# Git Rebase

* 두개의 공통 BASE를 가진 Branch에서 한 Branch의 Base를 다른 Branch의 최신 Commit으로 Base를 옮기는 작업 -> 기원을 다시 설정한다.
* Merge는 여러 Branch를 하나로 통합하는 느낌
* Rebase는 Branch의 base를 재설정 
  * Base: Branch가 뻗어 나오는 시작점

![alt](https://user-images.githubusercontent.com/26623547/133927057-539dd858-dc43-48a9-a1a1-982540963a04.png)

* feature의 base를 b -> m2(master의 최신 커밋)로 재설정 

## Rebase 과정

현재 브랜치가 feature 일때 `git rebase master` 수행 했을시 과정

![alt](https://user-images.githubusercontent.com/26623547/133971436-666ff03a-83a8-4e92-8fcc-4638a1e4f0eb.png)

* **공통 조상인 base commit 부터 현재 브랜치 까지의 모든 변경 사항을 patch 로 저장**

![alt](https://user-images.githubusercontent.com/26623547/133971560-9885c850-9662-4f84-b408-ec4b6dfdf6bd.png)

* **Head를 Master로 변경**

![alt](https://user-images.githubusercontent.com/26623547/133971699-5e20168a-d8d5-4bad-957f-0c6054a1e492.png)

* **master의 최신 커밋부터 patch에 있는 변경 사항을 하나씩 적용해 나감**

![alt](https://user-images.githubusercontent.com/26623547/133972005-98643842-f1b7-41d3-a64c-b663ece406c2.png)

* **feature는 변경 사항이 완료된 f2'를 가리킨다.**

## Rebase Conflict

* Rebase는 변경 사항을 patch로 만들어 임시 저장함
* 그 후 만들어진 patch들을 새 base에 하나씩 병합을 진행
* **Conflict를 해결하려면 patch수 만큼 merge conflict를 해결하는 방식으로 해결해 나가면 됨**
* 1. **충돌 파일 수정**
* 2. **git add**
* 3. **git rebase --continue**
* 4. rebase 전으로 되돌리고 싶다면  git rebase --abort

### reference

* <https://seosh817.tistory.com/240>
* <https://velog.io/@hosunghan0821/Git-%EC%8B%A4%EB%AC%B4%EC%97%90%EC%84%9C-%EB%B0%B0%EC%9A%B4-Git-Rebase>
* <https://wonyong-jang.github.io/git/2021/02/05/Github-Rebase.html>