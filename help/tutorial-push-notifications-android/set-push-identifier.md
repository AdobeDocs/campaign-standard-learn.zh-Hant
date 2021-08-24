---
title: 步驟4 — 設定pushidentifier
description: '**pushIdentifier**是包含推播通知之裝置代號的字串。 此代號與Firebase所傳送的代號相同，會使用MobileCore.setPushIdentifier方法傳遞至SDK。'
feature: 推播
kt: 4828
doc-type: tutorial
activity: use
team: TM
exl-id: 08387b84-edaa-45ee-ae66-53bcbd5c7c39
source-git-commit: 5a2f8c9a78bf5100b272f9b4461131545b3aeb8b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 步驟4 — 設定[!DNL pushidentifier]

**[!DNL pushidentifier]**&#x200B;是包含[!DNL Push]通知之裝置代號的字串。 此代號與[!DNL Firebase]傳送的代號相同，會使用[!DNL MobileCore.setPushIdentifier]方法傳遞至SDK。

在[!DNL Android™ ]studio中開啟您的專案。 刪除[!DNL MainActivity] **中的整個代碼，但第一行是您的包語句**。

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

現在是測試應用程式、再繼續操作的好時機。

* 按一下綠色箭頭或選取&#x200B;**[!DNL Run->Run'app']**&#x200B;以執行應用程式。
* [!DNL Android™]模擬器應該會啟動，而您應該會看到應用程式以[!DNL "Hello World" ]文字執行。
* 開啟[!DNL logcat]視窗。 搜尋「[!DNL Got]」。 您應該會看到從[!DNL Firebase]收到並寫入記錄的代號，如下所示。 &quot;[!DNL Got token]&quot;後面的長字串是傳送至Adobe Campaign的[!DNL pushidentifier ]。

![logcat-token](assets/logcat-got-token.PNG)

### 檢查行動應用程式訂閱者

登入您的Adobe Campaign Standard執行個體。
導航**[!UICONTROL Administration->Channels->Mobile App(Experience Platform SDK)]**。 開啟適當的行動應用程式。 頁簽到[!UICONTROL Mobile Application Subscribers]頁簽。 您應會看到[!UICONTROL registration token ]已列出。

![mobile-application-subscribers](assets/mobile-application-subscribers.PNG)

>[!NOTE]
>
>若您未在[!UICONTROL Mobile Application Subscribers]標籤STOP中看到註冊代號，則繼續操作。
