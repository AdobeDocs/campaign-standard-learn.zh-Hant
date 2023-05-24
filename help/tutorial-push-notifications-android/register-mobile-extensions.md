---
title: 步驟 3－在您的行動應用程式中註冊擴充功能
description: 在本部分中，我們將新增程式碼以註冊UserProfile、Identity、Lifecycle和Signal擴充功能。
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

在本部分中，我們將新增程式碼以註冊使用者設定檔、身分、生命週期和訊號擴充功能。 這些擴充功能屬於 [[!UICONTROL Mobile Core Extensions]](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core). 我們還需要註冊Adobe Campaign Standard擴充功能，如下所示。

在中開啟您的專案 [!DNL Android] 工作室。 刪除MainApp中的整個程式碼 **第一行是您的封裝陳述式除外**.

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

第32行，您需要提供[!UICONTROL  Launch] 屬性的環境檔案識別碼。 這可以從以下位置存取： [!UICONTROL environment tab] 的 [!UICONTROL Launch] 屬性。

![launch-id](assets/launch-id-property.PNG)
