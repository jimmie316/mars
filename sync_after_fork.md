git常用命令以及如何与fork别人的仓库保持同步
简单常用命令
1、git status
查看当前仓库是否有文件改动
a:提示
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean时候是没有改动
b:提示有红色就是有改动，可以提交
2、git add .
add .代表添加所有文件到本地仓库
3、git commit -m '注释内容'
提交到仓库，会弹出远程仓库的帐号和密码输入即可
4、git push origin master
推送到远程仓库
5、git pull
从当前仓库拉取到本地仓库
6、git clone 仓库名(英文)
从远程仓库克隆到本地(可以克隆任何仓库)
7、git remote -v
查看当前仓库地址


SHH 模式的仓库地址形如：git@github.com:jimmie316/mars.git
HTTPS 模式的仓库地址形如：https://github.com/jimmie316/mars.git

###fork 别人的项目后，把自己名下 fork 别人的项目 clone 到本地后，如何与作者的项目保持同步,

例如我 fork 了 git@github.com:Tencent/mars.git，该仓库到我的名下为：git@github.com:jimmie316/mars.git

并把 git@github.com:jimmie316/mars.git clone 到本地

想同步作者的修改
1、git remote add marsgroup git@github.com:Tencent/mars.git

marsgroup是关联的原仓库在我本地的名字，可以自定义

2、git fetch --all 就将更新 git remote 中所有的远程 repo 所包含分支的最新 commit-id, 将其记录到 .git/FETCH_HEAD 文件中

3、同步执行：git rebase marsgroup/master

此时本地已经与作者同步了，但是自己 fork 的远程仓库还没与作者同步，需要：git push origin master，提交到自己的仓库即可

###如何让自己的 github 仓库也同步（git@github.com:jimmie316/mars.git）

4、git status 会看到作者有多少次提交

5、需要：git push origin master，HTTPS 模式输入账号和密码，SSH 模式不需要输入，将本地更新后的 push 到远程自己 fork 的仓库即可
