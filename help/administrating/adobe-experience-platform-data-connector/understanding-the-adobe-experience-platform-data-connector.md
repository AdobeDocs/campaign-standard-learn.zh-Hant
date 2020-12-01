---
title: 瞭解 Adobe Experience Platform Data Connector
description: Adobe Experience Platform Data Connector將XTK資料（在Campaign中收錄的資料）對應至Adobe Experience Platform上的Experience Data Model(XDM)資料，協助現有客戶在Adobe Experience Platform上提供其資料。
feature: Adobe Experience Platform Data Connector
topics: ACoP
kt: 2826
thumbnail: 27304.jpg
doc-type: feature video
activity: understand
team: TM
translation-type: tm+mt
source-git-commit: 11263e247184ddc6a8e3df6a8ed0899907fbb366
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 10%

---


# Understanding the Adobe Experience Platform [!UICONTROL Data Connector]

>[!NOTE]
>
>此功能目前為測試版，可能會經常更新和修改，恕不另行通知。
>
>如果您計畫實 [!UICONTROL Adobe Customer Support] 作此功能，請聯絡。

## 概觀

Adobe Experience Platform將XTK資料（在Adobe Campaign中擷取的資料）對應至Adobe Experience Platform上的 [!UICONTROL Data Connector][!DNL Experience Data Model] (XDM)資料，協助現有客戶將其資料發佈至Adobe Experience Platform。

請注意，此連接器是單向的，會將資料從Adobe Campaign Standard傳送至Adobe Experience Platform。 資料從未從Adobe Experience Platform傳送至Adobe Campaign Standard。

Adobe Experience Platform是 [!UICONTROL Data Connector] 專為瞭解Adobe Campaign Standard並瞭解 [!UICONTROL custom resources] 客戶整體資料架構應如何位於Adobe Experience Platform內的資料工程師而設計。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12)

*此影片提供Adobe Experience Platform的概觀(09 [!UICONTROL Data Connector] :35分鐘)*

>[!NOTE]
>
>不支援現成可用的 [!UICONTROL subscription events] 傳輸。 若要傳 [!UICONTROL subscription events]輸，您可以在Adobe Experience Platform上建立對應的XDM和資料集，然後為這些資料設定自訂資料對應。
>
>現有 [!UICONTROL experience events] 的Adobe Experience Platform無法吸收，但持續產生的 [!UICONTROL experience events] 內容會串流至Adobe Experience Platform。

## 執行資料映射的關鍵步驟

下列教學課程說明在Campaign Standard和Adobe Experience Platform之間執行資料對應的關鍵步驟：

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
