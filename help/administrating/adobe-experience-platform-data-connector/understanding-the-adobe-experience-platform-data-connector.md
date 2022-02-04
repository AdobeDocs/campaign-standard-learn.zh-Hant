---
title: 瞭解Adobe Experience Platform資料連接器
description: Adobe Experience Platform資料連接器通過將XTK資料（在活動中攝取的資料）映射到Adobe Experience Platform的經驗資料模型(XDM)資料，幫助現有客戶提供其Adobe Experience Platform資料。
feature: People Core Service Integration
kt: 2826
thumbnail: 27304.jpg
doc-type: feature video
activity: understand
team: TM
exl-id: 686961f9-5374-4cc6-8b36-7ee0584ea720
source-git-commit: cccc2cd4141d4da4d06132af8bab3f15f7ecc853
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 4%

---

# 理解Adobe Experience Platform [!UICONTROL Data Connector]

>[!NOTE]
>
>此功能為Beta版，並且需要頻繁更新和修改，恕不另行通知。
>
>請聯繫 [!UICONTROL Adobe Customer Support] 如果您計畫實施此功能。

## 概覽

Adobe Experience Platform [!UICONTROL Data Connector] 通過將XTK資料(在Adobe Campaign接收的資料)映射到 [!DNL Experience Data Model] (XDM)Adobe Experience Platform資料。

連接器是單向的，並將資料從Adobe Campaign Standard發送到Adobe Experience Platform。 資料從未從Adobe Experience Platform發送到Adobe Campaign Standard。

Adobe Experience Platform [!UICONTROL Data Connector] 是為瞭解Adobe Campaign Standard的資料工程師準備的 [!UICONTROL custom resources] 並瞭解客戶的整體資料架構應如何位於Adobe Experience Platform。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12)

*此視頻概述了Adobe Experience Platform [!UICONTROL Data Connector] （09:35分）*

>[!NOTE]
>
>開箱轉移 [!UICONTROL subscription events] 不支援。 要轉移 [!UICONTROL subscription events]，可以在Adobe Experience Platform建立相應的XDM和資料集，然後為這些資料配置自定義資料映射。
>
>現有 [!UICONTROL experience events] 不能被攝入Adobe Experience Platform，但正在生成 [!UICONTROL experience events] 都是流到Adobe Experience Platform。

## 執行資料映射的關鍵步驟

以下教程介紹在Campaign Standard和Adobe Experience Platform之間執行資料映射的關鍵步驟：

1. [映射自定義資源](/help/administrating/adobe-experience-platform-data-connector/mapping-custom-resources.md)
2. [對應體驗事件](/help/administrating/adobe-experience-platform-data-connector/mapping-experience-events.md)
3. [映射種子表資料](/help/administrating/adobe-experience-platform-data-connector/mapping-seed-table-data.md)
4. [修改資料映射](/help/administrating/adobe-experience-platform-data-connector/modifying-data-mapping.md)
5. [檢查資料擷取作業的狀態](/help/administrating/adobe-experience-platform-data-connector/checking-status-of-data-ingestion-jobs.md)

