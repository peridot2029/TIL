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

### Reference <a id="reference"></a>

Git Branching - Basic Branching and Merging [→ \(SITE\)](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

