---
title: 設定事件
description: 「了解事件如何定義由使用者啟動的動作，以觸發要顯示的應用程式內訊息。 」
feature: 應用程式內
kt: 2548
thumbnail: 26245.jpg
doc-type: feature video
activity: use
team: TM
exl-id: 2c7937f4-b0da-46e5-934e-c660012c2c6f
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 2be2719ddd84490b796d9abc6300376fa896ff0c
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# 設定 [!UICONTROL Events] {#configuring-events}

設定[!UICONTROL In-App]訊息時，您需要定義要顯示的是由哪些使用者啟動的動作觸發訊息。 這些動作稱為[!UICONTROL events]。 有三類[!UICONTROL events]可用：[!UICONTROL Mobile Application events]、[!UICONTROL Life Cycle events]和[!UICONTROL Analytics events]。

## [!UICONTROL Mobile Application Events] {#mobile-application-events}

[!UICONTROL Mobile Application events] 是 [!UICONTROL custom events] 在行動應用程式中實作的。

例如：

* 客戶已檢視項目
* 客戶新增項目至購物車
* 放棄購買
* 客戶已購買某些商品

您必須在Adobe Campaign中設定這些[!UICONTROL events]。 以下影片說明如何執行此作業。

>[!VIDEO](https://video.tv.adobe.com/v/26245?quality=12)

## [!UICONTROL Life Cycle events] {#life-cycle-events}

[!UICONTROL Lifecycle events] 現成可用 [!UICONTROL events]。可使用下列[!UICONTROL events]:

* [!UICONTROL launched]
* [!UICONTROL upgraded]
* [!UICONTROL crashed]

範例使用案例可能是在升級或事件升級後引入新功能的訊息。

>[!NOTE]
>
>[!UICONTROL Lifecycle module]必須在行動應用程式中設定。 請參閱這裡以取得[如何將生命週期新增至應用程式](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle)的詳細資訊

## [!UICONTROL Analytics Events] {#analytics-events}

根據您的行動應用程式中所創作的內容，支援下列三個類別：

* Adobe Analytics
* [!UICONTROL Context data]
* [!UICONTROL View state]

>[!NOTE]
>
>[!UICONTROL Analytics events] 需要Adobe Analytics授權。在您設定[[!DNL Analytics] 擴充功能](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#configure-analytics-extension-in-launch)並將[Analytics新增至您的應用程式](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#add-analytics-to-your-app)後，這些事件即可在ACS的[!UICONTROL In-App]設定中使用。

## 其他資源

* [啟用生命週期量度（檔案）](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk#enable-lifecycle-metrics)
