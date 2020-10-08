# 📄 Git - Stash

## 1. Git - Stash

### \(1\). Git - Stash

🔎 **gitfh**  폴더를 다시 **Git** 버전 관리하게끔 **초기화** 시킨 다음에 작

* **Stash**는 **감추다, 숨겨두다** 라는 뜻을 갖고 있는 단어이다.
* 브랜치를 만들어서 작업을 하던 중에, **작업하던 내용을 끝내지 않고 다른 브랜치로 이동해야 될 경우**에 사용한다.
* **Stash**의 기능을 통해서 **작업이 끝나지 않은 작업을 커밋하지 않고, 작업했던 내용을 숨겨**둘 수 있게 된다.



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

# exp 브랜치에서 작업하는 중간에 다시 master 브랜치로 돌아갈 경
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

# stash 목록 확
$ git stash list
stash@{0}: WIP on exp: 192353a 1




```



