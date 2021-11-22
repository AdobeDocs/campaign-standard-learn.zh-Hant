---
title: 步驟 2 – 整合行動裝置 SDK
description: 在本部分中，我們將整合Android應用程式與行動SDK。 將行動SDK與Android應用程式整合
feature: Push
kt: 4826
doc-type: tutorial
activity: use
team: TM
exl-id: 0fa53536-8330-4e96-be2f-afc078609bcd
source-git-commit: ada0b029245190f53d58fa93c79c161719bfe9fd
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 3%

---

# 步驟2 — 整合 [!UICONTROL Mobile SDK] 搭配Android應用程式

在此部分，我們將整合 [!DNL Android] 應用程式搭配 [!UICONTROL Mobile SDK]. 要整合 [!UICONTROL mobile SDK] 和 [!DNL Android] 應用程式，請遵循下列步驟：

* 開啟 *ACSPush教學課程* 項目 [!DNL Android Studio]
* 建立名為 *MainApp* 延伸 [!DNL android.app.Application]
* 此時的專案結構應如下所示

![主應用程式](assets/android-main-app.PNG)

* 展開 [!DNL Gradle Scripts] 檔案夾。 按兩下 [!DNL build.gradle] 的下一頁。 將下列相依性貼入的相依性區段中， [!DNL build.gradle] 檔案。 您的 [!DNL build.gradle] 檔案現在看起來應該如下所示

<!--
Removed `{.line-numbers}` below
-->

```java
implementation 'com.adobe.marketing.mobile:campaign:1.+'
implementation 'com.adobe.marketing.mobile:userprofile:1.+'
implementation 'com.adobe.marketing.mobile:sdk-core:1.+'
```

![模組 — Gradle](assets/module-build-gradle.PNG)

* 同步您的 [!DNL Android] 按一下「立即同步」按鈕，同步您的專案

## 修改 [!DNL AndroidManifest.xml]{#modify-android-manifest}

開啟 *AndroidManifest.xml* 並在資訊清單元素後面和應用程式元素之前貼上下列2行。 這可讓您的應用程式與外部世界通訊

<!--
Removed `{.line-numbers}` below
-->

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

在應用程式元素中複製以下行
[!DNL android:name=".MainApp"]
儲存 [!DNL AndroidManifest.xml]
您的 [!DNL AndroidManifest.xml] 應該是這樣

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
