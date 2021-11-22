---
title: 步驟4 — 設定pushidentifier
description: '**pushIdentifier**是包含推播通知之裝置代號的字串。 此代號與Firebase所傳送的代號相同，會使用MobileCore.setPushIdentifier方法傳遞至SDK。'
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

此 **[!DNL pushidentifier]** 是字串，其中包含 [!DNL Push] 通知。 它是由傳送的相同Token [!DNL Firebase] 和會透過 [!DNL MobileCore.setPushIdentifier] 方法。

在 [!DNL Android™ ]工作室。 刪除 [!DNL MainActivity] **除了第一行，它是您的包語句**.

將下列程式碼貼入 [!DNL MainActivity]:

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

現在是測試應用程式、再繼續操作的好時機。

* 按一下綠色箭頭或選取以執行應用程式 **[!DNL Run->Run'app']**.
* 此 [!DNL Android™] 模擬器應會啟動，而您應會看到應用程式正在執行 [!DNL "Hello World" ]文字。
* 開啟 [!DNL logcat] 窗口。 搜索「[!DNL Got]」。 您應會看到從 [!DNL Firebase] 寫入記錄檔，如下所示。 後面的長字串[!DNL Got token]「是 [!DNL pushidentifier ]被發送到Adobe Campaign。

![logcat-token](assets/logcat-got-token.PNG)

### 檢查行動應用程式訂閱者

登入您的Adobe Campaign Standard執行個體。
導覽 **[!UICONTROL Administration->Channels->Mobile App(Experience Platform SDK)]**. 開啟適當的行動應用程式。 標籤 [!UICONTROL Mobile Application Subscribers] 標籤。 您應會看到 [!UICONTROL registration token ]已列出。

![mobile-application-subscribers](assets/mobile-application-subscribers.PNG)

>[!NOTE]
>
>如果您在 [!UICONTROL Mobile Application Subscribers] 標籤在此停止，然後再繼續。
