---
title: 步驟1 — 建立Android應用程式和設定以使用Firebase雲端訊息
description: 在此部分，我們將建立 [!DNL Android] App to receive [!UICONTROL Push notifications] 寄自Adobe Campaign Standard。 若要接收推播通知，應用程式必須向Google註冊 [!DNL Firebase Cloud Service].
feature: Push
kt: 4825
doc-type: tutorial
activity: use
team: TM
exl-id: f087d9f2-cce9-4903-977f-3c5b47522c06
source-git-commit: ada0b029245190f53d58fa93c79c161719bfe9fd
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 2%

---

# 步驟1 — 建立 [!DNL Android] 應用程式和設定以使用 [!DNL Firebase Cloud Messaging]

在此部分，您將建立 [!DNL Android] 要接收的應用程式 [!UICONTROL Push notifications] 寄自Adobe Campaign Standard。 若要接收推播通知，應用程式必須向Google註冊 [!DNL Firebase Cloud Service].

1. 登入 [!DNL Firebase] 帳戶。

   [!DNL Firebase] 是Google的行動平台，可協助您快速開發高品質應用程式。 如果您沒有 [!DNL Firebase] 帳戶，請建立一個 [從這裡](https://firebase.google.com).

2. Launch [!DNL Android Studio]
3. 按一下 **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL New Project].**
4. 選取 **[!UICONTROL Empty Activity]** 並按一下 **[!UICONTROL Next]。**

   ![android-project](assets/android-project.PNG)

5. 為專案提供有意義的名稱。

   為了進行本示範，我們將專案命名為 *[!DNL ACSPushTutorial]*

   ![android-project-configuration](assets/android-project-configuration.PNG)

6. 接受預設包名，然後按一下 **[!DNL Finish]** 來建立專案。
7. 您的專案結構應該看起來類似下方的螢幕擷取畫面

   ![android-project-structure](assets/android-project-structure.PNG)

8. 按一下 **[!UICONTROL Tools]** > **[!UICONTROL Firebase].** (這會將專案新增至 [!DNL Firebase])
9. 按一下&#x200B;**[!UICONTROL Set up Firebase Cloud Messaging]。**

   ![設定firebase](assets/android-project-firebase-messaging.PNG)

10. 按一下&#x200B;**[!UICONTROL Connect to Firebase]。**
11. 將應用程式連線至Firebase後，按一下 **[!UICONTROL Add FCM to your app].**
12. 按一下&#x200B;**[!UICONTROL Accept Changes]。**

   將FCM新增至應用程式時，精靈需要您的權限才能對專案進行一些變更。

   ![[!DNL add-fcm-to-your-app]](assets/firebase-add-fcm-to-app.PNG)

當應用程式與Firebase成功整合時，您應該會收到如下所示的訊息：

![[!DNL fcm-successfull]](assets/android-firebase-success.PNG)

[確認您的專案列於 [!DNL Firebase ]主控台](https://console.firebase.google.com/)

## 設定 [!UICONTROL Push Channel] 設定

1. 登入 [!DNL Firebase] 主控台
2. 開啟 **[!UICONTROL ACSPushTutorial]** 專案。
3. 按一下 **齒輪表徵圖** 並開啟專案設定

   ![專案設定](assets/firebase-project-settings.PNG)

4. 標籤 **[!UICONTROL Cloud Messaging]** 標籤。
5. 複製伺服器密鑰

   ![server-key](assets/firebase-server-key.PNG)

6. 登入Adobe Campaign Standard執行個體
7. 按一下 **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile App].**
8. 選取適當的 **[!UICONTROL Mobile Application Property].**
9. 按一下 **[!DNL Android]圖示** 在 **[!UICONTROL Push Channel settings]** 區段。
10. 將伺服器金鑰貼入伺服器金鑰欄位中。

如果一切順利，您應會看到SUCCESS訊息。

![推播頻道設定](assets/push-channel-settings.PNG)

總之，我們已建立 [!DNL Android App] 並連接 [!DNL Android App] with [!DNL Firebase]. 接著，我們連線Adobe Campaign的行動應用程式， [!DNL Android App] 貼上 [!DNL Android] Adobe Campaign Standard中行動應用程式中應用程式的伺服器金鑰。
