 �ڶ���ʵ��
 
 ## 1.ʵ��Ŀ��
 �˽�Android������
 
 ## 2.ʵ�鲽��
��1����Issues�д����Լ���ѡ�⣺https://github.com/hzuapps/android-labs-2018/issues ��
 (2��������ѡ��Ŀ����дһ������Activity�����о�����ѧ��ǰ׺���ŵ��Լ���Java���£���
��3������������Ϊ�Լ���ѧ��+��Ӧ�Ĺ��ܻ���Ŀ��
��4�������Լ�ѡ�����Ŀʵ��Activity�е��������õȹ��ܣ�ѡ���� ## 3.ʵ����
 

 ## 3.ʵ����

 ###1��AndroidManifest.xml
 <?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.hzu.com1614080901140">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity android:name=".Com1614080901140MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>

###2.Com1614080901140Activity.java
package com.hzu.com1614080901140;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;

public class Com1614080901140MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_com1614080901140_main);
    }
}


###3.activity_com1614080901140_main.xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".Com1614080901140MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</android.support.constraint.ConstraintLayout>


###4.strings.xml
<resources>
    <string name="app_name">��·12306</string>
</resources>

 ## 4.ʵ�����
       ��һ�νӴ�Android ���������һ��Android��Ŀ�ʹ�����һ��activity���о���û�������е��ѣ������Ǹ��𲽰ɡ�