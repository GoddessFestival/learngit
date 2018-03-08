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
git remote add origin(learngit) git@github.com:GoddessFestival/learngit.git

git remote  查看远程仓库列表

代码提交到远程
	第一次提交
	git push -u origin master   
	以后提交
	git push origin master







 