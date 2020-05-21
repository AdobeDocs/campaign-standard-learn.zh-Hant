---
title: 步驟4 —— 設定密碼符
description: '**pushIdentifier**是包含推播通知之裝置Token的字串。 這是Firebase所傳送並使用MobileCore.setPushIdentifier方法傳遞至SDK的相同Token。'
feature: Push
topics: MOBILE
kt: 4828
doc-type: tutorial
activity: use
team: TM
translation-type: tm+mt
source-git-commit: a2f194821a9ce06272eaed979ee2d8c62cccac2b
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# 步驟4 —— 設定 [!DNL pushidentifier]

此字 **[!DNL pushidentifier]** 串包含通知的裝置Token [!DNL Push] 。 這是由傳送並使用方 [!DNL Firebase] 法傳遞至SDK的相同代 [!DNL MobileCore.setPushIdentifier] 號。

在Studio中開啟您的 [!DNL Android ]專案。 刪除中的整個代 [!DNL MainActivity] 碼， **但第一行是包語句**。

將下列程式碼貼入 [!DNL MainActivity]:

```java{.line-numbers}
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

* 按一下綠色箭頭或選取，以執行您的應用程式 **[!DNL Run->Run'app']**。
* 模擬 [!DNL Android] 器應該會啟動，而且您應會看到應用程式以文字 [!DNL "Hello World" ]執行。
* 開啟窗 [!DNL logcat] 戶。 搜尋「[!DNL Got]」。 您應該會看到從寫入記錄檔 [!DNL Firebase] 中收到的Token，如下所示。 &quot;&quot;後面的長[!DNL Got token]字串是傳 [!DNL pushidentifier ]送至Adobe Campaign的字串。

![logcat-token](assets/logcat-got-token.PNG)

### 檢查行動應用程式訂閱者

登入您的Adobe Campaign Standard實例。
導覽 **[!UICONTROL Administration->Channels->Mobile App(AEP SDK)]**。 開啟適當的行動應用程式。 頁籤 [!UICONTROL Mobile Application Subscribers] 中。 您應該會看到 [!UICONTROL registration token ]清單。

![行動應用程式用戶](assets/mobile-application-subscribers.PNG)

>[注意]
>如果您未在此標籤STOP中看到註冊Token, [!UICONTROL Mobile Application Subscribers] 然後再繼續進行任何操作。
