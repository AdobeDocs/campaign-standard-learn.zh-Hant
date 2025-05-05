---
title: 步驟1 — 建立Android應用程式並設定為使用Firebase雲端通訊
description: 在此部分中，我們將建立 [!DNL Android] 應用程式以接收從Adobe Campaign Standard傳送的[!UICONTROL Push notifications]。 若要接收推播通知，應用程式必須向Google的 [!DNL Firebase Cloud Service]註冊。
feature: Push
user: Admin
level: Experienced
jira: KT-4825
doc-type: tutorial
activity: use
team: TM
recommendations: noDisplay
exl-id: f087d9f2-cce9-4903-977f-3c5b47522c06
source-git-commit: 0ad82fb0533ed8fc2a85c2a32c7e54deef14d05a
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# 步驟1 — 建立[!DNL Android]應用程式並設定為使用[!DNL Firebase Cloud Messaging]

在此部分中，您將建立[!DNL Android]應用程式以接收從Adobe Campaign Standard傳送的[!UICONTROL Push notifications]。 若要接收推播通知，應用程式必須向Google的[!DNL Firebase Cloud Service]註冊。

1. 登入您的[!DNL Firebase]帳戶。

   [!DNL Firebase]是Google的行動平台，可幫助您快速開發高品質的應用程式。 如果您沒有[!DNL Firebase]帳戶，請從這裡[&#128279;](https://firebase.google.com)建立一個。

2. 啟動[!DNL Android Studio]
3. 按一下&#x200B;**[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL New Project].**
4. 選取&#x200B;**[!UICONTROL Empty Activity]**&#x200B;並按一下&#x200B;**[!UICONTROL Next].**

   ![android — 專案](assets/android-project.PNG)

5. 為專案提供有意義的名稱。

   為了這個示範的目的，我們已將專案命名為&#x200B;*[!DNL ACSPushTutorial]*

   ![android-project-configuration](assets/android-project-configuration.PNG)

6. 接受預設封裝名稱，然後按一下&#x200B;**[!DNL Finish]**&#x200B;以建立您的專案。
7. 您的專案結構看起來應該類似下列熒幕擷取畫面

   ![android-project-structure](assets/android-project-structure.PNG)

8. 按一下&#x200B;**[!UICONTROL Tools]** > **[!UICONTROL Firebase]。** （這會將專案新增至[!DNL Firebase]）
9. 按一下&#x200B;**[!UICONTROL Set up Firebase Cloud Messaging].**

   ![設定firebase](assets/android-project-firebase-messaging.PNG)

10. 按一下&#x200B;**[!UICONTROL Connect to Firebase].**
11. 在您的應用程式連線到Firebase之後，按一下&#x200B;**[!UICONTROL Add FCM to your app].**
12. 按一下&#x200B;**[!UICONTROL Accept Changes].**

   將FCM新增至應用程式時，精靈需要您的許可權才能對專案進行某些變更。

   ![[!DNL add-fcm-to-your-app]](assets/firebase-add-fcm-to-app.PNG)

應用程式與Firebase成功整合後，您應會收到如下所示的訊息：

![[!DNL fcm-successfull]](assets/android-firebase-success.PNG)

[確定您的專案列在 [!DNL Firebase &#x200B;]主控台](https://console.firebase.google.com/)

## 設定[!UICONTROL Push Channel]設定

1. 登入[!DNL Firebase]主控台
2. 開啟&#x200B;**[!UICONTROL ACSPushTutorial]**&#x200B;專案。
3. 按一下&#x200B;**齒輪圖示**&#x200B;並開啟專案設定

   ![專案設定](assets/firebase-project-settings.PNG)

4. 以Tab鍵前往&#x200B;**[!UICONTROL Cloud Messaging]**&#x200B;標籤。
5. 複製伺服器金鑰

   ![伺服器金鑰](assets/firebase-server-key.PNG)

6. 登入Adobe Campaign Standard執行個體
7. 按一下「**[!UICONTROL Adobe Campaign]** > **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile App].**」
8. 選取適當的&#x200B;**[!UICONTROL Mobile Application Property].**
9. 按一下&#x200B;**[!UICONTROL Push Channel settings]**&#x200B;區段中的&#x200B;**[!DNL Android]圖示**。
10. 在伺服器金鑰欄位中貼上伺服器金鑰。

如果一切順利，您應該會看到SUCCESS訊息。

![推播通道設定](assets/push-channel-settings.PNG)

總而言之，我們已建立[!DNL Android App]並連線[!DNL Android App]與[!DNL Firebase]。 接著，我們將[!DNL Android]應用程式的伺服器金鑰貼入Adobe Campaign中的行動應用程式，藉此將Adobe Campaign Standard中的行動應用程式與[!DNL Android App]連線。
