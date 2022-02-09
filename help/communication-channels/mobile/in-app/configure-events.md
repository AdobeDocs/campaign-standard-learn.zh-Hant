---
title: 設定事件
description: '"瞭解事件如何定義哪些用戶啟動的操作將觸發要顯示的應用程式內消息。 」'
feature: In App
kt: 2548
thumbnail: 26245.jpg
doc-type: feature video
activity: use
team: TM
exl-id: 2c7937f4-b0da-46e5-934e-c660012c2c6f
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 57dbf456625d22cd2e4526d92e5a8c20a048d339
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 2%

---

# 設定 [!UICONTROL Events] {#configuring-events}

配置 [!UICONTROL In-App] 消息，您需要定義哪些用戶啟動的操作觸發要顯示的消息。 這些操作被調用 [!UICONTROL events]。 三類 [!UICONTROL events] 可用： [!UICONTROL Mobile Application events]。 [!UICONTROL Life Cycle events], [!UICONTROL Analytics events]。

## [!UICONTROL Mobile Application Events] {#mobile-application-events}

[!UICONTROL Mobile Application events] 是 [!UICONTROL custom events] 在您的移動應用程式中實現。

例如：

* 客戶已查看物料
* 客戶將物料添加到購物車
* 購物車放棄
* 客戶已購買了

必須配置這些 [!UICONTROL events] 在Adobe Campaign。 以下視頻介紹如何執行此操作。

>[!VIDEO](https://video.tv.adobe.com/v/26245?quality=12)

## [!UICONTROL Life Cycle events] {#life-cycle-events}

[!UICONTROL Lifecycle events] 現成 [!UICONTROL events]。 以下 [!UICONTROL events] 可用：

* [!UICONTROL launched]
* [!UICONTROL upgraded]
* [!UICONTROL crashed]

示例用例可以是在升級後介紹新功能的消息，也可以是事件升級。

>[!NOTE]
>
>的 [!UICONTROL Lifecycle module] 需要在移動應用程式中配置。 有關更多資訊，請參閱此處 [如何將生命週期添加到應用](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle)

## [!UICONTROL Analytics Events] {#analytics-events}

根據移動應用中檢測的內容，支援以下三個類別：

* Adobe Analytics
* [!UICONTROL Context data]
* [!UICONTROL View state]

>[!NOTE]
>
>[!UICONTROL Analytics events] 需要Adobe Analytics執照。 一旦你擁有 [[!DNL Analytics] 擴展配置](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#configure-analytics-extension-in-launch) 並添加 [分析到你的應用](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#add-analytics-to-your-app)，這些事件在 [!UICONTROL In-App] 配置。
