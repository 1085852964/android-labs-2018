#���Ĵ�ʵ��

##1.ʵ��Ŀ��
1.����ѡ��Ҫ����ƽ��沼�ּ��ؼ�ʹ�ã�

2.����xml��������Ʋ��������ύ����ͼ��

3.��Ӧ�����н����ͼ��

##2.ʵ������
1.ʹ������һ�ֲ��ַ�ʽ�������ѡ��Ŀ�Ľ��棻

2.ͨ���ؼ�ID��ȡ�������ִ����ز�����android:id="@+id/my_button"

3.ʵ�ֽ���ؼ����¼�������������ť��
public class MainActivity extends Activity  implements OnClickListener {    
    ......   
    @Override    
    public void onClick(View v) { 
    ......

##3.ʵ�鲽��
1.��Android Studio��

2.����res/layout�ļ��У���activity_soft1614080902407_1.xml��activity_second.xml��

3.�����Լ���ѡ��ѡ����ز����Լ������Ӧ�Ŀؼ���# 1015����¼ ����LinearLayout����

4.ʵ��Button���¼������봦��

5.���ֻ������в��Բ��޸�

##4.ʵ����

��1��activity_soft1614080902407_1.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".Soft1614080902407Activity_1"
    android:orientation="vertical">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="500dp">
        <ListView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:id="@+id/listview">
        </ListView>
    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center_vertical">
        <Button
            android:id="@+id/btn_new"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="@string/button_new"
            android:textStyle="bold"/>
    </LinearLayout>

</LinearLayout>

��2��activity_second.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".SecondActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="match_parent"
            android:layout_weight="1"
            android:gravity="center"
            android:text="����"
            android:textSize="20dp"
            android:textStyle="bold" />

    </LinearLayout>

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:gravity="start">

        <EditText
            android:id="@+id/text1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:ems="20"
            android:hint="@string/hint_content"
            android:inputType="textMultiLine"
            android:minLines="5"
            android:textAppearance="?android:attr/textAppearanceLargeInverse" />
    </LinearLayout>

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content">

        <ImageView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:background="@drawable/example" />
    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center_horizontal">

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="��ʱ����"
            android:textStyle="bold" />

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="���ͼƬ"
            android:textStyle="bold" />
    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center_vertical">

        <Button
            android:id="@+id/btnJoin"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="��ӱ���¼"
            android:textStyle="bold" />

        <Button
            android:id="@+id/gback"
            android:layout_width="50dp"
            android:layout_height="wrap_content"
            android:background="@drawable/ic_arrow_back_black_24dp" />
    </LinearLayout>

</LinearLayout>

��3��Soft1614080902407Activity_1.java

package edu.hzuapps.androidlabs.soft1614080902407;

import android.app.Activity;
import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

public class Soft1614080902407Activity_1 extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_soft1614080902407_1);

        final Activity  thisActivity = this;
        Button  btnHome = (Button)findViewById(R.id.btn_new);
        btnHome.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent = new Intent(thisActivity,SecondActivity.class);
                thisActivity.startActivity(intent);

            }
        });

    }
}

��4��SecondActivity.java

package edu.hzuapps.androidlabs.soft1614080902407;

import android.app.Activity;
import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.ArrayAdapter;
import android.widget.Button;
import android.widget.EditText;
import android.widget.ListView;
import android.widget.TextView;

public class SecondActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);

        final Activity thisActivity = this;
        Button btnBack = (Button)findViewById(R.id.gback);
        btnBack.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent = new Intent(thisActivity,Soft1614080902407Activity_1.class);
                thisActivity.startActivity(intent);
            }
        });
    }
}

��5��strings.xml

<resources>
<string name="app_name">Soft1614080902407����¼</string>
<string name="title_activity_second">��ҳ</string>
<string name="button_new">�½�����¼</string>
<string name="hint_content">�����������뱸��¼������</string>
</resources>

[image]()

[image]()

##5.ʵ�����

����ʵ��Ƚϸ��ӣ�ͨ��������ѯ�˽Ⲣѧ��ʹ����һЩ�ؼ��벼�֣��Լ��¼��Ĵ����ܶ���֮������ʵ��ʮ�����ջ�