# 📄 Git - Repository Introduction

## 1. Git - Repository Introduction

### \(1\).  Repository 란?

* **저장소 \(Repository\)**란 말 그대로 파일 또는  폴더를 저장해두는 곳이다.
* **Git** 저장소가 제공하는 장점 중 하나는 파일이 변경 이력 별로 구분되어 저장 된다는 점이다.
* 비슷한 파일이라도 실제 내용 일부 문구가 서로 다르면 다른 파일로 인식하기 때문에 파일을 변경 사항 별로 구분해서 저장할 수 있다.
* **Git**은 **로컬 저장소 \(Local Repository\),** **원격 저장소 \(Remote Repository\)** 두 종류의 저장소로 나뉜다.

### \(2\).  Local Repository

* **로컬 저장소 \(Local Repository\)**는 **내 PC**에 파일이 저장되는 개인 저장소를 말한다.

### \(3\). Remote Repository

* **원격 저장소 \(Remote Repository\)**는 파일이 원격 저장소 전용 서버에서 관리되며 여러 사람이 함께 공유하기 위한 저장소를 말한다.
* 평상시에는 **내 PC**의 **로컬 저장소**에서 작업하다가 작업한 내용을 공개하고 싶을 때 **원격 저장소**에 업로드 한다.

### \(4\). Remote Repository Create

🔎**Github**에서 **gitfth**  라는 이름으로 새로운 원격 저장소를 생성한다.

* git remote add origin https://github.com/peridot2029/gitfth.git
  * 현재 **로컬 저장소\(Local Repository\)** 에 **원격 저장소 \(Remote Repository\)**를 연결시킨다.
  * 메인 되면서 주로 동기화 하는 원격 저장소는 origin 이라는 별칭을 많이 사용한다.
  * **원격 저장소 URL** - https://github.com/peridot2029/gitfth.git
  * **원격 저장소 별칭 -** origin
* git push - u origin master
  * **로컬 저장소**에서 **원격 저장소**에 작업한 내용을 보내는 것을 **push** 라고 한다.
  * **로컬 저장소** 작업 내용을 **origin** 원격 저장소의 **master** 브랜치로 보낸다는 의미이다.
  * **-u** 는 한 번만 쓰면 다음부터는`git push`로 쉽게 업로드 할 수 있게  해주는 역할
* git clone remote add https://github.com/peridot2029/gitfth.git



```bash
# gifth 작업 폴더 생성
$ mkdir gitfth

# .git 폴더 생
$ git init

$ vi f1.txt

$ cat f1.txt
a

$ git add f1.txt

$ git commit -m"1"

# 로컬 저장소에서 원격 저장소를 연결
$ git remote add origin https://github.com/peridot2029/gitfth.git

# origin 원격 저장소가 만들어진 걸 확인
$ git remote
origin

# 원격 저장소 상세 조회
$ git remote -v
origin  https://github.com/peridot2029/gitfth (fetch)
origin  https://github.com/peridot2029/gitfth (push)

# 로컬 저장소의 작업 내용을 원격 저장소에 업로드한다.
$ git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 199 bytes | 199.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/peridot2029/gitfth
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

$ vi f1.txt

$ cat f1.txt
a
b

$ git commit -am"2"
warning: LF will be replaced by CRLF in f1.txt.
The file will have its original line endings in your working directory
[master 1fa844a] 2
 1 file changed, 1 insertion(+)
 
$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 230 bytes | 230.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/peridot2029/gitfth
   db8dc37..1fa844a  master -> master
   
# Desktop 이동
$ cd ..

$ mkdir gitfth2

$ cd gitfth2

$ git clone https://github.com/peridot2029/gitfth.git .
Cloning into '.'...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 6 (delta 0), reused 6 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), 377 bytes | 15.00 KiB/s, done.

# 원격 저장소가 로컬 저장소로 동기화 된 것을 확
$ ls -al
total 17
drwxr-xr-x 1 user 197609 0 10월 15 23:15 ./
drwxr-xr-x 1 user 197609 0 10월 15 23:14 ../
drwxr-xr-x 1 user 197609 0 10월 15 23:15 .git/
-rw-r--r-- 1 user 197609 6 10월 15 23:15 f1.txt

# 원격 저장소와 로컬 저장소 연결 상태와 기본적인 origin 이름 확인한다.
$ git remote -v
origin  https://github.com/peridot2029/gitfth.git (fetch)
origin  https://github.com/peridot2029/gitfth.git (push)
```











