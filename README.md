# learnGit

 参考[git官方文档](https://git-scm.com/book/zh/v2)  

## 常用操作
* git clone url 从web下载到本地
* git commit -r -a "add hello" 提交
* git rm *.bak 删除
* git mv a b 改名
* git add *.c 增加
* git reset HEAD CONTRIBUTING.md 撤销
* git push 本地仓库的修改提交到仓库

 [git官方文档](https://git-scm.com/book/zh/v2)

## remote
 1. git remote

## 标签
 * 推送本地某个标签git push origin v0.1
 * 推送本地所有标签git push origin --tags
 * 在某个标签上创建某个分支 git checkout -b version2 v2.0.0  

## 别名  

	$ git config --global alias.co checkout 用co检出  
	$ git config --global alias.br branch 用br建分支  
	$ git config --global alias.ci commit 用ci提交  
	$ git config --global alias.st status 用st显示状态  
	$ git config --global alias.unstage 'reset HEAD --' 用unstage取消暂存  
	$ git config --global alias.last 'log -1 HEAD' 用last看最后一次提交  

## 分支
	git init 创建master分支
	git branch -vv 查看分支列表  
	git branch testing 创建testing分支
	git checkout testing 切换到testing分支 HEAD随之移动
	以上命令可以合并成git checkout -b iss53	等同于branch和checkout两句一起使用
	git checkout master 切换到master分支 HEAD随之移动
	git log --oneline --decorate --graph --all 查看分支分叉情况
	git branch --merged 查看merge到当前分支的  
	git branch --no-merged 查看未merge的分支  

### 分支的应用场景:    
	git checkout -b iss53  创建一个分支  
	git commit -a -m 'added a new footer [issue 53]'  提交点东西  
	git checkout master  切换到master分支  
	git checkout -b hotfix1   创建另一个hotfix1分支  
	git commit -a -m 'fixed the broken email address[hosfix1]'  提交点东西  
	git checkout master 切换到master   
	git merge hotfix	合并到master   
	git branch -d hotfix1 删除此分支  
	同样可以合并iss53分支到master  
	如果合并时发生冲突手工编辑冲突文件后再commit  
### 协作
	如果git push失败(别人已经提交内容)
	git fetch origin 获取服务器最新内容  
	git merge origin/master 本地合并  
	git push origin master	推送到服务器  
### 本地分支与远程分支
	git push origin serverfix 让远程分支切换到serverfix，别人
	git fetch origin 在本地生成一个远程分支 origin/serverfix，指向服务器的serverfix 分支的引用  
	可以用git merge origin/serverfix 合并到本地分支
	git clone跟踪的是master分支 而 git checkout -b [branch] [remotename]/[branch] 可以跟踪指定分支 如果加-u则是跟踪其上游分支
	git push origin --delete serverfix 删除服务器上的serverfix分支(可恢复)
	git pull 相当于git getch(并不合并) 与 get merge 的组合

### 变基
	git checkout experiment  
	git rebase master 变基,自动找到共同祖先，并将基底指向较近的并且和experiment修改无关的  
	git checkout master   
	git merge experiment  
	更复杂的变基	git rebase master server client(后两个是不同分支)之后再checkoout master 并merge client
