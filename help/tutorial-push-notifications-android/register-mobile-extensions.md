---
title: 步驟3 —— 在您的行動應用程式中註冊擴充功能
description: 在本部分，我們將添加代碼來註冊UserProfile、Identity、Lifecycle和Signal擴展。
feature: Push
topics: Mobile
kt: 4827
doc-type: tutorial
activity: use
team: TM
translation-type: tm+mt
source-git-commit: 13b4f1d395dfe53f9fc5263e7b06be700e30b986
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 0%

---


# 步驟3 —— 在您的行動應用程式中註冊擴充功能

在本部分，我們將添加代碼來註冊用戶配置檔案、身份、生命週期和信號擴展。 這些擴充功能是[[!UICONTROL Mobile Core Extensions]](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core)的一部分。 我們也需要註冊Adobe Campaign Standard擴充功能，如以下程式碼所示。

在[!DNL Android]工作室中開啟您的專案。 刪除MainApp **中的整個代碼，但第一行是您的package語句**。

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

第32行需要提供[!UICONTROL  Launch]屬性的環境檔案ID。 您可從[!UICONTROL Launch]屬性的[!UICONTROL environment tab]存取此項。

![launch-id](assets/launch-id-property.PNG)
