---
title: Adobe Campaign Standard(ACS)的隱私權要求——概觀
description: 本教學課程說明如何透過Adobe Campaign Standard(ACS)介面建立隱私權要求。
feature: GDPR, CCAP
topic: Privacy
kt: 1480
doc-type: feature video
activity: use
team: TM
translation-type: tm+mt
source-git-commit: 556bff4c94e16d3a94561dee1ccb311bc003b631
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 20%

---


# 使用Adobe Campaign Standard使用者介面要求隱私權

Adobe Campaign為資料掌控者提供三種方法，以依據隱私權法案(例如GDPR（一般資料保護規則）和CCPA（加州消費者隱私法案）執行PII資料的隱私權存取和刪除要求：

* **透過隱私權核心服務整合：從** 所有Experience Cloud解決方 [!UICONTROL Privacy Service] 案推送至隱私權要求的作業，由Campaign透過專屬的工作流程自動處理。請參閱[Adobe Experience Platform Privacy Service](https://adobe.io/apis/cloudplatform/gdpr.html)以瞭解如何從隱私權核心服務建立隱私權要求

* **透過API:** Adobe Campaign提供API，允許使用REST自動處理隱私權要求

* **透過Adobe Campaign介面：針對每** 個隱私權要求，資料掌控者會在Adobe Campaign中建立新的隱私權要求

>[!NOTE]
>
> **ACS 19.4的更改：**
> 
> [隱私權服務整合](https://adobe.io/apis/cloudplatform/gdpr.html)是您應用於所有存取和刪除要求的方法。 從19.4開始，已不再使用促銷活動API和介面來存取和刪除請求。 有關Campaign Standard已過時和已移除功能的詳細資訊，請參閱[本頁](https://helpx.adobe.com/tw/campaign/kb/acs-deprecated-and-removed-features.html)。
>
>**選擇退出個人資訊銷售 (CCPA)**
>
>從 19.4 開始，Campaign 介面及 API 中會提供「CCPA 選擇退出」欄位。19.3版中，若要運用此資訊，您必須在Adobe Campaign Standard中建立此欄位。 如需詳細資訊，請參閱[詳細檔案](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ccpa)。
>
> 按一下介面右上方的 ? 圖示並選取「關於」，即可檢查自己的版本資訊。

## 教學影片

### 隱私權要求的先決條件

1. [建立命名空間](/help/privacy/namespaces-for-privacy-requests.md)
1. [修改自訂資源](/help/privacy/custom-resources-for-privacy-requests.md)

### 透過Adobe Campaign使用者介面建立、追蹤及執行隱私權要求

* [透過Adobe Campaign使用者介面建立及追蹤隱私權要求](/help/privacy/create-and-track-privacy-requests.md)
* [執行隱私權要求](/help/privacy/execute-privacy-requests.md)

## 其他資源

* [Campaign 的一般隱私權指引](https://helpx.adobe.com/tw/campaign/kb/campaign-privacy-overview.html)
* [ACS 的 CCPA](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)
* [Adobe Experience Platform隱私權服務](https://adobe.io/apis/cloudplatform/gdpr.html)
* [Adobe Campaign Standard REST API檔案](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#privacy-management)
