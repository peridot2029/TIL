# 📄 Git Term

## 1. Git Term

### \(1\). Working space

개인 컴퓨터 환경에서 소스 코드를 편집하는 **일반적인 프로젝트 폴더**

### \(2\). R**epository**

작업 공간을 Git이 제공하는 자료구조 안에서 압축 시켜 넣은 것

**local  repository, remote  repository** 두 개의 저장소로 나뉜다.

### \(3\). Remote r**epository**

다른 어딘가의 서버에 위치에 있는 원격 저장소

원격 저장소를 사용하면 여러 사람이 서버에 있는 하나의 저장소를 공유해서 공동 작업 할 수 있다.

* `$ git remote` : 원격 저장소와 로컬 저장소를 연결시키는 명령어
* `$ git clone` : `git pull` 과 비슷하지만 서버의 클라이언트 상에서 아무것도 없을 때, 프로젝트를 내려받는 명령어
* `$ git fetch` : 원격 저장소에 업데이트 된 저장소를 받아서 로컬 저장소를 갱신하는 명령어
* `$ git push` : 원격에 내 로컬 저장소를 올리는 명령어
* `$ git pull` : `git fetch`한 다음 작업공간 까지 갱신하는 명령

### \(4\). Commit

작업 공간의 상태를 저장한 것, 즉, 어떤 시점의 스냅샷을 의미

### \(5\). Staging Area

Git 에는 Staging Area 라는 공간이 있다. 어떤 변경 사항이 저장소에 **커밋 되기 전**에, 반드시 거쳐야 하는 중간 단계 이다. 

### \(6\). Branch

커밋에서 분기된 브랜치

* `master` : 기본 설정된 브랜치
* `origin` : 기본 설정된 원격 저장소 주소에 붙는 별명

### \(7\). Log

Git 에서 히스토리를 조회하는 명령어,`$ git log`를 하게 되면 최신순으로 커밋 로그를 조회한다.

* `$ git log --oneline` : 옵션을 적용해서,  커밋에 대한 내용을 한 줄로 표시
* `$ git log -p` : 차이점을 커밋별로 보고 싶을 때 사용
* `$ git diff` : 버전의 차이점 비교, diff 를 사용하면 로컬의 브랜치 간 비교, 커밋 간 비교 등이 가능

### \(8\).  Work tree

Git은 서로 다른 세 트리를 관리하는 시스템이다.

| tree | role |
| :--- | :--- |
| HEAD | 마지막 커밋 스냅샷, 다음 커밋의 부모 커 |
| index | 다음에 커밋할 스냅 |
| working directory | 작업하는 폴더\(공간\) |

### \(9\). Reset





### \(8\). HEAD

**HEAD**는 현재 브랜치를 가리키는 포인터 이며, 브랜치는 브랜치에 담긴 커밋 중 가장 마지막 커밋을 가리킨다.  즉, HEAD는 현재 브랜치의 마지막 커밋의 스냅샷 이다.





### \(10\). Revert







### Reference <a id="reference"></a>

vi 명령어 정리 [ →\(SITE\)](https://blockdmask.tistory.com/25)

git diff 사용하기 [→\(SITE\)](http://hochulshin.com/git-diff/)





