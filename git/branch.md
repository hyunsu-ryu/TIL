# Git branch

- branch의 기능은 프로젝트 진행 시 가지들을 구성하여 작업을 용이하고 편리하게 해준다



## 1. branch 명령어 및 사용어

| 명령어                                                       | 기능                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| `$git remote add origin<URL> ## $git remote add <remote_name> <URL>` | 나의 gitHub 위치를 알려줌 (주소붙여넣기 shift + insert)      |
| `$ push origin master # git push <remote_name> <branch>`     | branch나 master gitbub에 업로드 하기                         |
| `$ git branch`                                               | 현재 branch 들을 알려줌                                      |
| `$ git branch <branch>`                                      | branch를 만듬                                                |
| `$ git branch -d <branch>`                                   | branch를 삭제함                                              |
| `$ git branch -D <branch>`                                   | 바뀐게 있는걸 물어볼 수 있는데 무시하고 삭제                 |
| `$ git switch <branch>`                                      | 해당 branch로 이동                                           |
| `$ git switch -c <branch> == $ git checkout -b <branch>`     | branch를 생성함과 동시에 그 branch로 이동                    |
| `$ git checkout <branch/commit_id>`                          | head를 branch로 이동한다 , commit 부분은 h1 처럼 거쳐간 과거를 들여다 보는 기능 |
| `git merge <branch>` #`(master)있는 영역에서 실행하기`       | master에서 하위 branch를 가져와 병합하는 과정                |
| `re -f <dir/file> # re -rf <dir/file>`                       | 파일을 지운다(지울껀지 다시물어봄),  파일을 지운다 (강제삭제) |
| `git remote -v`                                              | 현재 TIL의 위치 확인 가능                                    |

- remote repo(원격저장소)
- HEAD : 내가 보는 부분!
- fast forward : master가 꽃길을 바로 간다는 뜻
- conflict : 각 branch 에 read.md가 있고 n번째 Line에 내용이 다를 시 생기는 trouble이라고 생각하자
- 자동 merge : branch 간 conflict가 없을때 (commit -m) 해주면 통과
- 수동 merge : branch 간 conflict이 있을때 사용자가 직접 무었으로 할지 결정해야함
- 수동 시(master|merging)  병합상태이고 내가 수동으로 골라주면 된다.

## 2. merge 의 3가지 상황

### 	A. 여러 branch가 아닐경우 기존 branch가 만들어 놓은 꽃길로 가게 된다.		

### 		(FastForwoard = no merge commit)

### 	B. branch1과 branch2가 다르게 갓는데 프로그램이 두개 합칠 수 있다고 생각하면 합쳐		버린다.(auto merge commit) 			

​			-  즉 Automatic merge라고 하며 Vim 화면이 발생하는데 그냥 저장하고 나가면됨

### 	C. 2개의 branch에서 같은 Line 충돌 시 우리한테 제어권을 넘김 우리가 수동(VC)로 결		정해줘야 함(conflict = manual merge commit)

- merge를 할때에는 해당 branch에서 나온 후 master 영역에서 merge 해준다.  그러면 branch 요소는 모두 master 것이 되며 branch의 영역은 더이상 쓸모가 없게 되므로 해당 branch는 지워주면 된다!
- branch의 name은 bugfix/indent 처럼 조금 복잡하게 해도 된다.



## 3. gitHub 업로드 과정 

- Local에서 내용을 작성
- staging 및 commit을 진행한다
- github의 로그인창 오른쪽 위 + 칸에서 repo를 만듦
- Local을 저장소 에 등록
- push origin master를 이용해 등록! 



- github에는 완성되고 합쳐진 master만 넘겨주기 때문에 1개만 올라가고 올리기 전 3개의 branch가 github에 올라가지 않음(올려 줄 순있지만 이 3가지 branch는 비어버린 branch 이다)



## 4. 기타

- Origin 주소는 컴퓨터를 바꾸지 않는이상 한번만 등록하면 됨
- touch pages/new.md 처럼 만들면 cd dir를 이용해 들어가지 않고 바로 md 파일 생성가능함
- merge 한뒤 about , contact  branch는 쓸모없어서 지워도 됨