# ��4��ʵ��
## 1.ʵ��Ŀ��
1.����ѡ��Ҫ����ƽ��沼�ּ��ؼ�ʹ�ã�

2.����xml��������Ʋ��������ύ����ͼ��

3.��Ӧ�����н����ͼ��
## 2.ʵ������
1.ʹ������һ�ֲ��ַ�ʽ�������ѡ��Ŀ�Ľ���

2.ͨ���ؼ�ID��ȡ�������ִ����ز�����
android:id="@+id/my_button"

3.ʵ�ֽ���ؼ����¼�������������ť��
public class MainActivity extends Activity  implements OnClickListener {    
    ......   
    @Override    
    public void onClick(View v) { 
    ......
    
## 3.ʵ�鲽��
1.��Android Studio��

2.��layout�ļ������soft_1609081602618_activity2.xml��soft_1609081602618_activity3.xml��

3.��ƽ��沼�֣���ӿؼ���

4.ʵ�ֲ��ֿؼ����¼�����

5.���в��ԡ�
## 4.ʵ����
![image](https://github.com/unihaoke/android-labs-2018/blob/master/soft1609081602618/1526055697(1).png)
6.ʵ�����
��ε�ʵ����Ҫ��2��bug���һ��������ʱ��
1.��һ��bug����ImageView�е�src�������png��ʽͼƬ��ʱ����ʾ�쳣�������ĳ�jpg��ʽ�Ϳ���ʹ���ˣ�����ԭ�����������ʦ���һ��
2.�ڶ�������fragment������
FragmentTransaction begin=fragmentManager.beginTransaction();��д��ʱ�����ȳ�ʼ��FragmentTransaction��Ȼ����click���������е���commit��������������Logcat��ʾcommit��������������󣬺����鿴��һ��API����
ÿ�ύһ��commit������Ҫ����һ��FragmentTransaction����
3.֮ǰѧϰ��ListView����Ҫʹ���������ײ����ֵģ����Ǻ���������Fragment+ViewPagerʵ�ֵײ����ּӻ���Ч������ã����Ծ�û��ʹ��ListView��