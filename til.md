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
