# CMS Membership 欄位及操作指南

## 標籤

#user-guide #membership #customer-service #field-reference #confirmed

## 文件用途

本文件整理 Storellet CMS `Membership` 模組已確認的查詢條件、顯示欄位、可編輯欄位及操作按鈕，供 Account Servicing、Customer Service、營運人員及 Chatbot 使用。

資料來源：`Storellet_CMS_UserGuide.pptx.pdf` Membership 章節 p.61–p.73，以及 `membership_confirmed_fields(1).xlsx`。

> 重要：本文件只將教學截圖及標註中清楚顯示的內容列為已確認資料。權限、審批、Audit Trail、CSV 格式及未有明確解釋的操作，不可由 Chatbot 自行推斷。

---

## 狀態定義

| 狀態 | 意思 |
|---|---|
| 查詢條件 | 用於搜尋資料，不代表建立或編輯時必填 |
| 顯示欄位 | 系統顯示資料，一般不用手動輸入 |
| 顯示／可編輯 | 顯示現有資料，並可在指定介面修改 |
| 必填／操作欄位 | 執行指定操作時必須填寫或選擇 |
| 視乎需要 | 只在適用情況下填寫 |
| 選填／可編輯 | 可以留空，亦可按需要修改 |
| 操作按鈕 | 觸發功能的按鈕，不是資料欄位 |

---

## 模組範圍

- 3.1 Member：會員搜尋、會員資料、Discount Card、Coupon、Stamp、Bingo、History
- 3.2 Verification Code：驗證碼搜尋及結果
- 3.3 Invoice：Invoice 搜尋及結果（是否屬 Membership 正式範圍仍待確認）

---

# 1. 3.1.1 List member’s details

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Member No. | 查詢條件 | Enter either one search parameter | 用會員編號搜尋會員資料 | 四選一輸入即可：Member No. / Phone No. / Email / Facebook ID | p.61 |
| Phone No. | 查詢條件 | Enter either one search parameter | 用電話號碼搜尋會員資料 | 四選一輸入即可 | p.61 |
| Email | 查詢條件 | Enter either one search parameter | 用 Email 搜尋會員資料 | 四選一輸入即可 | p.61 |
| Facebook ID | 查詢條件 | Enter either one search parameter | 用 Facebook ID 搜尋會員資料 | 四選一輸入即可 | p.61 |
| Search | 操作按鈕 | Click Search | 搜尋會員資料 | 不是資料欄位，屬操作按鈕 | p.61 |

# 2. 3.1.2 Edit member’s details

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Member No. | 顯示欄位 | System display | 顯示 Storellet 會員編號及 security code | 一般不需手動修改 | p.62 |
| Status | 可操作 / 顯示欄位 | Active / Inactive / Unsubscribe | 顯示會員目前狀態；可停用 membership 或 unsubscribe selected membership group | 涉及會員狀態，操作前需確認 | p.62-p.63 |
| Alias no | 顯示欄位 | System display | 顯示會員 alias no. | 一般不需手動修改 | p.62 |
| Security Code | 顯示欄位 | System display | 顯示安全碼 | 前台 QR / 會員識別有機會使用 | p.62 |
| Phone No. | 顯示 / 可編輯 | Member phone number | 顯示及更新會員電話 | User Profile popup 可編輯 | p.62 |
| Country Code | 顯示欄位 | System display | 顯示電話國家 / 地區碼 | 例：HK | p.62 |
| Email | 顯示 / 可編輯 | Member email | 顯示及更新會員 Email | 支援 Send verification email / Toggle User Email Verify Status | p.62 |
| Facebook ID | 顯示 / 可編輯 | Member Facebook ID | 顯示及更新會員 Facebook ID | 如會員無綁定可留空 | p.62 |
| Display Name | 顯示 / 可編輯 | Member display name | 前台 / CMS 顯示會員名稱 | User Profile popup 可編輯 | p.62 |
| First Name | 顯示欄位 | System / member profile | 顯示會員 First Name | 視乎會員資料是否有填 | p.62 |
| Last Name | 顯示欄位 | System / member profile | 顯示會員 Last Name | 視乎會員資料是否有填 | p.62 |
| Gender | 顯示 / 可編輯 | Male / Female / other available option | 顯示會員性別 | User Profile popup 可編輯 | p.62 |
| Birthday | 顯示 / 可編輯 | YYYY/MM/DD or YYYYMMDD | 顯示會員生日 | User Profile popup 標示 Birthday (YYYYMMDD) | p.62 |
| Join Date | 顯示欄位 | System display | 顯示會員加入日期 | 不建議手動修改 | p.62-p.63 |
| Expiry Date | 顯示 / 可編輯 | Set expiry date if needed | 顯示 membership expiry date | 可按 Edit 修改；需跟會員條款一致 | p.63 |
| Point(s) | 顯示 / 可操作 | System display / Point Adjustment | 顯示會員現有積分；可進入 point adjustment | 加減分操作需內部確認 | p.63 |
| Delivery Coupon | 操作按鈕 | Click Delivery Coupon | 手動派發 coupon 給會員 | 打開 Delivery Coupon popup | p.63 |
| Actual Accu. Sales Amount | 查詢 / 顯示欄位 | Select date range + Check | 根據 Brand ID / 日期區間顯示累積消費金額 | 可勾選 Use Net Amount When Calculating Accumulated Sales | p.63 |
| Receive News - Global | 顯示 / 操作欄位 | Checkbox | 顯示會員是否同意接收該 group 推廣訊息 | 當會員不同意推廣，對應 box 會被 ticked / 更新狀態需小心 | p.63-p.64 |
| Receive News - by Email | 顯示 / 操作欄位 | Checkbox | Email 推廣同意狀態 | 屬會員推廣同意紀錄 | p.64 |
| Receive News - by App Push | 顯示 / 操作欄位 | Checkbox | App Push 推廣同意狀態 | 屬會員推廣同意紀錄 | p.64 |
| Receive News - by Sms | 顯示 / 操作欄位 | Checkbox | SMS 推廣同意狀態 | 屬會員推廣同意紀錄 | p.64 |
| Receive News - by Communication Platform | 顯示 / 操作欄位 | Checkbox | Communication Platform 推廣同意狀態 | 屬會員推廣同意紀錄 | p.64 |
| Receive News - by Website | 顯示 / 操作欄位 | Checkbox | Website 推廣同意狀態 | 屬會員推廣同意紀錄 | p.64 |
| Membership Group | 操作欄位 | Select company group | 選擇會員加入的 company group | PPT 標示 select the company group of the membership | p.62 |
| Brands | 操作欄位 | Select brand | 顯示 / 篩選會員 brand profile | User Brand Profile will be shown if exists | p.62 |

# 3. 3.1.2 Delivery Coupon popup

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Brand | 必填 / 操作欄位 | Select brand | 選擇派 coupon 所屬品牌 | 派發 coupon 前需選正確 brand | p.63 |
| Coupon | 必填 / 操作欄位 | Select coupon | 選擇要派發的 coupon | 需先有 coupon config | p.63 |
| Available Shop | 視乎需要 | Select available shop if applicable | 限制 coupon 可用分店 | 無分店限制可按 coupon config | p.63 |
| Expiry Date | 必填 / 操作欄位 | Select date | 設定手動派發 coupon 到期日 | 需同 campaign / coupon validity 一致 | p.63 |
| Remark | 選填 | Max 250 characters | 派發備註 | PPT 顯示字數限制 250 | p.63 |

# 4. 3.1.2 User Profile popup

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Alternative Phone No. | 選填 / 可編輯 | Optional phone number | 會員替代電話 | 如無資料可留空 | p.62 |
| Instagram | 選填 / 可編輯 | Instagram account / link | 會員 social profile | 如無資料可留空 | p.62 |
| facebook | 選填 / 可編輯 | Facebook account / link | 會員 social profile | 如無資料可留空 | p.62 |
| littleredbook | 選填 / 可編輯 | Little Red Book account / link | 會員 social profile | 如無資料可留空 | p.62 |
| openricehk | 選填 / 可編輯 | OpenRice account / link | 會員 social profile | 如無資料可留空 | p.62 |

# 5. 3.1.3 Discount card

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Brand | 顯示欄位 | System display | 顯示 discount card 所屬 brand | 會員所有 discount cards 會被列出 | p.65 |
| Membership Level | 顯示欄位 | System display | 顯示會員 membership level；前台亦會顯示 | 例如 Paid TIER 3 MEMBER | p.65 |
| Discount Rate | 顯示欄位 | System display | 顯示該 card 提供折扣率 | 例如 10 代表 10% off | p.65 |
| Expiry Date | 顯示 / 可編輯 | Edit expiry date if needed | 顯示 discount card 有效期 | 可按 Edit 修改 expiry date | p.65 |
| Start Date | 顯示欄位 | System display | 顯示 discount card 開始日期 | 前台有效期依此顯示 | p.65 |
| Status | 顯示欄位 | active / expired | 顯示 discount card 當前狀態 | 狀態會是 active / expired | p.65 |
| Remark | 顯示欄位 | System display | 顯示 discount card 備註 | 如無備註可為空 | p.65 |
| Detail | 操作按鈕 | Click Detail | 查看 / 修改 discount card 詳細設定 | 會切換到 Assets > Discount Card section | p.65 |
| Expire | 操作按鈕 | Click Expire | 手動令 discount card 過期 | 操作前需確認 | p.65 |
| Edit | 操作按鈕 | Click Edit | 修改 discount card expiry date | 會影響會員前台卡有效期 | p.65 |

# 6. 3.1.4 Coupon Summary

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Brand | 顯示欄位 | System display | 顯示 coupon 所屬 brand | 會員所有 coupon summary 會列出 | p.66 |
| Coupon ID | 顯示欄位 | System display | 顯示 coupon ID | 用作 coupon config reference | p.66 |
| Coupon | 顯示欄位 | System display | 顯示 coupon name | 會員 wallet coupon summary | p.66 |
| Active Count | 顯示欄位 | System display | 顯示 active coupon 數量 | PPT 指出 current status quantity 會顯示 | p.66 |
| Used Count | 顯示欄位 | System display | 顯示已使用 coupon 數量 | 會員 coupon 狀態統計 | p.66 |
| Expired Count | 顯示欄位 | System display | 顯示已過期 coupon 數量 | 會員 coupon 狀態統計 | p.66 |
| Status | 顯示欄位 | active / expired | 顯示 coupon config 狀態 | 狀態會是 active / expired | p.66 |
| Detail | 操作按鈕 | Click Detail | 查看 coupon card details | 會切換到 Assets > Coupon section | p.66 |

# 7. 3.1.5 Coupon card

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Brand | 顯示欄位 | System display | 顯示 coupon card 所屬 brand | 會員所有 coupon cards 會列出 | p.67 |
| Coupon | 顯示欄位 | System display | 顯示 coupon name / coupon ID | 會顯示於前台 coupon card | p.67 |
| Start Date | 顯示欄位 | System display | 顯示 coupon card 開始有效日期 | 前台顯示優惠券有效日期 | p.67 |
| Expiry Date | 顯示欄位 | System display | 顯示 coupon card 到期日 | 前台顯示優惠券有效日期 | p.67 |
| Extended Expiry Date | 顯示欄位 | System display | 顯示延長後到期日 | 如未延長會顯示 / | p.67 |
| Serial No. | 顯示欄位 | System display | 顯示 coupon 識別號碼 | PPT 指出為 coupon identification number | p.67 |
| Status | 顯示欄位 | active / used / expired | 顯示 coupon card 當前狀態 | PPT 指出 active / expired；畫面亦有 used | p.67 |
| Remark | 顯示欄位 | System display | 顯示 coupon card 備註 | 如無備註可為 --- | p.67 |
| Detail | 操作按鈕 | Click Detail | 查看 / 修改 coupon card detail | 會切換到 Assets > Coupon section | p.67 |
| Expire | 操作按鈕 | Click Expire | 手動令 coupon card 過期 | 操作前需確認 | p.67 |
| Use | 操作按鈕 | Click Use | 手動標記 coupon 使用 | 操作前需確認，會影響會員 wallet | p.67 |

# 8. 3.1.6 Stamp

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Brand | 顯示欄位 | System display | 顯示 stamp 所屬 brand | 會員所有 stamps 會列出 | p.68 |
| Create Date | 顯示欄位 | System display | 顯示 stamp record 建立日期 | 用於追蹤印花取得時間 | p.68 |
| Name | 顯示欄位 | System display | 顯示 stamp campaign / stamp name | 例如 Stamp Card | p.68 |
| Type | 顯示欄位 | normal / special | 顯示印花類型 | PPT 指出 type will be either normal or special | p.68 |
| Status | 顯示欄位 | Active / Expired | 顯示 stamp record 狀態 | PPT 指出 active / expired | p.68 |
| Invoice | 顯示欄位 | System display | 顯示相關 invoice details | 包括 invoice no., shop code, net amount, order type, payment method | p.68 |
| Show Summary | 操作按鈕 | Click Show Summary | 查看 stamp summary | 不是資料欄位 | p.68 |
| Add Stamp | 操作按鈕 | Click Add Stamp | 手動新增 stamp | 操作前需確認活動及會員資格 | p.68 |
| Void | 操作按鈕 | Click Void | 取消 / 作廢 stamp record | 操作前需確認 | p.68 |

# 9. 3.1.7 Stamp Card

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Brand | 顯示欄位 | System display | 顯示 stamp card 所屬 brand | 會員所有 stamp cards 會列出 | p.69 |
| Create Date | 顯示欄位 | System display | 顯示 stamp card record 建立日期 | 用作追蹤兌換紀錄 | p.69 |
| No. of Stamp used | 顯示欄位 | System display | 顯示會員兌換 coupon 所使用的 stamp 數量 | PPT 第 ① 點 | p.69 |
| Redeemed Coupon | 顯示欄位 | System display | 顯示會員已兌換 coupon 類型 | PPT 第 ② 點 | p.69 |

# 10. 3.1.8 Bingo

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Brand | 顯示欄位 | System display | 顯示 Bingo 所屬 brand | 會員所有 Bingo 會列出 | p.70 |
| Name | 顯示欄位 | System display | 顯示 Bingo name | 如無資料會顯示 No data available | p.70 |
| Start Date | 顯示欄位 | System display | 顯示 Bingo start date | Bingo validity reference | p.70 |
| Expiry Date | 顯示欄位 | System display | 顯示 Bingo expiry date | Bingo validity reference | p.70 |
| Serial No. | 顯示欄位 | System display | 顯示 Bingo identification number | PPT 第 ② 點 | p.70 |
| Status | 顯示欄位 | active / expired | 顯示 Bingo 當前狀態 | PPT 第 ③ 點 | p.70 |

# 11. 3.1.9 History

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Brand | 顯示欄位 | System display | 顯示 record 所屬 brand | 會員詳細紀錄 summary table | p.71 |
| Create Date | 顯示欄位 | System display | 顯示 record 建立日期及時間 | PPT 第 ① 點 | p.71 |
| Transaction Time | 顯示欄位 | System display if transaction type | 顯示交易紀錄時間 | 只有 transaction type record 會有資料 | p.71 |
| Point Change | 顯示欄位 | System display | 顯示會員積分變動 | 例如 +8 / +200 / -20 | p.71 |
| Type | 顯示欄位 | coupon / coupon collect / coupon purchase / discount card / transaction / adjustment | 顯示 record 類型 | PPT 列明可見 record types | p.71 |
| Shop | 顯示欄位 | System display | 顯示相關 shop no. | 如無相關 shop 會顯示 --- | p.71 |
| Description | 顯示欄位 | System display | 顯示 record details | 例如 coupon details、payment reference、membership details、invoice details 等 | p.71 |

# 12. 3.2.1 Search verification code

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Phone No. | 查詢條件 | Enter phone no. | 搜尋該電話號碼對應 verification code | 會員註冊時驗證碼會發送到 mobile device | p.72 |
| Email | 查詢條件 | Enter email | 用 Email 搜尋 verification code | 視乎系統有否以 Email 查詢 | p.72 |
| Verification Code | 顯示欄位 | System display | 顯示對應電話 / Email 的 verification code | Result table 欄位 | p.72 |
| Expiry Date | 顯示欄位 | System display | 顯示 verification code 到期日 | Result table 欄位 | p.72 |
| Status | 顯示欄位 | System display | 顯示 verification code 狀態 | Result table 欄位 | p.72 |

# 13. 3.3.1 Search Invoice

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Complete Invoice No. | 查詢條件 / 顯示欄位 | Enter complete invoice no. if available | 搜尋 / 顯示完整 invoice no. | Invoice section 出現於 Membership menu | p.73 |
| Brand | 查詢條件 / 顯示欄位 | Select brand | 按 brand 搜尋 invoice / 顯示 invoice brand | 例：Storellet cafe | p.73 |
| Shop | 查詢條件 / 顯示欄位 | Enter / select shop | 按 shop 搜尋 invoice / 顯示 invoice shop | 例：(STRIPE) | p.73 |
| Transaction Date | 查詢條件 | Select date range | 按交易日期搜尋 invoice | 需輸入 start date / end date | p.73 |
| Purchase Time | 顯示欄位 | System display | 顯示購買時間 | Invoice result table 欄位 | p.73 |
| Info | 顯示欄位 | System display | 顯示 invoice details | 包含 Status、Invoice Amount、Net Amount、Order Type、Payment Method、Items、Discount、Coupons、Member No.、Used Promo Code | p.73 |
| Redeem | 顯示欄位 | System display | 顯示 redeem 時間 / 狀態 | Invoice result table 欄位 | p.73 |

---

# 14. 重要操作說明

## 搜尋會員

在「List member’s details」可用以下其中一項搜尋會員：

- Member No.
- Phone No.
- Email
- Facebook ID

四項選一輸入即可，然後按 Search。Chatbot 不應聲稱必須同時填寫多項，亦不可自行加入「部分匹配」、「QR Code 搜尋」或特定電話格式要求。

## 手動派發 Coupon

Delivery Coupon Popup 已確認欄位：

- Brand：必填
- Coupon：必填
- Available Shop：視乎需要
- Expiry Date：必填
- Remark：選填，最多 250 characters

操作前需確認正確 Brand、Coupon、有效期及適用分店。是否符合手動派發規則、操作權限及審批流程仍待確認。

## Receive News

頁面顯示以下推廣同意狀態：Global、Email、App Push、SMS、Communication Platform 及 Website。教學資料指出會員不同意推廣時，相應 Checkbox 可能會被 Tick；目前 CMS 的 Tick／Untick 準確含義仍待確認，因此 Chatbot 不可直接以「Tick = 同意」回答。

## 會員資產及高風險操作

以下按鈕會改變會員資料或資產狀態，操作前必須核對目標會員及相關活動：

- Status：Deactivate／Unsubscribe Membership
- Point(s)：Point Adjustment
- Discount Card：Expire／Edit
- Coupon Card：Expire／Use
- Stamp：Add Stamp／Void

現有資料只確認按鈕及大概用途，未確認操作權限、審批要求及 Audit Trail。

---

# 15. 待進一步確認項目

以下內容不可由 Chatbot 自行推斷：

| Section | Field / Area | Reason | Source |
|---|---|---|---|
| 3.1.2 Edit member’s details | Deactivate / Unsubscribe membership | 會直接影響會員狀態及推廣訂閱；應由 account / CS 確認權限與流程 | p.63 |
| 3.1.2 Edit member’s details | Point Adjustment | 涉及會員積分加減，需確認內部審批及原因記錄要求 | p.63 |
| 3.1.2 Delivery Coupon | Manual coupon delivery rule | 手動派 coupon 需要確認 coupon 是否可派、有效期、available shop 及 remark 標準 | p.63 |
| 3.1.2 Receive News checkboxes | Checkbox interpretation | PPT 指出 member disagreed with promotion 時對應 box 會 ticked；需確認目前 CMS 實際 tick/untick 邏輯 | p.64 |
| 3.1.5 Coupon card | Manual Use / Expire | 會直接改變會員優惠券狀態，需確認操作權限及 audit trail | p.67 |
| 3.1.6 Stamp | Add Stamp / Void | 會影響會員 stamp wallet，需確認手動補印 / void 的內部流程 | p.68 |
| 3.1.8 Bingo | Bingo field meaning | PPT 第 ① 點標示 ???，未確認該欄位用途 | p.70 |
| 3.3 Invoice | Invoice module scope | Overview p.4 未列 Invoice，但 p.73 出現 3.3 Invoice；需確認是否納入 Membership checklist 正式範圍 | p.4 / p.73 |

---

# 16. Chatbot 回答規則

1. 回答時要指出 Sub-section、Field／UI Item、Status 及用途。
2. 不可將「查詢條件」誤稱為建立會員時的必填欄位。
3. 不可將「顯示欄位」誤稱為可編輯欄位。
4. 「視乎需要」必須連同適用情況回答。
5. 涉及 Deactivate、Unsubscribe、Point Adjustment、Delivery Coupon、Expire、Use、Add Stamp 或 Void，必須提示屬高風險操作及需確認內部流程。
6. 不可自行加入 Excel 未確認的 URL、欄位限制、權限、審批、Audit Log、Export、QR Code、密碼管理、虛擬會員或封禁手機流程。
7. Receive News Checkbox 的 Tick／Untick 意思未完全確認，需向 Account／CS／Tech Team 核實。
8. Bingo p.70 第 ① 點欄位用途未確認，不可推斷。
9. Invoice 雖出現於 p.73，但是否正式屬 Membership Checklist 範圍仍待確認。
10. 如資料未在本文件確認，應回答：「現有已確認 Membership 教學未有清楚定義，需向相關 Team 確認。」

---

# 17. 常見問題

## Q1：搜尋會員需要填寫全部搜尋欄位嗎？

不需要。Member No.、Phone No.、Email 或 Facebook ID 四選一即可，再按 Search。

## Q2：CMS 可以修改哪些會員基本資料？

已確認可在相關介面編輯或操作的資料包括 Phone No.、Email、Facebook ID、Display Name、Gender、Birthday、Expiry Date，以及 User Profile Popup 內的 Alternative Phone No. 和部分 Social Profile。First Name、Last Name、Country Code、Join Date 等在現有教學中只確認為顯示欄位。

## Q3：如何手動派 Coupon？

在會員詳情按 Delivery Coupon，選擇 Brand、Coupon 及 Expiry Date；Available Shop 視乎需要，Remark 可選填並最多 250 characters。實際派發前需確認內部授權及 Coupon 規則。

## Q4：Coupon Summary 與 Coupon Card 有甚麼分別？

Coupon Summary 顯示各 Coupon 的 Active、Used、Expired 數量及 Coupon Config 狀態；Coupon Card 則列出會員每張 Coupon 的 Start Date、Expiry Date、Serial No.、Status 及相關操作。

## Q5：Coupon Card 有哪些已確認狀態？

已確認可見 Active、Used 及 Expired。手動 Use 或 Expire 會直接影響會員 Wallet，操作權限及 Audit Trail 仍待確認。

## Q6：如何查看會員的積分變動？

在 History 可查看 Point Change，例如 +8、+200 或 -20；同時可查看 Type、Create Date、Transaction Time、Shop 及 Description。

## Q7：Verification Code 可以用甚麼搜尋？

已確認可使用 Phone No. 或 Email 搜尋；結果會顯示 Verification Code、Expiry Date 及 Status。

## Q8：Receive News Checkbox Tick 代表同意嗎？

暫時不可直接作此結論。教學資料指出會員不同意推廣時相應 Checkbox 可能會被 Tick，準確邏輯需按目前 CMS 實際行為確認。

---

**最後更新**：2026-07-17  
**資料狀態**：108 項已確認；8 項待進一步確認  
**適用角色**：Account Servicing、Customer Service、營運人員、Marketing
