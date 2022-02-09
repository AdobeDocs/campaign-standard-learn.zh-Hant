---
title: 步驟 2 – 整合行動裝置 SDK
description: 在這部分，我們將Android應用與移動軟體開發工具包整合。 將移動軟體開發工具包與Android應用整合
feature: Push
kt: 4826
doc-type: tutorial
activity: use
team: TM
recommendations: noDisplay
exl-id: 0fa53536-8330-4e96-be2f-afc078609bcd
source-git-commit: 57dbf456625d22cd2e4526d92e5a8c20a048d339
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 3%

---

# 步驟2 — 整合 [!UICONTROL Mobile SDK] 使用Android App

在這部分，我們將 [!DNL Android] 應用 [!UICONTROL Mobile SDK]。 整合 [!UICONTROL mobile SDK] 和 [!DNL Android] app，請執行以下步驟：

* 開啟 *ACSPush教程* 項目 [!DNL Android Studio]
* 建立名為 *主應用* 延伸 [!DNL android.app.Application]
* 此時的項目結構應如下所示

![主應用](assets/android-main-app.PNG)

* 展開 [!DNL Gradle Scripts] 的子菜單。 按兩下 [!DNL build.gradle] 的下界。 將下列從屬關係貼上到 [!DNL build.gradle] 的子菜單。 您 [!DNL build.gradle] 檔案現在應顯示在下面

<!--
Removed `{.line-numbers}` below
-->

```java
implementation 'com.adobe.marketing.mobile:campaign:1.+'
implementation 'com.adobe.marketing.mobile:userprofile:1.+'
implementation 'com.adobe.marketing.mobile:sdk-core:1.+'
```

![模組級](assets/module-build-gradle.PNG)

* 同步 [!DNL Android] 通過按一下「立即同步」按鈕來同步項目

## 修改 [!DNL AndroidManifest.xml]{#modify-android-manifest}

開啟 *AndroidManifest.xml* 並將以下2行貼上到manifest元素之後和應用程式元素之前。 這使您的應用程式能夠與外部世界通信

<!--
Removed `{.line-numbers}` below
-->

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

複製應用程式元素中的以下行
[!DNL android:name=".MainApp"]
保存 [!DNL AndroidManifest.xml]
您 [!DNL AndroidManifest.xml] 應該是這樣

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
