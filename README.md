node.js mvc framework
=====

### @version 1.0
- encapsulate routing layer, controller layer, model layer, view layer ---> ��װ·�ɣ����Ʋ㣨C�������ݲ㣨M������ͼ�㣨V��
	
### @version 2.0
- ·�ɷַ���˳���ǣ� ·�ɱ����  >  Ĭ�ϵ�URL��֡� ����ƥ��·�ɱ��еĹ������е���������app.all��
	·�ɱ��������ڡ�/mvc/routes/routes.map.js���ļ���������ӻ�ɾ������Ӵ˹��ܵĿ�����Ϊ��ʹURL����̸��ÿ���Ҳ����SEO��
- Ĭ�ϵ�URL�����ȡURL��path���ֵ��������·������"[http://localhost:3000/sasas/fasasdf/user/index](http://localhost:3000/sasas/fasasdf/user/index)"ȡuser����������
	index��action�� indexҲ����ʡ�ԣ�Ĭ�ϵ�action��ΪindexAction����"[http://localhost:3000/user/index](http://localhost:3000/user/index)"��
	 "[http://localhost:3000/user/](http://localhost:3000/user/)"��"[http://localhost:3000/sasas/fasasdf/user/index](http://localhost:3000/sasas/fasasdf/user/index)"��ַ���ͬһ��������ͬһ��action���档
- �������ķַ�˳����: �����������(hook)  >  ��ͨ������(controller)
- ��־��¼ģ���˳���ǣ�mongodb > �ļ���־ > �նˡ�  ���Ƚ���־��¼��mongodb���������ʧ�ܣ��ټ�¼����־�ļ����Ҳ����ʧ�ܣ�ֱ�����ն˴�ӡ������
- MODEl������������PHP�е�PDOԤ������ʽ����װ�ġ�