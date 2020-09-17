# 📄Git - reset, revert

## 1. Git - reset,  **revert**

* Git 를 사용해서 버전 관리를 하게 되면 과거로 돌아갈 수 있다. 
* 즉, **commit**를 취소하는 명령어 이다.

### \(1\). git reset

`git reset`명령어는 특정 커밋으로 되돌아 갈 수 있는데, 되돌린 버전 이후의 버전들은 **히스토리에서 삭제**된다.

🤚**내 버전을 공유한 이후**에는 즉, 프로젝트에 협업하여 작업할 때,  `git reset`은 함부로 해서는 안된다. 

🤚`git reset`  **공유하기 이전에 내 PC에 있는 버전들만** `git  reset`**할 수 있다.**

```bash
# 기 f1.txt 파일 내용 출력
$ cat f1.txt
source : 1

# 기존 f1.txt 파일 내용 수정 후 다시 저장
$ vi f1.txt 

# 변경된 f1.txt 파일 내용 출력
$ cat f1.txt
f1.txt : 1

# 현재 상태 조회, 변경 f1.txt 파일은 git add를 하지 않았기 때문에
# 추적되지 않아서 modified : f1.txt로 빨간색으로 출력 되어서 나온다.
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f1.txt

no changes added to commit (use "git add" and/or "git commit -a")

# 버전 관리하는 파일은 수정을 했을 때에도 git 다시 추적하기 위해서
# git add 명령어를 실행한다.
$ git add f1.txt

# 수정을 하고 git add 명령어를 실행한 f1.txt 파일은 다시 git 추적해서 관리한다.
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   f1.txt
        
# 변경된 f1.txt 파일은 commit 메세지를 남겨서 버전을 등록한다
$ git commit -m"f1.txt changes content"
[master d6e0d84] f1.txt changes content
 1 file changed, 1 insertion(+), 1 deletion(-)

# git log 명령어에 --oneline 옵션을 주어서 log를 한 줄로 출력한다.
$ git log --oneline
d6e0d84 (HEAD -> master) f1.txt changes content
5f2d478 second commit
fe872b3 first commit

# git reset 명령어로 버전 d6e0d84, 5f2d478 2개를 지우고
# fe872b3 first commit 으로 되돌아 가고자 한다. 이때에
# --hard 옵션을 주면 working directory 내용 까지 모두 바꾼다.
$ git reset --hard fe872b3
HEAD is now at fe872b3 first commit

# git rest --hard 명령을 실행한 후, log 확인
$ git log --oneline
fe872b3 (HEAD -> master) first commit

# fe872b3 first commit 버전에 해당 되는 소스 코드의 상태로 되돌아 왔다.
$ ls -al
total 21
drwxr-xr-x 1 user 197609  0  9월 17 17:58 ./
drwxr-xr-x 1 user 197609  0  9월 17 15:12 ../
drwxr-xr-x 1 user 197609  0  9월 17 17:58 .git/
-rw-r--r-- 1 user 197609 12  9월 17 17:58 f1.txt

# fe872b3 first commit 버전일 때 f1.txt 소스 코드 출력
$ cat f1.txt
source : 1

# fe872b3 first commit 버전명 변경
$ git commit --amend -m"1"
[master 9297e6f] 1
 Date: Thu Sep 17 15:33:45 2020 +0900
 1 file changed, 1 insertion(+)
 create mode 100644 f1.txt


# f2.txt 파일 생성 후 작업, add, commit 명령 까지 실행
$ vi f2.txt

$ cat f2.txt
source : 2

$ git add f2.txt

$ git commit -m"2"

# f1.txt 파일 내용 수정, add, commit 까지 실행
$ vi f1.txt

$ cat f1.txt
source : 3

$ git add f1.txt

$ git commit -m"3"

$ git log --oneline
083f79d (HEAD -> master) 3
7e7d2cb 2
9297e6f 1
```

### \(2\). git revert

**reset**은 버전은 되돌리면서, 버전 이후의 히스토리를 모두 삭제하는 반면에 **revert는 버전은 되돌리지만, 이력을 남기면서 모든 히스토리를 유지한다.**

🤚 **revert**는 **reset**과 반대로 좀 더 안전한 방법으로 **롤백\(rollback\)**이력을 남긴다.

```bash
# reset은 버전은 되돌리면서, 버전 이후의 히스토리를 모두 삭제하는 반면에
# revert는 버전은 되돌리지만 모든 히스토리를 유지한다.

# revert 커밋 메세지는 어떤 커밋으로 되돌린건지 알 수 있도록, 자동으로
# 커밋 메세지를 채워준다.
$ git revert 7e7d2cb
Removing f2.txt
[master 8dee3bf] Revert "2"
 1 file changed, 1 deletion(-)
 delete mode 100644 f2.txt

# revert 작업, log 조
$ git log --oneline
8dee3bf (HEAD -> master) Revert "2"
083f79d 3
7e7d2cb 2
9297e6f 1

$ ls -al
total 21
drwxr-xr-x 1 user 197609  0  9월 17 18:37 ./
drwxr-xr-x 1 user 197609  0  9월 17 15:12 ../
drwxr-xr-x 1 user 197609  0  9월 17 18:37 .git/
-rw-r--r-- 1 user 197609 12  9월 17 18:26 f1.txt
```



  



