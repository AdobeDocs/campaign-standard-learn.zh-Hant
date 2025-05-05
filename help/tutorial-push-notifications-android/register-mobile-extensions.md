---
title: 步驟 3－在您的行動應用程式中註冊擴充功能
description: 在此部分中，我們會新增程式碼以註冊UserProfile、身分、生命週期和訊號擴充功能。
feature: Push
user: Admin
level: Experienced
jira: KT-4827
doc-type: tutorial
activity: use
team: TM
exl-id: d8c0d8c6-2e04-4c27-b27a-d0de79dd953b
source-git-commit: 9be31e056800b806c49a2c5ffbf9f9f42b001d4c
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 14%

---

# 步驟 3－在您的行動應用程式中註冊擴充功能

在本部分中，我們會新增程式碼以註冊使用者設定檔、身分、生命週期和訊號擴充功能。 我們也必須註冊Adobe Campaign Standard擴充功能，如下列程式碼所示。

在[!DNL Android]工作室中開啟您的專案。 刪除MainApp **中的整個程式碼，但第一行是您的封裝陳述式**&#x200B;除外。

將下列程式碼貼入MainApp

<!--
Removed `{.line-numbers}` below
-->

```java
import [!DNL android].app.Application;
import android.util.Log;

import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.Campaign;
import com.adobe.marketing.mobile.Identity;
import com.adobe.marketing.mobile.InvalidInitException;
import com.adobe.marketing.mobile.Lifecycle;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;
import com.adobe.marketing.mobile.Signal;
import com.adobe.marketing.mobile.UserProfile;

public class MainApp extends Application {

@Override
public void onCreate() {
super.onCreate();

MobileCore.setApplication(this);
MobileCore.setLogLevel(LoggingMode.DEBUG);

try{
    Campaign.registerExtension();
    UserProfile.registerExtension();
    Identity.registerExtension();
    Lifecycle.registerExtension();
    Signal.registerExtension();
    MobileCore.start(new AdobeCallback () {
        @Override
        public void call(Object o) {
            MobileCore.configureWithAppID("copy your launch property id here");
        }
    });
} catch (InvalidInitException e) {
    Log.d("ACS Exception", "exception");
}
}
}
```

第32行，您必須提供[!UICONTROL &#x200B; Launch]屬性的環境檔案識別碼。 您可從[!UICONTROL Launch]屬性的[!UICONTROL environment tab]存取此專案。

![啟動識別碼](assets/launch-id-property.PNG)
