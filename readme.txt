git is not a version control system,
git is not a free software
new line to check

======================================================
给自己创建私钥，并将其关联到Github
1. 使用ssh-keygen -t rsa -C "youremail@example.com" 创建自己的私钥
2. 在自己的根目录下的.ssh文件夹下会产生id_rsa和id_rsa.pub两个文件， id_rsa是私钥
3. 登陆GitHub，打开“Account settings”，“SSH Keys”页面
4. 点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容

======================================================
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
12. git remote add origin git@github.com:Luke7810/learngit.git // 将本地仓库添加到github上
13. git push -u origin <master> //将本地仓库第一次推送到远程
14. git push origin <master>  //以后再次推送的命令，去掉-u
15. git clone git@github.com:Luke7810/gitskills.git  //将远程仓库克隆到本地
16. git branch <dev>  //创建一个dev的分支
17. git checkout <dev> //切换到dev分支上去
18. git checkout -b <dev>  //创建并切换到dev分支上去
19. git branch  //查看分支的情况
20. git merge <dev>  //合并dev分支到当前分支
21. git branch -d <dev>  //删除分支
22. git branch -D <dev>  //这是分支强行删除语句，此语句可以删除还没有合并的分支
23. git log --graph --pretty=oneline --abbrev-commit  //以图形的方式显示分支的状态
24. git merge --no-ff -m "some commnt" <dev>   //合并dev分支到当前分支，使用 no Fast-forward模式，这样合并后的历史有分支，能看出来曾经做过合并
25. git stash   //用以保存当前现场，保存后，清理干净工作区现场
26. git stash list  //查看存放区中的状态
27. git stash apply  //从存放区恢复内容到开发区，但是不删除存放区内容
28. git stash drop   //删除存放区内容
29. git stash pop    //从存放区恢复内容到开发区, 同时删除存放区内容
30. git stash apply <stash@{0}>  //存放区可以存放多个内容，使用这个命令可以恢复指定的存放区中的内容
31. git remote   //查看远程仓库信息
===================================================================
32. 团队合作方式
32.01 首先创建一个主项目在远程服务器上。 ex. 项目叫ABC
32.02 在本地clone这个项目  （git clone git@github.com:Luke7010/ABC.git)
32.03 在本地创建这个项目的dev分支  (git checkout -b dev)
32.04 将本地创建的dev分支同步到远程仓库  (git push origin dev:dev)
32.05 使用 git branch -a 可以查看所有本地和远程的分支状况 

32.06 ========== 以上就完成了，git的初始配置，其他成员可以进行follow===========

32.07 这是加入一名新成员， 首先要将远程仓库内容clone下来   （git clone git@github.com:Luke7810/ABC.git）
32.08 因为远程已经存在dev分支，同步这个分支，并创建本地dev分支  (git checkout -b dev origin/dev)
32.09 使用git branch -a 可以查看所有的本地和远程分支情况
32.10 这时，创建本地的自己使用的分支  (git checkout -b Lukedev)
32.11 所有的修改都在本地的个人分支上进行操作
32.12 修改后，在git上进行修改确认  (git add filename)
32.13 进行提交操作，这时所有的提交操作都在本地Lukedev上进行   (git commit -m "log")
32.14 当认为自己修改的差不多时，需要向远程仓库的dev进行提交。
32.15 首先要将本地的的dev分支和远程仓库的dev分支进行同步，因为，在你修改的时候，别人已经修改了dev分支
32.16 切换到自己的dev分支   (git checkout dev)
32.17 同步服务器上的dev分支   (git pull)
32.18 合并Lukedev分支到dev分支   (git merge --no-ff -m "some commnt" Lukedev)
32.19 将本地的dev推送到远程服务器上去   (git push origin dev)

32.20 ========= 在Team要进行push操作时，要进行协调，使得大家进行顺序的push操作 ========

32.21 当Team都已经完成了的push到dev的操作后，就意味着，进行版本release了，由Admin进行操作
32.22 由于大家都已经完成了同步到dev的操作，这时，大家都不在进行push操作了。
32.23 Admin开始从远程仓库同步dev分支, 首先切换到dev分支  (git checkout dev)
32.24 Admin开始同步远程dev分支  (git pull)
32.25 Admin切换到master分支   (git checkout master)
32.26 Admin合并dev分支    (git merge --no-ff -m "some commnt" dev)
32.27 Admin将master分支推送到远程仓库   (git push origin master)
32.28 这时就完成了这次release操作

32.29 完成release操作后，所有开发人员进行master分支和dev分支的同步   (切换分支，git pull)
===================================================================

33. git tag <name>  给某个分支加上一个tag
34. git tag <name> <commit id>  给指定的commit id的分支加上tag
35. git tag 列出所有打过tag的列表
36. git show <name> 列出指定tag(如：v1.0)的详细信息
37. git tag -a <tagname> -m "blablabla..."  设定标签，并增加对这个标签的说明
38. git tag -d <tagname> 删除一个本地标签
39. git push origin <tagname>  推送一个本地标签到远程仓库
40. git push origin --tags  推送所有未推送的本地标签到远程
41. git push origin :refs/tags/<name>  删除远程标签

42. 忽略特殊文件，Java中的class什么的，一般进行忽略，可以增加一个.gitignore文件，这个文件不用自己写，到https://github.com/github/gitignore去下载就行了

43. 增加别名git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"， 以后使用$ git lg就可以查看所有版本信息了。

=================================================
44. 搭建Git Server

44.1 在server上安装git：  sudo apt-get install git
44.2 增加git用户：  sudo adduser git
44.3 收集所有需要登录的用户的公钥，就是他们自己的id_rsa.pub文件，把所有公钥导入到/home/git/.ssh/authorized_keys文件里，一行一个
44.4 初始化Git仓库，先选定一个目录作为Git仓库，假定是/srv/sample.git，在/srv目录下输入命令， sudo git init --bare sample.git
44.5 把owner改为git， sudo chown -R git:git sample.git
44.6 禁用shell登录， 编辑/etc/passwd， 找到类似下面的一行：git:x:1001:1001:,,,:/home/git:/bin/bash 改为 git:x:1001:1001:,,,:/home/git:/usr/bin/git-shell
44.7 现在，可以通过git clone命令克隆远程仓库了，在各自的电脑上运行： git clone git@server:/srv/sample.git
其实没这么简单，在CentOS 上搭建Git还有一些步骤，在百度上找CentOS 搭建Git Server

