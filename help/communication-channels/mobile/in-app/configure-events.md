---
title: 設定事件
description: 「瞭解事件如何定義哪些使用者起始的動作會觸發要顯示的應用程式內訊息。 」
feature: In App
kt: 2548
thumbnail: 26245.jpg
doc-type: feature video
activity: use
team: TM
exl-id: 2c7937f4-b0da-46e5-934e-c660012c2c6f
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 89df23d00913d36b93d3be03b62c74320524f9c7
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 2%

---

# 設定 [!UICONTROL Events] {#configuring-events}

設定時 [!UICONTROL In-App] 訊息，您必須定義使用者啟動的動作會觸發訊息顯示。 這些動作稱為 [!UICONTROL events]. 三個類別 [!UICONTROL events] 可用： [!UICONTROL Mobile Application events]， [!UICONTROL Life Cycle events]、和 [!UICONTROL Analytics events].

## [!UICONTROL Mobile Application Events] {#mobile-application-events}

[!UICONTROL Mobile Application events] 是 [!UICONTROL custom events] 在您的行動應用程式中實作的專案。

範例包括：

* 客戶已檢視一個專案
* 客戶新增專案至購物車
* 放棄購買
* 客戶已購買某件商品

您必須設定這些專案 [!UICONTROL events] 在Adobe Campaign中。 以下影片說明如何執行此操作。

>[!VIDEO](https://video.tv.adobe.com/v/26245?quality=12&learn=on)

## [!UICONTROL Life Cycle events] {#life-cycle-events}

[!UICONTROL Lifecycle events] 是現成可用的 [!UICONTROL events]. 下列專案 [!UICONTROL events] 可用：

* [!UICONTROL launched]
* [!UICONTROL upgraded]
* [!UICONTROL crashed]

一個使用案例範例可能是升級或事件促銷活動後推出新功能的訊息。

>[!NOTE]
>
>此 [!UICONTROL Lifecycle module] 需要在行動應用程式中設定。 請參閱此處，瞭解更多關於 [如何將生命週期新增至您的應用程式](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle)

## [!UICONTROL Analytics Events] {#analytics-events}

根據您的行動應用程式中所檢測的內容，支援下列三個類別：

* Adobe Analytics
* [!UICONTROL Context data]
* [!UICONTROL View state]

>[!NOTE]
>
>[!UICONTROL Analytics events] 需要Adobe Analytics授權。 一旦您擁有 [[!DNL Analytics] 擴充功能已設定](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#configure-analytics-extension-in-launch) 並已新增 [Analytics至應用程式](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#add-analytics-to-your-app)，這些事件便可在以下位置取得： [!UICONTROL In-App] ACS中的設定。
