# Git 써보기

## repository와 commit

### 1. 레포지토리(repository)

 : **커밋이 저장되는 곳**

프로젝트 디렉토리의 각 버전이 담기는 저장소

> .git 디렉토리(숨겨진 디렉토리)이다.

### 2. 커밋(commit)

: 프로젝트 디렉토리의 특정 모습을 **하나의 버전으로 남기는 행위 & 결과물**



## Git이 보는 파일의 4가지 상태

### Untracked 상태

> '추적되지 않고 있는'이라는 뜻이다

=> 파일이 Git에 의해서 그 변동사항이 전혀 추적되고 있지 않는 상태를 뜻

### Tracked 상태

=> 파일이 Git에 의해 그 변동사항이 추적되고 있는 상태

> 이 상태는 특성에 따라 3가지 나뉠 수 있다

#### Staged 상태

새로 생성한 파일에 내용을 쓰고 git add를 해주거나 한 번이라도 커밋에 포함됐었던 파일이라도 내용을 수정하고 git add를 해주면 이 상태

#### Unmodified 상태

현재 파일의 내용이 최신 커밋의 모습과 비교했을 때 전혀 바뀐 게 없는 상태면 그 파일은 Unmodified(수정되지 않은, 변한 게 없는) 상태

#### Modified 상태

최신 커밋의 모습과 비교했을 때 조금이라도 바뀐 내용이 있는 상태면 그 파일은 Modified(수정된) 상태



## Git 정리

#### git init 

: 현재 디렉토리를 Git이 관리하는 프로젝트 디렉토리(=working directory)로 설정하고 그 안에 레포지토리(.git 디렉토리) 생성

#### git config user.name 'codeit'

: 현재 사용자의 아이디를 'codeit'으로 설정(커밋할 때 필요한 정보)

#### git config user.email 'teacher@codeit.kr

: 현재 사용자의 이메일 주소를 'teacher@codeit.kr'로 설정(커밋할 때 필요한 정보)

#### git add [파일 이름]

: 수정사항이 있는 특정 파일을 staging area에 올리기

#### git add [디렉토리명]

: 해당 디렉토리 내에서 수정사항이 있는 모든 파일들을 staging area에 올리기 

#### git add .

: working directory 내의 수정사항이 있는 모든 파일들을 staging area에 올리기

#### git reset [파일 이름]

: staging area에 올렸던 파일 다시 내리기

### git status

: Git이 현재 인식하고 있는 프로젝트 관련 내용들 출력(문제 상황이 발생했을 때 현재 상태를 파악하기 위해 활용하면 좋음) 

#### git commit -m "커밋 메시지"

: 현재 staging area에 있는 것들 커밋으로 남기기

#### git help [커맨드 이름]

: 사용법이 궁금한 Git 커맨드의 공식 메뉴얼 내용 출력