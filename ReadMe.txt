HELLO  WORLD

git diff  �鿴�޸�



����ssh
1.���ն����롣

ssh-keygen -t rsa -C "username" (ע��usernameΪ��git�ϵ��û���)

2.cat  /c/Users/Administrator/.ssh/id_rsa.pub


�����û���������
git config -global user.name
git config -global user.email

��ʼ�����ؿ�
git init
git status
git add .       git add filename
git commit -m"�ύ��������"

��Զ�ֿ̲⽨������
git remote add origin(learngitԶ�ֿ̲����) git@github.com:GoddessFestival/learngit.git
learngit ==  url

git remote  �鿴Զ�ֿ̲��б�

�����ύ��Զ��
	��һ���ύ
	git push -u origin master   
	�Ժ��ύ
	git push origin master    git push learngit master

��Զ������ȡ����
git pull                git pull learngit  
git fetch               git fetch learngit



��¡Զ�̿�
git clone  git@github.com:GoddessFestival/learngit.git


��֧�������ϲ�
git branch dev
git checkout dev        git checkout -b dev   һ�����

   Creating a new branch is quick.����dev��֧���ύ��
	
	��dev��֧���ύ
	git add ReadMe.txt
	git commit -m "branch test"   �ݴ���
��֧�ĺϲ�
	git checkout master
	git merge dev   ��dev��֧�ϲ�����ǰ��֧��master��

	ע�⵽�����Fast-forward��Ϣ��Git�������ǣ���κϲ��ǡ����ģʽ	����Ҳ����ֱ�Ӱ�masterָ��dev�ĵ�ǰ�ύ�����Ժϲ��ٶȷǳ��졣

ɾ��dev��֧
git branch -b dev  



���湤���ֳ�
��ǰ����dev�Ͻ��еĹ�����û���ύ���Ȱѹ����ֳ�git stashһ�£�
Ȼ����master��֧�ϴ���issue-101��֧
git checkout -b issue-101     ȥ�޸�bug��
�޸����ύ�����л���master��֧�Ϻϲ�issue-101��֧����ɾ��������bug�޸�����ż���������
�л���dev��֧  
��git stash pop���ص������ֳ���


git merge �Cno-ff ���Ա�����֮ǰ�ķ�֧��ʷ���ܹ����õĲ鿴 merge��ʷ���Լ�branch ״̬��
git merge �򲻻���ʾ feature��ֻ����������֧��¼��

git stash list
git stash apply �Ȼָ�������    git stash apply stash@{0}�ָ�ָ����stash
git stash drop  ɾ��stash �����洢��ĳ���ط��ˣ� 
git stash pop  �ָ���ͬʱ��stash����Ҳɾ�ˣ���֧�µ����У�

��ϸ��ο���
https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137602359178794d966923e5c4134bc8bf98dfb03aea3000#0
 

��ǩ����
git tag  v1.0
git tag v0.9 6224937(commit��id)
git tag -a v0.1 -m "version 0.1 released"    -aָ����ǩ�� -m˵������
git tag -s v0.2 -m "signed version 0.2 released"  -s��˽Կǩ��һ����ǩgpg
git log --pretty=oneline --abbrev-commit      commit�ύ����ʷ�б�



������ǩ  ���ͱ�ǩ��Զ�̺�ɾ��Զ�̱�ǩ
����git push origin <tagname>��������һ�����ر�ǩ
����git push origin --tags��������ȫ��δ���͹��ı��ر�ǩ��
����git tag -d <tagname>����ɾ��һ�����ر�ǩ��
����git push origin :refs/tags/<tagname>����ɾ��һ��Զ�̱�ǩ��


�ύ��־
git log
ctrl+c ���� ctrl+d   ������־


�����Ļ
ʹ������ reset �ӻس�������ʵ�������Ļ


githubʹ��
��GitHub�ϣ���������Fork��Դ�ֿ⣻
�Լ�ӵ��Fork��Ĳֿ�Ķ�дȨ�ޣ�
��������pull request���ٷ��ֿ������״���



�git������
�Git��������Ҫ׼��һ̨����Linux�Ļ�����ǿ���Ƽ���Ubuntu��Debian
sudoȨ�޵��û��˺�
�Git�������ǳ��򵥣�ͨ��10���Ӽ�����ɣ�
Ҫ�������Կ����Gitosis��
Ҫ��SVN������̬�ؿ���Ȩ�ޣ���Gitolite��
��һ������װgit��
sudo apt-get install git
�ڶ���������һ��git�û�����������git����
sudo adduser git
������������֤���¼
�ռ�������Ҫ��¼���û��Ĺ�Կ�����������Լ���id_rsa.pub�ļ��������й�Կ���뵽/home/git/.ssh/authorized_keys�ļ��һ��һ��
���Ĳ�����ʼ��Git�ֿ⣺
��ѡ��һ��Ŀ¼��ΪGit�ֿ⣬�ٶ���/srv/sample.git����/srvĿ¼���������
sudo git init --bare sample.git
Git�ֿ�ͨ������.git��β��Ȼ�󣬰�owner��Ϊgit��
sudo chown -R git:git sample.git
���岽������shell��¼
ͨ���༭/etc/passwd�ļ����
git:x:1001:1001:,,,:/home/git:/bin/bash
��Ϊgit:x:1001:1001:,,,:/home/git:/usr/bin/git-shell
����������¡Զ�ֿ̲⣺
git clone git@server:/srv/sample.git


��������˵��
git commit -a -m ""  ���ύ�޸Ĺ�������û����ӵ����������ļ����޸Ĺ��ľ����ύ��
git commit -m ""  ֻ���ύ��ӵ����������ļ���ֻ�ύ��ӵģ�








 