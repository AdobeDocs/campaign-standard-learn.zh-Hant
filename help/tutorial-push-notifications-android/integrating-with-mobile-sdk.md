---
title: 第 2 步 – 整合行動 SDK
description: 在本部分，我們將整合Android應用程式與Mobile SDK。 將行動SDK與Android應用程式整合
feature: Push
topics: Mobile
kt: 4826
doc-type: tutorial
activity: use
team: TM
translation-type: tm+mt
source-git-commit: 13b4f1d395dfe53f9fc5263e7b06be700e30b986
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 3%

---

# 步驟2 —— 將[!UICONTROL Mobile SDK]與Android應用程式整合

在本部分，我們將整合[!DNL Android]應用程式與[!UICONTROL Mobile SDK]。 若要將[!UICONTROL mobile SDK]與[!DNL Android]應用程式整合，請依照下列步驟進行：

* 在[!DNL Android Studio]中開啟&#x200B;*ACSPushTutorial*&#x200B;專案
* 建立名為&#x200B;*MainApp*&#x200B;的新Java類，可擴充[!DNL android.app.Application]
* 此時的專案結構應如下所示

![主應用程式](assets/android-main-app.PNG)

* 展開[!DNL Gradle Scripts]資料夾。 按兩下模組的[!DNL build.gradle]。 將以下相關性貼上到[!DNL build.gradle]檔案的「相關性」部分。 您的[!DNL build.gradle]檔案現在應如下所示

<!--
Removed `{.line-numbers}` below
-->

```java
implementation 'com.adobe.marketing.mobile:campaign:1.+'
implementation 'com.adobe.marketing.mobile:userprofile:1.+'
implementation 'com.adobe.marketing.mobile:sdk-core:1.+'
```

![模組格式](assets/module-build-gradle.PNG)

* 按一下「立即同步」按鈕，同步您的[!DNL Android]專案，以同步您的專案

## 修改[!DNL AndroidManifest.xml]{#modify-android-manifest}

開啟&#x200B;*AndroidManifest.xml*，並在資訊清單元素後面和應用程式元素之前貼上下列2行。 這可讓您的應用程式與外界通訊

<!--
Removed `{.line-numbers}` below
-->

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

在應用程式元素中複製以下行
[!DNL android:name=".MainApp"]
儲存[!DNL AndroidManifest.xml]
您的[!DNL AndroidManifest.xml]應該如下所示

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
