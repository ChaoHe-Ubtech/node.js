node.js mvc framework
=======
	
### @version 1.0 
	encapsulate routing layer, controller layer, model layer, view layer
	��װ·�ɡ����Ʋ㣨C�������ݲ㣨M������ͼ�㣨V��

### @version 2.0
	1��
		a) ·�ɷַ���˳���ǣ� ·�ɱ����  >  Ĭ�ϵ�URL��֡� ����ƥ��·�ɱ��еĹ������е���������app.all
		ע��·�ɱ��������ڡ�/mvc/routes/routes.map.js���ļ���������ӻ�ɾ����   
		    ��Ӵ˹��ܵĿ�����Ϊ��ʹURL����̸��ÿ���Ҳ����SEO��
		b) Ĭ�ϵ�URL�����ȡURL��path���ֵ��������·�����硰[http://localhost:3000/sasas/fasasdf/user/index](http://localhost:3000/sasas/fasasdf/user/index)��ȡuser����������
		   index��action�� indexҲ����ʡ�ԣ�Ĭ�ϵ�action��ΪindexAction������[http://localhost:3000/user/index](http://localhost:3000/user/index)����
		   ��[http://localhost:3000/user/](http://localhost:3000/user/)���͡�[http://localhost:3000/sasas/fasasdf/user/index](http://localhost:3000/sasas/fasasdf/user/index)����ַ���ͬһ��������ͬһ��action���档
		   
	2�� �������ķַ�˳����: �����������(hook)  >  ��ͨ������(controller)
	
	3�� ��־��¼ģ���˳���ǣ�mongodb > �ļ���־ > �նˡ�  ���Ƚ���־��¼��mongodb���������ʧ�ܣ��ټ�¼����־�ļ��
	         ��Ҳ����ʧ�ܣ�ֱ�����ն˴�ӡ������
	
	4�� MODEl������������PDO��Ԥ������ʽ����װ�ġ�
	
<hr />

### The problems in the development:
	1����̬�ļ�����CSS�ļ���ͼƬ�ļ��ȵȣ����������ʱ��Ҳ������·�ɷַ������
		�������������app.use(express.static(path.join(__dirname, 'public'))); �����ڡ�app.use(app.router); ��֮ǰ���ɡ�
		��������ܼ򵥣�ȴ�����������졣�塣
		
	2�� MODEL����ѹ������ʱ������100��ʧ���ˡ�
		����������� node-mysql �Դ������ӳط�װ�� mysql���Ӷ��� ���ɡ�
		
	3�� ϵͳһ��ʱ�䲻�����κβ�����mysql���Ӷ����Զ��Ͽ�������node.js��ֹ���С�
		����������� mysql���Ӷ�����¼����������� 
		mysqlObject.on('error', function(error){
			if(error){
				������ó�ʼ��mysql���Ӷ�����룬���´����µ����Ӷ���
			}
		}) 
		
	4�� EventEMitter���¼������ڴ������
		����������� emitter.setMaxListeners()  ������������
		
	5�� ���򱨣�Can't set headers after they are sent  �Ĵ���
		����������������������Ǵ�������⣩
		���������ڷ��������������������Ӧ���ݺ��ּ�������headerͷ����������ġ���ÿ��
		���������������ʱ��res.render��res.redirect�ȵ�)����ǰ�߼Ӹ� ��return��,����return res.redirect(...)��
		��һ��function�ڣ�����callbackʱ�����Ҳ return һ�� ---> return callback(error, result);
	 
		����ϵͳ�У����һ��ʱ��֮�󲻽����κβ��������ǻᱨ������󣬵����ֲ�Ӱ��ϵͳ���С�
		���������˵�����node core ��BUG��0.8�İ汾������ִ����⣨[https://github.com/visionmedia/express/issues/751](https://github.com/visionmedia/express/issues/751)����

### ����
	1.		[���������������ӵ�www.google.com](http://www.google.com)
		
<hr />
		
### My opinion:
	1��node.js �����ܷǳ��ã��������Ӧ�ٶȶ��ǳ��죬MODEL��Ӧ�÷�װ�� ORM ����ܸ���
	        �����ֳ� node.js ���������ƣ�ϵͳ����ʱ���õ�PDO��ʽ����
	
	2���� javascript �������������д�����ܽ�ʡϵͳ��Դ��֧�ʹ������á�
	
	3���������������hook�����ڴ�����������µ� action 



 

 