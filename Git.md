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

`git push -u origin master` 깃에게 마스터에 있는 내용을 오리진으로 올린다는 명령어 (여기서 -u는 최초에 push 할 때만 쓰고 그다음 부터는 쓰지 않는다)

`git clone {repository address}` 	remote repo를 local로 복사 (clone한 repository는 remote repository와 연결 되어 있다. 따라서 바로 push 할 수 있다.)

`git push origin master`

`git remote remove origin` 기존 레포지토리 remote 제거 명령어