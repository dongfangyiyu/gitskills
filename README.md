# gitskills

# git学习笔记

## 1.`git add`	添加本地库文件到仓库，未提交状态

	git add -A 提交所有变化
	git add -u 提交被修改（modified）和被删除（deleted）文件，不包括新文件（new）
	git add . 提交新文件（new）和被修改（modified）文件，不包括被删除（deleted）文件

## 2.`git commit -m` 一次提交添加的文件们到仓库

## 3.版本修改

	git status 查看仓库状态
	git diff 文件名 查看对比

## 4.时光穿梭

### 4.1 版本回退(上一个版本) `git reset --hard HEAD^`
 
     git reset --hard commit_id 可以回到任意版本（快照）
     git log，git reflog 可查看commit_id提交日志
     git log --graph --pretty=oneline --abbrev-commit 查看分支的提交情况（简略版）
### 4.2 管理修改
 
     cat 文件名 查看文件内容
     git diff 工作区与stage比较
     git diff --cached stage区和仓库分支比较
     git diff HEAD -- 文件名 工作区和仓库分支比较
### 4.3 撤销修改
 
     git checkout -- file 丢弃工作区修改内容
     先 git reset HEAD <file>,丢掉暂存区修改的内容，再git checkout -- file 丢掉工作区修改内容
     提交到版本库未提交到远程库想撤回参考4.1
### 4.4 删除文件与恢复 
 
     4.4.1 rm file 删除工作区的文件 git rm file（删除stage中内容）或者git add file（将删除的行为添加到stage中），
	   然后git commit
     4.4.2 git checkout -- file 恢复工作区误删文件

## 5.远程仓库

 ### 5.1 本地添加远程库
 
     git remote add origin 远程库地址，origin是远程库名字，默认origin
     git push -u origin master,-u是关联本地分支和远程分支，再次push时-u可省略
     第一次使用到问题：Please make sure you have the correct access rightsand the repository exists 或Permission         denied (publickey).这是本地没有权限上传到github账户上，需要配置ssh，将本地的公钥放到GitHub的ssh key 里面。
 ### 5.2 本地克隆远程库
 
     git clone 远程库地址

## 6.分支管理

 ### 6.1 创建分支、合并分支、删除分支
 
     查看分支：git branch
     创建分支：git branch <name>
     切换分支：git checkout <name>
     创建+切换分支：git checkout -b <name>
     合并某分支到当前分支（快速合并）：git merge <name>
     删除分支：git branch -d <name>
     强制删除分支（删除后不可恢复）：git branch -D <name>
 ### 6.2 冲突解决
 
     出现冲突，手动合并，再提交
 ### 6.3 分支管理策略
 
     git merge --no-ff -m <message> <branchname>,禁用快速合并模式并生成commit信息，可在log中看到merge信息
 ### 6.4 Bug分支
 
     储藏未完成任务先解决master分支bug
     git stash 储藏目前分支未完结工作进度
     git stash list 查看所有保存工作进度
     git stash apply 恢复并保存stash内容
     git stash drop 删除stash内容
     git stash pop 恢复并删除stash内容（常用）
     上面的命令也可以再后面加stash_id来对具体某一个stash进行操作
     git stash 命令后，会隐藏当前进度。会回到上次提交的状态
 ### 6.5 多人协作
 
     git fetch origin 刷新远程库分支信息
     git pull 把最新的提交从origin/dev抓取在本地合并，解决冲突，再推送
     第一次git pull需要本地分支dev与远程分支dev建立连接 git branch --set-upstream-to=origin/dev dev

## 7.标签管理

 ### 7.1 创建标签
 
     git tag <tagname> 给最近的一次提交打上标签
     git tag 查看所有标签
     git log --pretty=oneline --abbrev-commit 查看历史提交的commit_id
     git tag <tagname> <commit_id> 给对应的commit_id打上标签
     git show <tagname> 查看标签信息
     git tag -a <tagname> -m <message> <commit_id> 创建带有说明信息的标签
     git tag -d <tagname> 删除标签
 ### 7.2 操作标签
 
     git push origin <tagname> 推送具体标签
     git push origin tags 推送所有没有被推送过的标签
     git push origin :refs/tags/<tagname> 删除远程库标签

## 8.补充

	git remote show 展示远程库的名字
	git show 展示本地库信息
	git branch -m newname 将本地所有分支赋予新名字
	git branch -m oldname newname 指定要重命名分支名字
	git remote rm origin 在本地仓库删除远程库
	git remote add origin 远程库地址 添加远程库

























