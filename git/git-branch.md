# 📄 Git -

## 1. Branch 생성 및 조회

`$ git branch <branchname>` : git branch 생성

`$ git branch`:  옵션 지정하지 않고, branch 명령어를 실행하면 브랜치 목록 전체를 확인 가능하다.

```text
$ git branch issue1

$ git branch

lesson-01
* master
```

## 2.  Branch 전환

`$ git checkout <branch>`: lesson-01 브랜치 사용하여 작업을 수행하기 위해서, 명시적으로 지정

`$ git checkout -b <branch>`: checkout 명령에 옵션 -b를 넣으면 브랜치 작성 및 체크아웃 한번에 실

```text
$ git checkout issue1
```

## 3. Branch 병합

`$ git merge <commit>` : 브랜치 병합은 merge 명령어로 실행, 병합할 커밋 이름을 넣어 실행하면 지정한 커밋 내용이 "HEAD"가 가리키고 있는 브랜치에 넣어진다.

## 4. Branch 삭제

`$ git branch -d <branchname>` : 브랜치를 삭제하면 branch 명령에 -d 옵션을 지정하여 실

```text
$ git branch -d issue1

$ git branch

* master
```

### 



