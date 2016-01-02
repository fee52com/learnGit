# learnGit
## git clone url 从web下载到本地
## git commit -r -a "add hello" 提交
## git rm *.bak 删除
## git mv a b 改名
## git add *.c 增加
## git reset HEAD CONTRIBUTING.md 撤销
## git push 本地仓库的修改提交到仓库

 [git官方文档](https://git-scm.com/book/zh/v2)
##remote
 -1. git remote
##标签
 -1. 推送本地某个标签git push origin v0.1
 -2. 推送本地所有标签git push origin --tags
 -3. 在某个标签上创建某个分支 git checkout -b version2 v2.0.0
##别名
`
$ git config --global alias.co checkout 用co检出
$ git config --global alias.br branch 用br建分支
$ git config --global alias.ci commit 用ci提交
$ git config --global alias.st status 用st显示状态
$ git config --global alias.unstage 'reset HEAD --' 用unstage取消暂存
git config --global alias.last 'log -1 HEAD' 用last看最后一次提交
`

