#���Ĵ�ʵ�鱨��
## һ.ʵ��Ŀ��

����ѡ��Ҫ����ƽ��沼�ּ��ؼ�ʹ�ã�
����xml��������Ʋ��������ύ����ͼ��
��Ӧ�����н����ͼ������Ҫ����¼ע�ᣡ��

## ��.ʵ�鲽��
 

��ʵ�������Ƕ��Ź�������������ΪActivity������Ҫʵ���½����ţ�Activity2����������Activity3���������ܡ�

###1. ���ȴ���ǰ���õ�android���̣����뵽Activity��design�ؼ�����ҳ��
###2. ʵ��3ʵ�ֵĴ�Activity2��Ϊ�½����Ź��ܵ�ʵ�֣�ͬ���ģ�ҪŪһ����Activity3��ʵ����������
��Activity��design����������һ��idΪbutton�İ�ť����������һ�������ı��������������ؼ��ʣ������λ��
###3. ��Activity��Ӧ��java�ļ��м���Դ˰�ť�ļ����Լ��¼������´���
����
  Button button2 = (Button)findViewById(R.id.button);
        button2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent = new Intent();
                intent.setClass(Soft1614080902314Activity.this,soft1614080902314Activity3.class);
                startActivity(intent);
����
###4. ��Activity3��design��������һ��listview�ؼ���Ϊ���������
###5. ��ȫ�½����Ź��ܵĽ���
   ��Activity2��design���棬�������������ı��������ռ��ˣ�����������ݣ���Ϊ���ŵĻ������ݣ������������㣬�����������ť��ͨѶ¼�����ͣ�������������
###6����ÿ��Activity�ؼ����ֽ������Լ����������

## ��.ʵ����
    

## ��.ʵ�����    
ͨ������ʵ�飬�˽⵽�������android�ؼ����ֽ���������ؼ���ͬʱҲ���ײ��ֽ�����Ҫ��Լ�������������úã���������ʱ�ؼ��Ĳ������ҵġ�
