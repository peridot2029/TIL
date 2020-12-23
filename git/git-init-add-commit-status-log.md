# 📄 init, add, commit, status, log

### 1. git init

여러 파일을 추적하는 **.git** 폴더가 생긴다. 

* **working directory**  
  *  **.git** 폴더의 상위 폴더를 의미한다. 아래의 예제에서는 **gitfth**를 폴더를 가리킨다.
* **.git**
  *   **working directory**에 존재하는 파일들의 버전 관리를 한다.

```bash
# 바탕화면으로 이동
$ cd Desktop/

# gitfth 프로젝트 폴더 생성
$ mkdir gitfth

# gitfth 프로젝트 폴더 이동
$ cd gitfth/

# .git 폴더 생성 되기 전, gitfth 프로젝트 파일 목록
$ ls -al
total 12
drwxr-xr-x 1 user 197609 0  9월 17 14:21 ./
drwxr-xr-x 1 user 197609 0  9월 17 14:21 ../

# .git이 버전 관리를 시작 하도록, 초기화된 .git 폴더 생성
$ git init
Initialized empty Git repository in C:/Users/user/Desktop/gitfth/.git/

# .git 폴더 생성 후 목
$ ls -al
total 16
drwxr-xr-x 1 user 197609 0  9월 17 14:28 ./
drwxr-xr-x 1 user 197609 0  9월 17 14:21 ../
drwxr-xr-x 1 user 197609 0  9월 17 14:28 .git/

# .git 폴더 만든 후에 아무것도 작업하지 않았으므로 
# working directory에는 commit 할 게 없다고 출력된다.

$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)

```

### 2. git add

Git이 추적하고 있는 수정된 파일이 **working directory**에서 **staging area**에 저장된다.

```bash
# working directory에 f1.txt 파일 생성 및 작업
$ vi f1.txt

# 작업한 f1.txt 파일 내용 출력
$ cat f1.txt
source : 1

# f1.txt 파일을 작업한 다음에 상태를 조회해 보면 추적되지 않는 파일
# (Untracked files)목록을 보여준다.
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        f1.txt

nothing added to commit but untracked files present (use "git add" to track)

# git add 명령어를 실해서 git 추적할 수 있도록 한다.
$ git add f1.txt
warning: LF will be replaced by CRLF in f1.txt.
The file will have its original line endings in your working directory

# git add 명령을 실행 후에 상태를 확인하면, 아까와는 다르게 초록색 문장으로
# new file: f1.txt로 새로운 파일 추가되어 추적을 시작했다는 것을 확인할 수 있다.
# f1.txt는 add 명령만 실행 했기 때문에 staging area에 머물고 있다.
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   f1.txt
```

### 3. git commit

* **commit**은 작업을 마무리 했다는 의미로 버전을 등록한다. 
* 즉, **staing area**에 저장되었던 파일이 **local repository**로 확정된다.

```bash
# git commit 명령어를 실행하면, staing area의 내용을 local repository 저장하고
# 하나의 버전으로 등록한다.
$ git commit -m"1"
[master (root-commit) c5fcfc9] 1
 1 file changed, 1 insertion(+)
 create mode 100644 f1.txt
 
# commit 후 상태를 확인하면, 더 이상 commit 할 게 없다고 출력된다.
$ git status
On branch master
nothing to commit, working tree clean

# commit 메세지를 잘못 입력한 경우에는 --amend 옵션을 다시 커밋 메세지를 수정할 수 있다.
$ git commit --amend -m"first commit"
[master fe872b3] first commit
 Date: Thu Sep 17 15:33:45 2020 +0900
 1 file changed, 1 insertion(+)
 create mode 100644 f1.txt


# git log 명령어를 실행해서 커밋 히스토리를 조회
$ git log
commit fe872b3c1ea53ab0330e1093263ba45ae4ba33d4 (HEAD -> master)
Author: peridot2029 <peridot2029@gmail.com>
Date:   Thu Sep 17 15:33:45 2020 +0900

# working directory에 f2.txt 파일 생성 및 작업
$ vi f2.txt

# 작업한 f2.txt 파일 내용 출력
$ cat f2.txt
source : 2

# f2.txt 파일을 git이 추적할 수 있게끔 add 명령 실행 
$ git add f2.txt

# f2.txt 파일 commit 메세지는"second commit"으로 버전을 등록한다.
$ git commit -m"second commit"
[master 5f2d478] second commit
 1 file changed, 1 insertion(+)
 create mode 100644 f2.txt


# git log 옵션 -p를 실행하면, 각 commit의 diff 결과를 줄 단위로 출력된다.
$ git log -p
commit 5f2d478f207a884ab27ed837632982248d847c40 (HEAD -> master)
Author: peridot2029 <peridot2029@gmail.com>
Date:   Thu Sep 17 15:57:00 2020 +0900

    second commit

diff --git a/f2.txt b/f2.txt
new file mode 100644
index 0000000..2456b16
--- /dev/null
+++ b/f2.txt
@@ -0,0 +1 @@
+source : 2

commit fe872b3c1ea53ab0330e1093263ba45ae4ba33d4
Author: peridot2029 <peridot2029@gmail.com>
Date:   Thu Sep 17 15:33:45 2020 +0900

    first commit

diff --git a/f1.txt b/f1.txt
new file mode 100644
index 0000000..e2eaf76
--- /dev/null
+++ b/f1.txt
@@ -0,0 +1 @@
+source : 1

# git log에서 -p 옵션과 같이 --word-diff를 사용하면 diff를 결과를 단어 단위로
# 출력 되어서 보여준다.

$ git log -p --word-diff
commit 5f2d478f207a884ab27ed837632982248d847c40 (HEAD -> master)
Author: peridot2029 <peridot2029@gmail.com>
Date:   Thu Sep 17 15:57:00 2020 +0900

    second commit

diff --git a/f2.txt b/f2.txt
new file mode 100644
index 0000000..2456b16
--- /dev/null
+++ b/f2.txt
@@ -0,0 +1 @@
{+source : 2+}

commit fe872b3c1ea53ab0330e1093263ba45ae4ba33d4
Author: peridot2029 <peridot2029@gmail.com>
Date:   Thu Sep 17 15:33:45 2020 +0900

    first commit

diff --git a/f1.txt b/f1.txt
new file mode 100644
index 0000000..e2eaf76
--- /dev/null
+++ b/f1.txt
@@ -0,0 +1 @@
{+source : 1+}
```

```bash
# 버전 관리하는 파일을 수정 후, add 하지 않고도 commit 명령어 옵션에 -am를
# 사용해서 add와 동시에 커밋 메세지를 남길 수 있다.

# f1.txt 파일 내용을 임의로 수정 후, -am 옵션을 사용해서 커밋 기록 남기
$ vi f1.txt 

$ cat f1.txt
source : 3
4

$ git commit -am"4"

$ git log --oneline
4a154f6 (HEAD -> master) 4
8dee3bf Revert "2"
083f79d 3
7e7d2cb 2
9297e6f 1
```

### 4. git status

Git에 의해 관리되는 파일들의 상태\(status\)이다.

### 5. git log

지금 까지의 commit 된 기록들이 출력되며, 가장 위에 나오는 내역이 가장 최근 내역임을 알 수 있다.

### Reference <a id="reference"></a>

vi 명령어 정리 [ →\(SITE\)](https://blockdmask.tistory.com/25)

git diff 사용하기 [→\(SITE\)](http://hochulshin.com/git-diff/)





