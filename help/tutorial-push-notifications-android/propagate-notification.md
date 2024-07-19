---
title: 步驟 5 – 傳播通知
description: 在本部分中，我們將使用Android Notification Manager.Firebase傳播從Adobe Campaign收到的訊息
feature: Push
jira: KT-4829
user: Admin
level: Experienced
doc-type: tutorial
activity: use
team: TM
exl-id: b0e01224-4ddc-4999-b8c6-794e49245428
source-git-commit: 200dcb4d6698c174f7fde508779609b11043d031
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 2%

---

# 新增服務以傳送通知

在本部分中，我們將使用[!DNL Android Notification Manager]傳播從Adobe Campaign收到的訊息。 [!DNL Notification manager]用於通知使用者發生的事件。
這是您告訴使用者背景中發生某些事情的方式：

* 啟動[!DNL Android Studio]
* 開啟&#x200B;*[!DNL ACSPushTutorial]*&#x200B;專案
* 展開專案結構
* 用滑鼠右鍵按一下封裝資料夾([!DNL com.example.acspushtutorial])和[!DNL New ->Java Class]
* 命名這個類別&#x200B;*[!DNL MyService]*&#x200B;並確定它擴充[!DNL FirebaseMessagingService]
* 在此類別中建立&#x200B;*[!DNL sendNotification]*&#x200B;方法。 在此方法中，您需要使用[!DNL NotificationCompat.Builder]物件來設定通知的內容和通道。 若要讓通知出現，請呼叫[!DNL NotificationManagerCompat.notify()]，為通知傳遞唯一識別碼，並傳回[!DNL NotificationCompat.Builder.build()]的結果。

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

將已建立的服務新增至您的[!DNL AndroidManifest.xml]。 最終[!DNL AndroidManifest.xml]應該如下所示：

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

按一下工具列上的&#x200B;**綠色箭頭**&#x200B;或從[!DNL Run]功能表執行應用程式。
