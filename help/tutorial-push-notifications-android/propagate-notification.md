---
title: 第 5 步 – 傳播通知
description: 在本部分，我們將使用Android Notification Manager.Firebase來傳播從Adobe Campaign收到的訊息。
feature: Push
topics: Mobile
kt: 4829
doc-type: tutorial
activity: use
team: TM
translation-type: tm+mt
source-git-commit: 13b4f1d395dfe53f9fc5263e7b06be700e30b986
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 1%

---

# 新增服務以傳送通知

在本部分，我們將使用[!DNL Android Notification Manager]來傳播從Adobe Campaign收到的訊息。 [!DNL Notification manager] 用於通知用戶發生的事件。這就是您告訴使用者背景發生了什麼：

* 啟動[!DNL Android Studio]
* 開啟&#x200B;*[!DNL ACSPushTutorial]*&#x200B;專案
* 展開專案結構
* 按一下右鍵包資料夾([!DNL com.example.acspushtutorial])和[!DNL New ->Java Class]
* 將此類命名為&#x200B;*[!DNL MyService]* ，並確保其擴展[!DNL FirebaseMessagingService]
* 在此類中建立&#x200B;*[!DNL sendNotification]*&#x200B;方法。 在此方法中，您需要使用[!DNL NotificationCompat.Builder]物件來設定通知的內容和頻道。 若要顯示通知，請呼叫[!DNL NotificationManagerCompat.notify()]，並傳遞通知的唯一ID和[!DNL NotificationCompat.Builder.build()]結果。

<!--
Removed `{.line-numbers}` below
-->

```java
package com.example.pushmessaging;
import android.app.NotificationChannel;
import android.app.NotificationManager;
import android.app.PendingIntent;
import android.content.Context;
import android.content.Intent;
import android.media.RingtoneManager;
import android.net.Uri;
import android.os.Build;
import android.util.Log;

import androidx.core.app.NotificationCompat;

import com.google.firebase.messaging.FirebaseMessagingService;
import com.google.firebase.messaging.RemoteMessage;

import java.util.Map;

public class MyService extends FirebaseMessagingService {
@Override
public void onMessageReceived(RemoteMessage remoteMessage)
{
Map<String,String> data  = remoteMessage.getData();
Log.d("data payload: ", data.toString());
sendNotification(remoteMessage);
}


private void sendNotification(RemoteMessage message) {
Intent intent = new Intent(this, MainActivity.class);
intent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP);
PendingIntent pendingIntent = PendingIntent.getActivity(this, 0 /* Request code */, intent, PendingIntent.FLAG_ONE_SHOT);

String channelId = "0";
Uri defaultSoundUri = RingtoneManager.getDefaultUri(RingtoneManager.TYPE_NOTIFICATION);
NotificationCompat.Builder notificationBuilder =
        new NotificationCompat.Builder(this, channelId)
                .setSmallIcon(R.drawable.ic_launcher_background)
                .setContentTitle("Message from AEM")
                .setContentText(message.getData().get("body"))
                .setAutoCancel(true)
                .setSound(defaultSoundUri)
                .setContentIntent(pendingIntent);

NotificationManager notificationManager =
        (NotificationManager) getSystemService(Context.NOTIFICATION_SERVICE);

// Since android Oreo notification channel is needed.
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
    NotificationChannel channel = new NotificationChannel(channelId,
            "Channel human readable title",
            NotificationManager.IMPORTANCE_DEFAULT);
    notificationManager.createNotificationChannel(channel);
}

notificationManager.notify(0 /* ID of notification */, notificationBuilder.build());
}
}
```

## 修改[!DNL AndroidManifest.xml]

將已建立的服務添加到[!DNL AndroidManifest.xml]。 最終[!DNL AndroidManifest.xml]應如下所示：

<!--
Removed `{.line-numbers}` below
-->

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.pushmessaging">

    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />

    <application
        android:name=".MainApp"
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <service
            android:name=".MyService"
            android:exported="false">
            <intent-filter>
                <action android:name="com.google.firebase.MESSAGING_EVENT" />
            </intent-filter>
        </service>

        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

## 執行應用程式

按一下工具列上的&#x200B;**綠色箭頭**&#x200B;或[!DNL Run]選單，以執行應用程式。
