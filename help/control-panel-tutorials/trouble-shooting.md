---
title: 控制面板疑難排解
description: 「控制面板」可讓您依執行個體及允許清單IP位址來監視和管理您的SFTP儲存。
feature: Control Panel
kt: 2938
doc-type: article
activity: use
team: PM
exl-id: f546f791-a69b-4586-abfa-3e626b8feb17
source-git-commit: 481cbdcc9ac7446cc36fbff6e3d6e43fe333d30b
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 47%

---

# 疑難排解 [!UICONTROL Control Panel]

瞭解使用控制面板時，如何進行問題疑難排解。

## 登入和首頁

登入和首頁發生的問題。

### 症狀：無法登入Adobe Experience Cloud

**該做什麼：**
使用者必須找到 [!DNL IMS Org ID] (xxx)。 管理員必須將使用者新增至 [!UICONTROL product profile] [!DNL “Campaign-xxx-Admins”] 針對他們想要管理的每個例項。 如果使用者是所有執行個體的管理員，則使用者必須將自己新增為 *[!UICONTROL user]*.

### 症狀：使用者看不到 [!UICONTROL Adobe Experience Cloud Home] 中存取 [!UICONTROL Control Panel] 的連結

**原因：**
使用者新增為 [!UICONTROL product profile] `Campaign-xxx-Administrators/Admin`的使用者後，才可以看到連結

**該做什麼：**
管理員必須將使用者新增至 [!UICONTROL product profile] *[!DNL Campaign-xxx-Admins]* 針對他們想要管理的每個例項。 如果使用者是所有執行個體的管理員，則使用者必須將自己新增為 *[!UICONTROL user]*.

### 症狀：執行個體未列於 [!UICONTROL Control Panel]

**原因：**
最可能的使用者必須新增為 *[!UICONTROL user]* 產品設定檔 `Campaign-xxx-Administrators/Admin` 缺少的實例

**該做什麼：**
管理員必須將使用者新增至產品設定檔 `Campaign-xxx-Admins` 針對他們想要管理的每個例項。 如果使用者是所有執行個體的管理員，則使用者必須將自己新增為 *[!UICONTROL user]*.

### 有用的影片

>[!VIDEO](https://video.tv.adobe.com/v/27183?quality=12)

*檢查 [!DNL IMS Org ID] （00:26 分鐘）*

>[!VIDEO](https://video.tv.adobe.com/v/27147?quality=12)

*如何為 [!UICONTROL product profile] [!DNL administrators] 新增管理員，以利使用 [!UICONTROL Control Panel]（01:03 分鐘）*

### 實用文件

* [探索 [!UICONTROL Control Panel]](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant)
* [管理 [!UICONTROL Control Panel]的權限](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=en)

## 建立與 SFTP 伺服器（用戶端或 API）的連線

連線至 SFTP 伺服器需要：

* [!UICONTROL allow listing] 您連接到 SFTP 伺服器的 IP 位址
* 需要以 Adobe Campaign 註冊私人/公有金鑰組
* 如果直接連線至SFTP伺服器，您需要SFTP用戶端軟體

### 實用文件 {#helpful-docs}

* [登入您的 SFTP 伺服器](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=en)
