---
title: Adobe Campaign Standard (ACS) 的隱私權請求 - 概覽
description: 本教學課程說明如何透過 Adobe Campaign Standard (ACS) 介面建立隱私權請求。
feature: GDPR, CCAP
topic: Privacy
kt: 1480
doc-type: feature video
activity: use
team: TM
translation-type: ht
source-git-commit: 556bff4c94e16d3a94561dee1ccb311bc003b631
workflow-type: ht
source-wordcount: '371'
ht-degree: 100%

---


# 使用 Adobe Campaign Standard 使用者介面提出隱私權請求

Adobe Campaign 為資料掌控者提供三種方法，讓資料掌控者根據隱私權行為，例如 GDPR (一般資料保護規則) 和 CCPA (加州消費者隱私法)，執行 PII 資料的隱私權存取和刪除請求：

* **透過隱私權核心服務整合：**&#x200B;從推送至所有 Experience Cloud 解決方案[!UICONTROL Privacy Service]的隱私權請求，由 Campaign 透過專用工作流程自動處理。請參閱 [Experience Platform 隱私權服務](https://adobe.io/apis/cloudplatform/gdpr.html)文件，以瞭解如何透過隱私權核心服務建立隱私權請求。

* **透過 API：** Adobe Campaign 提供API，允許使用 REST 自動處理隱私權請求

* **透過 Adobe Campaign 介面：**&#x200B;針對每個隱私權請求，資料控制者會在 Adobe Campaign 建立新的隱私權請求

>[!NOTE]
>
> **ACS 19.4的變更：**
> 
> [隱私權服務整合](https://adobe.io/apis/cloudplatform/gdpr.html)是可讓您用於處理所有存取和刪除請求的方法。自 19.4 版本以來，不建議使用 Campaign API 和介面來存取和刪除請求。有關 Campaign Standard 已過時和已刪除功能的詳細資訊，請參閱[此頁](https://helpx.adobe.com/tw/campaign/kb/acs-deprecated-and-removed-features.html)。
>
>**選擇退出個人資訊銷售 (CCPA)**
>
>從 19.4 開始，Campaign 介面及 API 中會提供「CCPA 選擇退出」欄位。對於 19.3 版，您必須在 Adobe Campaign Standard 中建立此欄位，才能善用此資訊。如需詳細資訊，請參閱[詳細文件](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ccpa)。
>
> 按一下介面右上方的 ? 圖示並選取「關於」，即可檢查自己的版本資訊。

## 影片教學課程

### 隱私權請求的必要條件

1. [建立命名空間](/help/privacy/namespaces-for-privacy-requests.md)
1. [修改自訂資源](/help/privacy/custom-resources-for-privacy-requests.md)

### 透過 Adobe Campaign 使用者介面建立、追蹤及執行隱私權請求

* [透過 Adobe Campaign 使用者介面建立及追蹤隱私權請求](/help/privacy/create-and-track-privacy-requests.md)
* [執行隱私權請求](/help/privacy/execute-privacy-requests.md)

## 其他資源

* [Campaign 的一般隱私權指引](https://helpx.adobe.com/tw/campaign/kb/campaign-privacy-overview.html)
* [ACS 的 CCPA](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ccpa)
* [Adobe Experience Platform 隱私權服務](https://adobe.io/apis/cloudplatform/gdpr.html)
* [Adobe Campaign Standard REST API 文件](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#privacy-management)
