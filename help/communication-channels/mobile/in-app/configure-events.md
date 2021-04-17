---
title: 設定事件
description: 「瞭解事件如何定義使用者啟動的動作，以觸發應用程式內訊息的顯示。 」
feature: 應用程式中
topics: Mobile
kt: 2548
thumbnail: 26245.jpg
doc-type: feature video
activity: use
team: TM
exl-id: 2c7937f4-b0da-46e5-934e-c660012c2c6f
role: Business Practitioner, Developer
level: Beginner, Intermediate
translation-type: tm+mt
source-git-commit: 5d2bc8bd3a3a0fdb5e2f1ef75af2ab60b8f6abc8
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 2%

---

# 配置[!UICONTROL Events] {#configuring-events}

在配置[!UICONTROL In-App]消息時，您需要定義由哪些用戶啟動的動作觸發要顯示的消息。 這些動作稱為[!UICONTROL events]。 [!UICONTROL events]有三種類別可供使用：[!UICONTROL Mobile Application events]、[!UICONTROL Life Cycle events]和[!UICONTROL Analytics events]。

## [!UICONTROL Mobile Application Events] {#mobile-application-events}

[!UICONTROL Mobile Application events] 是在 [!UICONTROL custom events] 您的行動應用程式中實作的。

例如：

* 客戶已檢視項目
* 客戶新增項目至購物車
* 購物車放棄
* 客戶已購買

您必須在Adobe Campaign配置這些[!UICONTROL events]。 以下影片說明如何執行此動作。

>[!VIDEO](https://video.tv.adobe.com/v/26245?quality=12)

## [!UICONTROL Life Cycle events]  {#life-cycle-events}

[!UICONTROL Lifecycle events] 是現成可用的 [!UICONTROL events]。以下[!UICONTROL events]可供使用：

* [!UICONTROL launched]
* [!UICONTROL upgraded]
* [!UICONTROL crashed]

範例使用案例可以是在升級後介紹新功能的訊息，或事件促銷。

>[!NOTE]
>
>[!UICONTROL Lifecycle module]必須在行動應用程式中設定。 如需[如何將生命週期新增至應用程式的詳細資訊，請參閱此處](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle)

## [!UICONTROL Analytics Events] {#analytics-events}

根據您的行動應用程式中所創作的內容，支援下列三個類別：

* Adobe Analytics
* [!UICONTROL Context data]
* [!UICONTROL View state]

>[!NOTE]
>
>[!UICONTROL Analytics events] 需要取得Adobe Analytics執照。在您設定[[!DNL Analytics] 擴充功能](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#configure-analytics-extension-in-launch)並將[Analytics新增至您的App](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#add-analytics-to-your-app)後，這些事件就會在ACS的[!UICONTROL In-App]設定中提供。

## 其他資源

* [啟用生命週期度量（檔案）](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk#enable-lifecycle-metrics)
