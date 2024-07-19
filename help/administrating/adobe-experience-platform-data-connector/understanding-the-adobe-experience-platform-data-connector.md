---
title: 瞭解Adobe Experience Platform資料聯結器
description: Adobe Experience Platform Data Connector將XTK資料（在Campaign中擷取的資料）對應至Adobe Experience Platform上的Experience Data Model (XDM)資料，協助現有客戶在Adobe Experience Platform上提供其資料。
feature: People Core Service Integration
jira: KT-2826
thumbnail: 27304.jpg
role: User
level: Experienced
doc-type: feature video
activity: understand
team: TM
exl-id: 686961f9-5374-4cc6-8b36-7ee0584ea720
source-git-commit: 943599bd7ce139ef846f093ebda9084a91550aca
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 5%

---

# 瞭解Adobe Experience Platform [!UICONTROL Data Connector]

>[!NOTE]
>
>此功能為測試版，且可能會不時更新和修改，恕不另行通知。
>
>如果您計畫實作此功能，請聯絡[!UICONTROL Adobe Customer Support]。

## 概覽

Adobe Experience Platform [!UICONTROL Data Connector]將XTK資料(在Adobe Experience Platform中擷取的資料)對應至Adobe Experience Platform上的[!DNL Experience Data Model] (XDM)資料，協助現有客戶使其資料可在Adobe Campaign上使用。

聯結器是單向的，會將資料從Adobe Campaign Standard傳送至Adobe Experience Platform。 資料絕不會從Adobe Experience Platform傳送至Adobe Campaign Standard。

Adobe Experience Platform [!UICONTROL Data Connector]是專為瞭解Adobe Campaign Standard [!UICONTROL custom resources]，並瞭解客戶整體資料結構描述應如何存在於Adobe Experience Platform中的資料工程師所設計。

>[!VIDEO](https://video.tv.adobe.com/v/27304?learn=on){transcript=true}

*此影片概述Adobe Experience Platform [!UICONTROL Data Connector] （09:35分鐘）*

>[!NOTE]
>
>不支援現成可用的[!UICONTROL subscription events]傳輸。 若要傳輸[!UICONTROL subscription events]，您可以在Adobe Experience Platform上建立對應的XDM和資料集，然後為這些資料設定自訂資料對應。
>
>無法將現有的[!UICONTROL experience events]擷取到Adobe Experience Platform，但進行中產生的[!UICONTROL experience events]會串流到Adobe Experience Platform。

## 執行資料對應的重要步驟

下列教學課程說明在Campaign Standard和Adobe Experience Platform之間執行資料對應的關鍵步驟：

1. [對應自訂資源](/help/administrating/adobe-experience-platform-data-connector/mapping-custom-resources.md)
2. [對應體驗事件](/help/administrating/adobe-experience-platform-data-connector/mapping-experience-events.md)
3. [對應種子表格資料](/help/administrating/adobe-experience-platform-data-connector/mapping-seed-table-data.md)
4. [修改資料對應](/help/administrating/adobe-experience-platform-data-connector/modifying-data-mapping.md)
5. [檢查資料擷取作業的狀態](/help/administrating/adobe-experience-platform-data-connector/checking-status-of-data-ingestion-jobs.md)

