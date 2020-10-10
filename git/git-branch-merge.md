# 📄 Git - Branch Merge

## 1. Git - Branch Merge

### \(1\).  Git - Branch 병합

🔎 **gitfh**  작업 공간에서 **master 브랜치**, **exp 브랜치** **2개의 브랜치**를 **병합\(merge\)**하는 작업

* **Merge** 란 작업을 분기해서 각자의 작업을 이어가다가, **현재 브랜치**에서 **다른 대상의 브랜치의 내용을 합치는 것을 병합\(Merge\)**이라고 한다.
* git merge &lt;name&gt;
  * **현재 브랜치**에서 **입력한 브랜치**를 **병합**
* git log --branches --decorate --graph --oneline
  * 병합한 다음에 커밋 상태를 확인하면 **새로운 커밋이 만들어지고 자동으로 커밋 메세지를 남긴다.**
  * 병합된 커밋은 **2개를 부모 커밋**을 가진다.  
    * **master 브랜치**에서 작업한 5번 → `7843a37` 
    * **exp 브랜치**에서 작업한 3, 4번 → `12afe1d`, `edd1c65`
    * 모두 가지고 있는 상태를 뜻한다.
  * git branch -d &lt;name&gt;
    * **병합이 끝난 다음 더 이상 필요 없게된 브랜치 삭제**

```bash
# 현재 master 브랜치에서 전체 커밋 로그 간결하게 확인
$ git log --branches --decorate --graph --oneline
* 7843a37 (HEAD -> master) 5
| * 12afe1d (exp) 4
| * edd1c65 3
|/
* 6191eef 2
* 3950edc 1

# exp 브랜치에서 작업한 3, 4번 커밋을 master로 옮기기
$ git merge exp
Merge made by the 'recursive' strategy.
 f1.txt | 1 +
 f2.txt | 1 +
 2 files changed, 2 insertions(+)
 create mode 100644 f2.txt

# 병합한 후 커밋 상태를 확인, 병합된 커밋은 두 개의 부모 커밋을 가진다.
$ git log --branches --decorate --graph --oneline
*   b6e1bef (HEAD -> master) Merge branch 'exp' into master
|\
| * 12afe1d (exp) 4
| * edd1c65 3
* | 7843a37 5
|/
* 6191eef 2
* 3950edc 1

# 파일 목록 확인
$ ls -al
total 23
drwxr-xr-x 1 user 197609 0 10월  6 21:10 ./
drwxr-xr-x 1 user 197609 0 10월  6 14:10 ../
drwxr-xr-x 1 user 197609 0 10월  6 21:11 .git/
-rw-r--r-- 1 user 197609 9 10월  6 21:10 f1.txt
-rw-r--r-- 1 user 197609 3 10월  6 21:10 f2.txt
-rw-r--r-- 1 user 197609 3 10월  6 20:56 f3.txt

# exp 브랜치 이동
$ git checkout exp

# exp 브랜치에서 master 브랜치를 병합
$ git merge master
Updating 12afe1d..b6e1bef
Fast-forward
 f3.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 f3.txt

# 병합을 하게 되면, 2개의 브랜치는 똑같은 최신 커밋을 가지므로 두 브랜치는 현재 똑같은 상태
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

# 병합한 exp 브랜치는 더 이상 필요 없기 때문에 제거
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

### \(2\). Git - Branch를 만들고 병합할 때 크 2가지의 경우

* **fast-foward**
  * **출시한 버전  브랜치** → **master 브랜치**, **출시한 버전 문제를 해결하는 브랜치** → **hotfix 브랜**
  * 출시한 버전에서 **갑작스러운 문제가 발생**할 경우
  * **master 브랜치**에서 바로 **hotfix 브랜치**를 만들어서 **문제를 해결**한다.
  * **문제를 해결**하면 다시  **master 브랜치**로 이동해서  **hotfix 브랜치의** 작업을 **병합**한다.
  * **master 브랜치**가 새로운 커밋을 생성하지 않았을 때
  * 별도의 커밋을 생성하여 병합하는게 아니라, **master 브랜치**가 가리키고 있는 **브랜치의 포인터**를 바꾸기만 한다. 
  * 그런 다음에는 해결한 **hotfix 브랜치**를 **제거**한다.
* **merge commit**
  * **문제에 대한 이슈 브랜치** → **hotfix 브랜치**, **이슈를 작업하는 브랜치** → **iss53 브랜치**
  * 다시 **이슈 작업하는 브랜치**로 돌아와서 처리한 후에는 **커밋을 만든**다.
  * 이슈를 처리했으니 **master 브랜치로 돌아가서 이슈를 병**합한다.
  * 이슈에 대한 병합은 **'recursive' strategy.** 라는 문구가 나온다.
  * 이슈 브랜치가 만들어진 이후에 **master 브랜치에는 새로운 커밋이 생성**되었다. 그러므로 **fast-forward가 되지 않는다.**
  * 이럴 때 **Git** 내부적으로 **master 브랜치와 iss53 브랜치의 공통 조상**을 찾는다.
  * 그 다음에 **'3-way Merge'**라는 방법으로 합친다.
  * **합쳐진 결과는 새로운 커밋**을 만든다.

### \(3\).  Git - Branch 병합 시 충돌 해결

🔎 기존에 있던 exp 브랜치를 지우고 다시 만들어서 작업하기



```bash
# 기존에 있던 exp 브랜치 삭제
$ git branch -d exp
Deleted branch exp (was b5a96a4).

# exp 브랜치 다시 생성
$ git branch exp

$ vi master.txt

$ cat master.txt
a

$ git add master.txt

# master 브랜치에서 master.txt 파일 작업 후 커밋
$ git commit -m"6"

# exp 브랜치 이동
$ git checkout exp
Switched to branch 'exp'

$ vi exp.txt

$ cat exp.txt
a

$ git add exp.txt

# exp 브랜치에서 exp.txt 파일 작업 후 커밋
$ git commit -m"7"


$ git checkout master
Switched to branch 'master'

$ git log --branches --decorate --graph
* commit 5855d6d041881f10b1c41ae1cd4ab3109ff7333f (exp)
| Author: peridot2029 <peridot2029@gmail.com>
| Date:   Sat Oct 10 21:07:38 2020 +0900
|
|     7
|
| * commit 36088cd8f3194a7fd42e4bae1a28d72672018035 (HEAD -> master)
|/  Author: peridot2029 <peridot2029@gmail.com>
|   Date:   Sat Oct 10 21:07:07 2020 +0900
|
|       6
|
*   commit b5a96a4eaf1ac9c23ad78a87d1cdf705a7142587
|\  Merge: 8317d2e eb5ac0a
| | Author: peridot2029 <peridot2029@gmail.com>
| | Date:   Sat Oct 10 21:04:26 2020 +0900
| |
| |     Merge branch 'exp' into master
| |
| * commit eb5ac0a17c7b697aa596f2db1ca0b999dae2a6a7
| | Author: peridot2029 <peridot2029@gmail.com>
| | Date:   Sat Oct 10 21:02:29 2020 +0900
| |
| |     4
| |
| * commit dae1297f38ae68aef6757f2ff49f01067edc0ae0
| | Author: peridot2029 <peridot2029@gmail.com>
| | Date:   Sat Oct 10 21:01:11 2020 +0900
| |
| |     3
| |
* | commit 8317d2e0b15b48356e62f3a3dc68a38c61f2a410
|/  Author: peridot2029 <peridot2029@gmail.com>
|   Date:   Sat Oct 10 21:03:21 2020 +0900
|
|       5
|
* commit a7e31e113348fcc6b1123a2f4200e4cedaf8a3b3
| Author: peridot2029 <peridot2029@gmail.com>
| Date:   Sat Oct 10 21:00:08 2020 +0900
|
|     2
|
* commit 9e142a13378697555c6fab98b40347431060e63a
  Author: peridot2029 <peridot2029@gmail.com>
  Date:   Sat Oct 10 20:59:48 2020 +0900

      1
      
# exp 브랜치 병합
$ git merge exp
Merge made by the 'recursive' strategy.
 exp.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 exp.txt

$ git log --branches --decorate --graph
*   commit e71ce76cb0c0d561973a3ce0cad9ca7ca61a1237 (HEAD -> master)
|\  Merge: 36088cd 5855d6d
| | Author: peridot2029 <peridot2029@gmail.com>
| | Date:   Sat Oct 10 21:08:54 2020 +0900
| |
| |     Merge branch 'exp' into master
| |
| * commit 5855d6d041881f10b1c41ae1cd4ab3109ff7333f (exp)
| | Author: peridot2029 <peridot2029@gmail.com>
| | Date:   Sat Oct 10 21:07:38 2020 +0900
| |
| |     7
| |
* | commit 36088cd8f3194a7fd42e4bae1a28d72672018035
|/  Author: peridot2029 <peridot2029@gmail.com>
|   Date:   Sat Oct 10 21:07:07 2020 +0900
|
|       6
|
*   commit b5a96a4eaf1ac9c23ad78a87d1cdf705a7142587
|\  Merge: 8317d2e eb5ac0a
| | Author: peridot2029 <peridot2029@gmail.com>
| | Date:   Sat Oct 10 21:04:26 2020 +0900
| |
| |     Merge branch 'exp' into master
| |
| * commit eb5ac0a17c7b697aa596f2db1ca0b999dae2a6a7
| | Author: peridot2029 <peridot2029@gmail.com>
| | Date:   Sat Oct 10 21:02:29 2020 +0900
| |
| |     4
| |
| * commit dae1297f38ae68aef6757f2ff49f01067edc0ae0
| | Author: peridot2029 <peridot2029@gmail.com>
| | Date:   Sat Oct 10 21:01:11 2020 +0900
| |
| |     3
| |
* | commit 8317d2e0b15b48356e62f3a3dc68a38c61f2a410
|/  Author: peridot2029 <peridot2029@gmail.com>
|   Date:   Sat Oct 10 21:03:21 2020 +0900
|
|       5
|
* commit a7e31e113348fcc6b1123a2f4200e4cedaf8a3b3
| Author: peridot2029 <peridot2029@gmail.com>
| Date:   Sat Oct 10 21:00:08 2020 +0900
|
|     2
|
* commit 9e142a13378697555c6fab98b40347431060e63a
  Author: peridot2029 <peridot2029@gmail.com>
  Date:   Sat Oct 10 20:59:48 2020 +0900

      1

# exp 브랜치를 병합하면 master 브랜치에도 exp.txt 파일을 가진다.
$ ls -al
total 25
drwxr-xr-x 1 user 197609 0 10월 10 21:08 ./
drwxr-xr-x 1 user 197609 0 10월  8 21:41 ../
drwxr-xr-x 1 user 197609 0 10월 10 21:08 .git/
-rw-r--r-- 1 user 197609 3 10월 10 21:08 exp.txt
-rw-r--r-- 1 user 197609 9 10월 10 21:04 f1.txt
-rw-r--r-- 1 user 197609 3 10월 10 21:04 f2.txt
-rw-r--r-- 1 user 197609 3 10월 10 21:05 f3.txt
-rw-r--r-- 1 user 197609 3 10월 10 21:07 master.txt

# exp 브랜치 이동
$ git checkout exp
Switched to branch 'exp'

$ vi common.txt

$ cat common.txt
function a(){
}

$ git add common.txt

# exp 브랜치에서 common.txt 파일 작업 후 커밋
$ git commit -m"8"
[exp 3a27e5d] 8
 1 file changed, 1 insertion(+)
 create mode 100644 common.txt

# master 브랜치 이동
$ git checkout master
Switched to branch 'master'

# exp 브랜치 병합
$ git merge exp
Merge made by the 'recursive' strategy.
 common.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 common.txt

# master, exp 2개의 브랜치가 공통으로 common.txt 파일을 가지고 있다.
$ ls -al
total 26
drwxr-xr-x 1 user 197609 0 10월 10 21:22 ./
drwxr-xr-x 1 user 197609 0 10월  8 21:41 ../
drwxr-xr-x 1 user 197609 0 10월 10 21:22 .git/
-rw-r--r-- 1 user 197609 3 10월 10 21:22 common.txt
-rw-r--r-- 1 user 197609 3 10월 10 21:08 exp.txt
-rw-r--r-- 1 user 197609 9 10월 10 21:04 f1.txt
-rw-r--r-- 1 user 197609 3 10월 10 21:04 f2.txt
-rw-r--r-- 1 user 197609 3 10월 10 21:05 f3.txt
-rw-r--r-- 1 user 197609 3 10월 10 21:22 master.txt

$ vi common.txt

$ cat common.txt
function a(){
}
function b(){
}

$ git commit -am"9"
[master 0264498] 9
 1 file changed, 1 insertion(+), 1 deletion(-)

$ git checkout exp
Switched to branch 'exp'

$ vi common.txt

$ cat common.txt
function a(){
}
function c(){
}

$ git commit -am"10"
[exp 62aeeae] 10
 1 file changed, 2 insertions(+), 1 deletion(-)

$ git checkout master
Switched to branch 'master'

# 브랜치를 병합할 때, 같은 파일이여도 수정하는 위치가 다르면 자동으로 병합한다. 
$ git merge exp
Auto-merging common.txt
Merge made by the 'recursive' strategy.
 common.txt | 2 ++
 1 file changed, 2 insertions(+)

$ cat common.txt
function b(){
}
function a(){
}
function c(){
}

$ git checkout exp
Switched to branch 'exp'

$ cat common.txt
function a(){
}
function c(){
}

$ git merge master
Updating a6f3888..ec1c56f
Fast-forward
 common.txt | 2 ++
 exp.txt    | 1 +
 master.txt | 1 +
 3 files changed, 4 insertions(+)
 create mode 100644 exp.txt
 create mode 100644 master.txt

$ cat common.txt
function b(){
}
function a(){
}
function c(){
}

$ git checkout master
Switched to branch 'master'

$ cat common.txt
function b(){
}
function a(master){
}
function c(){
}

$ git commit -am"11"
[master b0184f2] 11
 1 file changed, 2 insertions(+), 2 deletions(-)

$ git checkout exp
Switched to branch 'exp'

$ cat common.txt
function b(){
}
function a(exp){
}
function c(){
}

$ git commit -am"12"
[exp d7ef5cf] 12
 1 file changed, 2 insertions(+), 2 deletions(-)

$ git checkout master
Switched to branch 'master'

$ git merge exp
Auto-merging common.txt
CONFLICT (content): Merge conflict in common.txt
Automatic merge failed; fix conflicts and then commit the result.

$ git status
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   common.txt

# <<< HEAD ~ ==== - 현재 체크아웃한 브랜치의 수정사항
# >>> exp - exp 브랜치의 내용
$ cat common.txt
function b(){
}
<<<<<<< HEAD
function a(master){
=======
function a(exp){
>>>>>>> exp
}
function c(){
}

# 병합에 실패하므로 직접 파일의 내용을 수정
$ vi common.txt

$ cat common.txt
function b(){
}
function a(master,exp){
}
function c(){
}

$ git add common.txt

$ git status
On branch master
All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Changes to be committed:
        modified:   common.txt

$ git commit

$ git log --oneline
74a3d0c (HEAD -> master) Merge branch 'exp' into master
d7ef5cf (exp) 12
b0184f2 11
ec1c56f Merge branch 'exp' into master
a6f3888 10
a14dab1 9
7b38c1b Merge branch 'exp' into master
9b5cc0c 8
97c472a Merge branch 'exp' into master
edd9bcd 7
6315ec3 6
2ae1b16 Merge branch 'exp' into master
eb66d36 5
173651b 4
9cc0572 3
97017c5 2
6168b10 1
```





### Reference <a id="reference"></a>

Git Branching - Basic Branching and Merging [→ \(SITE\)](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

