---
title: 步驟1 —— 建立Android應用程式並設定使用Firebase Cloud訊息
description: 在本部分，我們將建立從Adobe Campaign Standard發送的 [!DNL Android] App to receive [!UICONTROL Push notifications] 。 若要接收推播通知，應用程式必須向Google的 [!DNL Firebase Cloud Service]註冊。
feature: 推播
kt: 4825
doc-type: tutorial
activity: use
team: TM
exl-id: f087d9f2-cce9-4903-977f-3c5b47522c06
translation-type: tm+mt
source-git-commit: ada0b029245190f53d58fa93c79c161719bfe9fd
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 3%

---

# 步驟1 —— 建立[!DNL Android]應用程式並配置為使用[!DNL Firebase Cloud Messaging]

在此部分，您將建立[!DNL Android]應用程式以接收從Adobe Campaign Standard發送的[!UICONTROL Push notifications]。 若要接收推播通知，應用程式必須向Google的[!DNL Firebase Cloud Service]註冊。

1. 登入您的[!DNL Firebase]帳戶。

   [!DNL Firebase] 是Google的行動平台，可協助您快速開發高品質應用程式。如果您沒有[!DNL Firebase]帳戶，請從這裡建立一個[。](https://firebase.google.com)

2. 啟動[!DNL Android Studio]
3. 按一下&#x200B;**[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL New Project]。**
4. 選取 **[!UICONTROL Empty Activity]** 並按一下 **[!UICONTROL Next]。**

   ![android-project](assets/android-project.PNG)

5. 為專案提供有意義的名稱。

   在本展示中，我們將專案命名為&#x200B;*[!DNL ACSPushTutorial]*

   ![android-project-configuration](assets/android-project-configuration.PNG)

6. 接受預設包名，然後按一下&#x200B;**[!DNL Finish]**&#x200B;建立項目。
7. 您的專案結構應類似下方的螢幕擷取畫面

   ![android-project-structure](assets/android-project-structure.PNG)

8. 按一下 **[!UICONTROL Tools]** > **[!UICONTROL Firebase].** (這會將專案新增至 [!DNL Firebase])
9. 按一下 **[!UICONTROL Set up Firebase Cloud Messaging]。**

   ![設定防火牆](assets/android-project-firebase-messaging.PNG)

10. 按一下 **[!UICONTROL Connect to Firebase]。**
11. 在您的應用程式連線至Firebase後，按一下&#x200B;**[!UICONTROL Add FCM to your app]。**
12. 按一下 **[!UICONTROL Accept Changes]。**

   當您將FCM新增至應用程式時，精靈需要您的權限才能對專案進行一些變更。

   ![[!DNL add-fcm-to-your-app]](assets/firebase-add-fcm-to-app.PNG)

在應用程式成功與Firebase整合後，您應該會收到如下所示的訊息：

![[!DNL fcm-successfull]](assets/android-firebase-success.PNG)

[確定您的專案已列在主控台 [!DNL Firebase ]中](https://console.firebase.google.com/)

## 配置[!UICONTROL Push Channel]設定

1. 登錄至[!DNL Firebase]控制台
2. 開啟&#x200B;**[!UICONTROL ACSPushTutorial]**&#x200B;專案。
3. 按一下&#x200B;**齒輪表徵圖**&#x200B;並開啟項目設定

   ![project-settings](assets/firebase-project-settings.PNG)

4. 頁籤至&#x200B;**[!UICONTROL Cloud Messaging]**&#x200B;頁籤。
5. 複製伺服器密鑰

   ![server-key](assets/firebase-server-key.PNG)

6. 登入您的Adobe Campaign Standard實例
7. 按一下&#x200B;**[!UICONTROL Adobe Campaign]** > **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile App]。**
8. 選擇適當的&#x200B;**[!UICONTROL Mobile Application Property]。**
9. 按一下&#x200B;**[!UICONTROL Push Channel settings]**&#x200B;部分中的&#x200B;**[!DNL Android]表徵圖**。
10. 將伺服器密鑰貼上到伺服器密鑰欄位中。

如果一切順利，您應該會看到SUCCESS訊息。

![推播頻道設定](assets/push-channel-settings.PNG)

總之，我們建立了[!DNL Android App] ，並將[!DNL Android App]與[!DNL Firebase]連接。 然後，我們將[!DNL Android]應用程式的伺服器金鑰貼入Adobe Campaign Standard的行動應用程式，將[!DNL Android App]連線至Adobe Campaign的行動應用程式。
