---
title: 步驟 2 – 整合行動裝置 SDK
description: 在本部分中，我們將整合Android應用程式與行動SDK。 若要整合行動SDK與Android應用程式
feature: Push
user: Admin
level: Experienced
jira: KT-4826
doc-type: tutorial
activity: use
team: TM
recommendations: noDisplay
exl-id: 0fa53536-8330-4e96-be2f-afc078609bcd
TQID: 'https://experienceleague.adobe.com/6WL8yj7aMoS9C6l-HwQZZ3Hg0B2jmNtlmaFnsAi0Ohw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: a4657621-810c-498b-8a27-7ced9c176dda
    internal-label: Push notifications
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 508c3590ce956401ccfba3a256000cbc5849a684
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 3%
---
# 步驟2 — 整合[!UICONTROL Mobile SDK]與Android應用程式

在此部分中，我們將整合[!DNL Android]應用程式與[!UICONTROL Mobile SDK]。 若要將[!UICONTROL mobile SDK]與[!DNL Android]應用程式整合，請遵循下列步驟：

* 在[!DNL Android Studio]中開啟&#x200B;*ACSPushTutorial*&#x200B;專案
* 建立名為&#x200B;*MainApp*&#x200B;且擴充[!DNL android.app.Application]的新Java類別
* 此時您的專案結構應如下所示

![主要應用程式](assets/android-main-app.PNG)

* 展開[!DNL Gradle Scripts]資料夾。 按兩下模組的[!DNL build.gradle]。 將下列相依性貼到[!DNL build.gradle]檔案的相依性區段中。 您的[!DNL build.gradle]檔案現在看起來應該如下所示

<!--
Removed `{.line-numbers}` below
-->

```java
implementation 'com.adobe.marketing.mobile:campaign:1.+'
implementation 'com.adobe.marketing.mobile:userprofile:1.+'
implementation 'com.adobe.marketing.mobile:sdk-core:1.+'
```

![模組Gradle](assets/module-build-gradle.PNG)

* 按一下立即同步處理按鈕來同步處理您的[!DNL Android]專案，以同步處理您的專案

## 修改[!DNL AndroidManifest.xml]{#modify-android-manifest}

開啟&#x200B;*AndroidManifest.xml*，並將下列2行貼在資訊清單元素之後、應用程式元素之前。 這可讓您的應用程式與外部世界通訊

<!--
Removed `{.line-numbers}` below
-->

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

複製應用程式元素中的下列行
[!DNL android:name=&quot;。MainApp&quot;]
儲存您的 [!DNL AndroidManifest.xml]
您的[!DNL AndroidManifest.xml]看起來應該像這樣

<!--
Removed `{.line-numbers}` below
-->

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.acspushtutorial">
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

<activity android:name=".MainActivity">
<intent-filter>
    <action android:name="android.intent.action.MAIN" />
    <category android:name="android.intent.category.LAUNCHER" />
</intent-filter>
</activity>
</application>

</manifest>
```
