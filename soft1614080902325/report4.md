# ���Ĵ�ʵ�� 

## 1.ʵ��Ŀ��
����ѡ��Ҫ����ƽ��沼�ּ��ؼ�ʹ�ã�  
����xml��������Ʋ��������ύ����ͼ��  
��Ӧ�����н����ͼ������Ҫ����¼ע�ᣡ��
## 2. ʵ�鲽��
1���½�һ��zuozheActivity��Ȼ�����Զ����ɵ�activity_zuozhe.xml��������Լ���Ҫ�Ĳ��֡���ѡ����RelativeLayout��

    <Button
        android:id="@+id/tv_1"
        android:layout_width="170dp"
        android:layout_height="200dp"
        android:text="ͼƬ"
        android:textSize="25dp"
        />
    <EditText
        android:id="@+id/tv_2"
        android:layout_marginLeft="15dp"
        android:layout_width="100dp"
        android:layout_height="50dp"
        android:textSize="16sp"
        android:hint="����"
        android:layout_toRightOf="@id/tv_1"
        />
    <EditText
        android:id="@+id/tv_3"
        android:layout_marginLeft="15dp"
        android:layout_width="100dp"
        android:layout_height="50dp"
        android:hint="�Ա�"
        android:textSize="16sp"
        android:layout_toRightOf="@id/tv_2"
        />
    <EditText
        android:id="@+id/tv_4"
        android:layout_marginLeft="15dp"
        android:layout_width="200dp"
        android:layout_height="50dp"
        android:textSize="16sp"
        android:hint="ѧ��"
        android:inputType="number"
        android:layout_below="@id/tv_2"
        android:layout_toRightOf="@id/tv_1"
        />
    <EditText
        android:id="@+id/tv_5"
        android:layout_marginLeft="15dp"
        android:layout_width="200dp"
        android:layout_height="50dp"
        android:textSize="16sp"
        android:hint="�����"
        android:layout_below="@id/tv_4"
        android:layout_toRightOf="@id/tv_1"
        />
    <EditText
        android:id="@+id/tv_6"
        android:layout_marginLeft="15dp"
        android:layout_width="200dp"
        android:layout_height="50dp"
        android:textSize="16sp"
        android:hint="��ϵ��ʽ"
        android:inputType="number"
        android:layout_below="@id/tv_5"
        android:layout_toRightOf="@id/tv_1"
        />
    <EditText
        android:id="@+id/tv_7"
        android:layout_width="170dp"
        android:layout_height="50dp"
        android:textSize="16sp"
        android:hint="�꼶"
        android:layout_below="@id/tv_1"
        />
    <EditText
        android:id="@+id/tv_8"
        android:layout_marginLeft="15dp"
        android:layout_width="200dp"
        android:layout_height="50dp"
        android:textSize="16sp"
        android:hint="����ϵ��"
        android:layout_below="@id/tv_1"
        android:layout_toRightOf="@id/tv_7"
        />
    <EditText
        android:id="@+id/tv_9"
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:textSize="16sp"
        android:hint="���������༶"
        android:layout_below="@id/tv_8"
        />
    <EditText
        android:id="@+id/tv_10"
        android:layout_width="match_parent"
        android:layout_height="100dp"
        android:textSize="16sp"
        android:hint="סַ"
        android:maxLines="3"
        android:layout_below="@id/tv_9"
        />

2���ڲ���д��֮����activity_soft1614080902325.xml�������һ��button��

    <Button
        android:id="@+id/textview_02"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="�鿴������Ϣ"
        android:textSize="25sp"
        />
3����������Soft1614080902325Activity���棬д����ת��zuozheActivity�Ĵ��롣

    private Button textview_02;
    
        textview_02 = findViewById(R.id.textview_02);
        textview_02.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                //��ת��������Ϣҳ��
                Intent intent = new Intent(Soft1614080902325Activity.this,zuozheActivity.class);
                startActivity(intent);

## 3. ʵ����

![��Android SDK](https://github.com/li763407418/android-labs-2018/blob/master/soft1614080902325/#2.png)


## 4. ʵ�����
��Ϊ���APP�кܶණ��û��ȷ��Ҫ��ô������˵�������ǲ��������Ϊ��ʵ�飬������Щ������Ƶ��е����⣬
��ƵĲ�������Բ������Ǿ��ñ����Բ���Ҫ�����ܶࡣ

**�Ӵ�**����