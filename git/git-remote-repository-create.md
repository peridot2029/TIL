# 📄 Git - Remote Repository Create

## 1. Git - Remote Repository Create

### \(1\). Git 원격 저장소 생성

🔎Github에서 gitfth  라는 이름으로 새로운 원격 저장소를 생성한다.

* git remote add origin https://github.com/peridot2029/gitfth.git
  * 현재 로컬 저장소\(Local Repository\) 에 원격 저장소 \(Remote Repository\)를 연결시킨다.
  * 메인 되면서 주로 동기화 하는 원격 저장소는 origin 이라는 별칭을 많이 사용한다.
  * 원격 저장소 URL - https://github.com/peridot2029/gitfth.git
  * 원격 저장소 별 - origin
* git push - u origin master
  * 로컬 저장소에서 원격 저장소에 작업한 내용을 보내는 것을 push 라고 한다.
  * 로컬 저장소 작업 내용을 origin 원격 저장소의 master 브랜치로 보낸다는 의미이다.
  * -u 는 한 번만 쓰면 다음부터는 git push로 쉽게 업로드 할 수 있게  해주는 역할
* git clone remote add https://github.com/peridot2029/gitfth.git

```bash
# gifth 작업 폴더 생성
$ mkdir gitfth

# git 버전 관리 시
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

