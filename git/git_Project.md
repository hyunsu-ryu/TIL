# git Project

- 강의를 들으면서 2인 1개조로 git에서 branch를 이용한 팀 프로젝트를 실습하였다.
- `add # commit # push` 항상 이 세가지가 주요한것을 잊지말자 
- origin , master 는 git에서 가장 main 이고
- remote, repo 는 github에서 가장 main 영역이라고 이해해두자.

## 1. Project를 위한 기본 설정

- 항상 시작전 팀장은 `git init # touch ignore # README.md` 를 이용해 세팅을 해두자 
- gitbub에서 project(learn_together dirctory)를 생성한 후, 닉네임으로 팀원을 초대한다. 
- 초대받은 팀원은 주소를 복사하고, `git clone '주소'` 를 입력한다.
- 팀원에게도  learn_together 라는 디렉토리가 생성되게 된다. 
- 이때 팀원은 팀장이 `init`을 해두었기 때문에 따로 master화 작업을 할 필요가 없다! (만약 하게 되면 repo 안에 또 repo가 생기는 bad현상 발생)
- 그 후, Visual studio Code 에서 git bash 터미널을 설정(ctrl + `)하고 팀 프로젝트를 진행한다.



## 2. project 진행과 Conflict요소 

- 작업이 시작되면 master가 아닌 각자의 branch를 생성하고 그 평행세계에서 작업을 시작한다.
- 각자 branch에서 작업을 끝낸 후 master로 돌아와 (master)내에서 `git merge branchname` 을 실행한다.
- 그러면 abc.md라는 파일에 작업이 업로드가 된다.
- 하지만 , abc.md 에서 10Line의 사항이 branch 평행 세계에서 다를때 merge 시 Conflict가 발생하게 된다 .
- 이를 방지하기위해 push를 하기전에 `git pull origin master`를 실행하여 변경사항을 확인한다.
- 만약 동시에 push를 하면 늦게 push를 한 팀원이 10 Line의 수정을 직접 하게되며 이때 팀원간 소통이 필요하다고 생각한다.

### - 즉, 가장 중요한것은 `pull`을 통해 변경사항을 `push` 하기전 파악하는 것이다!!!!



## 3. git ignore

- 프로젝트 진행시 필요없는 파일을 알아서 걸러주는 행위이다.
- `touch .gitignore.txt`로 file을 VSC 에 생성한다. 
- https://www.toptal.com/developers/gitignore 에 접속하여 내가 쓰는 언어를 선택하고  보이는 이름모를 파일 명들을 모두 복사한다.
- gitignore 에 복사한후 commit 해주면 작업 진행시 필요 없는 file 형식을 알아서 처리해준다. 