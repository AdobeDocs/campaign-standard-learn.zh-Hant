---
title: 外部訊號活動 — 使用參數呼叫工作流程
description: 了解如何從另一個工作流程開始支援更複雜的客戶歷程，同時更能監控和回應問題。
feature: 執行活動
kt: 2750
thumbnail: 27249
doc-type: feature video
activity: use
team: TM
exl-id: d3996185-681c-4906-85f0-0543ab767519
role: User, Developer
level: Experienced
source-git-commit: 2be2719ddd84490b796d9abc6300376fa896ff0c
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 9%

---

# [!UICONTROL External Signal activity ] — 使用參數呼叫工作流程

[!UICONTROL External Signal activity]可用來組織和協調不同的流程，這些流程是同一客戶歷程中不同工作流程的一部分。 它允許從另一個工作流程開始，以支援更複雜的客戶歷程，同時更能監控和回應問題。

在ACS 19.2中，[!UICONTROL External Signal activity]不僅可以調用工作流，而且還可以將參數傳遞到工作流（要定位的對象名、要導入的檔案名、消息內容的一部分等） 從其他工作流程或REST API呼叫移轉至工作流程，以與外部系統整合。

這也包含新的&#x200B;**Test**&#x200B;活動，您可在此功能上執行測試。

以下影片說明所需的設定步驟：

1. **從外部** 系統(如內容管理系統(CRM))接收外部參數：

   * 在外部信號活動中聲明參數
   * 設定API呼叫以定義參數並觸發工作流程外部訊號活動。 如需如何設定API呼叫的詳細資訊，請參閱[觸發訊號活動](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity)。

1. **使用外部參數** （事件變數）自訂工作流程：

   觸發工作流程後，參數會擷取至工作流程的事件變數中，並可在工作流程中使用。 如需所有可使用事件變數自訂的活動，請參閱[檔案](https://helpx.adobe.com/campaign/standard/automating/using/calling-a-workflow-with-external-parameters.html):

   * 設定測試活動（19.2中的新功能）
   * 設定讀取對象和電子郵件傳送活動

1. **設定結束活** 動以使用外部參數呼叫工作流程

>[!VIDEO](https://video.tv.adobe.com/v/27249/?quality=12)

## 其他資源

* [外部信號（文檔）](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/calling-workflow-external-parameters/calling-a-workflow-with-external-parameters.html)
