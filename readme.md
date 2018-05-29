# test
## test2
# master
## 删除远程分支
- 列出本地分支
    git branch
- 删除本地分支
    git branch -D BranchName其中-D也可以是--delete，如：git branch --delete BranchName
- 删除本地的远程分支
    git branch -r -D origin/BranchName
- 远程删除git服务器上的分支
    git push origin -d BranchName其中-d也可以是--delete，如：git push origin --delete BranchName