# 📄 Gistory - git status

## 1. Gitstory - git status

### \(1\). git status의 원리

* **index** 파일에 **status**의 명령이 어떻게 동작하는 지 원리에 대한 정리
* **index** 파일과 **최신 커밋 파일 \(tree\)**의 비교를 통해서 `git status`가 커밋할게 있는지, 없는 지 여부를 결정한다.
  * 만약 두 내용이 일치한다면 `git status` 에서 커밋할게 없다고 판단한다.
* **gitfth2** 폴더에서 **f2.txt** 파일을 내용을 변경 후`git status` 명령을 해서 파일이 수정된 것을 확인 할 수 있다.
  * **Git**은 **index** 파일에 적혀 있는 **f2.txt** 의 내용의 값과 실제 **f2.txt**의 내용이 다르면 해당 **파일이 수정되었다고 감지**한다.
* 변경된 파일을 `git add f2.txt` 하고, `git status` 명령을 하면, **Gistory** 에서  **index**의 **f2.txt** 파일 내용을 확인하면 수정된 파일 내용을 확인 할 수 있다.
* **Git**은 **index**의 내용과 **최신 커밋의 tree**가 가리키고 있는 **f2.txt**의 내용이 다르다면, 현재 **f2.txt**는 **index**에 **add** 되어 **커밋 대기 상태**가 된 것을 확인할 수 있다.

```bash
# 현재 상태 조회를 하면 commit 할 게 없다고 나온다.
$ git status
On branch master
nothing to commit, working tree clean

# f2.txt 파일 내용을 변경
$ vi f2.txt

$ cat f2.txt
x
y
z

# f2.txt 파일 내용 변경 후 → git status으로 파일이 수정된 것을 확인
# "changes not staged for commit" - 수정만 하고, 커밋에 대상에 포함하지 않는다.
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f2.txt

no changes added to commit (use "git add" and/or "git commit -a")


# 변경된 f2.txt 파일 git add
$ git add f2.txt

# f2.txt 파일 git add → git status으로 index 파일 내용과 현재 파일 내용이 일치한다.
# "changes to be committed" - 커밋에 대상, 커밋 대기 상
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   f2.txt


```





