# 📄 Git - Stash

## 1. Git - Stash

### \(1\). Git - Stash

🔎 **gitfh**  폴더를 다시 **Git** 버전 관리하게끔 **초기화** 시킨 다음에 작

* **Stash**는 **감추다, 숨겨두다** 라는 뜻을 갖고 있는 단어이다.
* 브랜치를 만들어서 작업을 하던 중에, **작업하던 내용을 끝내지 않고 다른 브랜치로 이동해야 될 경우**에 사용한다.
* **Stash**의 기능을 통해서 **작업이 끝나지 않은 작업을 커밋하지 않고, 작업했던 내용을 숨겨**둘 수 있게 된다.
* git stash 
  * 하던 **작업을 임시로 저장**한다.
* git stash list
  * **stash 목록** 확인
  * 여러 번 **stash** 했다면  **가장 최신 순으로 위에서 stash  목록을 확인**할 수 있다.
* git stash apply
  * **stash** 했던 **작업을 다시 가져**오기
  * **apply** 명령을 하게 되면 **stash** 목록 중에서 맨 위에 있는 **stash**에 적용된다.
* git stash drop
  * **apply** 옵션은 단순히 **stash**를 적용하므로 스택에 남아 있는다.
  * 스택에 남아 있는 **stash**는 **drop** 명령을 사용하여 **제거**한다.
* git stash pop
  * **stash**의 **apply** 와 **drop** 명령을 **동시에 실행**한다.

```bash
# gitfh 작업 폴더 초기화
$ git init

$ vi f1.txt

$ cat f1.txt
a

$ git add f1.txt

# f1.txt 파일 만들고 작업한 다음에 커밋
$ git commit -m"1"

# 새로운 exp 브랜치 만든 다음에 exp 브랜치로 이동
$ git checkout -b exp

$ git branch
* exp
  master

$ vi f1.txt

$ cat f1.txt
a
b

# exp 브랜치에서 작업하는 중간에 다시 master 브랜치로 돌아갈 경우
$ git checkout master
Switched to branch 'master'
M       f1.txt

# master 브랜치에서 상태를 확인하면, exp 브랜치에 작업한 내용
# master 브랜치에게 까지 영향을 미치게 된다.
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f1.txt

$ git checkout exp

# stash save를 하면 스택에 새로운 stash가 만들어지면서
# 워킹 디렉토리는 깨끗해진다.
$ git stash save
warning: LF will be replaced by CRLF in f1.txt.
The file will have its original line endings in your working directory
Saved working directory and index state WIP on exp: 192353a 1

$ git status
On branch exp
nothing to commit, working tree clean

# stash 목록 확인
$ git stash list
stash@{0}: WIP on exp: 192353a 1

# 제일 최신 커밋 상태로 돌아간다.
$ git reset --hard HEAD
HEAD is now at 192353a 1

$ git status
On branch exp
nothing to commit, working tree clean

# stash 목록에서는 아까 stash 한 게 아직 남아 있다.
$ git stash list
stash@{0}: WIP on exp: 192353a 1

# git reset --hard 명령을 통해서 날린 것을 apply 해서 다시 가져온다.
$ git stash apply
On branch exp
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f1.txt
                
# 최신 커밋 상태로 되돌아간다.
$ git reset --hard
HEAD is now at 192353a 1

# 날려 버린 것을 다시 복원한다.
$ git stash apply
On branch exp
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f1.txt
        
# stash 목록에 있는 것은 명시적으로 삭제하지 않는 이상 존재한다.        
$ git stash list
stash@{0}: WIP on exp: 192353a 1

$ git reset --hard
HEAD is now at 192353a 1

$ vi f2.txt

$ cat f2.txt
a

# f2.txt 파일 만들어서 작업한 후에, git add
$ git add f2.txt
warning: LF will be replaced by CRLF in f2.txt.
The file will have its original line endings in your working directory

# stash 실
$ git stash
Saved working directory and index state WIP on exp: 192353a 1

# 현재 stash 목록에는 2개의 stash가 저장된 걸 볼 수 있다.
# 위에서 부터 가장 최신 순으로 목록들이 나오면서 apply 하면 최신순이 적용
$ git stash list
stash@{0}: WIP on exp: 192353a 1
stash@{1}: WIP on exp: 192353a 1

$ git status
On branch exp
nothing to commit, working tree clean

# 가장 최신순의 stash 상태로 돌아간다.
$ git stash apply
On branch exp
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   f2.txt

$ git stash list
stash@{0}: WIP on exp: 192353a 1
stash@{1}: WIP on exp: 192353a 1

# 가장 최신순의 stash가 삭제된다.
$ git stash drop
Dropped refs/stash@{0} (16b66fd6d85464ff3aad913bcca4244591c44357)

$ git stash list
stash@{0}: WIP on exp: 192353a 1

# apply, drop 명령을 동시에 실행
$ git stash apply; git stash drop

$ git status
On branch exp
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   f2.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f1.txt
        
# stash의 목록을 조회하면 더 이상 아무것도 나오지 않는다
$ git stash list

$ git reset --hard

$ vi f1.txt

$ cat f1.txt
a
b
 
$ git add f1.txt

$ git stash
Saved working directory and index state WIP on exp: 192353a 1

$ git status
On branch exp
nothing to commit, working tree clean

# stash의 apply + drop의 동시 실행
$ git stash pop
On branch exp
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f1.txt

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (f7e8541590e425c83da62d523cc1fa2c855c97ff)

$ git stash list

$ ls -al
total 21
drwxr-xr-x 1 user 197609 0 10월  8 19:52 ./
drwxr-xr-x 1 user 197609 0 10월  8 19:08 ../
drwxr-xr-x 1 user 197609 0 10월  8 19:52 .git/
-rw-r--r-- 1 user 197609 6 10월  8 19:52 f1.txt

$ git reset --hard
HEAD is now at 192353a 1

$ vi f1.txt

$ cat f1.txt
a
b

$ vi f2.txt

$ cat f2.txt
a

$ git status
On branch exp
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f1.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        f2.txt

no changes added to commit (use "git add" and/or "git commit -a")

$ git stash
Saved working directory and index state WIP on exp: 192353a 1

# f2.txt 파일은 추적되지 않기 때문에 stash 되지 않는다.
# stash는 최소한 git이 추적하고 있는 파일을 stash 할 수 있다.
$ git status
On branch exp
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        f2.txt                                                                                                                                
```

```bash
# gitfh 작업 폴더 초기화
$ git init

$ vi f1.txt

$ cat f1.txt
a

$ git add f1.txt

# f1.txt 파일 만들고 작업한 다음에 커밋
$ git commit -m"1"

# 새로운 exp 브랜치 만든 다음에 exp 브랜치로 이동
$ git checkout -b exp

$ git branch
* exp
  master

$ vi f1.txt

$ cat f1.txt
a
b

# exp 브랜치에서 작업하는 중간에 다시 master 브랜치로 돌아갈 경우
$ git checkout master
Switched to branch 'master'
M       f1.txt

# master 브랜치에서 상태를 확인하면, exp 브랜치에 작업한 내용이 master 브랜치에게
# 까지 영향을 미치게 된다.
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f1.txt

$ git checkout exp

# stash save를 하면 스택에 새로운 stash가 만들어지면서, 워킹 디렉토리는 깨끗해진다.
$ git stash save
warning: LF will be replaced by CRLF in f1.txt.
The file will have its original line endings in your working directory
Saved working directory and index state WIP on exp: 192353a 1

$ git status
On branch exp
nothing to commit, working tree clean

# stash 목록 확인
$ git stash list
stash@{0}: WIP on exp: 192353a 1

# 제일 최신 커밋 상태로 돌아간다.
$ git reset --hard HEAD
HEAD is now at 192353a 1

$ git status
On branch exp
nothing to commit, working tree clean

# stash 목록에서는 아까 stash 한 게 아직 남아 있다.
$ git stash list
stash@{0}: WIP on exp: 192353a 1

# git reset --hard 명령을 통해서 날린 것을 apply 해서 다시 가져온다.
$ git stash apply
On branch exp
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f1.txt
                
# 최신 커밋 상태로 되돌아간다.
$ git reset --hard
HEAD is now at 192353a 1

# 날려 버린 것을 다시 복원한다.
$ git stash apply
On branch exp
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f1.txt
        
# stash 목록에 있는 것은 명시적으로 삭제하지 않는 이상 존재한다.        
$ git stash list
stash@{0}: WIP on exp: 192353a 1

$ git reset --hard
HEAD is now at 192353a 1

$ vi f2.txt

$ cat f2.txt
a

# f2.txt 파일 만들어서 작업한 후에, git add
$ git add f2.txt
warning: LF will be replaced by CRLF in f2.txt.
The file will have its original line endings in your working directory

# stash 실
$ git stash
Saved working directory and index state WIP on exp: 192353a 1

# 현재 stash 목록에는 2개의 stash가 저장된 걸 볼 수 있다.
# 위에서 부터 가장 최신 순으로 목록들이 나오면서 apply 하면 최신순이 적용
$ git stash list
stash@{0}: WIP on exp: 192353a 1
stash@{1}: WIP on exp: 192353a 1

$ git status
On branch exp
nothing to commit, working tree clean

# 가장 최신순의 stash 상태로 돌아간다.
$ git stash apply
On branch exp
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   f2.txt

$ git stash list
stash@{0}: WIP on exp: 192353a 1
stash@{1}: WIP on exp: 192353a 1

# 가장 최신순의 stash가 삭제된다.
$ git stash drop
Dropped refs/stash@{0} (16b66fd6d85464ff3aad913bcca4244591c44357)

$ git stash list
stash@{0}: WIP on exp: 192353a 1

# apply, drop 명령을 동시에 실행
$ git stash apply; git stash drop

$ git status
On branch exp
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   f2.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f1.txt
        
# stash의 목록을 조회하면 더 이상 아무것도 나오지 않는다
$ git stash list

$ git reset --hard

$ vi f1.txt

$ cat f1.txt
a
b
 
$ git add f1.txt

$ git stash
Saved working directory and index state WIP on exp: 192353a 1

$ git status
On branch exp
nothing to commit, working tree clean

# stash의 apply + drop의 동시 실행 
$ git stash pop
On branch exp
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f1.txt

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (f7e8541590e425c83da62d523cc1fa2c855c97ff)

$ git stash list

$ ls -al
total 21
drwxr-xr-x 1 user 197609 0 10월  8 19:52 ./
drwxr-xr-x 1 user 197609 0 10월  8 19:08 ../
drwxr-xr-x 1 user 197609 0 10월  8 19:52 .git/
-rw-r--r-- 1 user 197609 6 10월  8 19:52 f1.txt

$ git reset --hard
HEAD is now at 192353a 1

$ vi f1.txt

$ cat f1.txt
a
b

$ vi f2.txt

$ cat f2.txt
a

$ git status
On branch exp
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f1.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        f2.txt

no changes added to commit (use "git add" and/or "git commit -a")

$ git stash
Saved working directory and index state WIP on exp: 192353a 1

# f2.txt 파일은 추적되지 않기 때문에 stash 되지 않는다.
# stash는 최소한 git이 추적하고 있는 파일을 stash 할 수 있다.
$ git status
On branch exp
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        f2.txt                                                                                                                                
```





