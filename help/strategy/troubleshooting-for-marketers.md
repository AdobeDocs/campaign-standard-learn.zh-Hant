---
title: 面向營銷人員的故障排除
description: 瞭解最常見的錯誤有助於更快地解決問題並提高工作效率。 這些故障排除提示可幫助您在發生類似錯誤時有效地解決這些錯誤。
version: Standard
feature: Workflows
role: User
level: Beginner, Intermediate, Experienced
doc-type: Article
last-substantial-update: 2023-05-18T00:00:00Z
jira: KT-13256
thumbnail: KT-13256.jpeg
source-git-commit: 3da1b695d56f9deb5747cc89de023f19a5b25bad
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 1%

---


# 面向營銷人員的故障排除：5個常見工作流和交貨錯誤

依據： [蘇拉伊帕特拉](https://www.linkedin.com/in/suraj-p-51612053/){target="_blank"}, Meijer高級顧問

作為過去5年Adobe Experience Cloud產品的高級工程師和客戶專家，我使業務用戶能夠 [梅耶爾](https://www.meijer.com/){target="_blank"}美國超級中心連鎖公司成立於1934年，與ACS公司共同開展複雜的營銷和交易活動。 我參與過的幾個項目包括定制市場活動以儲存優惠和訂單詳細資訊以個性化，與Adobe Audience Manager整合，以及客戶洞察力以分部消化。


在使用ACS時，我遇到了一些錯誤，這些錯誤可能耗時且難以解決。 瞭解最常見的錯誤有助於更快地解決問題並提高工作效率。 下面是我的故障排除技巧，可幫助您在發生類似錯誤時有效地解決這些錯誤。

## 資料類型不匹配錯誤

**錯誤代碼:**
`PGS-220000 PostgreSQL error: ERROR: operator does not exist: character varying = bigint`

**原因：**
當您嘗試使用不同資料類型的欄位進行協調時，這些類型的錯誤會出現在工作流中。 例如，當您使用具有字串欄位的載入檔案上載檔案時，並嘗試將字串欄位與資料類型為int的配置檔案欄位協調。

![資料類型不匹配錯誤](/help/assets/kt-13256/data-type-mismatch.png)

**解決方案：**
將「載入檔案」活動中欄位的資料類型更改為您要匹配的資料類型。 開啟「載入檔案」活動。 移到「COLUMN DEFINITION」頁籤並更改所需欄位的資料類型。


![資料類型不匹配解](/help/assets/kt-13256/data-type-mismatch-solution.png)

## 傳遞個性化錯誤

**錯誤代碼:**
`The schema for profiles specified in the transition ('') is not compatible with the schema defined in the delivery template ('nms:recipient'). They should be identical.`

**原因：**
當您向某個地址發送電子郵件時會出現此錯誤，但電子郵件或任何其他標識符未與配置檔案協調。 要發送電子郵件通信，電子郵件或標識符應始終連結到配置檔案。

![協調活動的工作流](/help/assets/kt-13256/del-persn-error-wf.png)

**解決方案：**
必須從已載入的檔案中存在包含收件人表的公用ID。 此公用鍵將載入檔案聯接到協調活動中的收件人表。 電子郵件不能發送到要求工作流中此協調步驟的收件人表中不存在的記錄。 在執行此操作時，您將使用配置檔案中的標識符（如電子郵件ID）協調傳入的載入檔案活動。 的 `nms:recipient` schema引用配置檔案表，並將傳入記錄與配置檔案進行協調，使其在準備電子郵件期間可用。

請參閱下面所示的協調活動的螢幕快照。

![協調詳細資訊工作流](/help/assets/kt-13256/del-persn-error-wf-solution.png)

瞭解有關 [和解](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/data-management-activities/reconciliation.html?lang=en)。

## 公用欄位資料集錯誤

**錯誤代碼:**
`The document types of inbound events (''and'') are incompatible (step 'Exclusion'). Unable to perform the operation. `

**原因：**
使用 **排除活動** 在ACS工作流中，當根據ID執行排除時，當主集和排除集的欄位名稱不相同時。


![公用欄位資料集錯誤](/help/assets/kt-13256/dataset-error.png)

**解決方案:**

有兩種方法可解決此錯誤：

1. 在主欄位和排除欄位中使用相同的欄位名，並將該欄位用作ID

   或

2. 使用JOINS排除方法選擇要根據其排除記錄的欄位。

![常見欄位資料集錯誤 — 解決方案 ](/help/assets/kt-13256/dataset-error-solution.png)

## 欄位名稱刪除錯誤

**錯誤代碼:**
`XTK-170036 Unable to parse expression 'i__name'`

**原因：**

故障點可能發生在 **富集活性**。 下面顯示了最常見的一種。

![欄位名稱刪除錯誤](/help/assets/kt-13256/field-name-dropped-error.png)

手動編輯活動中的表達式名稱時會發生這種情況。 該圖顯示表達式已從 `name `至 `i__name`。

**解決方案:**

可以通過以下三種方式解決此錯誤：

1. 將名稱更改回原來存在的表達式。

2. 如果要使用新名稱，請更改 **富集活性**。

3. 如果您不記得已發生的更改，您最好的選擇是重新建立活動。

## 臨時表刪除錯誤 

**錯誤代碼:**
`XTK-170024 The temporary schema "temp:deliveryEmail1" is not defined in the current context.`

**原因：**
在涉及豐富或其他活動的複雜工作流中，這是常見的錯誤。 這可能意味著在對工作流進行多次更改時，某些活動工作流未正確保存。

![臨時表刪除錯誤 ](/help/assets/kt-13256/temp-table-dropped-error.png)

**解決方案：**
出現此錯誤的方式有很多，因此沒有簡單的修複方法。 如果是簡單的工作流，則最好重新配置活動。 在複雜的工作流中，最好將工作流活動複製到新工作流中，保存並重新運行它。