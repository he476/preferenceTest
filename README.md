# preferenceTest
## 使用PreferenceFragment实现设置页面<br>
![image](https://github.com/he476/preferenceTest/blob/master/images/6.JPG)<br><br>
## 实现效果
![image](https://github.com/he476/preferenceTest/blob/master/images/1.png)<br><br>
### 使用 XML 文件定义设置的集合:<br>
```
<?xml version="1.0" encoding="utf-8"?>
<PreferenceScreen xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
    ...
    ...
</PreferenceScreen>
```
<br>


<br>
### CheckBoxPreference的实现
```
<PreferenceCategory
        android:title="In-Line preference"
        android:key="pc_1">

        <CheckBoxPreference
            android:key="pref_cb"
            android:title="Checkbox preference"
            android:summary="this is a checkbox"
            android:defaultValue="true" />

    </PreferenceCategory>
```
### Dialog-based preferences:<br>
EditTextPreference<br>
ListPreference<br>
```
<PreferenceCategory
        android:title="Dialog-based preference"
        android:key="pc_2">
        <EditTextPreference
            android:key="pref_et"
            android:title="Edit Text preference"
            android:summary="an example that uses an edit text diglog"
            />
        <ListPreference
            android:key="pref_list"
            android:title="List preference"
            android:summary="an example that uses a list dialog"
            android:entries="@array/choose"
            android:entryValues="@array/chooseValue"
            android:dialogTitle="Choose one">
        </ListPreference>

    </PreferenceCategory>
```

ListPreference的键值对设置：
```
<string-array name="choose">
        <item>Alpha Option 01 </item>
        <item>Beta Option 02</item>
        <item>Charlie Option 03</item>
    </string-array>
    <string-array name="chooseValue">
        <item>1</item>
        <item>2</item>
        <item>3</item>
    </string-array>
```
### 实验效果：
![image](https://github.com/he476/preferenceTest/blob/master/images/2.png)<br>
![image](https://github.com/he476/preferenceTest/blob/master/images/3.png)<br>

### Launch preferences<br><br>
PreferenceScreen: 跳转到另一个PreferenceScreen<br>
```
<PreferenceScreen
            android:key="pref_screen"
            android:persistent="false"
            android:summary="shows another screen of preferences"
            android:title="Screen preference">
            <CheckBoxPreference
                android:key="pref_cb2"
                android:summary="@string/pref_cb2_summary" />
        </PreferenceScreen>
```
### 实验效果：
![image](https://github.com/he476/preferenceTest/blob/master/images/4.png)<br><br>
PreferenceScreen: 启动一个网页<br>
```
<Preference
            android:summary="@string/pref_intent_summary"
            android:title="Intent preference">
            <intent
                android:action="android.intent.action.VIEW"
                android:data="https://github.com/he476" />
        </Preference>
```
### Preference attributes<br><br>
CheckBox: 父选项
CheckBox: 子选项，当父选项勾选时呈现
```
<PreferenceCategory
        android:key="pc_4"
        android:title="Preference attribute">
        <CheckBoxPreference
            android:key="pref_cb3"
            android:title="Parent checkbox preference"
            android:summary="this is visually a parent"
            android:defaultValue="false"
            />
        <CheckBoxPreference
            android:key="pref_cb4"
            android:title="Child checkbox preference"
            android:summary="this is visually a child"
            android:dependency="pref_cb3"
            />
    </PreferenceCategory>
```
![image](https://github.com/he476/preferenceTest/blob/master/images/1.png)<br>



![image](https://github.com/he476/preferenceTest/blob/master/images/5.png)<br>
