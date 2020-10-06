# 📄 Git - Branch Introduction

## 1. Git - Branch Introduction

### \(1\).  Git - Branch  의 소개

* **Branch**란 독립적으로 어떤 작업을 진행하기 위한 개념이다.
* 필요에 의해 만들어지는 각각의 브랜치는 **다른 브랜치**의 영향을 받지 않기 때문에 여러 작업을 동시에 진행할 수 있게 한다.

![Branch&#xAC00; &#xC5C6;&#xB2E4;&#xBA74; &#xC791;&#xC5C5; &#xBAA8;&#xB450; &#xB2E4; &#xB9C8;&#xCE5C; &#xD6C4;&#xC5D0; &#xB2E4;&#xB978; &#xC791;&#xC5C5;&#xC790;&#xC5D0;&#xAC8C; &#xB118;&#xACA8;&#xC918;&#xC57C; &#xD55C;&#xB2E4;.](../.gitbook/assets/lr-branches-1.png)

![Branch &#xB97C; &#xD65C;&#xC6A9;&#xD55C;&#xB2E4;&#xBA74; &#xD558;&#xB098;&#xC758; &#xC791;&#xC5C5;&#xC744; &#xC5EC;&#xB7EC; &#xC2DC;&#xC810;&#xC5D0;&#xC11C; &#xB2E4;&#xC591;&#xD558;&#xAC8C; &#xD560; &#xC218; &#xC788;&#xB2E4;.](../.gitbook/assets/topic-branches-1.png)

### \(2\). Git - Branch의 종류 

* **Master Branch** 
  * **제품으로 출시될 수 있는 브랜치**
  * 배포 \(release\) 이력을 관리하기 위해 사용한다. 
  * 즉, 배포 가능한 상태만을 관리한다.
* **Develop Branch**
  * **다음 출시 버전을 개발하는 브랜치**
  * 기능을 개발을 위한 브랜치들을 병합하기 위해 사용한다.
  * 즉, 모든 기능이 추가되고 버그가 수정되어 배포 가능한 안적인 상태라면  **develop 브랜치**를 **master 브랜치**에 병합 \(merge\)한다.
  * 평상시에는 **develop 브랜치**를 기반으로 개발한다.
* **Feature branch**
  * **기능을 개발하는 브랜치**
  * **develop 브랜치**에서 새로운 기능에 대한 **feature 브랜치**를 분기한다.
  * 새로운 기능에 대한 작업을 수행한다. 
  * 작업이 끝나면 **develop 브랜치**로 병합한다.
  * 더 이상 필요하지 않은 **feature 브랜치**는 제거한다.
  * 새로운 기능에 대한 **feature 브랜치**를 중앙 원격 저장소 올린다.
* **Release Branch**
  * **다음 출시 버전을 준비하는 브랜치**
  * 배포를 위한 전용 브랜치를 사용함으로써 한 팀이 해당 배포를 준비하는 동안 다른 팀은 다음 배포를 위한 기능을 개발을 계속 할 수 있다.
  * **develop 브랜치**에 배포할 수 있는 수준의 기능이 모이면 또는 정해진 배포 일정이 되면, **release 브랜치**를 분기한다.
  * **release 브랜치**를 만드는 순간 부터 배포 사이클이 시작된다.
  * **release 브랜치**에서는 배포를 위한 **최종적인 버그 수정, 문서 추가**등을 **릴리스**와 직접적으로 관련된 작업을 수행한다.
  * 직접적으로 관련된 작업을 제외하고는 **release 브랜치**에 새로운 기능을 추가로 병합 하지 않는다.
  * **release 브랜치**에서 배포 가능한 상태, 즉 **모든 기능이 정상적으로 동작하는 상태가 되면 master 브랜치에 병합**한다.
  * 배포를 준비하는 동안 **release 브랜치**가 변경되었을 수 있으므로, **배포 완료 후  develop 브랜치도병합**한다.
  * 이때, **다음 번 배포 \(release\)를 위한 개발 작업은 develop 브랜치**에서 계속 진행해 나간다.
* **Hotfix Branch**
  * **출시 버전에서 발생한 버그를 수정 하는 브랜치**
  * 배포한 버전에 긴급하게 수정을 해야 할 필요가 있을 경우에는 **master 브랜치**에서 __**hotfix 브랜치**를 분기한다. 
  * **develop 브랜치**에서 문제가 되는 부분을 수정하여 배포 가능한 버전을 만들기에는 시간이 너무 많이 소요 되고, 안정성을 보장하기도 어려우므로 **바로 배포 가능한 master 브랜치에서 직접 브랜치를 만들어서 필요한 부분만을 수정한 후 다시  master 브랜치에 병합하여 이를 배포**해야 한다.
  * **이때 hoxfit 브랜치만 master 브랜치 에서 바로 딸 수 있다.**

### Reference <a id="reference"></a>

Git Branching Workflows [→\(SITE\)](https://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows)

Git 브랜치의 대한 종류 →[\(SITE\)](https://mylko72.gitbooks.io/git/content/branch/branch_type.html)

## 

##  

