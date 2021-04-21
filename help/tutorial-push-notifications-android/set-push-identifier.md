---
title: 步驟4 —— 設定密碼符
description: '**pushIdentifier**是包含推播通知之裝置Token的字串。 這是Firebase所傳送並使用MobileCore.setPushIdentifier方法傳遞至SDK的相同Token。'
feature: 推播
topic: 行動
kt: 4828
doc-type: tutorial
activity: use
team: TM
exl-id: 08387b84-edaa-45ee-ae66-53bcbd5c7c39
translation-type: tm+mt
source-git-commit: ddbb0843ea45a83d9ab5bfa0877287f6ba7d6210
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%

---

# 步驟4 —— 設定[!DNL pushidentifier]

**[!DNL pushidentifier]**&#x200B;是包含[!DNL Push]通知之裝置Token的字串。 這是[!DNL Firebase]所傳送並使用[!DNL MobileCore.setPushIdentifier]方法傳遞至SDK的相同Token。

在[!DNL Android ]studio中開啟您的專案。 刪除[!DNL MainActivity] **中的整個代碼，但第一行是您的package語句**。

將下列程式碼貼入[!DNL MainActivity]:

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

現在是測試您應用程式的好時機，再做進一步的測試。

* 按一下綠色箭頭或選取&#x200B;**[!DNL Run->Run'app']**，以執行您的應用程式。
* [!DNL Android]模擬器應該會啟動，您應該會看到應用程式以[!DNL "Hello World" ]文字執行。
* 開啟[!DNL logcat]窗口。 搜尋「[!DNL Got]」。 您應看到從[!DNL Firebase]寫入記錄檔中收到的代號，如下所示。 &quot;[!DNL Got token]&quot;後面的長字串是傳送至Adobe Campaign的[!DNL pushidentifier ]。

![logcat-token](assets/logcat-got-token.PNG)

### 檢查行動應用程式訂閱者

登入您的Adobe Campaign Standard實例。
導覽**[!UICONTROL Administration->Channels->Mobile App(AEP SDK)]**。 開啟適當的行動應用程式。 頁籤至[!UICONTROL Mobile Application Subscribers]頁籤。 您應該會看到[!UICONTROL registration token ]已列出。

![行動應用程式用戶](assets/mobile-application-subscribers.PNG)

>[!NOTE]
>
>如果您在[!UICONTROL Mobile Application Subscribers]標籤STOP中未看到註冊Token，然後再繼續執行任何操作。
