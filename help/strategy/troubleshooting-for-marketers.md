---
title: 行銷人員疑難排解
description: 瞭解最常見的錯誤有助於更快地解決問題，並提高生產力。 這些疑難排解提示可協助您有效解決類似錯誤。
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


# 行銷人員疑難排解：5個常見工作流程和傳送錯誤

作者： [蘇拉傑·帕特拉](https://www.linkedin.com/in/suraj-p-51612053/){target="_blank"}，資深顧問，梅傑

身為過去五年的Adobe Experience Cloud產品資深工程師和客戶專家，我能夠在以下位置支援業務使用者： [梅耶爾](https://www.meijer.com/){target="_blank"}成立於1934年的美國超級中心連鎖店，使用ACS執行複雜的行銷和交易式行銷活動。 我參與的一些專案包含自訂行銷活動，以儲存個人化的選件和訂單詳細資料、與Adobe Audience Manager整合，以及客戶對區段擷取的深入分析。


在我使用ACS的這段時間裡，我遇到了一些錯誤，解決這些錯誤既費時又費力。 瞭解最常見的錯誤有助於更快地解決問題，並提高生產力。 以下是我的疑難排解提示，可幫助您有效解決發生的類似錯誤。

## 資料型別不符錯誤

**錯誤代碼:**
`PGS-220000 PostgreSQL error: ERROR: operator does not exist: character varying = bigint`

**原因：**
當您嘗試使用不同資料型別的欄位進行調解時，這些型別的錯誤會出現在工作流程中。 例如，當您使用具有字串欄位的載入檔案上傳檔案，並嘗試協調字串欄位與具有int資料型別的設定檔欄位時。

![data-type-mismatch-error](/help/assets/kt-13256/data-type-mismatch.png)

**解決方案：**
將「載入檔案」活動中欄位的資料型別變更為您所比對的欄位。 開啟「載入檔案」活動。 移至「COLUMN DEFINITION」標籤，並變更所需欄位的資料型別。


![data-type-mismatch-solution](/help/assets/kt-13256/data-type-mismatch-solution.png)

## 傳遞個人化錯誤

**錯誤代碼:**
`The schema for profiles specified in the transition ('') is not compatible with the schema defined in the delivery template ('nms:recipient'). They should be identical.`

**原因：**
當您傳送電子郵件至某個地址，但該電子郵件或任何其他識別碼並未與設定檔進行調解時，會出現此錯誤。 若要傳送電子郵件通訊，電子郵件或識別碼應一律連結至設定檔。

![具有調解活動的工作流程](/help/assets/kt-13256/del-persn-error-wf.png)

**解決方案：**
具有收件者表格的載入檔案中必須存在通用ID。 此公用索引鍵會將載入檔案聯結至調解活動中的收件者表格。 電子郵件不可傳送至收件者表格中不存在的記錄，因為工作流程中需要此調解步驟。 這樣做時，您會使用設定檔中的電子郵件ID等識別碼調解傳入的載入檔案活動。 此 `nms:recipient` 結構描述是指設定檔表格，使用設定檔調解傳入記錄，使其可在電子郵件準備期間使用。

請參閱調解活動的熒幕擷圖，如下所示。

![包含調解詳細資料的工作流程](/help/assets/kt-13256/del-persn-error-wf-solution.png)

進一步瞭解 [調解](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/data-management-activities/reconciliation.html?lang=en).

## 通用欄位資料集錯誤

**錯誤代碼:**
`The document types of inbound events (''and'') are incompatible (step 'Exclusion'). Unable to perform the operation. `

**原因：**
此問題會在使用 **排除活動** 在ACS工作流程中，當根據ID執行排除時，主要集和排除集的欄位名稱不同。


![通用欄位資料集錯誤](/help/assets/kt-13256/dataset-error.png)

**解決方案:**

有兩種方式可解決此錯誤：

1. 在主要和排除中使用相同的欄位名稱，並將該欄位用作ID

   或

2. 使用JOINS排除方法，選取要據以排除記錄的欄位。

![通用欄位資料集錯誤 — 解決方案 ](/help/assets/kt-13256/dataset-error-solution.png)

## 欄位名稱捨棄錯誤

**錯誤代碼:**
`XTK-170036 Unable to parse expression 'i__name'`

**原因：**

失敗點可能發生於 **擴充活動**. 最常用的專案之一顯示於下方。

![欄位名稱捨棄錯誤](/help/assets/kt-13256/field-name-dropped-error.png)

當您手動編輯活動中的運算式名稱時，就會發生這種情況。 此影像顯示運算式修改自 `name `至 `i__name`.

**解決方案:**

您可以透過三種方式解決此錯誤：

1. 將名稱變回原先存在的運算式。

2. 如果您想使用新名稱，請變更 **擴充活動**.

3. 如果您不記得已變更的內容，最好是重新建立活動。

## 暫存資料表捨棄錯誤 

**錯誤代碼:**
`XTK-170024 The temporary schema "temp:deliveryEmail1" is not defined in the current context.`

**原因：**
這是涉及擴充或其他活動的複雜工作流程中的常見錯誤。 這可能表示在對工作流程進行多項變更期間，部分活動工作流程未正確儲存。

![暫存資料表捨棄錯誤 ](/help/assets/kt-13256/temp-table-dropped-error.png)

**解決方案：**
此錯誤發生的方式有很多種，因此沒有簡單的修正方法。 如果是簡單的工作流程，最好重新設定活動。 在複雜的工作流程中，最好將工作流程活動複製到新的工作流程、儲存並重新執行。