# ������ʵ�� 

## 1. ʵ��Ŀ��
������AndroidӦ����ʹ��ͼƬ����Դ�ķ�����
## 2. ʵ�鲽��
1����button�ؼ�ʵ����ת
��1����֮ǰʵ��д�õ�Android������activity_soft1614080902325.xmlдһ��button

    <Button
        android:id="@+id/textview_01"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="�鿴������Ϣ"
        android:textSize="25sp"
        android:layout_centerInParent="true"
��2���½�һ��Activity����ΪpersonalInformationActivity���Ȳ����µ�Activity���κθĶ���
Ȼ����Soft1614080902325Activity��������button��Ȼ��д��ʵ����ת�Ĵ���
	ʵ����ת�Ĵ������£�
        textview_01 = findViewById(R.id.textview_01);
        textview_01.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                //��ת��������Ϣҳ��
                Intent intent = new Intent(Soft1614080902325Activity.this,personalInformationActivity.class); 
                startActivity(intent);
            }
        });
2��ʵ��ͼƬ��ʾ
��1����res/drawable�ļ����з���ͼƬ������Ϊhuibiao
��2�����½�personalInformationActivity��ʱ��AndroidStudio�Զ����ɵ�activity_personal_information.xml��дһ��TextView

	    <TextView
        android:id="@+id/huibiao"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:drawableTop="@drawable/huibiao"
        android:text="hello_world" />

## 3. ʵ����

![��Android SDK](https://github.com/li763407418/android-labs-2018/blob/master/soft1614080902325/#2.png)


## 4. ʵ�����
���Ƚ���һ����Ϊʲô��ô�ٲŽ����ʵ�飬��������Ϊ�ҵ��ֻ���iPhone...ʵ�����еĵ���Ҳû��װ��׿�������
���ҵĵ�������AndroidStudio��ʱ���ڴ�ռ��50%��������AVD��׿�������ʱ���ϵ���90%ֱ�ӾͿ�����...Ȼ����
����ȥ�������ذ�׿ģ��������ҹ��ģ����Ҳ��ൽ80%���ǻ����ã���������һ��ҹ��ģ���������з��ֳ�����
�в��ˣ�����ҿ���һ��ҹ��ģ�����İ�׿�汾��4�㼸�ģ����ҵĳ����ǻ���5.0�����ģ�����Ϊ�ǰ汾���⣬��ȥ
�ٶ���θ�API�����Ҹ���һͨ���ֻ��ǲ������У�����ֻ�ܻ�����AndroidStudio��AVD���ڹص��ҵ��������ĳ���
ֻ����AndroidStudio������AVD����ǿ�����У����ֻ��ǲ������г��������ֻ���������½�һ��Android������
��д���룬����ȷʵ��Щ�ط������⣬�Ļ�����������������....ʵ�ڲ����ס�

**�Ӵ�**����