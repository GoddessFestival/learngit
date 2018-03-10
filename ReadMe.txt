HELLO  WORLD

git diff  查看修改



配置ssh
1.在终端输入。

ssh-keygen -t rsa -C "username" (注：username为你git上的用户名)

2.cat  /c/Users/Administrator/.ssh/id_rsa.pub


配置用户名和邮箱
git config -global user.name
git config -global user.email

初始化本地库
git init
git status
git add .       git add filename
git commit -m"提交内容描述"

和远程仓库建立连接
git remote add origin(learngit远程仓库别名) git@github.com:GoddessFestival/learngit.git
learngit ==  url

git remote  查看远程仓库列表

代码提交到远程
	第一次提交
	git push -u origin master   
	以后提交
	git push origin master    git push learngit master

从远程上拉取代码
git pull                git pull learngit  
git fetch               git fetch learngit



克隆远程库
git clone  git@github.com:GoddessFestival/learngit.git


分支创建及合并
git branch dev
git checkout dev        git checkout -b dev   一步完成

   Creating a new branch is quick.（在dev分支上提交）
	
	在dev分支上提交
	git add ReadMe.txt
	git commit -m "branch test"   暂存区
分支的合并
	git checkout master
	git merge dev   把dev分支合并到当前分支（master）

	注意到上面的Fast-forward信息，Git告诉我们，这次合并是“快进模式	”，也就是直接把master指向dev的当前提交，所以合并速度非常快。

删除dev分支
git branch -b dev  



保存工作现场
当前正在dev上进行的工作还没有提交，先把工作现场git stash一下，
然后在master分支上创建issue-101分支
git checkout -b issue-101     去修复bug，
修复后（提交），切换到master分支上合并issue-101分支（并删除），（bug修复完接着继续工作）
切换到dev分支  
再git stash pop，回到工作现场。


git merge –no-ff 可以保存你之前的分支历史。能够更好的查看 merge历史，以及branch 状态。
git merge 则不会显示 feature，只保留单条分支记录。

git stash list
git stash apply 先恢复工作区    git stash apply stash@{0}恢复指定的stash
git stash drop  删除stash （被存储在某个地方了） 
git stash pop  恢复的同时把stash内容也删了（分支下的所有）

详细请参考：
https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137602359178794d966923e5c4134bc8bf98dfb03aea3000#0
 

标签管理
git tag  v1.0
git tag v0.9 6224937(commit的id)
git tag -a v0.1 -m "version 0.1 released"    -a指定标签名 -m说明文字
git tag -s v0.2 -m "signed version 0.2 released"  -s用私钥签名一个标签gpg
git log --pretty=oneline --abbrev-commit      commit提交的历史列表



操作标签  推送标签到远程和删除远程标签
命令git push origin <tagname>可以推送一个本地标签
命令git push origin --tags可以推送全部未推送过的本地标签；
命令git tag -d <tagname>可以删除一个本地标签；
命令git push origin :refs/tags/<tagname>可以删除一个远程标签。


提交日志
git log
ctrl+c 或者 ctrl+d   结束日志


清空屏幕
使用命令 reset 加回车键即可实现清空屏幕


github使用
在GitHub上，可以任意Fork开源仓库；
自己拥有Fork后的仓库的读写权限；
可以推送pull request给官方仓库来贡献代码



搭建git服务器
搭建Git服务器需要准备一台运行Linux的机器，强烈推荐用Ubuntu或Debian
sudo权限的用户账号
搭建Git服务器非常简单，通常10分钟即可完成；
要方便管理公钥，用Gitosis；
要像SVN那样变态地控制权限，用Gitolite。
第一步，安装git：
sudo apt-get install git
第二步，创建一个git用户，用来运行git服务
sudo adduser git
第三步，创建证书登录
收集所有需要登录的用户的公钥，就是他们自己的id_rsa.pub文件，把所有公钥导入到/home/git/.ssh/authorized_keys文件里，一行一个
第四步，初始化Git仓库：
先选定一个目录作为Git仓库，假定是/srv/sample.git，在/srv目录下输入命令：
sudo git init --bare sample.git
Git仓库通常都以.git结尾。然后，把owner改为git：
sudo chown -R git:git sample.git
第五步，禁用shell登录
通过编辑/etc/passwd文件完成
git:x:1001:1001:,,,:/home/git:/bin/bash
改为git:x:1001:1001:,,,:/home/git:/usr/bin/git-shell
第六步，克隆远程仓库：
git clone git@server:/srv/sample.git


其他命令说明
git commit -a -m ""  能提交修改过，但是没有添加到缓存区的文件（修改过的就能提交）
git commit -m ""  只会提交添加到缓存区的文件（只提交添加的）








 