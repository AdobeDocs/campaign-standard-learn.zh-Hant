---
title: 應用程式內訊息簡介
description: 瞭解如何根據客戶在行動應用程式內的即時行為，向使用者呈現內容相關的應用程式內訊息。
feature: In App
kt: 1911
doc-type: feature video
activity: use
team: TM
exl-id: c51716eb-7239-4fc0-9ccf-9f5f0a5fae65
role: User
level: Beginner
source-git-commit: 57dbf456625d22cd2e4526d92e5a8c20a048d339
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 10%

---

# 簡介 [!UICONTROL In-App] 訊息 {#introduction}

此 [!UICONTROL In-App Messaging] 頻道可讓您在使用者於行動應用程式內活動時顯示訊息。 此管道需要整合行動應用程式 [!UICONTROL Adobe Experience Platform SDK].

本教學課程說明設定行動屬性所需的步驟， [!UICONTROL Launch] 的擴充功能 [!UICONTROL In-App Messaging] 頻道，以及如何準備、自訂和傳送 [!UICONTROL In-App] Adobe Campaign Standard中的訊息。 這些連結會引導您前往每個反白主題的影片教學課程。

## 必要條件 {#prerequisites}

1. 請確定您可以存取 **[!UICONTROL In-App]** 頻道。 如果您無法存取這些通道，請聯絡您的帳戶團隊。
1. 確認您的 **使用者** 具有必要的 **許可權** 在Adobe Campaign Standard和 [!UICONTROL Launch].

   1. 在Adobe Campaign Standard中，確認IMS使用者屬於 [!UICONTROL Standard User] 和 [!UICONTROL Administrator] 群組。

      此步驟可讓使用者登入Adobe Campaign Standard、導覽至Experience Platform SDK行動應用程式頁面，並檢視您在中建立的行動應用程式屬性 [!UICONTROL Launch].

   1. 在 [!UICONTROL Launch]，確認您的IMS使用者屬於 [!UICONTROL Launch] 產品設定檔。 此步驟可讓使用者登入 [!UICONTROL Launch] 以建立和檢視屬性。 在產品設定檔中，公司或屬性上應該沒有許可權設定，但使用者應該能夠仍然登入。

1. 在Adobe Experience Platform Launch中：

   1. 透過建立行動屬性來建立行動應用程式，並使用Experience Platform SDK檢測行動應用程式。
   1. 安裝 **Adobe Campaign Standard** 適用於您的行動應用程式的擴充功能。

如需擴充功能的詳細資訊，請參閱 [在Campaign Standard Launch中設定Adobe擴充功能](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) 在檔案中。

## 設定步驟 [!UICONTROL In-App] 訊息 {#steps-to-set-up}

1. [使用 Adobe Experience Platform SDK 設定行動應用程式](/help/communication-channels/mobile/configure-mobile-apps-using-aep-sdk.md).
1. [設定事件](/help/communication-channels/mobile/in-app/configure-events.md).

## 建立、管理和發佈 [!UICONTROL In-App] 傳遞 {#create-manage-publish}

您可以按一下「 」，建立一次性的應用程式內傳送。 **[!UICONTROL Create an In-App Message]** 卡片來自首頁、來自 [!UICONTROL Marketing Activities]，或您可以 [在工作流程中建立應用程式內傳遞](/help/communication-channels/mobile/in-app/in-app-activity.md).

設定傳送時，您有三個選項可透過從不同傳送範本中選擇來鎖定使用者：

1. [**廣播應用程式內訊息**](/help/communication-channels/mobile/in-app/broadcast-in-app-message.md) 將目標鎖定在行動應用程式的所有使用者。

   此訊息型別可讓您傳送訊息給行動應用程式的所有使用者（目前或未來），即使他們在Adobe Campaign中沒有現有的設定檔亦然。 因此，在自訂訊息時無法個人化，因為使用者設定檔不一定存在於Adobe Campaign中。

1. 根據使用者的行動應用程式設定檔鎖定所有使用者。

   此訊息型別可讓您鎖定在Adobe Campaign中具有行動設定檔的行動應用程式的所有已知或匿名使用者。 此訊息類型僅能使用非個人和非敏感屬性進行個人化，而且不需要 Mobile SDK 與 Adobe Campaign 的應用程式內訊息服務之間的安全交握。因此，個人化策略是根據您從使用者與裝置的互動中瞭解到的使用者內容。 例如，將目標鎖定為上週啟動應用程式超過5次的所有使用者。

1. [**根據其 Campaign 設定檔定位使用者**](/help/communication-channels/mobile/in-app/target-users-based-on-campaign-profile.md).

   此訊息型別可讓您定位已訂閱您行動應用程式的Adobe Campaign設定檔（CRM設定檔）。 此訊息可透過Adobe Campaign中所有可用的設定檔屬性進行個人化。 它需要在Mobile SDK和Campaign的應用程式內傳訊服務之間進行安全交握，以確保包含個人和敏感資訊的訊息僅供授權使用者使用。

若您已在其他管道（例如電子郵件或推播）上將使用者設為目標，此範本對於支援跨管道協調使用案例非常有用。 接著，您可根據使用者的回應，透過應用程式內訊息與他們互動。

## 報告您的應用程式內傳遞 {#report}

發佈傳遞後，您可以 [報告您的應用程式內傳遞](/help/communication-channels/mobile/in-app/in-app-reporting.md).
