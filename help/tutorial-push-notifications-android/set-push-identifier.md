---
title: 步驟4 — 設定推信器
description: '**pushIdentifier**是包含用於推送通知的設備令牌的字串。 它與Firebase發送的令牌相同，並使用MobileCore.setPushIdentifier方法傳遞給SDK。'
feature: Push
kt: 4828
doc-type: tutorial
activity: use
team: TM
exl-id: 08387b84-edaa-45ee-ae66-53bcbd5c7c39
source-git-commit: 5a2f8c9a78bf5100b272f9b4461131545b3aeb8b
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# 步驟4 — 設定 [!DNL pushidentifier]

的 **[!DNL pushidentifier]** 是包含的設備令牌的字串 [!DNL Push] 通知。 它是由 [!DNL Firebase] 並使用 [!DNL MobileCore.setPushIdentifier] 的雙曲餘切值。

在中開啟項目 [!DNL Android™ ]工作室。 刪除中的整個代碼 [!DNL MainActivity] **除了第一行是您的包語句**。

將以下代碼貼上到 [!DNL MainActivity]:

<!--
Removed `{.line-numbers}` below
-->

```java
import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.util.Log;
import android.widget.Toast;

import com.adobe.marketing.mobile.MobileCore;
import com.google.android.gms.tasks.OnCompleteListener;
import com.google.android.gms.tasks.Task;
import com.google.firebase.iid.FirebaseInstanceId;
import com.google.firebase.iid.InstanceIdResult;

public class MainActivity extends AppCompatActivity {

@Override
protected void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.activity_main);

registerToken();
}

void registerToken() {
FirebaseInstanceId.getInstance().getInstanceId()
    .addOnCompleteListener(new OnCompleteListener<InstanceIdResult>() {
        @Override
        public void onComplete(@NonNull Task<InstanceIdResult> task) {
            if (!task.isSuccessful()) {
                Log.w("Message App", "getInstanceId failed", task.getException());
                return;
            }

// Get new Instance ID token
String token = task.getResult().getToken();

Log.d("Got token", token);

MobileCore.setPushIdentifier(token);
}
});
}

@Override
public void onResume() {
super.onResume();
MobileCore.setApplication(getApplication());
MobileCore.lifecycleStart(null);
}

@Override
public void onPause() {
super.onPause();
MobileCore.lifecyclePause();
}
}
```

## Test你的應用

現在是test應用的好時機，然後再繼續操作。

* 通過按一下綠色箭頭或選擇來運行應用程式 **[!DNL Run->Run'app']**。
* 的 [!DNL Android™] 模擬程式應啟動，您應看到您的應用正在運行 [!DNL "Hello World" ]的子菜單。
* 開啟 [!DNL logcat] 的子菜單。 搜索「」[!DNL Got]。 您應該看到從 [!DNL Firebase] 寫入日誌，如下所示。 「」之後的長字串[!DNL Got token]」 [!DNL pushidentifier ]被送到Adobe Campaign。

![邏輯標籤](assets/logcat-got-token.PNG)

### 檢查移動應用程式訂閱者

登錄到您的Adobe Campaign Standard實例。
導航 **[!UICONTROL Administration->Channels->Mobile App(Experience Platform SDK)]**。 開啟相應的移動應用程式。 頁籤 [!UICONTROL Mobile Application Subscribers] 頁籤。 你應該看到 [!UICONTROL registration token ]清單。

![移動應用用戶](assets/mobile-application-subscribers.PNG)

>[!NOTE]
>
>如果在中未看到註冊標籤 [!UICONTROL Mobile Application Subscribers] 頁籤STOP ，然後繼續。
