---
title: 步驟 3－在您的行動應用程式中註冊擴充功能
description: 在本部分，我們將添加代碼以註冊UserProfile、Identity、Lifecycle和Signal擴展。
feature: Push
kt: 4827
doc-type: tutorial
activity: use
team: TM
exl-id: d8c0d8c6-2e04-4c27-b27a-d0de79dd953b
source-git-commit: ada0b029245190f53d58fa93c79c161719bfe9fd
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 11%

---

# 步驟 3－在您的行動應用程式中註冊擴充功能

在本部分中，我們將添加用於註冊用戶配置檔案、身份、生命週期和信號擴展的代碼。 這些擴展是 [[!UICONTROL Mobile Core Extensions]](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core)。 我們還需要註冊以下代碼所示的Adobe Campaign Standard分機。

在中開啟項目 [!DNL Android] 工作室。 刪除MainApp中的整個代碼 **除了第一行是您的包語句**。

將以下代碼貼上到MainApp

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

32線[!UICONTROL  Launch] 屬性的環境檔案ID。 可以從 [!UICONTROL environment tab] 你 [!UICONTROL Launch] 屬性。

![啟動ID](assets/launch-id-property.PNG)
