# �����ʵ��

## һ��ʵ������

ʹ���ļ��洢

1.��Ӧ�ò��������ݱ��浽�ļ��洢�У�

2.˵��ʹ�õ��ļ��洢��ʽ���ڲ� or �ⲿ��

3.�����н����ͼ��

## ����ʵ�鲽��

1.��Android Studio��

2.�޸�SecondActivity.java

3.��onCreate()�����л�ȡEditText��ʵ������д��onDestroy()�������Ӷ��ڻ����ǰ�ض�����������������������save()�������ı�������ڵ����ݴ洢���ļ��У������ڲ��洢

4.save()��������Java���ķ�ʽ��ͨ����ȡEditText�����ݣ����ô��л��������ַ���д���ļ��У��ļ��Ĳ���ģʽ����Ĭ�ϵĲ���ģʽ����MODE_PRIVATE

5.load()����Ϊ��ȡ�ļ�������Ҳ�ǲ���Java���ķ�ʽ��ȡ��EditText�У������ȡ��ť���ɶ�ȡ�ļ��������ı������

## ����ʵ�����ͽ�ͼ

��1��SecondActivity.java

package edu.hzuapps.androidlabs.soft1614080902407;

import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;
import java.lang.String;
import android.app.Activity;
import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.ArrayAdapter;
import android.widget.Button;
import android.widget.EditText;
import android.widget.ListView;

public class SecondActivity extends AppCompatActivity {
    private EditText editText;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);

        final Activity thisActivity = this;
        Button btnBack = (Button)findViewById(R.id.gback);
        Button btnJoin= (Button)findViewById(R.id.btnJoin);
        editText = (EditText)findViewById(R.id.edittext);

        btnBack.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent = new Intent(thisActivity,Soft1614080902407Activity_1.class);
                thisActivity.startActivity(intent);
            }
        });
        btnJoin.setOnClickListener(new View.OnClickListener() {//���ļ���ȡ����
            @Override
            public void onClick(View v) {
                String inputText = load();
                editText.setText(inputText);
                editText.setSelection(inputText.length());
            }
        });
    }
    protected void onDestroy() {                            //�洢�ļ�

        super.onDestroy();
        String  inputText = editText.getText().toString();
        save(inputText);
    }
    public void save(String inputText){
        FileOutputStream out;
        BufferedWriter  writer = null;
        try {
            out = openFileOutput("data", MODE_PRIVATE);
            writer = new BufferedWriter(new OutputStreamWriter(out));
            writer.write(inputText);
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                if(writer!=null){
                    writer.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }

    }
    public String load(){                                           //��ȡ�ļ�
        FileInputStream in =null;
        BufferedReader reader = null;
        StringBuilder content = new StringBuilder();
        try {
            in = openFileInput("data");
            reader = new BufferedReader(new InputStreamReader(in));
            String line = "";
            while ((line=reader.readLine())!= null){
                content.append(line);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }finally {
            if(reader!=null){
                try {
                    reader.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }
        return content.toString();
    }
}

��2��Soft1614080902407Activity_1.java

package edu.hzuapps.androidlabs.soft1614080902407;
import java.lang.String;
import android.app.Activity;
import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.ArrayAdapter;
import android.widget.Button;
import android.widget.ImageView;
import android.widget.ListView;

public class Soft1614080902407Activity_1 extends AppCompatActivity {
    String[]  adapterData;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_soft1614080902407_1);
        final ListView listView = (ListView)findViewById(R.id.listview);
        adapterData = new String[] { "�ı�1","�ı�2", "�ı�3","�ı�4"};
        ArrayAdapter<String> arrayAdapter = new ArrayAdapter<String>( Soft1614080902407Activity_1.this, android.R.layout.simple_list_item_1, adapterData);
        listView.setAdapter(arrayAdapter);
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

(3)activity_second.xml

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
            android:id="@+id/edittext"
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
            android:text="��ȡ����¼"
            android:textStyle="bold" />

        <Button
            android:id="@+id/gback"
            android:layout_width="50dp"
            android:layout_height="wrap_content"
            android:background="@drawable/ic_arrow_back_black_24dp" />
    </LinearLayout>

</LinearLayout>

![image]()

![image]()

## �ġ�ʵ�����

����ʵ���Ҳ����ڲ��洢�ķ�ʽ��ͨ������ʵ�飬��ȥѧϰ��Java����֪ʶ��ѧ�������ʹ��Java������һЩ�򵥵Ĳ������˽���Android��δ洢�ļ��Լ���ȡ�ļ�������Java���ķ�ʽ��EditText�����ݴ洢���ļ����Լ���ȡ��EditText