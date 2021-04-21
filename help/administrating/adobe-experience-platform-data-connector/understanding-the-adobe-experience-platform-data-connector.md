---
title: 瞭解 Adobe Experience Platform Data Connector
description: Adobe Experience Platform資料連接器將XTK資料（收錄於促銷活動的資料）對應至Adobe Experience Platform的體驗資料模型(XDM)資料，協助現有客戶在Adobe Experience Platform提供其資料。
feature: Adobe Experience Platform Data Connector
kt: 2826
thumbnail: 27304.jpg
doc-type: feature video
activity: understand
team: TM
exl-id: 686961f9-5374-4cc6-8b36-7ee0584ea720
translation-type: tm+mt
source-git-commit: ada0b029245190f53d58fa93c79c161719bfe9fd
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 11%

---

# 瞭解Adobe Experience Platform[!UICONTROL Data Connector]

>[!NOTE]
>
>此功能目前為測試版，可能會經常更新和修改，恕不另行通知。
>
>如果您計畫實施此功能，請聯絡[!UICONTROL Adobe Customer Support]。

## 概覽

Adobe Experience Platform[!UICONTROL Data Connector]將Adobe Experience Platform的XTK資料(收錄於Adobe Campaign的資料)對應至Adobe Experience Platform的[!DNL Experience Data Model](XDM)資料，協助現有客戶在提供其資料。

請注意，連接器是單向的，會將資料從Adobe Campaign Standard傳送至Adobe Experience Platform。 資料從未從Adobe Experience Platform發送到Adobe Campaign Standard。

Adobe Experience Platform[!UICONTROL Data Connector]是專為瞭解Adobe Campaign Standard[!UICONTROL custom resources]並瞭解客戶整體資料架構在Adobe Experience Platform內部的資料工程師而設計。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12)

*此視訊概述Adobe Experience Platform(09 [!UICONTROL Data Connector] :35分鐘)*

>[!NOTE]
>
>不支援[!UICONTROL subscription events]的現成傳輸。 若要傳輸[!UICONTROL subscription events]，您可以在Adobe Experience Platform建立對應的XDM和資料集，然後為這些資料設定自訂資料對應。
>
>現有的[!UICONTROL experience events]無法被收錄到Adobe Experience Platform，但正在產生的[!UICONTROL experience events]將被串流到Adobe Experience Platform。

## 執行資料映射的關鍵步驟

以下教學課程說明在Campaign Standard和Adobe Experience Platform之間執行資料映射的關鍵步驟：

1. [對應自訂資源](/help/administrating/adobe-experience-platform-data-connector/mapping-custom-resources.md)
2. [對應體驗事件](/help/administrating/adobe-experience-platform-data-connector/mapping-experience-events.md)
3. [映射種子表資料](/help/administrating/adobe-experience-platform-data-connector/mapping-seed-table-data.md)
4. [修改資料映射](/help/administrating/adobe-experience-platform-data-connector/modifying-data-mapping.md)
5. [檢查資料擷取作業的狀態](/help/administrating/adobe-experience-platform-data-connector/checking-status-of-data-ingestion-jobs.md)

## 其他資源

* [關於 Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-about-data-connector.html)
* [體驗資料模型概觀](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-data-model-overview.html)
* [映射定義](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-mapping-definition.html)
* [映射啟動](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-mapping-activation.html)
* [透過 API 觸發資料引入](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-triggering-data-ingestion.html)
