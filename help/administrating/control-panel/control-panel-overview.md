---
title: 控制面板
description: 「控制面板」可以讓您依執行個體及允許清單 IT 位址，監控及管理 SFTP 儲存。
feature: Control Panel
topics: Control Panel
kt: 4696
doc-type: feature video
activity: use
team: PM
translation-type: tm+mt
source-git-commit: db20c4e6aeb10dc04a6c4556fefaa8cd18366c44
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 100%

---


# [!UICONTROL Control Panel] {#control-panel}

>[!NOTE]
>
>Adobe Campaign 文件中的「[!UICONTROL whitelist]」及「[!UICONTROL blacklist]」字詞，已由「[!UICONTROL allow list]」及「[!UICONTROL block list]」取代。產品 UI、選項名稱、內部代碼及教學課程影片仍可能出現這些詞語。即將發行的「控制面板」版本，則將徹底取代原先的字詞。

[!UICONTROL Control Panel] 讓 Adobe Campaign 管理員監控關鍵資產並執行管理工作，例如依執行個體或 [!UICONTROL allow list] IP 位址管理 SFTP 儲存。

## 存取 [!UICONTROL Control Panel]

若要存取「控制面板」，請前往 Experience Cloud 首頁：[https://experiencecloud.adobe.com](https://experiencecloud.adobe.com)：

* **[!UICONTROL Experience Cloud Home]** > **[!UICONTROL Quick Access]**

   或
* **[!UICONTROL Experience Cloud Home]**  > [!UICONTROL Solution picker]：**Campaign** > **[!UICONTROL Control Panel]卡片&#x200B;**

   或

* 直接從 URL：[https://experience.adobe.com/#/controlpanel](https://experience.adobe.com/#/controlpanel)

## 必要條件

開始使用前，請先完成下列必要條件：

### 確認 [!DNL IMS Org ID]

您要瞭解您的 [!DNL IMS org ID]。以下影片說明您可以在何處查閱執行個體的 [!DNL IMS org ID]。

>[!VIDEO](https://video.tv.adobe.com/v/27183?quality=12)
*檢查[!DNL IMS Org ID](00:26 分鐘)*

### 管理員權限

必須擁有管理員權限才能存取 [!UICONTROL Control Panel]。
以下影片說明如何為 Campaign 執行個體新增管理員

>[!VIDEO](https://video.tv.adobe.com/v/27147?quality=12)
*如何為產品設定檔新增管理員「[!UICONTROL Administrators]」，以便使用[!UICONTROL Control Panel](01:03 分鐘)*

## 控制面板教學課程

* **管理 SFTP 伺服器**

   *瞭解如何監控伺服器容量、允許清單 IP 地址和新增 SSH 金鑰：*

   * [監控伺服器容量、允許清單 IP 位址和新增 SSH 金鑰](/help/administrating/control-panel/monitoring-server-capacity-allow-listing-adding-ssh-key.md)
   * [產生 SSH 金鑰](/help/administrating/control-panel/generate-ssh-key.md)
   * [連接到 SFTP 伺服器](/help/administrating/control-panel/connect-to-sftp-server.md)
* **[委派子網域](/help/administrating/control-panel/subdomain-delegation.md)**

   *瞭解如何將子網域完全委派至 Adobe Campaign*
* **[新增 SSL 憑證](/help/administrating/control-panel/adding-ssl-certificates.md)**

   *瞭解如何新增 SSL 憑證來保護您的子網域。*
* **[管理 SSL 憑證](/help/administrating/control-panel/managing-ssl-certificates.md)**

   *瞭解如何檢視子網域的 SSL 憑證狀態，以及要求續約。*
* **[Google TXT 記錄管理](/help/administrating/control-panel/google-txt-record-management.md)**

   *您可以透過 Campaign 控制面板，將 Google TXT 網站驗證紀錄新增至所有用於傳送電子郵件至 Gmail 地址的子網域。*

* **GPG 金鑰管理**

   *瞭解如何在指定的 Campaign 執行個體上產生和安裝公開/私人金鑰組，以加密傳出資料，以及在 Campaign 執行個體匯入和安裝公開金鑰，以解密傳入資料：*

   * [產生並安裝用於資料加密的 GPG 金鑰](./gpg-key-management/generating-and-installing-gpg-keys-for-data-encryption.md)
   * [使用 GPG 金鑰加密資料](./gpg-key-management/using-a-gpg-key-to-encrypt-data.md)
   * [解密資料](./gpg-key-management/decrypting-data.md)

* **[疑難排除](/help/administrating/control-panel/trouble-shooting.md)**

   *瞭解控制面板疑難排解*

## 其他資源：

* [控制面板說明中心](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/control-panel-home.html)

