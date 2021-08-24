---
title: 瞭解 Adobe Experience Platform Data Connector
description: Adobe Experience Platform Data Connector可將XTK資料（在Campaign中擷取的資料）對應至Adobe Experience Platform上的Experience Data Model(XDM)資料，以協助現有客戶將其資料在Adobe Experience Platform上可用。
feature: 人員核心服務整合
kt: 2826
thumbnail: 27304.jpg
doc-type: feature video
activity: understand
team: TM
exl-id: 686961f9-5374-4cc6-8b36-7ee0584ea720
source-git-commit: 64940a739897c3969574dcf1d1e36c5a986d0473
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 10%

---

# 了解Adobe Experience Platform [!UICONTROL Data Connector]

>[!NOTE]
>
>此功能目前仍在測試階段，可能會不時更新和修改，恕不另行通知。
>
>如果您計畫實作此功能，請聯絡[!UICONTROL Adobe Customer Support]。

## 概覽

Adobe Experience Platform [!UICONTROL Data Connector]將XTK資料(在Adobe Campaign中擷取的資料)對應至Adobe Experience Platform上的[!DNL Experience Data Model](XDM)資料，以協助現有客戶使其資料可在Adobe Experience Platform上使用。

請注意，連接器為單向連接，會將資料從Adobe Campaign Standard傳送至Adobe Experience Platform。 資料從不會從Adobe Experience Platform傳送至Adobe Campaign Standard。

Adobe Experience Platform [!UICONTROL Data Connector]適用於了解Adobe Campaign Standard [!UICONTROL custom resources]且了解客戶整體資料結構應如何存在於Adobe Experience Platform的資料工程師。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12)

*此影片提供Adobe Experience Platform的概 [!UICONTROL Data Connector] 觀（09:35分鐘）*

>[!NOTE]
>
>不支援[!UICONTROL subscription events]的現成傳輸。 若要傳輸[!UICONTROL subscription events]，您可以在Adobe Experience Platform上建立對應的XDM和資料集，然後為這些資料設定自訂資料對應。
>
>無法將現有的[!UICONTROL experience events]擷取至Adobe Experience Platform，但持續產生的[!UICONTROL experience events]會串流至Adobe Experience Platform。

## 執行資料對應的關鍵步驟

下列教學課程說明在Campaign Standard和Adobe Experience Platform之間執行資料對應的關鍵步驟：

1. [對應自訂資源](/help/administrating/adobe-experience-platform-data-connector/mapping-custom-resources.md)
2. [對應體驗事件](/help/administrating/adobe-experience-platform-data-connector/mapping-experience-events.md)
3. [映射種子表資料](/help/administrating/adobe-experience-platform-data-connector/mapping-seed-table-data.md)
4. [修改資料對應](/help/administrating/adobe-experience-platform-data-connector/modifying-data-mapping.md)
5. [檢查資料擷取作業的狀態](/help/administrating/adobe-experience-platform-data-connector/checking-status-of-data-ingestion-jobs.md)

## 其他資源

* [關於 Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-about-data-connector.html)
* [體驗資料模型概觀](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-data-model-overview.html)
* [映射定義](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-mapping-definition.html)
* [映射啟動](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-mapping-activation.html)
* [透過 API 觸發資料引入](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-triggering-data-ingestion.html)
