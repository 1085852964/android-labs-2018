# ������ʵ��

## һ��ʵ��Ŀ��

1.����Android������ʷ���

2.���XML��JSON��ʾ���ݵķ�����

## ����ʵ������

1.�ڸ���Ŀ¼�д���һ����ʾ���ݵ�XML��JSON�ļ�

2.�����ļ������ύ֮���GitHub��ȡ�ļ�URL

3.��Ӧ����ͨ�������̷���GitHub�������ļ�

4.��Ӧ���н�������ʾ�ļ�������������

5.��Ӧ�����н����ͼ

## ����ʵ�鲽��

1.��GitHub�ϱ༭JSON�ļ�����ȡ���ļ�URLhttps://raw.githubusercontent.com/Qiujialin/android-labs-2018/master/soft1614080902407/get_data.json����Android Studio

2.�༭AndroidManifest.xml�ļ�������������Ȩ����䣺
<uses-permission android:name="android.permission.INTERNET"/>

3.�༭app/build.gradle����dependencies�հ������������
implementation 'com.squareup.okhttp3:okhttp:3.10.0'

4.�༭SecondActivity.java������һ��OkHttpClientʵ��������һ��Request��������Ŀ������https://raw.githubusercontent.com/Qiujialin/android-labs-2018/master/soft1614080902407/get_data.json������OkHttpClient��newCall()��������һ��Call���󣬲�����execute�����������󲢻�ȡ���������ص�����

5.����parseJSONWithJSONObject()��������JSON���ݣ������������ص����ݴ���JSONArray���󣬱���ÿһ��JSONArray������getString()����ȡ�����ݣ���������ʾ��EditText��

6.�޸�ԭ��Button��idΪgetJson�����޸ĵ���¼�Ϊ����sendRequestWithOkHttp()���ж�ȡ������JSON�ļ���

## �ġ�ʵ��������ͼ

1.SecondActivity.java(��ӵĴ���)

    private void sendRequestWithOkHttp(){//���ʷ�����
        new Thread(new Runnable() {
            @Override
            public void run() {

                try {
                    OkHttpClient client = new OkHttpClient();
                    Request request = new Request.Builder().url("https://raw.githubusercontent.com/Qiujialin/android-labs-2018/master/soft1614080902407/get_data.json").build();
                    Response response = client.newCall(request).execute();
                    String responseData = response.body().string();
                    parseJSONWithJSONObject(responseData);
                } catch (IOException e) {
                    e.printStackTrace();
                }

            }
        }).start();
    }
    private void parseJSONWithJSONObject(String jsonData) {//����JSON
        try {
            JSONArray jsonArray = new JSONArray(jsonData);
            for(int i=0;i<jsonArray.length();i++){
                JSONObject jsonObject = jsonArray.getJSONObject(i);
                String id = jsonObject.getString("id");
                String  name = jsonObject.getString("name");
                String  text = "id is "+id+"\r\n"+"name is "+name;
                showResponse(text);
            }
        } catch (JSONException e) {
            e.printStackTrace();
        }
    }
    private void showResponse(final String response) {//��ʾ����
        runOnUiThread(new Runnable() {
            @Override
            public void run() {
                //editText.append(response);
                editText.setText(response);
            }
        });
    }

2.AndroidManifest.xml

<uses-permission android:name="android.permission.INTERNET"/>

3.app/build.gradle

implementation 'com.squareup.okhttp3:okhttp:3.10.0'

4.activity_second.xml

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
            android:id="@+id/getJson"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="��ȡ������JSON"
            android:textStyle="bold"/>
    </LinearLayout>

</LinearLayout>

5.get_data.json

[{
	"id": "1614080902407",
	"name": "�����"
}]

![image]()

![image]()

## �塢ʵ�����

ͨ���˴�ʵ�飬�˽�����η������磬�����JSONObject����JSON�Ĵ��룬�˴�ʵ����OkHttp���ԭ����HttpURLConnection����ԭ����HttpURLConnection����HTTP�����򵥣��˽���JSON�ļ��ĸ�ʽ�Լ����д���ڰ�׿�п���Ȩ����Ҫ��AndroidManifest.xml������Ȩ�޵���䣬��һ��ʼ����û�м����������Ȩ����䵼��ʵ�鲻�ɹ��������ҳ����󲢸�����

