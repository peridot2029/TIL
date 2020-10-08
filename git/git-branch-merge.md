# 📄 Git - Branch Merge

## 1. Git - Branch Merge

### \(1\).  Git - Branch 병합

작업을 분기해서 각자의 작업을 이어가다 병합\(merge\)하는 방법에 대해서 정리



```bash
# 현재 master 브랜치에서 전체 커밋 로그 간결하게 확인
$ git log --branches --decorate --graph --oneline
* 7843a37 (HEAD -> master) 5
| * 12afe1d (exp) 4
| * edd1c65 3
|/
* 6191eef 2
* 3950edc 1

# exp 브랜치에 있는 내용을 master 브랜치로 옮기 
# 밑에 명령을 실행하면 에디터에 "Merge branch 'exp' into master" 병합된 걸 확인  
$ git merge exp
Merge made by the 'recursive' strategy.
 f1.txt | 1 +
 f2.txt | 1 +
 2 files changed, 2 insertions(+)
 create mode 100644 f2.txt
 
# master 브랜치에서 exp 브랜치를 병합한 걸 확인, 커밋 메세지 "Merge branch exp" 확인 
# 해당의 커밋은 두 개의 부모를 가진다.
# master에서 작업한 5번 커밋, exp 에서 작업한 3,4번 커밋을 모두 가지고 있는 상태이다.
$ git log --branches --decorate --graph --oneline
*   b6e1bef (HEAD -> master) Merge branch 'exp' into master
|\
| * 12afe1d (exp) 4
| * edd1c65 3
* | 7843a37 5
|/
* 6191eef 2
* 3950edc 1

# 파일 목록 확
$ ls -al
total 23
drwxr-xr-x 1 user 197609 0 10월  6 21:10 ./
drwxr-xr-x 1 user 197609 0 10월  6 14:10 ../
drwxr-xr-x 1 user 197609 0 10월  6 21:11 .git/
-rw-r--r-- 1 user 197609 9 10월  6 21:10 f1.txt
-rw-r--r-- 1 user 197609 3 10월  6 21:10 f2.txt
-rw-r--r-- 1 user 197609 3 10월  6 20:56 f3.txt

# exp 브랜치 이
$ git checkout exp

# master 브랜치를 exp 브랜치로 가져온다.
$ git merge master
Updating 12afe1d..b6e1bef
Fast-forward
 f3.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 f3.txt

# exp 브랜치는 master 브랜치와 똑같은 커밋을 최신 커밋으로 가진다.
# exp 브랜치는 master 브랜치와 똑같은 상태가 된다.
$ git log --branches --graph --decorate --oneline
*   b6e1bef (HEAD -> exp, master) Merge branch 'exp' into master
|\
| * 12afe1d 4
| * edd1c65 3
* | 7843a37 5
|/
* 6191eef 2
* 3950edc 1

# master 브랜치 이동
$ git checkout master

# 병합한 exp 브랜치는 더 이상 필요 없기 때문에 제거한다.
$ git branch -d exp
Deleted branch exp (was b6e1bef).

# exp 브랜치 제거 후, 로그를 확인하면 exp 브랜치는 사라지고 더 깔끔해진다.
$ git log --branches --graph --decorate --oneline
*   b6e1bef (HEAD -> master) Merge branch 'exp' into master
|\
| * 12afe1d 4
| * edd1c65 3
* | 7843a37 5
|/
* 6191eef 2
* 3950edc 1
```



