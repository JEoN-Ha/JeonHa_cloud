# 문서를 읽기 전(README)

- 이 문서의 저작권은 '팽대원(FoRA)'에게 있음.
- 중요하다고 생각되는 단어 및 문장은 ***강조 효과***를 달았음.
- 추가적인 설명은 다음과 같이 회색으로 각주 효과를 달았음.

> 각주효과, 각주효과, 각주효과

# Git

#### git status

현재 파일 상태 보여주기

#### git init

storage 만들기

#### git add "a.c" / git add .

파일을 staging 추가(add . 을 하면 전체 파일 추가)

#### git remote add < remote > < URL >

ex) git remote add origin https://github.com/fora22/cloud.git

`origin`은 remote 변수로서 URL과 연결해주는 별명이라고 생각하면 편하다.

#### git push -u < remote > < master >

로컬 저장소에서 원격 저장소로 push 할 때 사용한다.

> 만약 다음과 같은 error 가 뜬다면 이렇게 해주어야 한다.
>
> ```tex
> error : failed to push some refs to https://github.com/fora22/cloud.git
> ```
>
> - push 전에 pull 해주기
>
> `refusing to merge unrelated histories` 문구가 뜨면서 진행되지 않는다면 다음 명령어를 사용한다.
>
> ```tex
>git pull < remote > < branch > --allow-unrelated-histories
> ```
>
> `--allow-unrelated-histories` 는 이미 존재하는 두 프로젝트의 기록(history)을 저장하는 드문 상황에서 사용된다고 한다. 즉, git에서는 서로 관련 기록이 없는 이질적인 두 프로젝트를 병합할 때 기본적으로 거부하는데, 이것을 허용해주는 것이다.

#### git branch

branch 상황 확인, `commit` 까지 하고 branch 만들것

#### git checkout -b < branch >

branch를 만들고, 만든 branch로 이동함

#### git checkout < branch >

branch로 이동

#### git merge < branch >

< branch > 와 < master >를 합친다.(내가 master branch 라면)

#### git log

commit 주소 보기



## git 이외의 window console 명령어

#### md < name >

< name > directory 를 만든다.

#### cd < name > 

< name > directory 로 이동한다.

#### notepad < file >

ex) notepad a.c  // c 확장자를 가진 메모장 파일을 만든다.



