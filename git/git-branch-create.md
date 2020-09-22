# 📄 Git - Branch Create

## 1. Git - Branch Create

### \(1\). Git - Branch 생성

🔎 새로운 **gitfth** 폴더를 생성 후에 작업

```bash
# 새로운 gitfth - working directory 생성
$ mkdir gitfth

$ cd gitfth/

# git 버전 관리를 하기 위한 초기
$ git init

# f1.txt 파일 생
$ vi f1.txt

$ cat f1.txt 
a

# f1.txt 파일 버전를 하기 위한 add
$ git add f1.txt

# commit 메세지 남기
$ git commit -m"1"

# f1.txt 파일 내용 변경
$ vi f1.txt
a
b

# 변경된 f1.txt 파일 add, commit 메세지 동시에 하기 위한 -am 옵
# git은 한 번도 add 하지 않은 파일은 -am 옵션을 사용할 수 없다.
$ git commit -am"2"

# log 확인
$ git log --oneline
6191eef (HEAD -> exp, master) 2
3950edc 1

# 현재 branch에 대한 정보를 보여준다.
$ git branch
* master

# exp(experiment) 이름을 가진 branch 생성
$ git branch exp

# exp, master 브랜치 두 개 존재, 현재 사용하는 브랜치에 * 표시 된다.
$ git branch
  exp
* master

# master 브랜치에서 exp 브랜치로 이동
$ git checkout exp

# 현재 exp 브랜치를 사용하고 있다고 확인
$ git branch
* exp
  master

# 현재 디렉토리에 있는 파일들 출
$ ls -al
total 21
drwxr-xr-x 1 user 197609 0  9월 20 19:48 ./
drwxr-xr-x 1 user 197609 0  9월 20 19:29 ../
drwxr-xr-x 1 user 197609 0  9월 20 20:33 .git/
-rw-r--r-- 1 user 197609 4  9월 20 19:48 f1.txt

# log 확인, master 브랜치와 exp 브랜치는 같은 상태임을 확인
# 즉, 브랜치를 생성하면 생성한 브랜치는 현재 속해 있는 브랜치의 상태를 그대로 복사한다.
$ git log --oneline
6191eef (HEAD -> exp, master) 2
3950edc 1

$ vi f1.txt

$ cat f1.txt
a
b
c

$ git commit -am"3"

# exp 브랜치에서 f1.txt 파일 변경 하고, 커밋한 다음에 log 확
$ git log --oneline
edd1c65 (HEAD -> exp) 3
6191eef (master) 2
3950edc 1

# exp 브랜치에서 master 브랜치로 이
$ git checkout master

# master 브랜치의 log 확
$ git log --oneline
6191eef (HEAD -> master) 2
3950edc 1

# 즉, f1.txt 파일은 현재 어떤 브랜치의 속해 있는지 따라서 파일의 내용이 달라진다. 
$ cat f1.txt
a
b

# master 브랜치에서 exp로 이동
$ git checkout exp

# 새로운 f2.txt 파일을 생성 한 다음에 add, commit 까지 실
$ vi f2.txt

$ cat f2.txt
a

$ git add f2.txt

$ git commit -m"4"

# exp 브랜치에서 다시 master 브랜치로 이동
# exp 브랜치에서 새롭게 생성한 f2.txt 파일은 사라진다.
$ git checkout master
```

### \(2\). Git - Branch 명령어 정리

* **git branch**
  * **브랜치의 목록**을 볼 때 사용한다. 현재 사용하고 있는 브랜치는 앞에 \* 표시가 되어 있다.
* **git branch &lt;name&gt;**
  * **새로운 브랜치 생성**
  * 새로운 브랜치를 생성하면 생성한 브랜치는 현재 속해 있는 브랜치의 상태를 그대로 복사한다.
* **git branch -d**
  * **브랜치를 삭제** 할 때 사용한다.
* **git branch -D**
  * **병합 \(merge\)하지 않은 브랜치를 강제 삭제**할 때 사용한다.
* **git checkout &lt;name&gt;**
  * **현재 브랜치에서 다른 브랜치로 이동** 할 때 사용한다.
* **git checkout -b &lt;name&gt;**
  * **새로운 브랜치를 생성하고, 이동**까지 할 때 사용한다.

