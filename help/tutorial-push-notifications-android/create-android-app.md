---
title: 步驟1 — 建立Android App並配置為使用Firebase雲消息
description: 在此部分，我們將建立 [!DNL Android] 要接收的應用 [!UICONTROL Push notifications] 從Adobe Campaign Standard寄來的。 要接收推送通知，需要向Google註冊 [!DNL Firebase Cloud Service]。
feature: Push
kt: 4825
doc-type: tutorial
activity: use
team: TM
recommendations: noDisplay
exl-id: f087d9f2-cce9-4903-977f-3c5b47522c06
source-git-commit: 57dbf456625d22cd2e4526d92e5a8c20a048d339
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 2%

---

# 步驟1 — 建立 [!DNL Android] 應用和配置以使用 [!DNL Firebase Cloud Messaging]

在此部件中，您將建立 [!DNL Android] 要接收的應用 [!UICONTROL Push notifications] 從Adobe Campaign Standard寄來的。 要接收推送通知，需要向Google註冊 [!DNL Firebase Cloud Service]。

1. 登錄到 [!DNL Firebase] 帳戶。

   [!DNL Firebase] 是Google的移動平台，幫助您快速開發高質量應用。 如果你沒有 [!DNL Firebase] 帳戶，請建立一個 [從這裡](https://firebase.google.com)。

2. 啟動 [!DNL Android Studio]
3. 按一下 **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL New Project]。**
4. 選取 **[!UICONTROL Empty Activity]** 並按一下 **[!UICONTROL Next]。**

   ![android項目](assets/android-project.PNG)

5. 為項目提供有意義的名稱。

   為了進行本演示，我們將項目命名為 *[!DNL ACSPushTutorial]*

   ![android項目配置](assets/android-project-configuration.PNG)

6. 接受預設包名稱，然後按一下 **[!DNL Finish]** 建立項目。
7. 您的項目結構應與下面的螢幕抓圖類似

   ![android項目結構](assets/android-project-structure.PNG)

8. 按一下 **[!UICONTROL Tools]** > **[!UICONTROL Firebase].** (這將項目添加到 [!DNL Firebase])
9. 按一下&#x200B;**[!UICONTROL Set up Firebase Cloud Messaging]。**

   ![設定firebase](assets/android-project-firebase-messaging.PNG)

10. 按一下&#x200B;**[!UICONTROL Connect to Firebase]。**
11. 在您的應用連接到Firebase後，按一下 **[!UICONTROL Add FCM to your app]。**
12. 按一下&#x200B;**[!UICONTROL Accept Changes]。**

   將FCM添加到應用時，嚮導需要您的權限對項目進行一些更改。

   ![[!DNL add-fcm-to-your-app]](assets/firebase-add-fcm-to-app.PNG)

成功將應用與Firebase整合後，您應收到如下消息：

![[!DNL fcm-successfull]](assets/android-firebase-success.PNG)

[確保項目列在 [!DNL Firebase ]控制台](https://console.firebase.google.com/)

## 配置 [!UICONTROL Push Channel] 設定

1. 登錄到 [!DNL Firebase] 控制台
2. 開啟 **[!UICONTROL ACSPushTutorial]** 項目。
3. 按一下 **齒輪表徵圖** 開啟項目設定

   ![項目設定](assets/firebase-project-settings.PNG)

4. 頁籤 **[!UICONTROL Cloud Messaging]** 頁籤。
5. 複製伺服器密鑰

   ![伺服器密鑰](assets/firebase-server-key.PNG)

6. 登錄到您的Adobe Campaign Standard實例
7. 按一下 **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile App]。**
8. 選擇相應的 **[!UICONTROL Mobile Application Property]。**
9. 按一下 **[!DNL Android]表徵圖** 的 **[!UICONTROL Push Channel settings]** 的子菜單。
10. 在伺服器密鑰欄位中貼上伺服器密鑰。

如果一切順利，您應看到SUCCESS消息。

![推送通道設定](assets/push-channel-settings.PNG)

總而言之，我們建立了 [!DNL Android App] 連接 [!DNL Android App] 與 [!DNL Firebase]。 然後，我們將Adobe Campaign的移動應用程式 [!DNL Android App] 通過貼上 [!DNL Android] 在Adobe Campaign Standard移動應用中的應用伺服器密鑰。
