---
title: 步驟2 —— 整合行動SDK
description: 在本部分，我們將整合Android應用程式與Mobile SDK。 將行動SDK與Android應用程式整合
feature: Push
topics: Mobile
kt: 4826
doc-type: tutorial
activity: use
team: TM
translation-type: tm+mt
source-git-commit: a2f194821a9ce06272eaed979ee2d8c62cccac2b
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 0%

---

# 步驟2 —— 與Android應 [!UICONTROL Mobile SDK] 用程式整合

在本部分，我們將整合應用 [!DNL Android] 程式與 [!UICONTROL Mobile SDK]。 若要與應 [!UICONTROL mobile SDK] 用程式 [!DNL Android] 整合，請遵循下列步驟：

* 開啟 *ACSPushTutorial專案* ，位於 [!DNL Android Studio]
* 建立名為 *MainApp* (可延伸 [!DNL android.app.Application]
* 此時的專案結構應如下所示

![主應用程式](assets/android-main-app.PNG)

* 展開資 [!DNL Gradle Scripts] 料夾。 按兩下 [!DNL build.gradle] 模組。 將下列從屬關係貼上到檔案的從屬關係部 [!DNL build.gradle] 分。 您的 [!DNL build.gradle] 檔案現在應如下所示

```java{.line-numbers}
implementation 'com.adobe.marketing.mobile:campaign:1.+'
implementation 'com.adobe.marketing.mobile:userprofile:1.+'
implementation 'com.adobe.marketing.mobile:sdk-core:1.+'
```

![模組格式](assets/module-build-gradle.PNG)

* 按一下「 [!DNL Android] 立即同步」按鈕以同步您的專案

## 修改 [!DNL AndroidManifest.xml]{#modify-android-manifest}

開啟 *AndroidManifest.xml* ，並在資訊清單元素後面和應用程式元素之前貼上下列2行。 這可讓您的應用程式與外界通訊

```xml{.line-numbers}
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

在應用程式元素中複製下列行[!DNL android:name=".MainApp"]儲存您 [!DNL AndroidManifest.xml]的 [!DNL AndroidManifest.xml] 應該如下所示

```xml{.line-numbers}
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
