# Git

### 분산 버전 관리 시스템

- 코드의 히스토리(버전)을 관리하는 도구
- 개발되어온 과정 파악 가능
- 이전 버전과의 변경 사항 비교 및 분석

```
분산

ex) 블록체인 
```

- git은 변경사항만을 저장함

- 변경사항만을 저장하므로 용량부담이 적고 속도가 빠르다.

#### GitHub

- Git 기반의 저장소 서비스
- Git Bash - Git 사용에 특화된 명령어 실행기 ( UNIX / Linux 명령어 사용 가능! )
- Git은 명령어를 통해서 사용(명령어: CLI...Command-Line Interface)

### 간단한 Unix/ Linux 명령어

- 현재 위치의 폴더, 파일 목록보기 ls

- 현재 위치 이동하기 cd <path>

  ​                                cd.. 상위 폴더로 이동

  ​								cd ~ 홈 디렉토리로 이동

- 폴더 생성하기 mkdir <name>

- 파일 생성하기 touch <name>

- 파일 삭제하기 rm <name>

- 폴더 삭제하기 rm -r <name>

### Repository

정의: 특정 디렉토리를 버전 광리하는 저장소

- `git init` 로컬 저장소를 생성하는 명령어
- `.git` 디렉토리에 버전관리에 필요한 모든 것이 들어있음

git에서 특정버전으로 남긴다 = " 커밋(Commit)한다 "

커밋은 3가지 영역을 바탕으로 동작

- `Working Directory`  내가 작업하고 있는 실제 디렉토리(폴더) 
- ` Staging Area`  커밋(commit)으로 **남기고 싶은**, 특정버전으로 **관리하고** 싶은 파일이 있는 곳
- `Repository`  커밋들이 저장되는 곳

```
Working Directory는 untracked 상태로 git add 명령어를 통해서 tracked 상태가 되고 Staging Area로 올린다. 이 상태를 staged 상태라고 한다. 

git commit이라는 명령어를 통해 특정 Repository에 저장한다. 이를 committed 상태라고 한다. 

만약 coomit된 파일을 수정을 한다면 modified 상태가 되고 다시 위의 과정을 거친 뒤 새로운 commit을 저장한다.

이렇게 버전 관리를 할 수 있다.
```

`..` 상위 폴더

`.` 현재 폴더

### Git 명령어

`git status` 현재 git으로 관리되고 있는 파일의 상태를 알 수 있게하는 명령어

`git log `	내가 지금까지 남긴 히스토리를 볼 수 있는 명령어

`git add .` 추적 되지 않은 모든 파일과 추적하고 있는 파일 중 수정된 파일 모두를 `Staging Area`로 올리는 명령어

`git commit -m "commit_message"` 커밋 내용을 저장하는 명령어 , **커밋 메세지는 자세하게!!**, 한글로 적어도 됨

`git config --global user.name "user_name"`	

`git config --global user.email"user_email"`	

`git init` 로컬 저장소를 생성하는 명령어

`git diff A B` A B 두 commit 간 차이 보기( A를 기준으로 B를 비교 )

### Remote Repository 와  Local Repository

`git remote add origin {repository address}` 리모트 레포지토리와 로컬 레포지토리를 연결( {}는 적지 않는다)

`git push -u origin master` 깃에게 마스터에 있는 내용을 오리진으로 올린다는 명령어 (여기서 -u는       최초에 push 할 때만 쓰고 그다음 부터는 쓰지 않는다)

`git clone {repository address}` 	remote repo를 local로 복사 (clone한 repository는 remote repository와 연결 되어 있다. 따라서 바로 push 할 수 있다.)

`git clone {repository address} .` 현재 경로에 클론하는 명령어

`git push` 클론된 레포지토리는 git push만 해줘도 잘 올라간다

`git remote remove origin` 기존 레포지토리 remote 제거 명령어

`git pull origin master ` 깃에게 오리진에 있는 마스터 브랜치에서 변경사항을 로컬 레포지토리로 당겨오는 명령어

`git restore --staged {file}` 파일을 스테이징 에어리어에서 이전 변경사항으로 취소시키는 명령어

`git restore {file}` 워킹 디렉토리에 변경사항 취소하는 명령어 ( 주의... 이전 변경사항을 모두 취소해 버리므로 신중히 쓸 것)

`git reset --hard{c_id}` 이전 commit으로 되돌리는 명령어 

`git reset` , `git rebase` 에 대해서 추가 학습 필요!!


**.gitignore** 	
- 깃으로 관리하고 싶지 않은 파일이나 폴더 제외하기
- 레포지토리를 만든 직후 바로 만든다. 수정은 나중에~ (README.md 파일도 동일)



||gitignore commands|
|----|-----|
|data.scv|특정파일 제외|
|secret/|특정폴더 제외|
|*.png|특정 확장자 제외|
|!profile.png|profile.png 파일은 관리</br>profile.png를 제외한 모든 png파일 제외| 
|||


### GitHub Pages

GitHub에서 제공하는 무료 웹 호스팅 서비스

Shared Repository Model : 동일한 저장소를 공유하여 활용하는 방식

### 브랜치 (Branch)  


​	특정 커밋을 가리키는 포인터

​	브랜치는 만들어야하나? 라는 고민이 들 때 무조건 만드는 것을 추천!

||**Branch basic commnds**|
|-------------|-----------|
|브랜치 생성 | (master)$ git branch {branch name}|
|브랜치 이동 | (master)$ git checkout {branch name}|
|브랜치 생성</br>및 이동 | (master)$ git checkout -b {branch name}|
|브랜치 목록 | (master)$ git branch|
|브랜치 삭제 | (master)$ git branch -d {branch name}|
|||

**Branch merge**

각 브랜치에서 작업을 한 이후 이력을 합치기 위해서는 일반적으로 merge 명령어를 사용한다

병합을 진행할 때, 만약 서로 다른 이력(commit)에서 동일한 파일을 수정한 경우 충돌이 발생 할 수 있다

이 경우 직접 수정을 진행한다

충돌이 발생한 것은 오류가 아니라 이력이 변경되는 과정에서 발생할 수 있는 것이다.

**Branch merge - fast - forword**

​	기존 master 브랜치에 변경사항이 없어 단순히 앞으로 이동

1. featuer-a branch로 이동 후 commit
2. master 별도 변경 없음
3. git merge feature-a
4. master branch로 병합

**Branch merge (merge commit case)**

​	기존 master 브랜치에 변경사항이 있어 병합 커밋 발생

1. featuer-a branch로 이동 후 commit
2. master 변경 사항 있음
3. maste branch와 featuer-a branch의 내용이 충돌, 직접 수정 후... 
4. master branch commit 
5. master branch로 병합

`git log --graph`	그래프 보기 

`git log --graph --online` 간단한 그래프 보기

협업의 시작 Pull Request

Git Flow 

git을 활용하여 협업하는 흐름으로 브랜치를 활용하는 전략

| | **Git Flow** | |
|--|--|--|
|**branch**|주요특징|예시|
|**Master</br>(main)**|  배포 가능한 상태의 코드| 게임클라이언트 라이브 버전**(1.0)**|
|**Develop</br>(main)**|**feature branch**로 나뉘어지거나,</br>발생된 버그 수정 등 개발 진행</br> 개발 이 후 release branch로 갈라짐| 다음패치를 위한 개발**(1.1)** |
|**feature branches</br>(surpporting)**|기능별 개발 브랜치**(topic branch)**</br>기능이 반영되거나 드랍되는 경우 브랜치 삭제|개발시 기능별 예)신규캐릭터 업데이트|
|**release branches</br>(surpporting)**|개발 완료 이후 **QA/Test** 등을 통해 얻어진 다음</br>배포전 **minor bug fix**등 반영|**1.1a, 1.1b...**|
|**Hotfixes</br>(surpporting)**|긴급하게 반영해야하는 **bug fix**</br>**release branch**는 다음 버전을 위한것이라면,</br>**hotfix branch**는 현재 버전을 위한 것|긴급패치를 위한 작업</br>예)버그로 인한 캐릭터 선택불가|
||||

**GitHub Flow**
기본 원칙
1. master branch는 반드시 배포 가능한 상태여야 한다.
2. feature branch는 각 기능의 의도를 알 수 있도록 작성한다.
3. Commit message는 매우 중요하며, 명확하게 작성한다.
4. Pull Request를 통해 협업을 진행한다.
5. 변경사항을 반영하고 싶다면, master branch에 병합한다.

**GitHub Flow Modles(협업)
내(작업자)가 해당 프로젝트 저장소에 직접적인 push 권한이 있는 지 여부에 따라
- Shared Repository Model
- Fork & Pull Model

**Fork & Pull Model**
Repository에 Collaborator가 등록되지 않고,</br>
Pull request를 통한 협업이 가능. 

![fork request](Git.assets/fork.jpg)
