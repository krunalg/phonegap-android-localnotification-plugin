## Phonegap - LocalNotification Plugin for Android
### Updated for PhoneGap/Cordova 2.7.0
This is a fork of [PhoneGap LocalNotification](https://github.com/phonegap/phonegap-plugins/tree/master/Android/LocalNotification), a plugin for accessing Android's LocalNotification library from a PhoneGap application. Due to a lack of updates to the original plugin, a few changes are needed in order to make it compatible with newer versions of PhoneGap/Cordova. This project contains those changes.

### In order to install the plugin into your PhoneGap application:
1. Copy the LocalNotification.js file to your js folder and include it in your index.html
2. Create a package com.phonegap.plugin.localnotification
3. Copy the .java files into this package
4. Fix the import in AlarmReceiver.java around line 13 to reference your own project instead of mine.
5. Add the following code to your res/xml/config.xml file within the `<plugins>` tag:

```
<plugin name="LocalNotification" value="com.phonegap.plugin.localnotification.LocalNotification" />
```

6. Add the following fragment in the AndroidManifest.xml inside the <application> tag:

```
<receiver android:name="com.phonegap.plugin.localnotification.AlarmReceiver" >
</receiver>
<receiver android:name="com.phonegap.plugin.localnotification.AlarmRestoreOnBoot" >
    <intent-filter>
        <action android:name="android.intent.action.BOOT_COMPLETED" />
    </intent-filter>
</receiver>
```

Refer to the original project [here](https://github.com/phonegap/phonegap-plugins/tree/master/Android/LocalNotification) for example usage of the plugin.