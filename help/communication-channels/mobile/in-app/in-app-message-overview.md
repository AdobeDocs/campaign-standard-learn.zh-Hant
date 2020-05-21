---
title: 應用程式內訊息簡介
description: Adobe Campaign Standard(ACS)應用程式內訊息通道可讓您針對客戶在行動應用程式中的即時行為，向使用者呈現與情境相關的應用程式內訊息。
feature: In-App
topics: Mobile
kt: 1911
doc-type: feature video
activity: use
team: TM
translation-type: tm+mt
source-git-commit: 82fb2d39dc61a55c0aa20ca1fa215f35a7dd9088
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 1%

---


# 訊息簡 [!UICONTROL In-App] 介 {#introduction}

當使 [!UICONTROL In-App Messaging] 用者在行動應用程式中處於作用中時，頻道可讓您顯示訊息。 此通道需要與行動應用程式整合 [!UICONTROL Adobe Experience Platform SDK]。

本教學課程將說明在Adobe Campaign Standard中設定行動裝置屬性、 [!UICONTROL Launch] 頻道 [!UICONTROL In-App Messaging] 擴充功能，以及如何準備、自訂和傳送 [!UICONTROL In-App] 訊息所需的步驟。 這些連結將引導您前往每個反白顯示主題的教學影片。

## 必要條件 {#prerequisites}

1. 請確定您可以存取頻 **[!UICONTROL In-App]** 道。 如果您無法存取這些渠道，請連絡您的帳戶團隊。
1. 確認您的使 **用者** 在Adobe Campaign Standard和中 **擁有必要** 的權限 [!UICONTROL Launch]。

   1. 在Adobe Campaign Standard中，請確定IMS使用者是該和群組的一 [!UICONTROL Standard User] 部 [!UICONTROL Administrator] 分。\
      此步驟可讓使用者登入Adobe Campaign Standard、導覽至Experience Platform SDK行動應用程式頁面，並檢視您在中建立的行動應用程式屬性 [!UICONTROL Launch]。
   1. 在中， [!UICONTROL Launch]請確定您的IMS使用者是產品設定檔的 [!UICONTROL Launch] 一部分。\
      此步驟可讓使用者登入以 [!UICONTROL Launch] 建立和檢視屬性。 如需有關中產品設定檔的詳細資 [!UICONTROL Launch]訊，請 [參閱建立產品設定檔](https://docs.adobelaunch.com/launch-reference/administration/user-permissions#3-create-your-product-profile)。 在產品設定檔中，公司或屬性上應未設定任何權限，但使用者仍可登入。

1. 在Adobe Experience Platform Launch中：

   1. 建立行動應用程式，方法是建立行動裝置屬性，並使用Experience Platform SDK測量行動應用程式。
   1. 為您的 **行動應用程式安裝Adobe Campaign Standard** 擴充功能。

如需擴充功能的詳細資訊，請參 [閱檔案中Adobe Launch中的Configure Campaign Standard擴充](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)[!UICONTROL Adobe Launch ]功能。

## 設定消息的步 [!UICONTROL In-App] 驟 {#steps-to-set-up}

1. [使用Adobe Experience Platform SDK設定行動應用程式](/help/communication-channels/mobile/configure-mobile-apps-using-aep-sdk.md)。

1. [設定事件](/help/communication-channels/mobile/in-app/configure-events.md)。

## 建立、管理和發佈傳送 [!UICONTROL In-App] 內容 {#create-manage-publish}

您可以從首頁、從中按一下卡片，建立一次「應用程式內傳送」 **[!UICONTROL Create an In-App Message]** ，或是在工作流程中 [!UICONTROL Marketing Activities][「建立應用程式內傳送」](/help/communication-channels/mobile/in-app/in-app-activity.md)。

設定傳送時，您有三個選項可從不同的傳送範本選擇，以鎖定您的使用者：

1. [**廣播應用程式內訊息&#x200B;**](/help/communication-channels/mobile/in-app/broadcast-in-app-message.md)，以行動應用程式的所有使用者為目標。

   此訊息類型可讓您傳送訊息給行動應用程式的所有使用者（目前或未來），即使他們在Adobe Campaign中沒有現有的設定檔亦然。 因此，當自訂訊息時，不可能進行個人化，因為Adobe Campaign中不一定有使用者設定檔。

1. 根據行動應用程式設定檔鎖定所有使用者。

   此訊息類型可讓您鎖定在Adobe Campaign中具有行動設定檔的行動應用程式的所有已知或匿名使用者。 此訊息類型僅能使用非個人和非敏感屬性進行個人化，而且不需要Mobile SDK與Adobe Campaign的應用程式內訊息服務之間的安全握手。 因此，個人化策略是根據您從使用者與裝置的互動中學到的。 例如，鎖定在上週啟動應用程式超過5次的所有使用者。

1. [**根據其促銷活動設定檔定位使用者&#x200B;**](/help/communication-channels/mobile/in-app/target-users-based-on-campaign-profile.md)。

   此訊息類型可讓您定位已訂閱您行動應用程式的Adobe Campaign設定檔（CRM設定檔）。 此訊息可與Adobe Campaign中所有可用的描述檔屬性個人化，但需要Mobile SDK與Campaign應用程式內訊息服務之間的安全握手，以確保只有授權使用者才會使用包含個人和敏感資訊的訊息。

此範本對於支援跨通道協調使用案例非常有用，因為您已針對電子郵件或推送等其他通道的使用者，而且根據他們的回應，您想要透過應用程式內訊息與他們互動。

## 報告您的應用程式內傳送 {#report}

發佈您的傳送後，您就可以 [報告應用程式內傳送](/help/communication-channels/mobile/in-app/in-app-reporting.md)。

## 其他資源

* [應用程式內報表](https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/list-of-reports/in-app-report.html)
* [設定行動裝置屬性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* [使用Adobe Experience Platform SDK設定行動應用程式](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)
* [準備和傳送應用程式內訊息](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/in-app-messaging/preparing-and-sending-an-in-app-message.html)
* [自訂應用程式內訊息](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/in-app-messaging/customizing-an-in-app-message.html)
* [在工作流程中傳送應用程式內訊息](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/channel-activities/in-app-delivery.html)
* [啟用生命週期度量](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk#enable-lifecycle-metrics)
