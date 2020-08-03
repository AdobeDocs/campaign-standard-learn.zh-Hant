---
title: 步驟1 —— 建立Android應用程式並設定使用Firebase Cloud訊息
description: 在本部分，我們將 [!DNL Android] App to receive [!UICONTROL Push notifications] 從Adobe Campaign Standard建立。 為了接收推播通知，應用程式必須向Google的註冊 [!DNL Firebase Cloud Service]。
feature: Push
topics: Mobile
kt: 4825
doc-type: tutorial
activity: use
team: TM
translation-type: tm+mt
source-git-commit: afe1ae6c8d73b7b776e0eec327fa16db76c23ce1
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 2%

---


# 步驟1 —— 建立應 [!DNL Android] 用程式並設定使用 [!DNL Firebase Cloud Messaging]

在本部分，您將建立應 [!DNL Android] 用程式，以接 [!UICONTROL Push notifications] 收從Adobe Campaign Standard傳送。 若要接收推播通知，應用程式必須向Google的註冊 [!DNL Firebase Cloud Service]。

1. 登入您的 [!DNL Firebase] 帳戶。

   [!DNL Firebase] 是Google的行動平台，可協助您快速開發高品質應用程式。 如果您沒有帳 [!DNL Firebase] 戶，請從這裡 [建立](https://firebase.google.com)。

2. 啟動 [!DNL Android Studio]
3. Click **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL New Project].**
4. 選取 **[!UICONTROL Empty Activity]** 並按一下 **[!UICONTROL Next]。**

   ![android-project](assets/android-project.PNG)

5. 為專案提供有意義的名稱。

   為了進行本展示，我們將專案命名為 *[!DNL ACSPushTutorial]*

   ![android-project-configuration](assets/android-project-configuration.PNG)

6. 接受預設套件名稱，然後按一 **[!DNL Finish]** 下以建立專案。
7. 您的專案結構應類似下方的螢幕擷取畫面

   ![android-project-structure](assets/android-project-structure.PNG)

8. 按一下 **[!UICONTROL Tools]** > **[!UICONTROL Firebase].**(這會將專案新增至[!DNL Firebase])
9. 按一下 **[!UICONTROL Set up Firebase Cloud Messaging]。**

   ![設定防火牆](assets/android-project-firebase-messaging.PNG)

10. 按一下 **[!UICONTROL Connect to Firebase]。**
11. 在您的應用程式連線至Firebase後，按一下 **[!UICONTROL Add FCM to your app]。**
12. 按一下 **[!UICONTROL Accept Changes]。**

   當您將FCM新增至應用程式時，精靈需要您的權限才能對專案進行一些變更。

   ![[!DNL add-fcm-to-your-app]](assets/firebase-add-fcm-to-app.PNG)

在應用程式成功與Firebase整合後，您應該會收到如下所示的訊息：

![[!DNL fcm-successfull]](assets/android-firebase-success.PNG)

[確定您的專案已列在主控台 [!DNL Firebase ]中](https://console.firebase.google.com/)

## 設定設 [!UICONTROL Push Channel] 定

1. 登入主控 [!DNL Firebase] 台
2. 開啟專 **[!UICONTROL ACSPushTutorial]** 案。
3. 按一下齒 **輪圖示** ，並開啟專案設定

   ![project-settings](assets/firebase-project-settings.PNG)

4. Tab to the **[!UICONTROL Cloud Messaging]** tab.
5. 複製伺服器密鑰

   ![server-key](assets/firebase-server-key.PNG)

6. 登入您的Adobe Campaign Standard實例
7. Click **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile App].**
8. 選擇適當的 **[!UICONTROL Mobile Application Property]。**
9. 按一下 **[!DNL Android]區段中&#x200B;**的&#x200B;**[!UICONTROL Push Channel settings]**圖示。
10. 將伺服器密鑰貼上到伺服器密鑰欄位中。

如果一切順利，您應該會看到SUCCESS訊息。

![推播頻道設定](assets/push-channel-settings.PNG)

總之，我們已建立並 [!DNL Android App] 將其連 [!DNL Android App] 結在 [!DNL Firebase]。 然後，我們將應用程式的伺服器金鑰貼 [!DNL Android App] 入Adobe Campaign Standard中的行動應用程式，以連線 [!DNL Android] Adobe Campaign中的行動應用程式。
