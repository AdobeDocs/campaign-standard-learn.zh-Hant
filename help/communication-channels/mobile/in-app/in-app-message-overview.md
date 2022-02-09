---
title: 應用程式內訊息簡介
description: 瞭解如何根據客戶在移動應用程式中的即時行為向用戶呈現上下文相關的應用內消息。
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

# 簡介 [!UICONTROL In-App] 消息 {#introduction}

的 [!UICONTROL In-App Messaging] 通道允許您在用戶在移動應用程式中處於活動狀態時顯示消息。 此渠道要求移動應用程式與 [!UICONTROL Adobe Experience Platform SDK]。

本教程介紹設定移動屬性所需的步驟， [!UICONTROL Launch] 擴展 [!UICONTROL In-App Messaging] 渠道，以及如何準備、自定義和發送 [!UICONTROL In-App] Adobe Campaign Standard。 這些連結指向每個突出顯示主題的視頻教程。

## 必要條件 {#prerequisites}

1. 確保您可以訪問 **[!UICONTROL In-App]** 頻道。 如果您無法存取這些通道，請聯絡您的帳戶團隊。
1. 驗證 **用戶** 有必要 **權限** 在Adobe Campaign Standard [!UICONTROL Launch]。

   1. 在Adobe Campaign Standard，確保IMS用戶是 [!UICONTROL Standard User] 和 [!UICONTROL Administrator] 組。

      此步驟允許用戶登錄到Adobe Campaign Standard，導航到Experience PlatformSDK移動應用頁面，並查看您在中建立的移動應用屬性 [!UICONTROL Launch]。

   1. 在 [!UICONTROL Launch]，確保您的IMS用戶是 [!UICONTROL Launch] 產品配置檔案。 此步驟允許用戶登錄到 [!UICONTROL Launch] 建立和查看屬性。 在產品配置檔案中，不應對公司或屬性設定任何權限，但用戶仍應能夠登錄。

1. 在Adobe Experience Platform Launch:

   1. 通過建立移動屬性並使用Experience PlatformSDK測試移動應用來建立移動應用。
   1. 安裝 **Adobe Campaign Standard** 移動應用程式的擴展。

有關擴展的詳細資訊，請參閱 [在Campaign Standard啟動中配置Adobe擴展](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) 的上界。

## 設定步驟 [!UICONTROL In-App] 消息 {#steps-to-set-up}

1. [使用 Adobe Experience Platform SDK 設定行動應用程式](/help/communication-channels/mobile/configure-mobile-apps-using-aep-sdk.md).
1. [配置事件](/help/communication-channels/mobile/in-app/configure-events.md)。

## 建立、管理和發佈 [!UICONTROL In-App] 交貨 {#create-manage-publish}

您可以通過按一下 **[!UICONTROL Create an In-App Message]** 從首頁， [!UICONTROL Marketing Activities]或 [在工作流中建立In-App交付](/help/communication-channels/mobile/in-app/in-app-activity.md)。

在設定交付時，您可以通過從不同的交付模板中進行選擇來確定用戶的目標：

1. [**廣播應用內消息**](/help/communication-channels/mobile/in-app/broadcast-in-app-message.md) 針對移動應用的所有用戶。

   此消息類型允許您向移動應用程式的所有用戶（當前或將來）發送消息，即使他們在Adobe Campaign沒有現有的配置檔案。 因此，在自定義消息時不可能進行個性化，因為用戶配置檔案不一定在Adobe Campaign。

1. 根據移動應用配置檔案瞄準所有用戶。

   此消息類型使您能夠將在Adobe Campaign具有移動配置檔案的移動應用的所有已知或匿名用戶作為目標。 此訊息類型僅能使用非個人和非敏感屬性進行個人化，而且不需要 Mobile SDK 與 Adobe Campaign 的應用程式內訊息服務之間的安全交握。所以，個性化策略是基於你從用戶與設備的交互中學到的關於用戶的資訊。 例如，針對所有在上週發佈了5次以上App的用戶。

1. [**根據其 Campaign 設定檔定位使用者**](/help/communication-channels/mobile/in-app/target-users-based-on-campaign-profile.md).

   此消息類型使您能夠將訂閱您的移動應用程式的Adobe Campaign配置檔案（CRM配置檔案）作為目標。 該消息可通過Adobe Campaign的所有可用配置檔案屬性進行個性化。 它要求移動軟體開發工具包與市場活動的In-App消息服務之間的安全握手，以確保只有授權用戶才使用包含個人和敏感資訊的消息。

此模板對支援跨渠道業務流程使用案例非常有用，在這些案例中，您已經針對了其他渠道（如電子郵件或推送）的用戶。 然後，根據他們的回應，您希望讓他們使用In-App消息。

## 報告您的In-App交付 {#report}

發佈交貨後，您可以 [有關您的應用內交付的報告](/help/communication-channels/mobile/in-app/in-app-reporting.md)。
