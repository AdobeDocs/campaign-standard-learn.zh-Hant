---
title: 控制面板疑難排解
description: 「控制面板」可以讓您依執行個體及允許清單 IT 位址，監控及管理 SFTP 儲存。
feature: Control Panel
topics: null
kt: 2938
doc-type: article
activity: use
team: PM
translation-type: tm+mt
source-git-commit: f120eaf237378db3ddd5833930c0222ee028941d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 疑難排解 [!UICONTROL Control Panel]

瞭解使用控制面板時，如何進行問題疑難排解。

## 登入和首頁

登入和首頁發生的問題。

### 症狀：無法登入 Adobe Experience Cloud

**該做什麼：**
使用者需要找到其 [!DNL IMS Org ID] (xxx)。管理員需要將使用者新增到 [!UICONTROL product profile] [!DNL “Campaign-xxx-Admins”] 他們想要管理的每個執行個體。如果使用者是所有執行個體的管理員，則他們仍需將自己新增為 *[!UICONTROL user]*。

### 症狀：使用者看不到 [!UICONTROL Adobe Experience Cloud Home] 中存取 [!UICONTROL Control Panel] 的連結

**原因：**
使用者新增為 [!UICONTROL product profile] `Campaign-xxx-Administrators/Admin`的使用者後，才可以看到連結

**該做什麼：**
管理員需要將使用者新增到他們想要管理的每個執行個體的 [!UICONTROL product profile] *[!DNL Campaign-xxx-Admins]*。如果使用者是所有執行個體的管理員，則他們仍需將自己新增為 *[!UICONTROL user]*。

### 症狀：執行個體未列於 [!UICONTROL Control Panel]

**原因：**
可能是使用者需要新增為消失的執行個體的 *[!UICONTROL user]* 產品設定檔 `Campaign-xxx-Administrators/Admin` 

**該做什麼：**
管理員需要將使用者新增到他們想要管理的每個執行個體的產品設定檔 `Campaign-xxx-Admins`。如果使用者是所有執行個體的管理員，則他們仍需將自己新增為 *[!UICONTROL user]*。

### 有用的影片

>[!VIDEO](https://video.tv.adobe.com/v/27183?quality=12)

*檢查 [!DNL IMS Org ID] （00:26 分鐘）*

>[!VIDEO](https://video.tv.adobe.com/v/27147?quality=12)

*如何為 [!UICONTROL product profile] [!DNL administrators] 新增管理員，以利使用 [!UICONTROL Control Panel]（01:03 分鐘）*

### 實用文件

* [探索 [!UICONTROL Control Panel]](https://helpx.adobe.com/tw/campaign/kb/control-panel-overview.html)
* [管理 [!UICONTROL Control Panel]的權限](https://helpx.adobe.com/tw/campaign/kb/control-panel-access.html)

## 建立與 SFTP 伺服器（用戶端或 API）的連線

連線至 SFTP 伺服器需要：

* [!UICONTROL allow listing] 您連接到 SFTP 伺服器的 IP 位址
* 需要向 Adobe Campaign 註冊私人/公有金鑰組
* 如果直接連接到 SFTP 伺服器，您還需要 SFTP 用戶端軟體

### 實用文件 {#helpful-docs}

* [登入您的 SFTP 伺服器](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/control-panel-home.html#LoggingintoyourSFTPserver)

