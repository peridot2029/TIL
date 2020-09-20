# 📄 Git - Branch Create

## 1. Git - Branch Create

### \(1\). Git - Branch 생성

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

# f1.txt 파일 내용 변
$ vi f1.txt
a
b

# 변경된 f1.txt 파일 add, commit 메세지 동시에 하기 위한 -am 옵
# git은 한 번도 add 하지 않은 파일은 -am 옵션을 사용할 수 없다.
$ git commit -am"2"

# log 확
$ git log --oneline
6191eef (HEAD -> exp, master) 2
3950edc 1



# 현재 branch에 대한 정보를 보여준다.
$ git branch
* master

# exp 이름을 가진 branch 생성
$ git branch exp

# exp, master 브랜치 두 개 존재, 현재 사용하는 브랜치에 * 표시 된다.
$ git branch
  exp
* master


# master 브랜치에서 exp 브랜치로 이동
$ git checkout exp

# 현재 exp 브랜치를 사용하고 있다고 확
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

# log 확인, master 브랜치와 exp 브랜치는 같은 상태임을 확
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











```

