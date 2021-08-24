---
title: 應用程式內訊息簡介
description: 了解如何向使用者呈現情境相關的應用程式內訊息，以回應客戶在行動應用程式內的即時行為。
feature: 應用程式內
kt: 1911
doc-type: feature video
activity: use
team: TM
exl-id: c51716eb-7239-4fc0-9ccf-9f5f0a5fae65
role: User
level: Beginner
source-git-commit: 30e8e10575aad4dcf2b0473cdd9fd6d5fc2815f4
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 11%

---

# [!UICONTROL In-App]訊息簡介 {#introduction}

當使用者在行動應用程式內處於作用中狀態時， [!UICONTROL In-App Messaging]通道可讓您顯示訊息。 此通道要求將移動應用程式與[!UICONTROL Adobe Experience Platform SDK]整合。

本教學課程說明設定行動屬性、[!UICONTROL In-App Messaging]通道的[!UICONTROL Launch]擴充功能，以及如何在Adobe Campaign Standard中準備、自訂和傳送[!UICONTROL In-App]訊息。 這些連結會導向每個醒目提示的主題的教學課程影片。

## 先決條件 {#prerequisites}

1. 請務必存取&#x200B;**[!UICONTROL In-App]**&#x200B;通道。 如果您無法存取這些通道，請聯絡您的帳戶團隊。
1. 確認您的&#x200B;**user**&#x200B;在Adobe Campaign Standard和[!UICONTROL Launch]中具有必要的&#x200B;**權限**。

   1. 在Adobe Campaign Standard中，確認IMS使用者是[!UICONTROL Standard User]和[!UICONTROL Administrator]群組的一部分。

      此步驟可讓使用者登入Adobe Campaign Standard、導覽至「Experience PlatformSDK」行動應用程式頁面，以及檢視您在[!UICONTROL Launch]中建立的行動應用程式屬性。

   1. 在[!UICONTROL Launch]中，確認您的IMS使用者屬於[!UICONTROL Launch]產品設定檔。 此步驟允許用戶登錄[!UICONTROL Launch]以建立和查看屬性。 在產品設定檔中，不應設定公司或屬性的權限，但使用者應仍可登入。

1. 在Adobe Experience Platform Launch:

   1. 透過建立行動屬性來建立行動應用程式，並使用Experience PlatformSDK測試您的行動應用程式。
   1. 安裝行動應用程式的&#x200B;**Adobe Campaign Standard**&#x200B;擴充功能。

如需擴充功能的詳細資訊，請參閱檔案中的[在AdobeLaunch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)中設定Campaign Standard擴充功能。

## 設定[!UICONTROL In-App]訊息的步驟 {#steps-to-set-up}

1. [使用 Adobe Experience Platform SDK 設定行動應用程式](/help/communication-channels/mobile/configure-mobile-apps-using-aep-sdk.md).
1. [設定事件](/help/communication-channels/mobile/in-app/configure-events.md)。

## 建立、管理和發佈[!UICONTROL In-App]傳遞 {#create-manage-publish}

您可以按一下首頁的&#x200B;**[!UICONTROL Create an In-App Message]**&#x200B;卡片從[!UICONTROL Marketing Activities]建立一次應用程式內傳送，或在工作流程](/help/communication-channels/mobile/in-app/in-app-activity.md)中建立應用程式內傳送。[

設定傳送時，您有三個選項可選擇不同傳送範本，以鎖定使用者：

1. [**廣播應用程式內訊**](/help/communication-channels/mobile/in-app/broadcast-in-app-message.md) 息，將目標鎖定在行動應用程式的所有使用者。

   此訊息類型可讓您傳送訊息給行動應用程式的所有使用者（目前或未來），即使他們在Adobe Campaign中沒有現有的設定檔亦然。 因此，自訂訊息時無法個人化，因為Adobe Campaign中不一定有使用者設定檔。

1. 根據行動應用程式設定檔鎖定所有使用者。

   此訊息類型可讓您鎖定在Adobe Campaign中具有行動設定檔的行動應用程式的所有已知或匿名使用者。 此訊息類型僅能使用非個人和非敏感屬性進行個人化，而且不需要 Mobile SDK 與 Adobe Campaign 的應用程式內訊息服務之間的安全交握。因此，個人化策略是以您從使用者與裝置的互動中了解到的資訊為基礎。 例如，將目標定位為在過去一週中啟動應用程式超過五次的所有使用者。

1. [**根據其 Campaign 設定檔定位使用者**](/help/communication-channels/mobile/in-app/target-users-based-on-campaign-profile.md).

   此訊息類型可讓您定位已訂閱您行動應用程式的Adobe Campaign設定檔（CRM設定檔）。 此訊息可透過Adobe Campaign中所有可用的設定檔屬性個人化。 它需要Mobile SDK與Campaign應用程式內訊息服務之間的安全交握，以確保只有授權使用者才會使用包含個人和敏感資訊的訊息。

此範本對於支援跨管道協調使用案例很實用，因為您已在其他管道（例如電子郵件或推播）上鎖定使用者。 然後，您會根據他們的回應，想要透過應用程式內訊息與他們互動。

## 報告您的應用程式內傳遞 {#report}

傳送發佈後，您可以[報告應用程式內傳送](/help/communication-channels/mobile/in-app/in-app-reporting.md)。

## 其他資源

* [應用程式內報表](https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/list-of-reports/in-app-report.html?lang=en)
* [設定行動屬性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* [使用Adobe Experience Platform SDK設定行動應用程式](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html?lang=en)
* [準備和傳送應用程式內訊息](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/in-app-messaging/preparing-and-sending-an-in-app-message.html?lang=en)
* [自訂應用程式內訊息](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/in-app-messaging/customizing-an-in-app-message.html?lang=en)
* [在工作流程中傳送應用程式內訊息](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/channel-activities/in-app-delivery.html?lang=en)
* [啟用生命週期量度](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk#enable-lifecycle-metrics)
