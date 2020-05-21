---
title: 開啟控制面板時出現問題
description: 「控制面板」可讓您依例項和白名單IP位址來監控和管理您的SFTP儲存空間。
feature: Control Panel
topics: null
kt: 2938
doc-type: article
activity: use
team: PM
translation-type: tm+mt
source-git-commit: cb5d5bc58137fd374eafe165c6ea13288a60d7db
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---


# 拍攝[!UICONCONTROL控制面板}時出現問題

瞭解如何使用控制面板疑難排解問題。

## 登入和首頁

登入和首頁發生的問題。

### 症狀： 無法登入Adobe Experience Cloud

**該做什麼：**
使用者需要找到其 [!DNL IMS Org ID] (xxx)。 管理員需要將用戶添加到他們 [!UICONTROL product profile] 要管理的 [!DNL “Campaign-xxx-Admins”] 每個實例中。 如果使用者是所有例項的管理員，則他們仍需將自己新增為管理員 *[!UICONTROL user]*。

### 症狀： 使用者不 [!UICONTROL Adobe Experience Cloud Home] 會看 [!UICONTROL Control Panel] 到存取的連結

**原因：**
使用者直到新增為 [!UICONTROL product profile] `Campaign-xxx-Administrators/Admin`

**該做什麼：**
管理員需要將用戶添加到他們 [!UICONTROL product profile] 要管理的 *[!DNL Campaign-xxx-Admins]* 每個實例中。 如果使用者是所有例項的管理員，則他們仍需將自己新增為管理員 *[!UICONTROL user]*。

### 症狀： 例項未列於 [!UICONTROL Control Panel]

**原因：**
最有可能的使用者需要新增為 *[!UICONTROL user]* 遺失例 `!DNL Campaign-xxx-Administrators/Admin` 項的產品設定檔

**該做什麼：**
管理員需要將使用者新增至每個想要管 `Campaign-xxx-Admins` 理之例項的產品設定檔。 如果使用者是所有例項的管理員，則他們仍需將自己新增為管理員 *[!UICONTROL user]*。

### 有用的影片

>[!VIDEO](https://video.tv.adobe.com/v/27183?quality=12)
*檢[!DNL IMS Org ID]查（00:26分鐘）*

>[!VIDEO](https://video.tv.adobe.com/v/27147?quality=12)
*如何將管理員添[!UICONTROL product profile]加到&#x200B;*[!DNL administrators]*以便能夠使[!UICONTROL Control Panel]用（01:03分鐘）*

### 實用檔案

* [探索[!UICONCONTROL控制面板]](https://helpx.adobe.com/campaign/kb/control-panel-overview.html)
* [管理[!UICONCONTROL控制面板]的權限](https://helpx.adobe.com/campaign/kb/control-panel-access.html)

## 建立與SFTP伺服器（用戶端或API）的連線

連線至SFTP伺服器需要：

* [!UICONTROL Whitelisting] 您從中連接到SFTP伺服器的IP地址
* 需要向Adobe Campaign註冊的私密／公用金鑰對
* 如果直接連接到SFTP伺服器，您還需要SFTP客戶端軟體

### 實用檔案

* [登入您的SFTP伺服器](https://helpx.adobe.com/campaign/kb/control-panel-sftp.html#LoggingintoyourSFTPserver)

