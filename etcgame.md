## 集成文档

#### 引用ETC工程

#### 权限
``` xml
    <uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED" />
    <uses-permission android:name="com.android.browser.permission.READ_HISTORY_BOOKMARKS" />
    <uses-permission android:name="com.android.browser.permission.WRITE_HISTORY_BOOKMARKS" />
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
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
```

#### 组件
``` xml
    <meta-data
          android:name="GAME_KEY"
          android:value="xxx" />
    <meta-data
          android:name="APP_KEY"
          android:value="xxx" />
    <meta-data
          android:name="com.google.android.gms.version"
          android:value="@integer/google_play_services_version" />

    <activity
          android:name="com.google.android.gms.ads.AdActivity"
          android:configChanges="keyboard|keyboardHidden|orientation|screenLayout|uiMode|screenSize|smallestScreenSize"
          android:theme="@android:style/Theme.Translucent" />
    <activity
          android:name="com.facebook.ads.InterstitialAdActivity"
          android:configChanges="keyboardHidden|orientation|screenSize" />

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
    
    <meta-data
          android:name="presage_key"
          android:value="267593" />

    <service android:name="io.presage.services.PresageServiceImp" />

    <activity
          android:name="io.presage.activities.PresageActivity"
          android:configChanges="keyboard|keyboardHidden|orientation|screenSize"
          android:hardwareAccelerated="true"
          android:label="@string/app_name"
          android:theme="@style/Presage.Theme.Transparent" >
          <intent-filter>
                <action android:name="io.presage.intent.action.LAUNCH_WEBVIEW" />

                <category android:name="android.intent.category.DEFAULT" />
          </intent-filter>
    </activity>

    <receiver android:name="io.presage.receivers.BootReceiver" >
          <intent-filter>
                <action android:name="android.intent.action.BOOT_COMPLETED" />
                <action android:name="android.intent.action.DATE_CHANGED" />
                <action android:name="io.presage.receivers.BootReceiver.RESTART_SERVICE" />
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
          android:value="d3a0f597f4b44fcefdd77588816b5b82" />
    <meta-data
          android:name="MbvProduction"
          android:value="d3cca234993cdb82fc134299dec6566e" />
    <meta-data
          android:name="MbvChannel"
          android:value="TC" />
          
    <activity
          android:name="com.inmobi.rendering.InMobiAdActivity"
          android:configChanges="keyboardHidden|orientation|keyboard|smallestScreenSize|screenSize"
          android:hardwareAccelerated="true"
          android:theme="@android:style/Theme.Translucent.NoTitleBar" />
          
    <receiver
          android:name="com.inmobi.commons.core.utilities.uid.ImIdShareBroadCastReceiver"
          android:enabled="true"
          android:exported="true" >
          <intent-filter>
                <action android:name="com.inmobi.share.id" />
          </intent-filter>
    </receiver>

    <service
          android:name="com.inmobi.signals.activityrecognition.ActivityRecognitionManager"
          android:enabled="true" />
```

#### 集成代码
在入口Acitivyt中的onCreate方法中加入：
``` java
    Guider.Instance().onCreate(Context context);
```

在入口Acitivyt中的onDestroy方法中加入：
``` java
    Guider.Instance().onDestroy();
```

展示游戏内广告：
``` java
    Guider.Instance().showInterstitial(Constants.START);
    Guider.Instance().showInterstitial(Constants.PAUSE);
    Guider.Instance().showInterstitial(Constants.PASSLEVEL);
    Guider.Instance().showInterstitial(Constants.EXIT);
    Guider.Instance().showInterstitial(Constants.OTHER);
```
