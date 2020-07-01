---
description: a basic term for dealing with git.
---

# 📄 Git term

### 1. Git term

#### Working space

개인 컴퓨터 환경에서 소스 코드를 편집하는 일반적인 프로젝트 폴더

#### R**epository**

작업 공간을 Git이 제공하는 자료구조 안에서 압축 시켜 넣은 것

Local  Repository, Remote  Repository 두 가지의 저장소를 나뉜다.

#### Remote  r**epository**

다른 어딘가의 서버에 위치에 있는 원격 저장소

원격 저장소를 사용하면 여러 사람이 서버에 있는 하나의 저장소를 공유해서 공동 작업 할 수 있다.

* `git remote` : 원격 저장소와 로컬 저장소를 연결시키는 명령어
* `git clone` : `git pull` 과 비슷하지만 서버의 클라이언트 상에서 아무것도 없을 때, 프로젝트를 내려받는 명령
* `git fetch` : 원격 저장소에 업데이트 된 저장소를 받아서 로컬 저장소를 갱신하는 명령어
* `git push` : 원격에 내 로컬 저장소를 올리는 명령어
* `git pull` : `git fetch`한 다음 작업공간 까지 갱신하는 명령

#### Commit

작업 공간의 상태를 저장한 것

즉, 어떤 시점의 스냅샷을 의미

#### Stage

작업 공간에서 변경이 발생한 파일을 다음 커밋에 포함되도록 예약하는 것을 추적\(Stage\)라고 한다.

#### Branch

커밋에서 분기된 브랜치

* `master` : 기본 설정된 브랜치
* `origin` : 기본 설정된 원격 저장소 주소에 붙는 별명

