---
title: 應用程式內訊息簡介
description: 「瞭解如何針對客戶在行動應用程式中的即時行為，向使用者呈現與情境相關的應用程式內訊息。」
feature: 應用程式中
topics: Mobile
kt: 1911
doc-type: feature video
activity: use
team: TM
exl-id: c51716eb-7239-4fc0-9ccf-9f5f0a5fae65
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 07c2696cbdc72e24563c5d1442bf5c39b22d5a22
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 12%

---

# [!UICONTROL In-App]消息{#introduction}簡介

[!UICONTROL In-App Messaging]頻道可讓您在使用者在行動應用程式中啟用時顯示訊息。 此通道要求移動應用程式與[!UICONTROL Adobe Experience Platform SDK]整合。

本教學課程將說明在Adobe Campaign Standard州設定行動裝置屬性、[!UICONTROL In-App Messaging]頻道的[!UICONTROL Launch]擴充功能，以及如何準備、自訂和傳送[!UICONTROL In-App]訊息所需的步驟。 這些連結將引導您前往每個反白顯示主題的教學影片。

## 必要條件 {#prerequisites}

1. 請確定您可以存取&#x200B;**[!UICONTROL In-App]**&#x200B;頻道。 如果您無法存取這些通道，請聯絡您的帳戶團隊。
1. 確認您的&#x200B;**使用者**&#x200B;在Adobe Campaign Standard和[!UICONTROL Launch]中具有必要的&#x200B;**權限。**

   1. 在Adobe Campaign Standard，請確定IMS使用者是[!UICONTROL Standard User]和[!UICONTROL Administrator]群組的一部分。\
      此步驟可讓使用者登入Adobe Campaign Standard、導覽至Experience PlatformSDK行動應用程式頁面，並檢視您在[!UICONTROL Launch]中建立的行動應用程式屬性。
   1. 在[!UICONTROL Launch]中，請確定您的IMS使用者是[!UICONTROL Launch]產品設定檔的一部分。\
      此步驟允許用戶登錄[!UICONTROL Launch]以建立和查看屬性。 如需[!UICONTROL Launch]中產品描述檔的詳細資訊，請參閱[建立產品描述檔](https://docs.adobelaunch.com/launch-reference/administration/user-permissions#3-create-your-product-profile)。 在產品設定檔中，公司或屬性上應未設定任何權限，但使用者仍可登入。

1. 在Adobe Experience Platform Launch:

   1. 建立行動應用程式，方法是建立行動裝置屬性，並使用Experience PlatformSDK來測量行動應用程式。
   1. 為您的行動應用程式安裝&#x200B;**Adobe Campaign Standard**&#x200B;擴充功能。

有關擴展的詳細資訊，請參閱[!UICONTROL Adobe Launch ]文檔中的[在AdobeLaunch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)中配置Campaign Standard擴展。

## 設定[!UICONTROL In-App]消息{#steps-to-set-up}的步驟

1. [使用 Adobe Experience Platform SDK 設定行動應用程式](/help/communication-channels/mobile/configure-mobile-apps-using-aep-sdk.md).

1. [設定事件](/help/communication-channels/mobile/in-app/configure-events.md)。

## 建立、管理和發佈[!UICONTROL In-App]傳送{#create-manage-publish}

您可以按一下首頁上的&#x200B;**[!UICONTROL Create an In-App Message]**&#x200B;卡片，或從[!UICONTROL Marketing Activities]建立一次應用程式內傳送，或在工作流程中建立應用程式內傳送。[](/help/communication-channels/mobile/in-app/in-app-activity.md)

設定傳送時，您有三個選項可從不同的傳送範本選擇，以鎖定您的使用者：

1. [**廣播應用程式內訊**](/help/communication-channels/mobile/in-app/broadcast-in-app-message.md) 息，以鎖定行動應用程式的所有使用者。

   此訊息類型可讓您傳送訊息給行動應用程式的所有使用者（目前或未來），即使他們在Adobe Campaign沒有現有的個人檔案亦然。 因此，在自訂訊息時，不可能個人化，因為使用者個人檔案不一定存在於Adobe Campaign。

1. 根據行動應用程式設定檔鎖定所有使用者。

   此訊息類型可讓您鎖定在Adobe Campaign擁有行動設定檔的行動應用程式的所有已知或匿名使用者。 此訊息類型僅能使用非個人和非敏感屬性進行個人化，而且不需要 Mobile SDK 與 Adobe Campaign 的應用程式內訊息服務之間的安全交握。因此，個人化策略是根據您從使用者與裝置的互動中學到的。 例如，鎖定在上週啟動應用程式超過5次的所有使用者。

1. [**根據其 Campaign 設定檔定位使用者**](/help/communication-channels/mobile/in-app/target-users-based-on-campaign-profile.md).

   此訊息類型可讓您定位已訂閱您行動應用程式的Adobe Campaign個人檔案（CRM個人檔案）。 該訊息可與Adobe Campaign所有可用的描述檔屬性個人化，但需要Mobile SDK和Campaign應用程式內訊息服務之間的安全握手，以確保只有授權使用者才會使用包含個人和敏感資訊的訊息。

此範本對於支援跨通道協調使用案例非常有用，因為您已針對電子郵件或推送等其他通道的使用者，而且根據他們的回應，您想要透過應用程式內訊息與他們互動。

## 報告您的應用程式內傳送{#report}

發佈傳送後，您可以[報告應用程式內傳送](/help/communication-channels/mobile/in-app/in-app-reporting.md)。

## 其他資源

* [應用程式內報表](https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/list-of-reports/in-app-report.html)
* [設定行動裝置屬性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* [使用Adobe Experience PlatformSDK設定行動應用程式](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html)
* [準備和傳送應用程式內訊息](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/in-app-messaging/preparing-and-sending-an-in-app-message.html)
* [自訂應用程式內訊息](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/in-app-messaging/customizing-an-in-app-message.html)
* [在工作流程中傳送應用程式內訊息](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/channel-activities/in-app-delivery.html)
* [啟用生命週期度量](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk#enable-lifecycle-metrics)
