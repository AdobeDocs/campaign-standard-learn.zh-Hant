---
title: 步驟4 — 設定pushidentifier
description: '**pushIdentifier**是包含推送通知之裝置代號的字串。 此代號與Firebase傳送的代號相同，並使用MobileCore.setPushIdentifier方法傳遞至SDK。'
feature: Push
user: Admin
level: Experienced
jira: KT-4828
doc-type: tutorial
activity: use
team: TM
exl-id: 08387b84-edaa-45ee-ae66-53bcbd5c7c39
source-git-commit: 757afce50981b96b7820c987308d639a73746c0c
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# 步驟4 — 設定[!DNL pushidentifier]

**[!DNL pushidentifier]**&#x200B;是包含[!DNL Push]通知的裝置權杖的字串。 它與[!DNL Firebase]傳送並使用[!DNL MobileCore.setPushIdentifier]方法傳遞至SDK的Token相同。

在[!DNL Android™]工作室中開啟您的專案。 刪除[!DNL MainActivity] **中的整個程式碼，但第一行是您的封裝陳述式**&#x200B;除外。

將下列程式碼貼到[!DNL MainActivity]中：

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

在前往下一步前，您可以先測試您的應用程式。

* 按一下綠色箭頭或選取&#x200B;**[!DNL Run->Run'app']**&#x200B;以執行您的應用程式。
* [!DNL Android™]模擬器應該會啟動，而且您應該會看到應用程式正在執行[!DNL "Hello World"]文字。
* 開啟[!DNL logcat]視窗。 搜尋&quot;[!DNL Got]&quot;。 您應該會看到從[!DNL Firebase]收到的權杖已寫入記錄檔，如下所示。 「[!DNL Got token]」之後的長字串是傳送至Adobe Campaign的[!DNL pushidentifier]。

![logcat-token](assets/logcat-got-token.PNG)

### 檢查行動應用程式訂閱者

登入您的Adobe Campaign Standard執行個體。
瀏覽&#x200B;**[!UICONTROL Administration->Channels->Mobile App(Experience Platform SDK)]**。 開啟適當的行動應用程式。 以Tab鍵前往[!UICONTROL Mobile Application Subscribers]標籤。 您應該會看到[!UICONTROL registration token]已列出。

![行動應用程式訂閱者](assets/mobile-application-subscribers.PNG)

>[!NOTE]
>
>如果您在[!UICONTROL Mobile Application Subscribers]索引標籤中看不到註冊權杖，請先在此停止，再繼續下一步。
