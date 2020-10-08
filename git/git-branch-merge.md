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
 
# master 브랜치에서 exp 브랜치를 병합한 후 로그 그래프 확
$ git log --branches --decorate --graph --oneline
*   b6e1bef (HEAD -> master) Merge branch 'exp' into master
|\
| * 12afe1d (exp) 4
| * edd1c65 3
* | 7843a37 5
|/
* 6191eef 2
* 3950edc 1




```



