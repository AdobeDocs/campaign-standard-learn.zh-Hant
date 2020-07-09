---
title: 控制面板
description: 「控制面板」可讓您依例項監視和管理SFTP儲存空間，並允許列出IP位址。
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
ht-degree: 4%

---


# [!UICONTROL Control Panel] {#control-panel}

>[!NOTE]
>
>Adobe Campaign文[!UICONTROL whitelist]件中的「[!UICONTROL blacklist]」和「」已取代[!UICONTROL allow list]「」和[!UICONTROL block list]「」。 產品UI、選項名稱、內部程式碼以及教學課程影片中可能仍會出現這些詞語。 在即將發行的「控制面板」版本中，將會取代它們。

可 [!UICONTROL Control Panel] 讓Adobe Campaign管理員監控關鍵資產並執行管理工作，例如依例項或IP位址管理SFTP [!UICONTROL allow list] 儲存。

## 存取 [!UICONTROL Control Panel]

若要存取「控制面板」，請前往Experience Cloud首頁： [https://experiencecloud.adobe.com](https://experiencecloud.adobe.com):

* **[!UICONTROL Experience Cloud Home]** > **[!UICONTROL Quick Access]**

   或
* **[!UICONTROL Experience Cloud Home]**  > [!UICONTROL Solution picker]: **促銷活動** > **[!UICONTROL Control Panel]卡片&#x200B;**

   或

* 直接從URL: [https://experience.adobe.com/#/controlpanel](https://experience.adobe.com/#/controlpanel)

## 必要條件

開始之前，請先完成下列必要條件：

### 確認 [!DNL IMS Org ID]

你要瞭解你的 [!DNL IMS org ID]。 以下視訊說明您可以在何處查閱例項 [!DNL IMS org ID]。

>[!VIDEO](https://video.tv.adobe.com/v/27183?quality=12)
*檢[!DNL IMS Org ID]查（00:26分鐘）*

### 管理員權限

必須擁有管理員權限才能訪問 [!UICONTROL Control Panel]。
以下影片說明如何新增管理員至促銷活動例項

>[!VIDEO](https://video.tv.adobe.com/v/27147?quality=12)
*如何將管理員新增至產品設定檔「[!UICONTROL Administrators]」，以便能夠使用([!UICONTROL Control Panel]01:03分鐘)*

## 控制面板教學課程

* **管理SFTP伺服器**

   *瞭解如何監控伺服器容量、允許列出IP地址和添加SSH密鑰：*

   * [監控伺服器容量、允許列出IP地址和添加SSH密鑰](/help/administrating/control-panel/monitoring-server-capacity-allow-listing-adding-ssh-key.md)
   * [生成SSH密鑰](/help/administrating/control-panel/generate-ssh-key.md)
   * [連接到SFTP伺服器](/help/administrating/control-panel/connect-to-sftp-server.md)
* **[委派子網域](/help/administrating/control-panel/subdomain-delegation.md)**

   *瞭解如何將子網域完全委派至Adobe Campaign*
* **[新增SSL憑證](/help/administrating/control-panel/adding-ssl-certificates.md)**

   *瞭解如何新增SSL憑證來保護您的子網域。*
* **[管理SSL憑證](/help/administrating/control-panel/managing-ssl-certificates.md)**

   *瞭解如何檢視子網域的SSL憑證狀態，以及要求續約。*
* **[Google TXT 記錄管理](/help/administrating/control-panel/google-txt-record-management.md)**

   *瞭解如何將Google TXT網站驗證記錄新增至您所有透過「促銷活動控制面板」傳送電子郵件至GMAIL位址的子網域。*

* **GPG密鑰管理**

   *瞭解如何在指定的促銷活動例項上產生和安裝公開／私密金鑰對，以加密傳出資料，以及在促銷活動例項上匯入和安裝公開金鑰，以解密傳入資料：*

   * [生成並安裝用於資料加密的GPG密鑰](./gpg-key-management/generating-and-installing-gpg-keys-for-data-encryption.md)
   * [使用GPG密鑰加密資料](./gpg-key-management/using-a-gpg-key-to-encrypt-data.md)
   * [解密資料](./gpg-key-management/decrypting-data.md)

* **[故障排除](/help/administrating/control-panel/trouble-shooting.md)**

   *瞭解如何疑難排解控制面板*

## 其他資源

* [控制面板說明中心](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/control-panel-home.html)

