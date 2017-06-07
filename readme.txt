git is not a version control system,
git is not a free software
new line to check

git command:
1. git add <filename> //将文件添加到git
2. git commit -m "some logs"  //进行git提交操作，同时提交版本信息
3. git status  //查看当前git状态
4. git diff    //列出不同
5. git log     //列出所有额提交记录
6. git reset --hard HEAD~  //回退到上一个版本
7. git reset --hard <xxxxx>  //回到指定的版本，xxxx为版本的hashcode，不用写全
8. git reflog  //查看本地提交信息
9. git checkout -- <filename> //将工作区的内容撤销
10. git reset HEAD <filename> //将暂存区的内容撤回到工作区
11. git rm <filename> //从版本库中删除文件
12. $ git remote add origin git@github.com:Luke7810/learngit.git // 将本地仓库添加到github上
13. git push -u origin master //将本地仓库第一次推送到远程
14. git push origin master  //以后再次推送的命令，去掉-u
15. git clone git@github.com:Luke7810/gitskills.git  //将远程仓库克隆到本地
16. git branch <dev>  //创建一个dev的分支
17. git checkout <dev> //切换到dev分支上去
18. git checkout -b <dev>  //创建并切换到dev分支上去
19. git branch  //查看分支的情况
20. git merge <dev>  //合并dev分支到当前分支
21. git branch -d <dev>  //删除分支
22. git log --graph --pretty=oneline --abbrev-commit  //以图形的方式显示分支的状态
========Luke dev Update======

========Luke dev add for release 2==========
