node.js mvc framework
======
	
### @version 1.0 
	encapsulate routing layer, controller layer, model layer, view layer
	��װ·�ɡ����Ʋ㣨C�������ݲ㣨M������ͼ�㣨V��

### @version 2.0
	-
		a) ·�ɷַ���˳���ǣ� ·�ɱ����  >  Ĭ�ϵ�URL��֡� ����ƥ��·�ɱ��еĹ������е���������app.all
		ע��·�ɱ��������ڡ�/mvc/routes/routes.map.js���ļ���������ӻ�ɾ����   
		    ��Ӵ˹��ܵĿ�����Ϊ��ʹURL����̸��ÿ���Ҳ����SEO��
		b) Ĭ�ϵ�URL�����ȡURL��path���ֵ��������·������"[http://localhost:3000/sasas/fasasdf/user/index](http://www.google.com)"ȡuser����������
		   index��action�� indexҲ����ʡ�ԣ�Ĭ�ϵ�action��ΪindexAction������http://localhost:3000/user/index����
		   ��[http://localhost:3000/user/](http://localhost:3000/user/)���͡�[http://localhost:3000/sasas/fasasdf/user/index](http://localhost:3000/sasas/fasasdf/user/index)����ַ���ͬһ��������ͬһ��action���档
		   
	- �������ķַ�˳����: �����������(hook)  >  ��ͨ������(controller)
	
	- ��־��¼ģ���˳���ǣ�mongodb > �ļ���־ > �նˡ�  ���Ƚ���־��¼��mongodb���������ʧ�ܣ��ټ�¼����־�ļ��
               ��Ҳ����ʧ�ܣ�ֱ�����ն˴�ӡ������
	
	- MODEl������������PDO��Ԥ������ʽ����װ�ġ�

### The problems in the development:
	- ��̬�ļ�����CSS�ļ���ͼƬ�ļ��ȵȣ����������ʱ��Ҳ������·�ɷַ������
		�������������app.use(express.static(path.join(__dirname, 'public'))); �����ڡ�app.use(app.router); ��֮ǰ���ɡ�
		��������ܼ򵥣�ȴ�����������졣�塣
		
	- MODEL����ѹ������ʱ������100��ʧ���ˡ�
		����������� node-mysql �Դ������ӳط�װ�� mysql���Ӷ��� ���ɡ�
		
	- ϵͳһ��ʱ�䲻�����κβ�����mysql���Ӷ����Զ��Ͽ�������node.js��ֹ���С�
		����������� mysql���Ӷ�����¼����������� 
		mysqlObject.on('error', function(error){
			if(error){
				������ó�ʼ��mysql���Ӷ�����룬���´����µ����Ӷ���
			}
		}) 
		
	- EventEMitter���¼������ڴ������
		����������� emitter.setMaxListeners()  ������������
		
	- ���򱨣�Can't set headers after they are sent  �Ĵ���
		����������������������Ǵ�������⣩
		���������ڷ��������������������Ӧ���ݺ��ּ�������headerͷ����������ġ���ÿ��
		���������������ʱ��res.render��res.redirect�ȵ�)����ǰ�߼Ӹ� ��return��,����return res.redirect(...)��
		��һ��function�ڣ�����callbackʱ�����Ҳ return һ�� ---> return callback(error, result);
	 
		����ϵͳ�У����һ��ʱ��֮�󲻽����κβ��������ǻᱨ������󣬵����ֲ�Ӱ��ϵͳ���С�
		���������˵�����node core ��BUG��0.8�İ汾������ִ����⣨[https://github.com/visionmedia/express/issues/751](https://github.com/visionmedia/express/issues/751)����
		
### My opinion:
	- node.js �����ܷǳ��ã��������Ӧ�ٶȶ��ǳ��죬MODEL��Ӧ�÷�װ�� ORM ����ܸ���
	        �����ֳ� node.js ���������ƣ�ϵͳ����ʱ���õ�PDO��ʽ����
	
	- �� javascript �������������д�����ܽ�ʡϵͳ��Դ��֧�ʹ������á�
	
	- �������������hook�����ڴ�����������µ� action 



 

 
