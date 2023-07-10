---
title: Adobe Campaign Standard (ACS) 的隱私權請求 - 概覽
description: 本教學課程說明如何透過 Adobe Campaign Standard 介面建立隱私權請求。
feature: Privacy Tools
jira: KT-1480
doc-type: feature video
activity: use
team: TM
recommendations: noDisplay
exl-id: fb766403-694c-4a7b-b3d1-4a418df85891
source-git-commit: b7c0c39339ff89bab2c81a3d9fd31f67b8ee4d71
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 90%

---

# 使用 Adobe Campaign Standard 使用者介面提出隱私權請求

Adobe Campaign 為資料掌控者提供三種方法，讓資料掌控者根據隱私權行為，例如 GDPR (一般資料保護規則) 和 CCPA (加州消費者隱私法)，執行 PII 資料的隱私權存取和刪除請求：

* **透過隱私權核心服務整合：**&#x200B;從推送至所有 Experience Cloud 解決方案[!UICONTROL Privacy Service]的隱私權請求，由 Campaign 透過專用工作流程自動處理。若要了解如何從隱私權核心服務建立隱私權要求，請參閱 [Adobe Experience Platform Privacy Service](https://developer.adobe.com/apis/experienceplatform/gdpr.html)

* **透過 API：** Adobe Campaign 提供 API，允許使用 REST 自動處理隱私權請求

* **透過 Adobe Campaign 介面：**&#x200B;針對每個隱私權請求，資料控制者會在 Adobe Campaign 建立新的隱私權請求

>[!NOTE]
>
> **ACS 19.4的變更：**
> 
> 此 [Privacy Service整合](https://developer.adobe.com/apis/experienceplatform/gdpr.html) 是您應用於所有存取和刪除要求的方法。 自 19.4 版本以來，不建議使用 Campaign API 和介面來存取和刪除請求。有關 Campaign Standard 已過時和已刪除功能的詳細資訊，請參閱[此頁](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hant)。
>
>**選擇退出個人資訊銷售 (CCPA)**
>
> Campaign 介面及 API 中會提供開箱即用的「CCPA 選擇退出」欄位。
>
> 您可以檢查您的版本，按一下&#x200B;**?**&#x200B;圖示並選取「關於」，即可檢查自己的版本資訊。

## 影片教學課程

### 隱私權請求的必要條件

1. [建立命名空間](/help/privacy/namespaces-for-privacy-requests.md)
1. [修改自訂資源](/help/privacy/custom-resources-for-privacy-requests.md)

### 透過 Adobe Campaign 使用者介面建立、追蹤及執行隱私權請求

* [透過 Adobe Campaign 使用者介面建立及追蹤隱私權請求](/help/privacy/create-and-track-privacy-requests.md)
* [執行隱私權請求](/help/privacy/execute-privacy-requests.md)

## 其他資源

* [Campaign 的一般隱私權指引](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=zh-Hant#getting-started)
* [ACS 的 CCPA](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=zh-Hant#privacy-requests)
* [Adobe Experience Platform 隱私權服務](https://developer.adobe.com/apis/experienceplatform/gdpr.html)
* [Adobe Campaign Standard REST API 文件](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#privacy-management)
