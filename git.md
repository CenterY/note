## git 常用命令


`廖雪峰 http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000`

`简明指南 http://www.runoob.com/manual/git-guide/`

### git 版本库
1. 要关联一个远程库，使用命令
	
		git remote add origin git@server-name:path/repo-name.git；

	关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容；

	此后，每次本地提交后，只要有必要，就可以使用命令`git push origin master`推送最新修改

2. 查看远程库信息
	
		git remote -v；

	本地新建的分支如果不推送到远程，对其他人就是不可见的；

### git branch

Git鼓励大量使用分支：

1. 查看分支：

		git branch

2. 创建分支：

		git branch <name>

3. 切换分支：

		git checkout <name>

4. 创建+切换分支：

		git checkout -b <name>

5. 合并某分支到当前分支：

		git merge <name>
		// '--no-ff'参数，表示禁用Fast forward 合并后产生合并记录
		git merge --no-ff -m "merge with no-ff" dev

6. 删除分支：

		git branch -d <name>

7. 查看所有包含未合并工作的分支，可以运行 

		git branch --no-merged
	
8. 如果要查看哪些分支已经合并到当前分支，可以运行 

		git branch --merged
		
9. 从本地推送分支，使用`git push origin branch-name` 如果推送失败，先用`git pull`抓取远程	的新提交；
	
		git push origin branch-name 

10.	在本地创建和远程分支对应的分支，使用`git checkout -b branch-name origin/branch-	name`本地和远程分支的名称最好一致；(快捷方式 `git checkout --track origin/branch-	name`)

		git checkout -b branch-name origin/branch-name 

11. 建立本地分支和远程分支的关联，使用`git branch --set-upstream branch-name origin/branch-name`从远程抓取分支，使用`git pull`，如果有冲突，要先处理冲突。

		git branch --set-upstream branch-name origin/branch-name

12. 删除远程分支

		 $ git push origin --delete serverfix 
	
	
##### git tag

1. 查看所有tag

		$ git tag
		
2. 新建tag （git tag <name>）

		$ git tag v1.0
		
3. 后补tag  （git tag <name> commit id）

		$ git tag v0.9 6224937
		
4. 查看tag详情 

		$ git show v0.9
		
5. 创建带有说明的标签，用-a指定标签名，-m指定说明文字

		$ git tag -a v0.1 -m "version 0.1 released" 3628164

6. 删除tag

		$ git tag -d v0.1
		
7. 如果要推送某个标签到远程，使用命令git push origin <tagname>

		$ git push origin v1.0
		
8. 一次性推送全部尚未推送到远程的本地标签

		$ git push origin --tags
		
9. 如果标签已经推送到远程，要删除远程标签就麻烦一点，先从本地删除，然后，从远程删除。删除命令也是push

		$ git tag -d v0.9
		Deleted tag 'v0.9' (was 6224937)
		$ git push origin :refs/tags/v0.9
		To git@github.com:michaelliao/learngit.git
		- [deleted]         v0.9
		
### git log

1. 查看历史记录

		$ git log
		
2. 每条log 显示一行 用`--pretty=oneline`参数

		$ git log --pretty=oneline	
		
3. Git提供了一个命令git reflog用来记录你的每一次命令

		$ git reflog
		
4. 用`git log --graph`命令可以看到分支合并图
		
### 撤销修改

1. 修改后未git add 的文件 使用git checkout -- file可以丢弃工作区的修改

		$ git checkout -- readme.txt 
		
2. 已经add 未 commit的修改

		$ git reset HEAD readme.txt
		
3. 已经commit的修改 回到上一个版本

		$ git reset --hard HEAD^
		
3. 已经commit的修改 回到指定commit id

		$ git reset --hard 3628164
		
### 删除文件

文件删除后如果确实要从版本库中删除该文件，那就用命令`git rm`删掉，并且`git commit`

另一种情况是删错了，因为版本库里还有呢，所以可以很轻松地把误删的文件恢复到最新版本：

	$ git checkout -- test.txt
	
	
#### 修改前一次commit message

		git commit --amend -m "New commit message"