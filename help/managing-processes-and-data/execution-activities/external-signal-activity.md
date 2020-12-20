---
title: 外部信號活動——使用參數調用工作流
description: 「外部信號活動」用於組織和協調不同的流程，這些流程是同一客戶歷程中不同工作流程的一部分。 它允許從另一個工作流程開始，以支援更複雜的客戶歷程，同時更能監控和回應問題。
feature: External Signal Activity
topics: Workflows
kt: 2750
thumbnail: 27249
doc-type: feature video
activity: use
team: TM
translation-type: tm+mt
source-git-commit: 11263e247184ddc6a8e3df6a8ed0899907fbb366
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 19%

---


# [!UICONTROL External Signal activity ]-使用參數呼叫工作流程

[!UICONTROL External Signal activity]用於組織和協調不同流程，這些流程是同一客戶歷程中不同工作流程的一部分。 它允許從另一個工作流程開始，以支援更複雜的客戶歷程，同時更能監控和回應問題。

在ACS 19.2中，[!UICONTROL External Signal activity]不僅可呼叫工作流，還可將參數傳遞至工作流（目標對象名、要導入的檔案名、消息內容的一部分等） 至其他工作流程或REST API呼叫的工作流程，以與您的外部系統整合。

這也包含新的&#x200B;**Test**&#x200B;活動，您可在其中執行此功能的測試。

以下視訊說明下列項目所需的設定步驟：

1. **從外部** 系統接收外部參數，例如內容管理系統(CRM):

   * 在「外部信號」活動中聲明參數
   * 設定API呼叫以定義參數並觸發工作流程「外部訊號活動」。 有關如何配置API調用的詳細資訊，請參閱[觸發信號活動](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity)。

1. **使用外部參數** （事件變數）自訂工作流程：

   觸發工作流程後，這些參數就會被收錄到工作流程的事件變數中，並可在工作流程中使用。 請參閱[documentation](https://helpx.adobe.com/campaign/standard/automating/using/calling-a-workflow-with-external-parameters.html)，以取得可使用事件變數自訂的所有活動：

   * 設定測試活動（19.2中的新功能）
   * 設定讀取對象和電子郵件傳送活動

1. **設定結束活** 動以使用外部參數呼叫工作流程

>[!VIDEO](https://video.tv.adobe.com/v/27249/?quality=12)

## 其他資源

* [外部信號（文檔）](https://docs.adobe.com/content/help/zh-Hant/campaign-standard/using/managing-processes-and-data/data-management-activities/external-api.html)
