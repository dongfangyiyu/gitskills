# gitskills

gitѧϰ�ʼ�
1.git add	��ӱ��ؿ��ļ����ֿ⣬δ�ύ״̬
	git add -A �ύ���б仯
	git add -u �ύ���޸ģ�modified���ͱ�ɾ����deleted���ļ������������ļ���new��
	git add . �ύ���ļ���new���ͱ��޸ģ�modified���ļ�����������ɾ����deleted���ļ�

2.git commit -m һ���ύ��ӵ��ļ��ǵ��ֿ�

3.�汾�޸�
	git status �鿴�ֿ�״̬
	git diff �ļ��� �鿴�Ա�

4.ʱ�⴩��
 4.1 �汾����(��һ���汾) git reset --hard HEAD^
     git reset --hard commit_id ���Իص�����汾�����գ�
     git log��git reflog �ɲ鿴commit_id�ύ��־
     git log --graph --pretty=oneline --abbrev-commit �鿴��֧���ύ��������԰棩
 4.2 �����޸�
     cat �ļ��� �鿴�ļ�����
     git diff ��������stage�Ƚ�
     git diff --cached stage���Ͳֿ��֧�Ƚ�
     git diff HEAD -- �ļ��� �������Ͳֿ��֧�Ƚ�
 4.3 �����޸�
     git checkout -- file �����������޸�����
     �� git reset HEAD <file>,�����ݴ����޸ĵ����ݣ���git checkout -- file �����������޸�����
     �ύ���汾��δ�ύ��Զ�̿��볷�زο�4.1
 4.4 ɾ���ļ���ָ� 
     4.4.1 rm file ɾ�����������ļ� git rm file��ɾ��stage�����ݣ�����git add file����ɾ������Ϊ��ӵ�stage�У���
	   Ȼ��git commit
     4.4.2 git checkout -- file �ָ���������ɾ�ļ�

5.Զ�ֿ̲�
 5.1 �������Զ�̿�
     git remote add origin Զ�̿��ַ��origin��Զ�̿����֣�Ĭ��origin
     git push -u origin master,-u�ǹ������ط�֧��Զ�̷�֧���ٴ�pushʱ-u��ʡ��
     ��һ��ʹ�õ����⣺Please make sure you have the correct access rightsand the repository exists ��Permission         denied (publickey).���Ǳ���û��Ȩ���ϴ���github�˻��ϣ���Ҫ����ssh�������صĹ�Կ�ŵ�GitHub��ssh key ���档
 5.2 ���ؿ�¡Զ�̿�
     git clone Զ�̿��ַ

6.��֧����
 6.1 ������֧���ϲ���֧��ɾ����֧
     �鿴��֧��git branch
     ������֧��git branch <name>
     �л���֧��git checkout <name>
     ����+�л���֧��git checkout -b <name>
     �ϲ�ĳ��֧����ǰ��֧�����ٺϲ�����git merge <name>
     ɾ����֧��git branch -d <name>
     ǿ��ɾ����֧��ɾ���󲻿ɻָ�����git branch -D <name>
 6.2 ��ͻ���
     ���ֳ�ͻ���ֶ��ϲ������ύ
 6.3 ��֧�������
     git merge --no-ff -m <message> <branchname>,���ÿ��ٺϲ�ģʽ������commit��Ϣ������log�п���merge��Ϣ
 6.4 Bug��֧
     ����δ��������Ƚ��master��֧bug
     git stash ����Ŀǰ��֧δ��Ṥ������
     git stash list �鿴���б��湤������
     git stash apply �ָ�������stash����
     git stash drop ɾ��stash����
     git stash pop �ָ���ɾ��stash���ݣ����ã�
     ���������Ҳ�����ٺ����stash_id���Ծ���ĳһ��stash���в���
     git stash ����󣬻����ص�ǰ���ȡ���ص��ϴ��ύ��״̬
 6.5 ����Э��
     git fetch origin ˢ��Զ�̿��֧��Ϣ
     git pull �����µ��ύ��origin/devץȡ�ڱ��غϲ��������ͻ��������
     ��һ��git pull��Ҫ���ط�֧dev��Զ�̷�֧dev�������� git branch --set-upstream-to=origin/dev dev

7.��ǩ����
 7.1 ������ǩ
     git tag <tagname> �������һ���ύ���ϱ�ǩ
     git tag �鿴���б�ǩ
     git log --pretty=oneline --abbrev-commit �鿴��ʷ�ύ��commit_id
     git tag <tagname> <commit_id> ����Ӧ��commit_id���ϱ�ǩ
     git show <tagname> �鿴��ǩ��Ϣ
     git tag -a <tagname> -m <message> <commit_id> ��������˵����Ϣ�ı�ǩ
     git tag -d <tagname> ɾ����ǩ
 7.2 ������ǩ
     git push origin <tagname> ���;����ǩ
     git push origin tags ��������û�б����͹��ı�ǩ
     git push origin :refs/tags/<tagname> ɾ��Զ�̿��ǩ

8.����
	git remote show չʾԶ�̿������
	git show չʾ���ؿ���Ϣ
	git branch -m newname ���������з�֧����������
	git branch -m oldname newname ָ��Ҫ��������֧����
	git remote rm origin �ڱ��زֿ�ɾ��Զ�̿�
	git remote add origin Զ�̿��ַ ���Զ�̿�

























