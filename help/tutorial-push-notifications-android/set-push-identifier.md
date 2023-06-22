---
title: 步驟4 — 設定pushidentifier
description: '**pushIdentifier**是包含推播通知的裝置代號的字串。 這是由Firebase傳送並使用MobileCore.setPushIdentifier方法傳遞至SDK的相同Token。'
feature: Push
jira: KT-4828
doc-type: tutorial
activity: use
team: TM
exl-id: 08387b84-edaa-45ee-ae66-53bcbd5c7c39
source-git-commit: c84867ef59a10448a377a959d0b67ae71343a4aa
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# 步驟4 — 設定 [!DNL pushidentifier]

此 **[!DNL pushidentifier]** 是字串，其中包含裝置代號 [!DNL Push] 通知。 這是由傳送的相同Token [!DNL Firebase] 和會傳遞至SDK，使用 [!DNL MobileCore.setPushIdentifier] 方法。

在中開啟您的專案 [!DNL Android™]工作室。 刪除中的整個程式碼 [!DNL MainActivity] **第一行是您的封裝陳述式除外**.

將下列程式碼貼入 [!DNL MainActivity]：

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

## 測試您的應用程式

現在正是測試您的應用程式的好時機，之後可再繼續測試。

* 按一下綠色箭頭或選取「 」以執行您的應用程式 **[!DNL Run->Run'app']**.
* 此 [!DNL Android™] 模擬器應會啟動，而您應會看到應用程式執行中 [!DNL "Hello World"]文字。
* 開啟 [!DNL logcat] 視窗。 搜尋&quot;[!DNL Got]「。 您應該會看到從收到的權杖 [!DNL Firebase] 寫入記錄檔中，如下所示。 「 」之後的長字串[!DNL Got token]「是 [!DNL pushidentifier]會傳送至Adobe Campaign的資訊。

![logcat-token](assets/logcat-got-token.PNG)

### 檢查行動應用程式訂閱者

登入您的Adobe Campaign Standard執行個體。
導覽 **[!UICONTROL Administration->Channels->Mobile App(Experience Platform SDK)]**. 開啟適當的行動應用程式。 按Tab鍵前往 [!UICONTROL Mobile Application Subscribers] 標籤。 您應會看到 [!UICONTROL registration token]列出。

![行動應用程式訂閱者](assets/mobile-application-subscribers.PNG)

>[!NOTE]
>
>如果您在中看不到註冊權杖 [!UICONTROL Mobile Application Subscribers] 按TAB鍵在此停下，再繼續下一步驟。
