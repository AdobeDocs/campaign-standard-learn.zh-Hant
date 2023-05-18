---
title: 行銷人員疑難排解
description: 了解最常見的錯誤有助於更快地解決問題並提高工作效率。 這些疑難排解提示可協助您在發生類似錯誤時，有效解決這些錯誤。
version: Standard
feature: Workflows
role: User
level: Beginner, Intermediate, Experienced
doc-type: Article
last-substantial-update: 2023-05-18T00:00:00Z
jira: KT-13256
thumbnail: KT-13256.jpeg
source-git-commit: bc9e83e1864b02208f9cd7fe591c77bf6d049a37
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 1%

---


# 行銷人員疑難排解：5個常見工作流程和傳送錯誤

按： [蘇拉伊·帕特拉](https://www.linkedin.com/in/suraj-p-51612053/){target="_blank"}，高級顧問，Meijer

作為過去5年的Adobe Experience Cloud產品高級工程師和客戶專家，我讓業務用戶 [梅耶爾](https://www.meijer.com/){target="_blank"}1934年成立的美國超級中心連鎖，用ACS開展複雜的營銷和交易活動。 我曾參與的一些專案包含自訂的促銷活動，可儲存選件和訂單詳細資料以供個人化、與Adobe Audience Manager整合，以及客戶分析以供區段擷取。


在使用ACS時，我遇到了一些錯誤，這些錯誤可能耗時且難以解決。 了解最常見的錯誤有助於更快地解決問題並提高工作效率。 以下是我的疑難排解秘訣，協助您在發生類似錯誤時有效解決。

## 資料類型不匹配錯誤

**錯誤代碼:**
`PGS-220000 PostgreSQL error: ERROR: operator does not exist: character varying = bigint`

**原因：**
當您嘗試使用不同資料類型的欄位進行調解時，這些類型的錯誤會出現在工作流程中。 例如，當您使用載入檔案上傳檔案時（載入檔案中包含字串欄位），並嘗試將字串欄位與資料類型為int的設定檔欄位調解。

![資料類型 — 不匹配 — 錯誤](/help/assets/kt-13256/data-type-mismatch.png)

**解決方案：**
將「載入檔案」活動中欄位的資料類型變更為您相符的類型。 開啟「載入檔案」活動。 移至「欄定義」標籤，並變更所需欄位的資料類型。


![資料類型 — 不匹配 — 解決方案](/help/assets/kt-13256/data-type-mismatch-solution.png)

## 傳遞個人化錯誤

**錯誤代碼:**
`The schema for profiles specified in the transition ('') is not compatible with the schema defined in the delivery template ('nms:recipient'). They should be identical.`

**原因：**
當您傳送電子郵件至地址時，會出現此錯誤，但電子郵件或任何其他識別碼未與設定檔調解。 若要傳送電子郵件通訊，電子郵件或識別碼應一律連結至設定檔。

使用調解活動，如下所示：

![協調活動的工作流](/help/assets/kt-13256/del-persn-error-wf.png)

**解決方案：**
載入的檔案中必須有包含收件者表格的通用ID。 此公用鍵將載入檔案聯接到調解活動內的收件人表。 電子郵件不得傳送給收件者表格中不存在的記錄，而這需要工作流程中的調解步驟。 這麼做時，您會使用設定檔的電子郵件ID等識別碼來調解傳入的載入檔案活動。 此 `nms:recipient` 架構會參照設定檔表格，並將傳入記錄與設定檔進行協調，以便在準備電子郵件時使用。

請參閱協調活動的螢幕截圖，如下所示。

![協調詳細資訊工作流](/help/assets/kt-13256/del-persn-error-wf-solution.png)

深入了解 [調解](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/data-management-activities/reconciliation.html?lang=en).

## 常見欄位資料集錯誤

**錯誤代碼:**
`The document types of inbound events (''and'') are incompatible (step 'Exclusion'). Unable to perform the operation. `

**原因：**
使用 **排除活動** 在ACS工作流程中。 根據ID執行和排除時，當主要集和排除集沒有相同的欄位名稱時，會發生錯誤。


![常見欄位資料集錯誤](/help/assets/kt-13256/dataset-error.png)

**解決方案:**

有兩種方法可解決此錯誤：

1. 在主要和排除項目中使用相同的欄位名稱，並將該欄位作為ID使用

   或

1. 使用JOINS排除方法來根據要排除記錄的欄位選擇。

![常見欄位資料集錯誤 — 解決方案 ](/help/assets/kt-13256/dataset-error-solution.png)

## 欄位名稱掉格錯誤

**錯誤代碼:**
`XTK-170036 Unable to parse expression 'i__name'`

**原因：**

故障點可能發生在 **擴充活動**. 最常見的一項顯示於下方。

![欄位名稱掉格錯誤](/help/assets/kt-13256/field-name-dropped-error.png)

當您手動編輯活動中的運算式名稱時，就會發生此情況。 影像顯示已從 `name `to `i__name`.

**解決方案:**

您可以透過三種方式解決此錯誤：

1. 將名稱變更回原本存在的運算式。

2. 如果您想使用新名稱，請變更 **擴充活動**.

3. 如果您不記得已變更的項目，最佳選擇是重新建立活動。

## 臨時表掉格錯誤 

**錯誤代碼:**
`XTK-170024 The temporary schema "temp:deliveryEmail1" is not defined in the current context.`

**原因：**
這是複雜工作流程中涉及擴充或其他活動的常見錯誤。 這可能表示在對工作流程進行多次變更期間，部分活動工作流程未正確儲存。

![臨時表掉格錯誤 ](/help/assets/kt-13256/temp-table-dropped-error.png)

**解決方案：**
此錯誤會以多種方式發生，因此沒有簡單的修正。 如果工作流程很簡單，則最好重新設定活動。 在複雜的工作流程中，最好將工作流程活動複製到新的工作流程、儲存並重新執行。