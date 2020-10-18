# 📄 Git - Syncing

## 1. Git - Syncing

### \(1\).  원격 저장소와 지역 저장소의 동기화

🔎Desktop 에서 git\_home 

* 하나의 원격 저장소를 중심으로 해서 두 개의 지역 저장소가 하나의 원격 저장소를 중심으로 작업을 동기화 하는 방법
* 협업이 가능하게 하며, 작업 환경이 바뀔 때 마다 그에 대한 대비가 가능하다.
* git clone &lt;Remote Repository URL&gt;
  * 원격 저장소를 복제하여 다른 곳에서 작업을 할 수 있는 명령어 이다.



```bash
$ git clone https://github.com/peridot2029/gitfth.git git_home
Cloning into 'git_home'...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 6 (delta 0), reused 6 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), 377 bytes | 17.00 KiB/s, done.


$ cd git_home/

$ git log --oneline
1fa844a (origin/master, origin/HEAD) 2
db8dc37 1

$ vi f1.txt

$ cat f1.txt
a
b
c

$ git commit -am"3"
[master 1c6f93c] 3
 1 file changed, 1 insertion(+)

$ git log --oneline
1c6f93c (HEAD -> master) 3
1fa844a (origin/master, origin/HEAD) 2
db8dc37 1

$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 232 bytes | 232.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/peridot2029/gitfth.git
   1fa844a..1c6f93c  master -> master
   
$ git pull
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 215 bytes | 14.00 KiB/s, done.
From https://github.com/peridot2029/gitfth
   1c6f93c..e48878c  master     -> origin/master
Updating 1c6f93c..e48878c
Fast-forward
 f1.txt | 1 +
 1 file changed, 1 insertion(+)
```

🔎Desktop 에서 git\_office

```bash

$ git clone https://github.com/peridot2029/gitfth.git git_office
Cloning into 'git_office'...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 6 (delta 0), reused 6 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), 377 bytes | 14.00 KiB/s, done.

$ cd git_office/

# 원격 저장소에 있는 내용을 그대로 현재 로컬 저장소에 가져온다.
$ git pull
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 212 bytes | 11.00 KiB/s, done.
From https://github.com/peridot2029/gitfth
   1fa844a..1c6f93c  master     -> origin/master
Updating 1fa844a..1c6f93c
Fast-forward
 f1.txt | 1 +
 1 file changed, 1 insertion(+)
 
 $ git log --oneline
1c6f93c (HEAD -> master, origin/master, origin/HEAD) 3
1fa844a 2
db8dc37 1

$ vi f1.txt

$ cat f1.txt
a
b
c
d

$ git commit -am"4"
[master e48878c] 4
 1 file changed, 1 insertion(+)

$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 235 bytes | 235.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/peridot2029/gitfth.git
   1c6f93c..e48878c  master -> master
```

