# 📄 Git - SSH

## 1. Git -SSH

### \(1\). Git - SSH Key 란 ?

* **SSH  Key** 를 생성하는 목적은 **Git**은 원격 저장소에 **push** 또는 **pull**  를 할 때 매 번 **패스워드**를 묻게 되는데 이 과정을 **SSH Key** 생성을 통해 생략할 수 있다.
* 이와 같은 방법은 사용자 패스워드 입력 방식보다 높은 수준의 보안을 필요로 할 때 필요하다.
* **SSH** 란 암호화된 원격 접속 프로트콜 이다.
* 즉,  컴퓨터와 컴퓨터가 인터넷 같은 **Public Network**를 통해 서로 통신을 할 때 보안적으로 안전하게 통신 하기 위해 사용하는 접속 프로트콜이다.
* **SSH Key**는 **SSH** 프로토콜 서버에 접속 시 서버 비밀번호 대신 **Key**를 제출하는 방식이다.

### \(2\).  SSH Key 생성

* id\_rsa
  * 개인키, 타인에게 노출 **Private Key** 이다. 
  * 본인 컴퓨터 내부에 저장하게 되어 있으며, 이 **Private Key** 를 통해서 암호화된 메세지를 복호화 할 수 있다.
* id\_rsa.pub
  * **Public Key**, 공개 되어도 비교적 안전한 **Key** 이다.
  * **Public Key**를 통해 메시지를 전송하기 전 암호화를 하게 된다.
  * **Public Key**로는 복호화는 불가능 하다.
* git remote set-url origin git@github.com:peridot2029/gitfth.git
  * 원격 저장소의 연결된 **URL**를 **SSH**로 변경한다.

```bash
# ssh key 만들
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/user/.ssh/id_rsa):
/c/Users/audwo/.ssh/id_rsa already exists.
Overwrite (y/n)? y
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/audwo/.ssh/id_rsa
Your public key has been saved in /c/Users/audwo/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:vbo2G5qTNz++Fvr+EGXMPiMN6ocwytRpUtKTnDRZKR8 audwo@DESKTOP-1EOBK1S
The key's randomart image is:
+---[RSA 3072]----+
|      oo..       |
|     +o+E  o     |
|    . Bo .. =    |
|     + o.o *     |
|    o * S + =    |
|   o + + ..+ o   |
|    o  .+.+.     |
|      oo*+o.     |
|      o++@*+.    |
+----[SHA256]-----+

# /c/Users/user/.ssh 폴더로 이동
$ cd ~/.ssh

# id_rsa - private key, id_rsa.pub - public key 2개 파일 생성된 걸 확
$ ls -al
total 40
drwxr-xr-x 1 user 197609    0  2월 14  2020 ./
drwxr-xr-x 1 user 197609    0 10월 18 17:55 ../
-rw-r--r-- 1 user 197609 2610 10월 18 17:57 id_rsa
-rw-r--r-- 1 user 197609  575 10월 18 17:57 id_rsa.pub

# 생성된 id_rsa.pub 파일 확인하고, git에서 접속해서 공개키(id_rsa.pub) 등록한다.
$ cat id_rsa.pub

# 
$ cd ../Desktop/

$ cd gitfth

$ git pull
remote: Enumerating objects: 8, done.
remote: Counting objects: 100% (8/8), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 6 (delta 0), reused 6 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), 415 bytes | 24.00 KiB/s, done.
From https://github.com/peridot2029/gitfth
   1fa844a..e48878c  master     -> origin/master
Updating 1fa844a..e48878c
Fast-forward
 f1.txt | 2 ++
 1 file changed, 2 insertions(+)

$ git log --oneline
e48878c (HEAD -> master, origin/master, origin/HEAD) 4
1c6f93c 3
1fa844a 2
db8dc37 1

# 이미 세팅된 url을 ssh로 변경한다.
$ git remote set-url origin git@github.com:peridot2029/gitfth.git

$ git remote -v
origin  git@github.com:peridot2029/gitfth.git (fetch)
origin  git@github.com:peridot2029/gitfth.git (push)

$ vi f1.txt

$ cat f1.txt
a
b
c
d
e

$ git commit -am"5"
[master da626a0] 5
 1 file changed, 1 insertion(+)

# push 가 잘되면 ssh가 잘 작동되어서 자동으로 업로드를 한다는 의
$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 235 bytes | 235.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:peridot2029/gitfth.git
   e48878c..da626a0  master -> master
```



