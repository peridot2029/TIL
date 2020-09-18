# 📄 Gistory -  Introduction, git add

## 1. Gistory -  Introduction and install

* **Gistory는 Git**에 대한 **내부적인 원리를 분석하기 위한 도구**이다.
* 명령을 내렸을 때,  **Git** 내부에서 어떤 일이 일어나는가 를 분석하면서 **Git**이 어떻게 동작하는가를 스스로 공부하는데 도움주기 위해 고안된 툴이다.

```bash
# window, gistory 설치방
# python 설치 후, cmd 에서 버전 확인
$ python -V
Python 3.8.5

# git bash 관리자 권한으로 실행
$ pip install gistory

# .git 폴더가 있는 저장소로 이동
$ cd Desktop/gitfth/

# .git 폴더로 이동
$ cd .git/

# gistory 실행, port 8805
$ gitsory
```

### \(1\).  git add에 대한 원리

먼저 `git add` 에 대한 원리를 알기 전에 새로운 **gitfth2** 폴더를 만든 다음에 **Git**이 버전 관리하도록 하고 새로운 파일에 대해서 추가를 한다.  **gistory**는 새로운 파일에 대한 생성은 아무런 감지도 않는다.

```bash
$ mkdir gitfth2

$ cd gitfth2/

$ gin init

# 새로운 f1.txt 파일을 생성해도 gistory에는 아무런 변화가 감지되지 않는다.
$ vi f1.txt

$ cat f1.txt
a

$ git add f1.txt
```

`git add` 명령어를 실행한 결과 **gistory**는 상단에 **./index,** .**/objects** 2개가 상단으로 올라와있다. 

* **./objects** 
  *  방금 **add** 한 **f1.txt** 파일과 **내용**이 일치한다.
* **./index** 
  *  **./objects** 폴더 안에 있는 디렉토리와 그 안의 **파일 이름**과 동일하다.

![](../.gitbook/assets/.png%20%285%29.png)

새로운 또 다른 파일을 만들고 `git add`를 하면 **gistory** **./index**에서 각각 파일명과 그 파일에 해당하는 내용을 볼 수 있다.

🤚 여기서 주의할 점은 **f3.txt** 파일은 **f1.txt** 파일의 **내용을 복사**해서 만들었기 때문에 내용 같다. 요약하자면 **Git은 파일이 이름이 달라도 내용이 같으면 같은 객체 \(object\)를  가리킨다.**

```bash
# 새로운 또 다른 파일 f2.txt 파일을 만들고 add 명령어 실행, gistory 확
$ vi f2.txt

$ cat f2.txt
z

$ git add f2.txt

# f1.txt 파일을 f3.txt로 복사
$ cp f1.txt f3.txt

$ git add f3.txt
```

![](../.gitbook/assets/.png%20%288%29.png)



