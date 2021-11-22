---
title: 步驟 5 – 傳播通知
description: 在此部分，我們將使用Android Notification Manager.Firebase傳播從Adobe Campaign收到的訊息
feature: Push
kt: 4829
doc-type: tutorial
activity: use
team: TM
exl-id: b0e01224-4ddc-4999-b8c6-794e49245428
source-git-commit: ada0b029245190f53d58fa93c79c161719bfe9fd
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 1%

---

# 添加要發送通知的服務

在此部分，我們將使用 [!DNL Android Notification Manager]. [!DNL Notification manager] 用於通知使用者發生的事件。
這是您告訴使用者背景發生了什麼事的方式：

* Launch [!DNL Android Studio]
* 開啟 *[!DNL ACSPushTutorial]* 專案
* 展開專案結構
* 以滑鼠右鍵按一下套件資料夾([!DNL com.example.acspushtutorial])和 [!DNL New ->Java Class]
* 為此類命名 *[!DNL MyService]* 並確保它能延伸 [!DNL FirebaseMessagingService]
* 建立 *[!DNL sendNotification]* 方法。 在此方法中，您需要使用 [!DNL NotificationCompat.Builder] 物件。 若要顯示通知，請呼叫 [!DNL NotificationManagerCompat.notify()]，會為通知及其結果傳遞唯一ID [!DNL NotificationCompat.Builder.build()].

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

## 修改 [!DNL AndroidManifest.xml]

將已建立的服務新增至 [!DNL AndroidManifest.xml]. 最後 [!DNL AndroidManifest.xml] 應如下所示：

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

按一下 **綠色箭頭** 或 [!DNL Run] 功能表。
