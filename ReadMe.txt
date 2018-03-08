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


分支常见及合并
git branch dev
git checkout dev        git checkout -b dev   一步完成

   Creating a new branch is quick.（在dev分支上提交）









 