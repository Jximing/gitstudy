# Git安装
下载地址:[https://git-scm.com/downloads](https://git-scm.com/downloads)<br>
官方中文教程地址：[https://git-scm.com/book/zh/v2](https://git-scm.com/book/zh/v2)
# 配置 Git
    $ git config –list 查看配置
    $ git config –global 增加配置
    $ git config --global user.name testname
    $ git config --global user.email test@example.com
    $ git config --global gui.encoding utf-8
    $ git config credential.helper store(保存密码) 
#  git基础
每次你提交更新，或在 Git 中保存项目状态时，它主要对当时的全部文件制作一个快照并保存这个快照的索引。<br>
![ ](.\pic\基础.JPG)<br>
Git 有三种状态，你的文件可能处于其中之一：已提交（committed）、已修改（modified）和已暂存（staged）。 已提交表示数据已经安全的保存在本地数据库中。 已修改表示修改了文件，但还没保存到数据库中。 已暂存表示对一个已修改文件的当前版本做了标记，使之包含在下次提交的快照中。由此引入 Git 项目的三个工作区域的概念：Git 仓库、工作目录以及暂存区域。
# git基本操作流程
- 克隆项目<br>
$ git clone 项目地址
- 查看修改了哪些文件<br>
$ git status
- 添加修改的文件至暂存区<br>
$ git add . (添加所以文件)<br>
$ git add filename (添加单个文件)<br>
$ git add -i (交互式暂存)<br>
- 提交文件至本地仓库<br>
$ git commit -m ""
- 拉取远程仓库文件<br>
$ git pull 等同于 $ git fetch + $ git merge
- 推送本地文件至远程仓库<br>
$ git push orign master

# git理解 
     push自己的代码前一定要先pull，因为git要求在本地合并文件。你在push时如果别人已经push了一个版本上去你的版本就不是最新的，所以需要先pull先获取最新的版本，再push。
两个人同时clone了一个仓库进行开发,A在此基础上提后B的仓库看起了就像这样的<br>
![ ](.\pic\1.JPG)<br>
此时B不能直接提交文件，必须将远程分支合并进本地后才能提交，合并后的仓库<br>
![ ](.\pic\1.1.JPG)<br>
提交后B的仓库<br>
![ ](.\pic\2.JPG)<br>
在此期间，A在一个特性分支上工作。她创建了一个称作 issue54 的特性分支并且在那个分支上做了三次提交。 她还没有抓取B的改动，所以她的提交历史看起来像这样：<br>
![ ](.\pic\3.JPG)<br>
从仓库进行抓取后<br>
![ ](.\pic\3.1.JPG)<br>
合并 issue54 和远程分支后<br>
![ ](.\pic\4.JPG)<br>
推送到仓库<br>
![ ](.\pic\6.JPG)<br>
整个工作的流程就是在一个特性分支工作一会儿，当它准备好整合时合并回你的 master 分支。 当想要共享工作时，将其合并回你自己的 master 分支，如果有改动的话然后抓取并合并 origin/master，最终推送到服务器上的 master 分支。<br>
![ ](.\pic\7.JPG)<br>
# 常用命令
- 初始化本地仓库<br>
$ git init 
- 将本地仓库和远程仓库对应起来<br>
$ git remote add origin 远程仓库地址 
- 上传本地库到远程库<br>
$ git push -u origin master 
- 检查空白错误<br>
$ git diff  --check
- 创建并切换分支<br>
$ git branch branchname(创建分支)<br>$ git checkout branchname(切换分支)<br>
$ git checkout  -b branchname(等同于上面两步)
- 创建远程分支
$ git push <br><远程主机名>  <本地分支名>：<远程分支名>
- 查看分支
<br>$ git branch(本地)<br>
 $ git branch -r(远程) <br>
 $ git branch -a(所有)
- 合并分支
<br>$ git merge 
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
- 还原版本<br>
$ git filter-branch --tree-filter 'rm -f filename' HEAD (错误的提交了某个文件时使用)


