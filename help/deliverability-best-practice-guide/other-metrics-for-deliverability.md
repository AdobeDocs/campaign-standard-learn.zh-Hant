---
title: 其他對傳遞能力而言很重要的指標
description: 識別傳送信譽問題的最佳方式之一，就是透過量度。 讓我們來看看要監控的一些關鍵傳遞能力指標，以及如何使用它們來識別信譽問題。
feature: null
topics: Deliverability
kt: 5256
doc-type: article
activity: understand
team: TM
translation-type: tm+mt
source-git-commit: 7aa32d583ac2ea756945a17634fb477d7b94cb7f
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 0%

---


# 其他對傳遞能力而言很重要的指標

識別傳送信譽問題的最佳方式之一，就是透過量度。 讓我們來看看要監控的一些關鍵傳遞能力指標，以及如何使用它們來識別信譽問題。

## 彈回數

彈回數是ISP提供返回故障通知的傳送嘗試和失敗的結果。 反彈處理是清單衛生的重要部分。 在指定的電子郵件連續多次反彈後，此程式會將其標籤為要抑制。 觸發抑制所需的彈回數和類型因系統而異。 此程式會防止系統繼續傳送無效的電子郵件地址。 彈回數是ISP用來判斷IP信譽的關鍵資料之一。 留意此量度非常重要。 「已傳遞」與「已反彈」可能是衡量行銷訊息傳遞方式最常見的方式：交付率越高越好。 我們將分析兩種不同的彈回數。

## 硬彈回數

硬彈回數是當ISP將寄送訂閱者位址的嘗試判斷為無法傳送後，產生的永久性失敗。 在Adobe Campaign中，分類為無法傳送的硬彈回會新增至隔離，這表示不會重新嘗試。 有些情況下，如果故障原因不明，則會忽略硬反彈。 以下是一些常見的硬彈回數範例：

* 地址不存在
* 帳戶已停用
* 語法錯誤
* 壞域

## 柔和彈回數

軟跳轉是ISP在發送郵件時遇到的臨時故障。 軟體失敗將會重試多次（視使用自訂或現成可用的Adobe Campaign傳送設定而異），以嘗試成功傳送。 在嘗試重試次數上限之前（依設定而異），不會將持續軟彈回數的位址新增至隔離。 軟體彈回數的常見原因包括：

* 郵箱已滿
* 接收電子郵件伺服器關閉
* 發件人信譽問題

![反彈類型](assets/bounce-types.png)

>[!NOTE]
>
>彈回數是聲譽問題的關鍵指標，因為它們可以強調不良資料來源（硬反彈）或ISP的信譽問題（軟反彈）。
軟體彈回數通常會在傳送電子郵件時發生，而且應允許在重試處理期間解決，才能將其定性為真正的傳遞能力問題。 如果單一ISP的軟反彈率大於30%，而且在24小時內無法解決，建議您向Adobe Campaign傳遞性顧問提出疑問。

## 投訴

當使用者指出電子郵件不需要或未預期時，就會註冊投訴。 當訂閱者按下垃圾訊息按鈕時，此訂閱者動作通常會透過訂閱者的電子郵件用戶端或透過第三方垃圾訊息報告系統來記錄。

### ISP投訴

大部分第1層和部分第2層ISP都會為其使用者提供垃圾訊息報告方法，因為選擇退出和取消訂閱程式過去曾惡意使用來驗證電子郵件地址。 Adobe Campaign會透過ISP FBL收到這些抱怨。 這是在為任何提供FBL的ISP設定程式中建立的，可讓Adobe Campaign自動新增抱怨寄送至隔離表格以進行封鎖的電子郵件地址。 ISP投訴的尖峰可能是清單品質不佳、清單收集方法不佳或參與政策不力的指標。 當內容不相關時，也常會注意到這些內容。

### 第三方投訴

有幾個反垃圾郵件群組允許在更廣的層級報告垃圾郵件。 這些第三方使用的投訴量度可用來標籤電子郵件內容以識別垃圾電子郵件。 此程式也稱為指紋。 這些第三方投訴方式的使用者通常對電子郵件比較熟悉，因此，如果沒有得到回應，他們可能會比其他投訴產生更大的影響。

>[!NOTE]
>
>ISP會收集投訴，並使用投訴來判斷傳送者的整體信譽。 所有申訴都應受到壓制，不應再按照當地法律法規盡快與之聯繫。

## 垃圾郵件陷阱

垃圾郵件陷阱是用於識別未授權或未經請求的電子郵件的地址。 垃圾郵件陷阱有助於識別來自詐騙寄件者或未遵循電子郵件最佳實踐者的郵件。 垃圾郵件陷阱電子郵件地址通常不會公開發佈，幾乎無法識別。 向垃圾郵件陷阱發送電子郵件可能會根據陷阱類型和ISP的不同嚴重性影響您的聲譽。 在以下幾節中進一步瞭解不同類型的垃圾郵件陷阱。

### 回收

回收的垃圾郵件陷阱是曾經有效但不再使用的地址。 要盡可能保持清晰的清單，一個關鍵方法是定期傳送電子郵件至您的整個清單，並適當地抑制被拒收的電子郵件。 這有助於隔離已放棄的電子郵件地址，並阻止其繼續使用。

在某些情況下，地址可在30天內循環使用。 定期發送是良好清單衛生的重要方面，也是定期抑制不活躍用戶的重要方面。 重新參與宣傳活動通常是複雜電子郵件行銷計畫的一部分。 此促銷活動樣式可讓傳送者嘗試讓原本不會再寄回的使用者回來。

### Typo

錯字垃圾訊息陷阱是包含拼字錯誤或錯誤的位址。 這通常發生於主要網域的已知錯誤拼 [!DNL Gmail] 字(例如： [!DNL gmail] 是常見的錯字)。 ISP和其他封鎖清單營運商將註冊已知的壞網域，將其用作垃圾訊息攔截器，以識別垃圾訊息發送者並測量傳送者的健康狀況。 防止錯誤垃圾訊息陷阱的最佳方式，是對清單收集使用雙重加入程式。

### 原始

原始垃圾郵件陷阱是指沒有最終用戶且從未有最終用戶的地址。 此地址的建立純粹是為了識別垃圾電子郵件。 這是最具影響力的垃圾訊息陷阱，因為幾乎無法識別，而且需要付出大量努力才能從清單中清除。 大多數黑名單會利用原始垃圾郵件陷阱來列出信譽不佳的發件人。 避免原始垃圾訊息陷阱感染更廣泛行銷電子郵件清單的唯一方法，就是利用雙重選擇程式來收集清單。

## Bulking

膨脹是指將郵件傳送到ISP的垃圾郵件或垃圾資料夾。 當低開啟率（有時點按率）與高傳送率配對時，即可識別。 電子郵件數量激增的原因因ISP而異。 不過，通常，如果訊息放在批量資料夾中，則影響傳送信譽的旗標（例如清單衛生）需要重新評估。 這是信譽在下降的訊號，這個問題需要立即修正，以免影響進一步的宣傳活動。 與您的Adobe Campaign提供能力顧問合作，根據您的情況修正任何膨脹問題。

## 封鎖

當垃圾郵件指示符達到專有的ISP閾值，而ISP開始阻止發件人發送的郵件（明顯地是通過拒絕的郵件嘗試）時，就會發生阻塞。 有各種類型的塊。 通常，塊會發生在IP位址的特定位置，但也可能發生在傳送網域或實體層級。 解決區塊需要具體的專業知識，請連絡您的Adobe Campaign傳遞能力顧問以取得協助。

## 黑名單

當第三方黑名單管理員註冊與發送者相關的垃圾郵件發送者類似行為時，就會發生黑名單。 黑名單的原因有時會由黑名單方公佈。 清單通常以IP位址為基礎，但在更嚴重的情況下，清單可能依IP範圍或甚至是傳送網域而定。 要解決黑名單問題，您的Adobe Campaign提供性顧問應提供支援，以便完全解決並防止進一步清單。 有些上市非常嚴重，可能導致難以解決的長期信譽問題。 黑名單的結果因黑名單而異，但可能會影響所有電子郵件的傳遞。

## 其他資源

* [傳送失敗類型和原因](https://docs.adobe.com/content/help/en/campaign-standard/using/testing-and-sending/monitoring-messages/understanding-delivery-failures.html#delivery-failure-types-and-reasons)