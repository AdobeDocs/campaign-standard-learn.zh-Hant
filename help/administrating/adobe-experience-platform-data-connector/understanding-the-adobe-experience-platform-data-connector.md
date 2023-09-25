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
source-wordcount: '270'
ht-degree: 4%

---

# 瞭解Adobe Experience Platform [!UICONTROL Data Connector]

>[!NOTE]
>
>此功能為測試版，且可能會不時更新和修改，恕不另行通知。
>
>請聯絡 [!UICONTROL Adobe Customer Support] 如果您計畫實作此功能。

## 概覽

Adobe Experience Platform [!UICONTROL Data Connector] 將XTK資料(在Adobe Campaign中擷取的資料)對應至Adobe Experience Platform，協助現有客戶使其資料可在上使用 [!DNL Experience Data Model] (XDM) Adobe Experience Platform上的資料。

聯結器是單向的，會將資料從Adobe Campaign Standard傳送至Adobe Experience Platform。 資料絕不會從Adobe Experience Platform傳送至Adobe Campaign Standard。

Adobe Experience Platform [!UICONTROL Data Connector] 專為瞭解Adobe Campaign Standard的資料工程師所設計 [!UICONTROL custom resources] 並瞭解客戶的整體資料結構應如何在Adobe Experience Platform中。

>[!VIDEO](https://video.tv.adobe.com/v/27304?learn=on){transcript=true}

*這部影片會概略介紹Adobe Experience Platform [!UICONTROL Data Connector] （09:35分鐘）*

>[!NOTE]
>
>現成可用的傳輸 [!UICONTROL subscription events] 不受支援。 要轉移 [!UICONTROL subscription events]，您可以在Adobe Experience Platform上建立對應的XDM和資料集，然後為這些資料設定自訂資料對應。
>
>現有 [!UICONTROL experience events] 無法擷取至Adobe Experience Platform，但正在產生 [!UICONTROL experience events] 會串流至Adobe Experience Platform。

## 執行資料對應的重要步驟

下列教學課程說明在Campaign Standard和Adobe Experience Platform之間執行資料對應的關鍵步驟：

1. [對應自訂資源](/help/administrating/adobe-experience-platform-data-connector/mapping-custom-resources.md)
2. [對應體驗事件](/help/administrating/adobe-experience-platform-data-connector/mapping-experience-events.md)
3. [對應種子表格資料](/help/administrating/adobe-experience-platform-data-connector/mapping-seed-table-data.md)
4. [修改資料對應](/help/administrating/adobe-experience-platform-data-connector/modifying-data-mapping.md)
5. [檢查資料擷取作業的狀態](/help/administrating/adobe-experience-platform-data-connector/checking-status-of-data-ingestion-jobs.md)

