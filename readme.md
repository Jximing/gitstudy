# test
## test2
# master
# Git安装
[git pro](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git)
## 删除远程分支
- 列出本地分支
     git branch
- 删除本地分支
    git branch -D BranchName其中-D也可以是--delete，如：git branch --delete BranchName
- 删除本地的远程分支
    git branch -r -D origin/BranchName
- 远程删除git服务器上的分支
    git push origin -d BranchName其中-d也可以是--delete，如：git push origin --delete BranchName
## 保存用户名密码
    $ git config credential.helper store