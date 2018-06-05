# Git安装
[git pro](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git)
# 保存用户名密码
    $ git config credential.helper store 
# 常用命令
- 检查空白错误<br>
$ git diff  --check
- 创建并切换分支<br>
$ git branch branchname(创建分支)<br>$ git checkout branchname(切换分支)<br>
$ git checkout  -b branchname(等同于上面两步)
- 列出本地分支
<br>$ git branch
- 删除本地分支
<br>$ git branch -D BranchName其中-D也可以是--delete，如：git branch --delete BranchName
- 删除本地的远程分支
<br>$ git branch -r -D origin/BranchName
- 远程删除git服务器上的分支
<br>$ git push origin -d BranchName其中-d也可以是--delete，如：git push origin --delete BranchName
- 储藏工作(当对文件修改后暂时不想提交又要切换分支时)<br>
$ git stash 将修改的文件储藏<br>
$ git stash list 查看储藏了哪些文件<br>
$ git stash apply --index(0时不用输入)
- 清理工作目录<br>
$ git clean -f -d(只会移除没有忽略的未跟踪文件 想要清除所有的可以给 clean 命令增加一个 -x 选项)
- 修改最后一次提交<br>
$ git commit --amend 提交后想添加或修改文件，先运行git add再运行git commit --amend
- 从每一个提交移除一个文件<br>
$ git filter-branch --tree-filter 'rm -f filename' HEAD (错误的提交了某个文件时使用)

# git理解 
     push自己的代码前一定要先pull，因为git要求在本地合并文件。你在push时如果别人已经push了一个版本上去你的版本就不是最新的，所以需要先pull先获取最新的版本，再push。

# git提交代码流程
- 查看修改了哪些文件<br>
$ git status
- 添加修改的文件至暂存区<br>
$ git add . (添加所以文件)<br>
$ git add filename (添加单个文件)<br>
$ git add -i (交互式暂存)<br>
- 提交文件至本地仓库<br>
$ git commit -m ""
- 拉取远程仓库文件<br>
$ git pull
- 推送本地文件至远程仓库<br>
$ git pull orign master