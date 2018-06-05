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
## 常用命令
- 检查空白错误<br>
$ git diff  --check
- 创建并切换分支<br>
$ git branch branchname(创建分支)<br>$ git checkout branchname(切换分支)<br>
$ git checkout  -b branchname(等同于上面两步)
## git理解 
     push自己的代码前一定要先pull，因为git要求在本地合并文件。你在push时如果别人已经push了一个版本上去你的版本就不是最新的，所以需要先pull先获取最新的版本，再push。

## git提交代码流程
- 查看修改了哪些文件<br>
$ git status
- 添加修改的文件至暂存区<br>
$ git add  . (添加所以文件)<br>
$ git add  filename (添加单个文件)<br>
$ git add  -i (交互式暂存)<br>
