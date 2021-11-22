---
title: 了解Adobe Experience Platform Data Connector
description: Adobe Experience Platform Data Connector可將XTK資料（在Campaign中擷取的資料）對應至Adobe Experience Platform上的Experience Data Model(XDM)資料，以協助現有客戶將其資料在Adobe Experience Platform上可用。
feature: People Core Service Integration
kt: 2826
thumbnail: 27304.jpg
doc-type: feature video
activity: understand
team: TM
exl-id: 686961f9-5374-4cc6-8b36-7ee0584ea720
source-git-commit: 2ba22e7e7d193278fd06cb4b2dc80f650f754ec8
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 7%

---

# 了解Adobe Experience Platform [!UICONTROL Data Connector]

>[!NOTE]
>
>此功能為測試版，可能會不時更新和修改，恕不另行通知。
>
>請聯繫 [!UICONTROL Adobe Customer Support] 如果您計畫實作此功能。

## 概覽

Adobe Experience Platform [!UICONTROL Data Connector] 協助現有客戶將XTK資料(在Adobe Campaign中擷取的資料)對應至 [!DNL Experience Data Model] (XDM)Adobe Experience Platform上的資料。

連接器為單向連接，會將資料從Adobe Campaign Standard傳送至Adobe Experience Platform。 資料從不會從Adobe Experience Platform傳送至Adobe Campaign Standard。

Adobe Experience Platform [!UICONTROL Data Connector] 適用於了解Adobe Campaign Standard的資料工程師 [!UICONTROL custom resources] 並了解客戶的整體資料結構在Adobe Experience Platform中應如何呈現。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12)

*此影片提供Adobe Experience Platform的概觀 [!UICONTROL Data Connector] （09:35分鐘）*

>[!NOTE]
>
>現成可用的 [!UICONTROL subscription events] 不支援。 要轉移 [!UICONTROL subscription events]，您可以在Adobe Experience Platform上建立對應的XDM和資料集，然後為這些資料設定自訂資料對應。
>
>現有 [!UICONTROL experience events] 無法擷取至Adobe Experience Platform，但持續產生 [!UICONTROL experience events] 會串流到Adobe Experience Platform。

## 執行資料對應的關鍵步驟

下列教學課程說明在Campaign Standard和Adobe Experience Platform之間執行資料對應的關鍵步驟：

1. [對應自訂資源](/help/administrating/adobe-experience-platform-data-connector/mapping-custom-resources.md)
2. [對應體驗事件](/help/administrating/adobe-experience-platform-data-connector/mapping-experience-events.md)
3. [映射種子表資料](/help/administrating/adobe-experience-platform-data-connector/mapping-seed-table-data.md)
4. [修改資料對應](/help/administrating/adobe-experience-platform-data-connector/modifying-data-mapping.md)
5. [檢查資料擷取作業的狀態](/help/administrating/adobe-experience-platform-data-connector/checking-status-of-data-ingestion-jobs.md)

## 其他資源

* [關於 Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html)

