---
title: 設定事件
description: '在Adobe Campaign Standard(ACS)事件中設定應用程式內訊息時，定義使用者啟動的動作會觸發要顯示的訊息。 '
feature: In-App
topics: Mobile
kt: 2548
doc-type: feature video
activity: use
team: TM
translation-type: tm+mt
source-git-commit: 82fb2d39dc61a55c0aa20ca1fa215f35a7dd9088
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 1%

---


# Configure [!UICONTROL Events] {#configuring-events}

在配置消 [!UICONTROL In-App] 息時，您需要定義哪些用戶啟動的操作觸發要顯示的消息。 這些動作稱為 [!UICONTROL events]。 提供三 [!UICONTROL events] 種類別： [!UICONTROL Mobile Application events]、 [!UICONTROL Life Cycle events]和 [!UICONTROL Analytics events]。

## [!UICONTROL Mobile Application Events] {#mobile-application-events}

[!UICONTROL Mobile Application events] 在您 [!UICONTROL custom events] 的行動應用程式中實作。

例如：

* 客戶已檢視項目
* 客戶新增項目至購物車
* 購物車放棄
* 客戶已購買

您必須在Adobe Campaign中 [!UICONTROL events] 設定這些項目。 以下影片說明如何執行此動作。

>[!VIDEO](https://video.tv.adobe.com/v/26245?quality=12)

## [!UICONTROL Life Cycle events]  {#life-cycle-events}

[!UICONTROL Lifecycle events] 是現成可用的 [!UICONTROL events]。 The following [!UICONTROL events] are available:

* [!UICONTROL launched]
* [!UICONTROL upgraded]
* [!UICONTROL crashed]

範例使用案例可以是在升級後介紹新功能的訊息，或事件促銷。

>[!NOTE]
>
>必須 [!UICONTROL Lifecycle module] 在行動應用程式中設定。 如需如何將生命週期新增至應用 [程式的詳細資訊，請參閱此處](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle)

## [!UICONTROL Analytics Events] {#analytics-events}

根據您的行動應用程式中所創作的內容，支援下列三個類別：

* Adobe Analytics
* [!UICONTROL Context data]
* [!UICONTROL View state]

>[!NOTE]
>
>[!UICONTROL Analytics events] 需要Adobe Analytics授權。 在您設定擴充 [[!DNL Analytics] 功能](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#configure-analytics-extension-in-launch) ，並將 [Analytics新增至應用程式後](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#add-analytics-to-your-app)，這些事件就可在ACS的設定 [!UICONTROL In-App] 中使用。

## 其他資源

* [啟用生命週期度量（檔案）](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk#enable-lifecycle-metrics)
