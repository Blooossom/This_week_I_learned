# This_Week_I_Learned


## INDEX

1. Wednesday

> - Git&Shell_Command
> - Git_Process
> - Gib_Branch


2. Thursday
> - Git_Flow
> - Github_Blog


3. Friday
> - Revert
> - How_to_Collaborate_with_teammate


## Wednesday

1. Git&Shell_Command
- mkdir {name} = make directory
- touch {name} = create file
- mv {file} {folder} = move
- rm {file} = remove
- cp {file} = copy
- pwd = Print Working Directory
- ls = list up
- cd {directory/..} = change directory

2. Vim_Mode&Command
### Vim Mode
- Normal_mode : press esc on any mode
- Insert_mode : press i on normal mode
- Visual_mode : press v on normal mode
- Command_mode : press : on normal mode


### Vim Command
- h j k l : arrow keys
- y : yank
- dd : delete
- p : paste
- a : append
- u : undo

3. Git_Process
- Add : Working directory to stage
- Commit : Stage to local repo
- push : Local repo to remote repo

4. Git_Command
- git add : add function
- git commit : commit function
- git push origin {}: push funtion
- git status : check git status
- git config --list : check git list

5. Git_ignore
- Can ignore some features of file
- use touch command, make .gitignore
- using vim, add some feature in .gitignore

6. Git_Branch
- If commit meaned the time, Branch mean the space.
- git branch : check the branch on git directory now
- git branch {directory_name} : make new branch
- git switch {branch_name} : move to branch to work
- git branch -d {branch_name} : delete branch
- git merge {branch_name} : merge other branch(it must use on main branch)
- Merge_Conflict




## Thursday

1. Branching_Models
## Gitflow
- (hotfix)-Main(master)-(release)-develop-(feautre)
- 일반적으로 Main Branch에서 주 작업을 진행하지는 않는다.
- 주로 Develop Branch에서 Feature Branch를 따로 생성하여 작업한 후 반영
- 완성 후 Develop에서 다시 Release로 이동하여 최종 Test를 거쳐 Main의 버전업이 되는 흐름
- 다만, 시급하고 중대한 문제가 발생했을 경우에는 Hotfix Branch에서 바로 Main으로 반영된다.

2. Branch_practice
1) 먼저 실습할 repo를 하나 작성하고, git_bash에서 git_clone을 이용하여 당겨오고
2) Main Branch에서 git flow init 커맨드 사용 > 자동으로 develop branch가 작성되고 이동
3) git flow feature start {name} 사용하여 feature로 이동
4) 파일 작성(vim 이용해서) 이후 add-commit
5) git flow feature finish {name} feature 종료
6) 이후 git flow release start {version} > git flow release finish {version}
7) 나오는 여러 창 알맞게 작성
8) 여기까지 마치면 git push -u(upstream) develop
8-1) -u하는 이유는 develop이 기본적으로 깃헙에 없기 때문에 논리적으로 같다고 하기 위해서?
9) 여기까지 하면 V1.0이 올라간 것 이후 반복

3. Github_blog

1. 먼저 npm install -g hexo cli를 통해 hexo를 설치해준다.
2. 설치가 되면 hexo init {blog name}을 실행시켜 blog를 만들고
3. 완료되면 테스트 삼아 포스트를 하나 작성해봄
3-1. 이때 사용하는 코드는 hexo new post "포스트 이름"
4. 이걸 vim으로 읽어서 적당히 수정해주면 되는데, 이때 구분선으로 구분된 부분은 프론트 메타라고 한다
5. 편집을 마치면 hexo generate를 통해 생성해주면 되는데,
5-1. 이유는 hexo는 한 개의 컨텐츠 당 한 개의 페이지가 필요하기 때문에 해줘야 한다고 한다.
6. generate까지 완료하면 deploy를 할 차례인데 그 전에 github에서 유저네임.github.io로 새 repo를 먼저 생성해주고
7. one deployment를 위해 npm install hexo-deployer-git --save 코드를 이용한다
8. 그 뒤 hexo 내에 존재하는 설정파일인 _config.yml을 vim을 이용하여 수정해주는데, 이는 hexo.io에 자세히 설명되있다.
8-1. 다만 중요한 것은 url 맨 뒤에 /를 붙이지 않는 것과 http가 아닌 https를 붙여야 한다는 점이다.
9. 설정까지 마치면 public에 생성된 것을 한 번 비우고 다시 채우는 과정을 거쳐야 한다.
9-1. 이때 사용하는 코드는 hexo clean && hexo generate
10. 거의 마지막 부분으로 hexo deploy를 실행시키면 유저네임.github.io로도 접속이 가능해진다.





## Friday

1. Revert_Everything

### Rename
- 일반적인 Shell Command인 mv를 이용하면 파일명 자체가 바뀌긴 하나, git status로 확인 시 
- 기존 파일이 삭제되고 새로운 파일이 생성된 방식으로 작동한 것을 알 수 있음
- 이는 mv커맨드의 메커니즘적인 문제인 것 같은데, mv 커맨드를 통한 파일명 변경이 위의 방식대로 작동하였기 때문인 듯함.
- 따라서 Git process에서의 rename 과정은 git mv {기존 파일명} {새 파일명}으로 커맨드를 작성해야함
- 예를 들자면 잠깐 가족이 해외여행 간 사이에 내가 알리지 않고 성형을 했다면 가족이 돌아왔을 때 누군지 인지 못하기에
- 가족에게 알리고 성형을 한다면 가족도 둘이 동일한 개체구나 할 것이기 때문임
- 즉 rename과정에서 git에게 해당 process를 진행하면 되는 것
- ++ 이 Process에서 따로 Onstaging이 일어나지 않는 것은 물리량의 변화가 없기 떄문

### Undoing
- git add 커맨드를 실행하기 전 과정임
- 이 작업은 작업 디렉토리에서 최신 Commit으로 돌아가는 프로세스임
- Git Process에서 어떤 파일을 잘못 생성하거나 수정 등의 작업을 했을 때 이를 실행 취소하는 프로세스임
- 다시 말해, 커맨드인 Git restore {file}을 실행하면 현재 작업 중인 디렉토리 하에 있는 모든 변화량이 최신 commit으로 돌아가는 것

### Unstaging 
- 이전 Undoing이 git add 전 과정이었다면, Unstaging은 add후 stage에 올라갔을 때 그를 되돌리는 과정임
- 위 상황에서 만약 git add 기능을 사용해 reverted.md를 스테이지에 올리고 난 후, err가 있는 것을 알았다면
- git reset HEAD {file} 커맨드를 이용해 unstage 가능함
- ++ 혹은 두 파일이 동시에 올라갔을 때 하나를 내리고 싶을 때도 위 커맨드를 사용하여 하나만 내리는 것도 가능
- ++ 이를 방지하기 위해 작업단위를 잘 지키는 것이 중요
- ++ 또한 이 모든 과정은 push가 일어나기 전이기 때문에 push가 일어나면 답이 없음
- ++ 따라서 push는 웬만하면 중간 혹은 최종 결산 때 작동시킬 것

### Reset&Revert
-  Reset 기능이 존재하긴 하지만 대단히 위험한 기능임
- Reset 기능은 강제적이고 강력한 기능이기 때문에 말 그대로 억지로 초기화 시키는 느낌이 가능하기 때문
- 따라서 Reset 기능보다는 Revert 기능을 쓰는 게 좋은데, 사용하기 전 git lg로 commit 로그를 확인
- 원하는 지점으로 되돌리기 위해 작성하는 커맨드는 
> git revert --no-comiit HEAD~3..
> 여기서 HEAD~3은 HEAD부터 3줄까지라는 의미이고 ..은 순차적으로라는 의미를 가짐
> 이를 번역하면 헤드에서부터 3줄까지 순차적으로 되돌리는 커맨드를 의미


2. Collaborate_with_teammate_using_fork,merge,pullrequest
- (1) 팀장 : Organization을 만든다
- (2) Issue Template을 생성
- (3) Clone 후 git flow init 커맨드 실행
- (4) 대상 파일 생성 후 origin develop으로 push
- (5) 팀원 : develop 확인 후 fork
- (6) 나의 repo 방문 전 내 할 일 issue 등록
- (7) fork한 repo clone, git flow init
- (8) git flow feature start {file}

-----WORK------

- (9) git flow feature finish {file}
- (10) push to origin develop
- (11) Open Pull Request
- (12) 팀장 : code review 후 Approve/Comment/Change request
- (13) 팀원 : 추가 작업 후 origin develop으로 push
- (14) merge conflict가 있다면 조직의 develop local로 pull하여 conflict 해결 후 add, commit, push
- (15) 팀장 : Merge pull request
- 여기까지 마무리 되었으면 Release process에 들어감
