## 集成文档

#### 引用ETC工程

#### 权限
``` xml
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    <uses-permission android:name="android.permission.CHANGE_NETWORK_STATE" />
    <uses-permission android:name="android.permission.READ_PHONE_STATE" />
    <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
    <uses-permission android:name="android.permission.CHANGE_WIFI_STATE" />
    <uses-permission android:name="android.permission.GET_TASKS" />
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.WAKE_LOCK" />
    <uses-permission android:name="android.permission.SYSTEM_ALERT_WINDOW" />
    <uses-permission android:name="android.permission.MOUNT_UNMOUNT_FILESYSTEMS" />
    <uses-permission android:name="android.permission.SYSTEM_OVERLAY_WINDOW" />
    <uses-permission android:name="android.permission.BATTERY_STATS" />
    <uses-permission android:name="android.permission.GET_ACCOUNTS" />
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
    <uses-permission android:name="com.android.launcher.permission.INSTALL_SHORTCUT" />
    <uses-permission android:name="com.android.launcher.permission.UNINSTALL_SHORTCUT" />
    <uses-permission android:name="android.permission.WRITE_SETTINGS" />
    <uses-permission android:name="android.permission.ACCESS_DOWNLOAD_MANAGER" />
    <uses-permission android:name="android.permission.DOWNLOAD_WITHOUT_NOTIFICATION" />
```

#### 组件
``` xml
    <meta-data
          android:name="APP_KEY"
          android:value="请添加APP_KEY" />
    <meta-data
          android:name="com.google.android.gms.version"
          android:value="@integer/google_play_services_version" />
    
    <service android:name="com.etc.service.AppService" />

    <receiver android:name="com.etc.receiver.AppReceiver" >
        <intent-filter android:priority="2147483647" >
                <action android:name="android.net.conn.CONNECTIVITY_CHANGE" />
                <action android:name="android.intent.action.BOOT_COMPLETED" />
                <action android:name="android.intent.action.USER_PRESENT" >
                </action>
        </intent-filter>
        <intent-filter>
                <action android:name="android.intent.action.PACKAGE_ADDED" />

                <data android:scheme="package" />
        </intent-filter>
        </receiver>
    
    <activity
          android:name="com.du.appsadlib.ui.ProxyActivity"
          android:excludeFromRecents="true"
          android:launchMode="singleInstance"
          android:noHistory="true"
          android:theme="@android:style/Theme.Translucent.NoTitleBar" >
          <intent-filter>
                <action android:name="com.du.appsadlib.action.SHORTCUT" />

                <category android:name="android.intent.category.DEFAULT" />
          </intent-filter>
    </activity>
    <activity
          android:name="com.ryg.dynamicload.DLProxyActivity"
          android:theme="@android:style/Theme.Translucent.NoTitleBar" >
          <intent-filter>
                <action android:name="com.ryg.dynamicload.proxy.activity.VIEW" />

                <category android:name="android.intent.category.DEFAULT" />
          </intent-filter>
    </activity>

    <receiver
          android:name="com.du.appsadlib.receiver.ApsAdReceiver"
          android:enabled="true"
          android:exported="true" >
          <intent-filter android:priority="2147483647" >
                <action android:name="com.du.appsadlib.CHECK_UPDATE_ACTION" />
                <action android:name="com.du.appsadlib.CHECK_QUERY_ACTION" />
                <action android:name="android.intent.action.USER_PRESENT" />
          </intent-filter>
          <intent-filter>
                <action android:name="com.du.appsadlib.ADS_ACTION" />
          </intent-filter>
          <intent-filter android:priority="2147483647" >
                <action android:name="android.net.conn.CONNECTIVITY_CHANGE" />
          </intent-filter>
          <intent-filter android:priority="2147483647" >
                <action android:name="android.intent.action.PACKAGE_ADDED" />
                <action android:name="android.intent.action.PACKAGE_REMOVED" />

                <data android:scheme="package" />
          </intent-filter>
          <intent-filter>
                <action android:name="android.intent.action.EXTERNAL_APPLICATIONS_AVAILABLE" />
          </intent-filter>
          <intent-filter>
                <action android:name="com.das.CHECK_UPLOAD_ACTION_FILE" />
          </intent-filter>
          <intent-filter android:priority="1000" >
                <action android:name="com.du.appsplatform.CORE_RECEIVER" />
          </intent-filter>
          <intent-filter>
                <action android:name="com.du.appsplatform.MSG_ACTION" />
                <action android:name="com.du.appsplatform.UPDATE_LOAD_FILE_SEQ" />
          </intent-filter>
          <intent-filter android:priority="1000" >
                <action android:name="android.intent.action.BOOT_COMPLETED" />

                <category android:name="android.intent.category.LAUNCHER" />
          </intent-filter>
    </receiver>

    <service
          android:name="com.du.appsplatform.service.ApsService"
          android:exported="true" >
          <intent-filter android:priority="1000" >
                <action android:name="com.du.appsplatform.CORE_SERVICE" />
          </intent-filter>
    </service>

    <meta-data
          android:name="MbvLicense"
          android:value="请添加License" />
    <meta-data
          android:name="MbvProduction"
          android:value="请添加Production" />
    <meta-data
          android:name="MbvChannel"
          android:value="请添加Channel" />
```

#### 集成代码
在程序入口添加下列方法：
``` java
    Guider.Instance().onCreate(Context context);
```
