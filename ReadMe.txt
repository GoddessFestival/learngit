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









 