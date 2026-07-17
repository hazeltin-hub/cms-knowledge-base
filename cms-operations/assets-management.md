# CMS Assets 欄位及設定指南

## 標籤

#user-guide #assets #points #discount-card #bingo #stamp #coupon #coupon-package #coupon-trigger #survey #field-reference

## 文件用途

本文件整理 Storellet CMS `Assets` 模組已確認的列表欄位、建立欄位、必填設定、前台影響及注意事項，供 Account Servicing、Marketing、營運人員及 Chatbot 使用。

資料來源：`Storellet_CMS_UserGuide.pptx.pdf` Assets 章節 p.29–p.60，以及 `assets_confirmed_fields(1).xlsx`。

> 重要：本文件只將教學截圖及標註中清楚顯示的內容列為已確認資料。標示為 `???`、`Not in use`、未確認檔案規格或涉及自動派發邏輯的內容，會獨立放在「待進一步確認項目」，Chatbot 不可自行推斷。

---

## 狀態定義

| 狀態 | 意思 |
|---|---|
| 必填 | 建立或提交 Asset 時必須填寫 |
| 建議必填 | 前台展示通常需要，來源以建議或圖片規格形式標示 |
| 視乎需要／活動／類型 | 只有指定功能、活動或欄位選項啟用時需要 |
| 選填 | 可按需要填寫或上載 |
| 系統欄位 | CMS 自動產生，一般不用修改 |
| 顯示／操作欄位 | 列表頁顯示資料或提供 Edit／Export 等操作，不是建立頁必填欄位 |

---

## 模組範圍

- 2.1 Points
- 2.2 Discount Card
- 2.3 Bingo
- 2.4 Stamp
- 2.5 Coupon
- 2.6 Coupon Package
- 2.7 Coupon Trigger Rule
- 2.8 Survey

---

# 1. 2.1.1 List all Points

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Points ID | 顯示 / 操作欄位 | System display / Click action | 顯示 point asset ID | 用作匯出 / 修改 reference | p.29 |
| Group | 顯示 / 操作欄位 | System display / Click action | 顯示所屬 group | 可用 group filter | p.29 |
| Point(s) | 顯示 / 操作欄位 | System display / Click action | 顯示 points value | 例如 welcome pack 50 / 100 points | p.29 |
| Type | 顯示 / 操作欄位 | System display / Click action | 顯示 points type | 例如 Welcome Pack / Birthday Gift / Anniversary Gift / Push / Redeem Code | p.29 |
| Start Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期開始日 | 用作 point item validity | p.29 |
| End Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期完結日 | 用作 point item validity | p.29 |
| White Label | 顯示 / 操作欄位 | System display / Click action | 顯示是否 White Label only | 按 app availability 判斷 | p.29 |
| Status | 顯示 / 操作欄位 | System display / Click action | 顯示狀態 | Active / Inactive | p.29 |
| Edit | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 修改 points detail | p.29 |
| Export | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 匯出 points details JSON file | p.29 |

# 2. 2.1.2 Create new Points

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Import File | 選填 | Upload file if needed | 匯入 points config / image | PPT 問 file size restriction；如無需匯入可留空 | p.30 |
| Group | 必填 | Select Group | 指定 points 歸屬 group | 需選正確 merchant group | p.30 |
| Point(s) | 必填 | Points value, e.g. 50 / 100 | 設定派發 points 數量 | 會員領取後會加到 wallet | p.30 |
| Type | 必填 | Welcome Pack / Birthday Gift / Anniversary Gift / Push / Redeem Code | 決定 points 類型及顯示 section | 按活動用途選擇 | p.30 |
| Start Date | 必填 | Campaign start date | 控制 point item 開始顯示 / 可領取時間 | 通常與 campaign start date 一致 | p.30 |
| End Date | 必填 | Campaign end date / long-term date | 控制 point item 完結時間 | 需同 campaign validity 對齊 | p.30 |
| Image | 建議必填 | Image file, recommended 1MB | 前台 App 顯示 points 圖片 | PPT 標示 file size recommendation: 1MB | p.30 |
| Available to White Label App Only | 視乎需要 | Untick unless white label only | 限制只可於 White Label App 使用 | 按 app availability 決定 | p.30 |
| Available to Storellet App Only | 視乎需要 | Untick unless Storellet App only | 限制只可於 Storellet App 使用 | 按 app availability 決定 | p.30 |
| Not Transferable | 視乎需要 | Tick / Untick | 設定 points 是否可轉贈 | PPT 標示為 point transferable to other member or not | p.30 |
| Status | 必填 | Active | 控制 points asset 是否有效 | 上線活動設 Active | p.30 |
| Create Date | 系統欄位 | Auto / CMS date | 建立紀錄 | 一般不用改 | p.30 |

# 3. 2.2.1 List all Discount Cards

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Discount Card ID | 顯示 / 操作欄位 | System display / Click action | 顯示 discount card ID | 用作 reference / export | p.31 |
| Brand | 顯示 / 操作欄位 | System display / Click action | 顯示所屬 brand | 可用 brand filter | p.31 |
| Name | 顯示 / 操作欄位 | System display / Click action | 顯示 card name | 例如 Basic / VIP / Tier card | p.31 |
| Is Welcome Pack | 顯示 / 操作欄位 | System display / Click action | 顯示是否 Welcome Pack | 所有 brand 至少需建立 1 個 Basic tier 並設 Welcome Pack | p.31 |
| Start Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期開始日 | 控制 card validity | p.31 |
| End Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期完結日 | 控制 card validity | p.31 |
| White Label | 顯示 / 操作欄位 | System display / Click action | 顯示是否 White Label only | 按 app availability 判斷 | p.31 |
| Status | 顯示 / 操作欄位 | System display / Click action | 顯示狀態 | Active / Inactive | p.31 |
| Edit | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 修改 discount card detail | p.31 |
| Export | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 匯出 card details JSON file | p.31 |

# 4. 2.2.2 Create new Discount Card

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Import File | 選填 | Upload file if needed | 匯入 discount card config | 如無需匯入可留空 | p.32 |
| Brand | 必填 | Select Brand | 指定 card 所屬 brand | 每個 brand 至少要有 1 個 Basic tier / Welcome Pack | p.32 |
| DiscountCard Type | 必填 | Normal Tier | 指定 card / tier 類型 | 按 merchant tier structure 設定 | p.32 |
| Discount Level | 必填 | Basic=1, Silver=2, Gold=3, VIP=4 | 設定會員等級排序 | 需跟 Tier level 一致 | p.32 |
| Name (English) | 必填 | English tier/card name | 前台英文 card name | 例如 VIP Card | p.32 |
| Name (Local Language) | 必填 | Chinese/local tier/card name | 前台中文 card name | 例如 VIP 會員 | p.32 |
| Image (English) | 建議必填 | Card image, recommended 1MB | 前台英文 discount card 圖片 | PPT 註：seems not working；仍保留為圖像欄位 | p.32 |
| Image (Local Language) | 建議必填 | Card image, recommended 1MB | 前台中文 discount card 圖片 | 如中英文同圖可重用 | p.32 |
| Image 2 / 3 | 選填 | Leave blank unless special implementation | 額外 card image | 一般前台未必使用 | p.32 |
| Discount Rate | 必填 | e.g. 20 = 20% off | 設定 card 折扣率 | 需跟 merchant benefit 一致 | p.32 |
| Redemption Period | 必填 | Start date - End date | 控制 discount card 有效期 | valid period of discount card | p.32 |
| Redemption Point | 視乎需要 | Points required if redeemable | 設定用 points 兌換 card 所需分數 | 若非兌換型 tier 可留空 / default | p.32 |
| Terms & Conditions (English) | 建議必填 | HTML format | 前台 T&C section 顯示 | 需用 HTML format | p.33 |
| Terms & Conditions (Local Language) | 建議必填 | HTML format | 前台中文 T&C 顯示 | 需用 HTML format | p.33 |
| How To Use (English) | 建議必填 | HTML format | 前台使用說明 | PPT 指示會顯示於 front-end application | p.33 |
| How To Use (Local Language) | 建議必填 | HTML format | 前台中文使用說明 | 需用 HTML format | p.33 |
| Set As Welcome Pack | 必填 | Yes for Basic welcome card | 控制是否註冊後自動加入 wallet | Basic member card 建議 Yes | p.33 |
| Welcome Pack Period | 視乎需要 | Start date - End date | 控制 welcome pack 派發期間 | Set As Welcome Pack = Yes 時需設定 | p.33 |
| Upgrade From | 視乎 tier | Can't Upgrade by default | 指定可由哪張 card upgrade | 預設 Can't Upgrade | p.33 |
| Point For Upgrade | 視乎 tier | -1 if not applicable | 設定升級所需最低分數 | 不適用留 -1 | p.33 |
| Renew Type | 必填 | Basic level set as Auto | 設定 card renewal method | 按 tier renewal logic 設定 | p.33 |
| Expiry Date Pattern | 必填 | Basic: Current date + 1 year / closest next 1/4/7/10; Other tiers: Current date + 1 year | 控制 card 到期日 pattern | 需同 tier policy 一致 | p.33 |
| Coupon List | 選填 | Select coupons + quantity | 設定此 card 包含的 coupon(s) | 需輸入每張 coupon quantity | p.34 |
| Available to White Label App Only | 視乎需要 | Tick / Untick | 限制 White Label App 使用 | 按 app availability 決定 | p.34 |
| Available to Storellet App Only | 視乎需要 | Tick / Untick | 限制 Storellet App 使用 | 按 app availability 決定 | p.34 |
| Point Multiply Ratio | 必填 | 1.0 / merchant ratio | 會員持卡獲得 points 倍率 | 需同會員等級規則一致 | p.34 |
| Stamp Multiply Ratio | 必填 | 1.0 / merchant ratio | 會員持卡獲得 stamp 倍率 | actual stamp x rate = wallet stamp | p.34 |
| Not Transferable | 視乎需要 | Tick / Untick | 設定 card 是否可轉贈 | PPT 標示為 transferable to other member or not | p.34 |
| Share With Brands | 視乎 master brand | Select brands if needed | 跨品牌分享 card | Master brand / multi-brand 才用 | p.34 |
| Hidden | 視乎需要 | Untick by default | 控制是否隱藏 card | 需按前台展示需要 | p.34 |
| Event Tracking Submit Option | 視乎需要 | Default | event tracking submit 設定 | 如無特別需求用 default | p.34 |
| Status | 必填 | Active | 控制 card 是否有效 | 上線用 Active | p.34 |
| Colour Code | 視乎設計 | Hex / selected color | 前台 card 色系 | 按 UI 設計填 | p.34 |
| Highlighted Colour Code | 視乎設計 | Hex / selected color | 前台 highlight 色系 | 按 UI 設計填 | p.34 |
| Shopline Membership Tier ID | 視乎 Shopline | Enter 'null' for Shopline Basic Tier | Shopline tier mapping | 有 Shopline integration 先需要 | p.34 |

# 5. 2.3.1 List all Bingo

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Bingo ID | 顯示 / 操作欄位 | System display / Click action | 顯示 Bingo ID | 用作 reference / export | p.37 |
| Brand | 顯示 / 操作欄位 | System display / Click action | 顯示所屬 brand | 可用 brand filter | p.37 |
| Name | 顯示 / 操作欄位 | System display / Click action | 顯示 Bingo name | CMS list 顯示 | p.37 |
| Type | 顯示 / 操作欄位 | System display / Click action | 顯示 Bingo type | 例如 Day Part | p.37 |
| Start Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期開始日 | validity | p.37 |
| End Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期完結日 | validity | p.37 |
| White Label | 顯示 / 操作欄位 | System display / Click action | 顯示是否 White Label only | 按 app availability 判斷 | p.37 |
| Status | 顯示 / 操作欄位 | System display / Click action | 顯示狀態 | Active / Inactive | p.37 |
| Edit | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 修改 bingo detail | p.37 |
| Export | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 匯出 bingo details JSON file | p.37 |

# 6. 2.3.2 Create new Bingo

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Import File | 選填 | Upload file if needed | 匯入 Bingo config | PPT 未確認 file size restriction | p.35 |
| Brand | 必填 | Select Brand | 指定 Bingo 所屬品牌 | 需選正確 brand | p.35 |
| Name (English) | 必填 | English campaign name | 前台 / CMS 顯示 Bingo campaign name | PPT 指示輸入英文名稱 | p.35 |
| Name (Local Language) | 必填 | Local campaign name | 前台中文 / 本地語言顯示 | PPT 指示輸入 local language name | p.35 |
| Image | 建議必填 | Bingo card image, recommended 1MB | 前台顯示 Bingo card image | PPT 標示 file size recommendation: 1MB | p.35 |
| Description (English) | 建議必填 | English description | 前台 Bingo description | 活動說明 | p.35 |
| Description (Local Language) | 建議必填 | Local description | 前台中文 Bingo description | 活動說明 | p.35 |
| Terms & Conditions (English) | 建議必填 | HTML format | 前台 T&C 顯示 | 需用 HTML format | p.35 |
| Terms & Conditions (Local Language) | 建議必填 | HTML format | 前台中文 T&C 顯示 | 需用 HTML format | p.35 |
| How To Use (English) | 建議必填 | HTML format | 前台 How to Use 顯示 | 需用 HTML format | p.35 |
| How To Use (Local Language) | 建議必填 | HTML format | 前台中文使用說明 | 需用 HTML format | p.35 |
| Day Period 1 / 2 / 3 | 視乎活動 | Tick weekdays | 設定 Bingo 有效星期 | Tick box indicate validity of Bingo | p.36 |
| Type | 必填 | Day Part / selected type | 設定 Bingo type | 配合 daypart/time slot 設定 | p.36 |
| Effective Period | 必填 | Start date - End date | Bingo 有效日期 | PPT 標示 enter the date to indicate validity | p.36 |
| Daypart Time Slot 1 / 2 / 3 | 視乎活動 | Start time - End time | 設定有效時段 | 例如 09:00 - 13:00 | p.36 |
| Daypart Slot Text EN/Local | 視乎活動 | Text form, e.g. 09:00-13:00 | 前台顯示時段文字 | PPT 指示 time slot in text form | p.36 |
| Reward 1-8 | 必填 | Select reward for each pattern | 為對應 Bingo pattern 設定獎賞 | PPT 指示 choose reward for corresponding pattern | p.38 |
| White Label Only | 視乎需要 | Tick / Untick | 限制 White Label App 使用 | 按 app availability 決定 | p.38 |
| Not Transferable | 視乎需要 | Tick / Untick | 設定 Bingo 是否可轉贈 | PPT 標示 transferable to other member or not | p.38 |
| Status | 必填 | Active | 控制 Bingo 是否有效 | 上線用 Active | p.38 |
| Create Date | 系統欄位 | Auto / CMS date | 建立紀錄 | 一般不用改 | p.38 |

# 7. 2.4.1 List all Stamps

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Stamp ID | 顯示 / 操作欄位 | System display / Click action | 顯示 Stamp ID | 用作 reference / export | p.39 |
| Brand | 顯示 / 操作欄位 | System display / Click action | 顯示所屬 brand | 可用 brand filter | p.39 |
| Name | 顯示 / 操作欄位 | System display / Click action | 顯示 stamp name | CMS list 顯示 | p.39 |
| Start Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期開始日 | validity | p.39 |
| End Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期完結日 | validity | p.39 |
| Status | 顯示 / 操作欄位 | System display / Click action | 顯示狀態 | Active / Inactive | p.39 |
| Edit | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 修改 stamp detail | p.39 |
| Export | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 匯出 stamp details JSON file | p.39 |

# 8. 2.4.2 Create new Stamp

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Brand | 必填 | Select Brand | 指定 stamp 所屬 brand | 需選正確 brand | p.40 |
| Required Discount Card Level | 視乎活動 | None / Select member level(s) | 限制可收取 stamp 的會員級別 | None 或選擇指定 discount card / member level | p.40 |
| Name (English) | 必填 | English stamp name | 前台 / CMS stamp name | 例如 Stamp Card | p.40 |
| Name (Local Language) | 必填 | Local stamp name | 前台中文 stamp name | 可與英文同名 | p.40 |
| Description (English) | 建議必填 | English description | 前台 stamp descriptions | 活動說明 | p.40 |
| Description (Local Language) | 建議必填 | Local description | 前台中文 stamp descriptions | 活動說明 | p.40 |
| Terms & Conditions (English) | 建議必填 | HTML format | 前台 T&C 顯示 | 需用 HTML format | p.40 |
| Terms & Conditions (Local Language) | 建議必填 | HTML format | 前台中文 T&C 顯示 | 需用 HTML format | p.40 |
| Image (English) | 建議必填 | Stamp card image | 前台 stamp card 圖片 | PPT 未確認 stamp card file size restriction | p.41 |
| Image (Local Language) | 建議必填 | Stamp card image | 前台中文 stamp card 圖片 | 如同圖可重用 | p.41 |
| Campaign Period | 必填 | Start date - End date | 控制 stamp campaign validity | PPT 文字誤寫 bingo；此處為 stamp validity | p.41 |
| Normal Stamp Image | 必填 | Image file, recommended 1MB, 1:1 | 普通 stamp 圖片 | 前台 stamp 顯示 | p.41 |
| Welcome Pack | 視乎活動 | 0 / quantity | 控制 welcome pack stamp 數量 | 有迎新印花先填 | p.41 |
| Special Stamp | 視乎活動 | Tick if applicable | 是否啟用 special stamp | 有特殊印花機率活動先 tick | p.41 |
| Special Stamp Image | 視乎活動 | Image file, recommended 1MB, 1:1 | special stamp 圖片 | Special Stamp 啟用時需要 | p.41 |
| Special Stamp Probability | 視乎活動 | Select probability | 控制 special stamp 出現機率 | 例如 5% | p.41 |
| Special Stamp Daily Limit | 視乎活動 | Upper limit per day | 設定 special stamp 每日上限 | 防止過量派發 | p.41 |
| Type | 必填 | By Transaction Amount / selected criteria | 選擇派發 stamp 條件 | PPT 指示 choose stamp giving criteria | p.42 |
| Transaction Amount | 視乎 Type | Default amount / custom amount | 按交易金額派 stamp | 可 Add Custom Transaction Amount | p.42 |
| Total Space | 必填 | Max stamp quantity | 會員 wallet 內 stamp 最大數量 | 控制 stamp card 空間 | p.42 |
| Gift | 必填 / 視乎 redeem | Select gift + stamp quantity | 設定印花換領獎賞及所需 stamp 數 | 每個 gift 要輸入對應 stamp qty | p.42 |
| Has Week Day And Time Criteria | 視乎活動 | Tick / Untick | 限制只於指定日期 / 時段使用 | Merchant 有時段限制先 tick | p.42 |
| Auto Redeem | 視乎活動 | Tick / Untick | 控制是否自動兌換 | 需同 merchant redeem flow 一致 | p.42 |
| Transferable | 視乎活動 | Tick / Untick | 設定 stamp 是否可轉贈 | PPT 文字誤寫 bingo；此處指 stamp | p.42 |
| Status | 必填 | Active | 控制 stamp campaign 是否有效 | 上線用 Active | p.42 |

# 9. 2.5.1 List all Coupons

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Coupon ID | 顯示 / 操作欄位 | System display / Click action | 顯示 Coupon ID | 用作 reference / export | p.43 |
| Brand | 顯示 / 操作欄位 | System display / Click action | 顯示所屬 brand | 可用 brand filter | p.43 |
| Name | 顯示 / 操作欄位 | System display / Click action | 顯示 coupon name | CMS list 顯示 | p.43 |
| Type | 顯示 / 操作欄位 | System display / Click action | 顯示 coupon type | Freebie / Item Discount / Receipt Discount | p.43 |
| Delivery Type | 顯示 / 操作欄位 | System display / Click action | 顯示派發方式 | Push / Purchase / Redeem / Welcome Pack 等 | p.43 |
| Start Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期開始日 | validity | p.43 |
| End Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期完結日 | validity | p.43 |
| White Label | 顯示 / 操作欄位 | System display / Click action | 顯示是否 White Label only | 按 app availability 判斷 | p.43 |
| Available to Storellet App Only | 顯示 / 操作欄位 | System display / Click action | 顯示 App availability | 限制 Storellet App 使用 | p.43 |
| Status | 顯示 / 操作欄位 | System display / Click action | 顯示狀態 | Active / Inactive | p.43 |
| Edit | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 修改 coupon detail | p.43 |
| Export | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 匯出 coupon details JSON / Unix file | p.43 |

# 10. 2.5.2 Create Coupon

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Import File | 選填 | Upload file if needed | 匯入 coupon config | PPT 未確認 file size restriction | p.44 |
| Coupon ID | 系統欄位 | Auto / existing ID | Coupon config reference | 一般不用改 | p.44 |
| Brand | 必填 | Select Brand | 指定 coupon 所屬 brand | 需選正確 brand | p.44 |
| Required Discount Card Level | 視乎活動 | None / Select member level(s) | 限制可領取 coupon 的會員級別 | None 或選擇 discount card / member level | p.44 |
| Type | 必填 | Freebie / Item Discount / Receipt Discount | 設定 coupon 類型 | 需參考 POS preferences | p.44 |
| Item Code | 視乎 Type/POS | POS item code; can be multiple | 同步 POS items | POS 提供，Item Discount 常用 | p.44 |
| Item Discount Value | 視乎 POS | Value + $ / % | 設定 item discount value | 需參考 POS preferences | p.44 |
| Delivery Type | 必填 | Welcome Pack / Birthday Gift / Push / Redeem | 控制 coupon 派發方式 | 未確認前建議 set Push，避免前台提前顯示 | p.44 |
| Name (English) | 必填 | English coupon name | 前台 coupon name | 例如 $10 Cash Coupon | p.44 |
| Name (Local Language) | 必填 | Local coupon name | 前台中文 coupon name | 例如 $10 現金券 | p.44 |
| Is CouponLeaflet | 視乎需要 | Tick / Untick | 標記 leaflet coupon | 按活動用途決定 | p.44 |
| Image (English) | 建議必填 | English coupon image | 前台英文 coupon image | App / website 顯示 | p.45 |
| Image (Local Language) | 建議必填 | Local coupon image | 前台中文 coupon image | App / website 顯示 | p.45 |
| Image 2 / 3 | 選填 | Leave blank unless special implementation | 額外 coupon images | 一般前台會 ignore，除非有特殊 implementation | p.45 |
| Description (English) | 選填 | English description | 前台 coupon description | 可按 coupon detail 填寫 | p.46 |
| Description (Local Language) | 選填 | Local description | 前台中文 coupon description | 可按 coupon detail 填寫 | p.46 |
| Terms & Conditions (English) | 建議必填 | HTML format | 前台 T&C 顯示 | 需用 HTML format | p.46 |
| Terms & Conditions (Local Language) | 建議必填 | HTML format | 前台中文 T&C 顯示 | 需用 HTML format | p.46 |
| How To Use (English) | 建議必填 | HTML format | 前台 How to Use 顯示 | 需用 HTML format | p.46 |
| How To Use (Local Language) | 建議必填 | HTML format | 前台中文使用說明 | 需用 HTML format | p.46 |
| External URL Wordings | 選填 | Button / link title | coupon 內外部連結顯示文字 | 最多可按不同語言填寫 | p.46 |
| External URL | 選填 | URL | 點擊 coupon 後導向外部網頁 | 取決於前台是否支援 | p.46 |
| Coupon Extendable | 必填 | No by default | 控制 coupon 是否可延長 | PPT 指示 leave default to No | p.47 |
| Effective Period | 必填 | Start date - End date | 控制 coupon overall validity | 需同 campaign period 對齊 | p.47 |
| Expiry Type | 必填 | By exact date / By effective day | 控制會員收到 coupon 後的到期計算方式 | 可用 exact date 或 received date + effective days | p.47 |
| Effective Day | 視乎 Expiry Type | No. of days | 收到 coupon 後有效天數 | Expiry Type = By Effective Day 時填 | p.47 |
| Redemption Point | 視乎 redeem | Points required | 設定用 points 兌換所需分數 | 例如 10 points | p.47 |
| Quantity | 視乎活動 | 0 / quantity | 設定總數 / 派發數量 | 需確認 quota logic | p.47 |
| Entitlement | 視乎活動 | Number | 設定每位會員 entitlement | 需按活動規則 | p.47 |
| Coupon / Discount Card List | 選填 | Select coupons/cards + quantity | 設定 coupon 內包含的 coupon / discount card | package / bundle 類 coupon 先用 | p.47 |
| Not Transferable | 視乎活動 | Tick / Untick | 設定 coupon 是否可轉贈 | PPT 標示 transferable to other member or not | p.48 |
| Checked as always field | 必填 | Checked as always | PPT 指示必須 always checked | 實際欄位名需以 CMS 畫面為準 | p.48 |
| Frontend dependent function | 視乎前台 | Unchecked by default | 功能可用性取決於 front-end app | PPT 指示 unchecked by default | p.48 |

# 11. 2.6.1 List all Coupon Packages

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Coupon Package ID | 顯示 / 操作欄位 | System display / Click action | 顯示 package ID | 用作 reference / export | p.51 |
| Coupon Package Name | 顯示 / 操作欄位 | System display / Click action | 顯示 package name | CMS list 顯示 | p.51 |
| Start Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期開始日 | validity | p.51 |
| End Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期完結日 | validity | p.51 |
| Status | 顯示 / 操作欄位 | System display / Click action | 顯示狀態 | Active / Inactive | p.51 |
| Edit | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 修改 package detail | p.51 |
| Export | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 匯出 package details JSON / Unix file | p.51 |

# 12. 2.6.2 Create Coupon Package

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Import File | 選填 | Upload file if needed | 匯入 coupon package config | PPT 未確認 file size restriction | p.52 |
| Brand | 必填 | Select Brand | 指定 package 所屬 brand | 需選正確 brand | p.52 |
| Coupon / Discount Card List | 必填 | Tick included coupons/cards + quantity | 設定 package 包含的 coupons / discount cards | 需輸入每項 quantity | p.52 |
| Delivery Type | 必填 | Select delivery type | 控制 package 派發方式 | 按 campaign use case 設定 | p.52 |
| Name (English) | 必填 | English package name | 前台 package name | CMS / App 顯示 | p.52 |
| Name (Local Language) | 必填 | Local package name | 前台中文 package name | CMS / App 顯示 | p.52 |
| Image | 建議必填 | Package image, recommended 1MB | 前台 package 圖片 | PPT 標示 file size recommendation: 1MB | p.53 |
| Description | 建議必填 | Package descriptions | 前台 package description | 活動說明 | p.53 |
| Terms & Conditions | 建議必填 | HTML format | 前台 T&C 顯示 | 需用 HTML format | p.53 |
| How To Use | 建議必填 | HTML format | 前台使用說明 | 需用 HTML format | p.54 |
| Effective Period | 必填 | Start date - End date | 控制 package 有效期 | PPT 指示 enter date to indicate validity | p.54 |
| Not Transferable | 視乎活動 | Tick / Untick | 設定 package 是否可轉贈 | PPT 標示 transferable to other member or not | p.54 |
| Status | 必填 | Active | 控制 package 是否有效 | 上線用 Active | p.54 |

# 13. 2.7.1 List all Coupon Trigger Rules

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Type | 顯示 / 操作欄位 | System display / Click action | 顯示 trigger rule type | CMS list 顯示 | p.55 |
| Start Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期開始日 | validity | p.55 |
| End Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期完結日 | validity | p.55 |
| Status | 顯示 / 操作欄位 | System display / Click action | 顯示狀態 | Active / Inactive | p.55 |
| Edit | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 修改 trigger rule detail | p.55 |

# 14. 2.7.2 Create Coupon Trigger Rule

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Brand | 必填 | Select Brand | 指定 trigger rule 所屬 brand | 需選正確 brand | p.56 |
| Required Discount Card Level | 視乎活動 | None / Select member level(s) | 限制可收到 coupon 的會員級別 | None 或選擇 discount card / member level | p.56 |
| Type | 必填 | Select trigger rule type | 設定 trigger rule 類型 | PPT 指示 select trigger rule type | p.56 |
| Day of Month | 視乎 Type | 1 / 15 / selected day | 設定每月派發日期 | 例如 monthly coupon 於每月 1 或 15 號派發 | p.56 |
| Effective Period | 必填 | Start date - End date | 控制 trigger rule 有效期 | PPT 指示 enter date to indicate validity | p.56 |
| Coupon List | 必填 | Select coupon(s) + quantity | 設定 rule 觸發後派發的 coupon(s) | 需輸入 quantity | p.57 |
| Status | 必填 | Active | 控制 trigger rule 是否有效 | 上線用 Active | p.57 |

# 15. 2.8.1 List all Surveys

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Survey ID | 顯示 / 操作欄位 | System display / Click action | 顯示 survey ID | 用作 reference / export | p.58 |
| Brand | 顯示 / 操作欄位 | System display / Click action | 顯示所屬 brand | 可用 brand filter | p.58 |
| Name | 顯示 / 操作欄位 | System display / Click action | 顯示 survey name | CMS list 顯示 | p.58 |
| Start Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期開始日 | validity | p.58 |
| End Date | 顯示 / 操作欄位 | System display / Click action | 顯示有效期完結日 | validity | p.58 |
| Status | 顯示 / 操作欄位 | System display / Click action | 顯示狀態 | Active / Inactive | p.58 |
| Edit | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 修改 survey detail | p.58 |
| Export | 顯示 / 操作欄位 | System display / Click action | 操作按鈕 | 匯出 survey details JSON file | p.58 |

# 16. 2.8.2 Create Survey

| Field / UI Item | Status | Suggested / Default | Purpose / Front-end Impact | Notes | Source |
|---|---|---|---|---|---|
| Import File | 選填 | Upload file if needed | 匯入 survey config | 如無需匯入可留空 | p.59 |
| Brand | 必填 | Select Brand | 指定 survey 所屬 brand | 需選正確 brand | p.59 |
| Name (English) | 必填 | English survey name | 前台 / CMS survey name | 活動名稱 | p.59 |
| Name (Local Language) | 必填 | Local survey name | 前台中文 survey name | 活動名稱 | p.59 |
| Description (English) | 建議必填 | English description | 前台 survey description | 活動說明 | p.59 |
| Description (Local Language) | 建議必填 | Local description | 前台中文 survey description | 活動說明 | p.59 |
| Terms & Conditions (English) | 建議必填 | HTML format | 前台 T&C 顯示 | 需用 HTML format | p.59 |
| Terms & Conditions (Local Language) | 建議必填 | HTML format | 前台中文 T&C 顯示 | 需用 HTML format | p.59 |
| How To Use (English) | 建議必填 | HTML format | 前台使用說明 | 需用 HTML format | p.59 |
| How To Use (Local Language) | 建議必填 | HTML format | 前台中文使用說明 | 需用 HTML format | p.59 |
| Questions / Answer Options | 視乎 survey | Add questions and options | 設定 survey 問題及答案 | 需按 survey design 填寫 | p.60 |
| Effective Period | 必填 | Start date - End date | 控制 survey 有效期 | 需同 campaign period 對齊 | p.60 |
| Reward / Coupon | 視乎活動 | Select reward if applicable | 完成 survey 後派發獎賞 | 需確認 campaign reward logic | p.60 |
| Status | 必填 | Active | 控制 survey 是否有效 | 上線用 Active | p.60 |

---

# 17. 上架前重點檢查

## 共通設定

1. 核對 Asset 所屬 Group 或 Brand。
2. 核對英文及本地語言名稱、描述、Terms & Conditions 及 How To Use。
3. 核對 Start Date、End Date 或 Effective Period。
4. 核對 White Label App／Storellet App 可用範圍。
5. 核對 Transferable／Not Transferable 設定。
6. 正式上架前確認 Status；已確認來源一般建議上線使用 Active。
7. 有圖片時，來源多處建議約 1MB，但部分模組實際檔案限制仍待確認。

## Points

- Group、Point(s)、Type、Start Date、End Date 及 Status 為必填。
- Type 已確認例子包括 Welcome Pack、Birthday Gift、Anniversary Gift、Push 及 Redeem Code。
- Available to White Label App Only、Available to Storellet App Only 及 Not Transferable 應按活動需要設定。

## Discount Card

- 每個 Brand 至少需要一個 Basic Tier／Welcome Pack Card。
- Discount Level 例子：Basic = 1、Silver = 2、Gold = 3、VIP = 4。
- Set As Welcome Pack、Renew Type、Expiry Date Pattern、Point Multiply Ratio 及 Stamp Multiply Ratio 會直接影響會員等級及前台體驗，必須跟 Merchant 已確認規則一致。
- Shopline Membership Tier ID 只適用於 Shopline Integration；來源指示 Shopline Basic Tier 填寫 `null`。

## Bingo

- 教學列出完整欄位，但同時標示 Bingo Not in use；Production 是否支援必須先確認。
- Day Period、Daypart Time Slot、Reward 1–8 應按活動設計設定。

## Stamp

- 核對 Stamp Type、有效期、Image、Terms & Conditions、How To Use、Day Period／Time Slot、Reward 及 Status。
- Promotion Message 及 Stamp Card Image 檔案限制仍待確認。

## Coupon

- 核對 Brand、Coupon Type、名稱、圖片、內容、有效期、Expiry Type 及 Status。
- Expiry Type 選 By Effective Day 時才填 Effective Day。
- Quantity 及 Entitlement 會影響總 Quota 及每位會員權益，現有教學未足以確認完整邏輯。
- `Checked as always field` 在來源中要求 Always Checked，但實際欄位名稱仍需以 CMS 畫面為準。

## Coupon Package

- 教學標示 Coupon Package Not in use；使用前先確認 Production 支援狀態。
- Coupon／Discount Card List 需選擇包含項目及每項 Quantity。

## Coupon Trigger Rule

- 核對 Brand、Type、Effective Period、Coupon List、Quantity 及 Status。
- Required Discount Card Level 及 Day of Month 視乎規則類型。
- 自動派券執行邏輯必須以現行 Production 規則及 Tech 確認為準。

## Survey

- 核對 Brand、名稱、描述、T&C、How To Use、Questions、Effective Period、Reward 及 Status。
- Questions／Answer Options 及 Reward 派發邏輯需跟實際 Campaign Design 確認。

---

# 18. 待進一步確認項目

Excel Summary 寫有 10 項，但「Need Further Confirm」工作表實際列出 12 項；以下以工作表實際內容為準。

| Section | Field / Area | Reason | Source |
|---|---|---|---|
| 2.1 Points | Import File / file size restriction | PPT 有 file upload，但未完全確認格式 / size restriction；一般可留空。 | p.30 |
| 2.2 Discount Card | Image display issue | PPT 標示 card image 1MB 但括號寫 seems not working，需要確認目前 CMS / App 是否仍有效。 | p.32 |
| 2.3 Bingo | Module status | PPT 標示 Bingo Not in use，但仍有完整欄位；使用前需確認現時 production 是否仍支援。 | p.35–p.38 |
| 2.3 Bingo | Amount Range 1–3 | PPT 標示 ???，欄位用途未確認。 | p.38 |
| 2.4 Stamp | Promotion Message | PPT 標示 ???，雖見 placeholder 但用途未確認。 | p.40 |
| 2.4 Stamp | Stamp card image file restriction | PPT 問 Any file size recommendation / restriction；需確認現時規格。 | p.41 |
| 2.5 Coupon | Import File / file size restriction | PPT 問 Any file size recommendation / restriction；需確認匯入格式及大小。 | p.44 |
| 2.5 Coupon | Quantity / Entitlement logic | 會影響派發 quota / 每人 entitlement，需跟 campaign rule / tech 確認。 | p.47 |
| 2.6 Coupon Package | Module status | PPT 標示 Coupon Package Not in use；使用前需確認現時 production 是否仍支援。 | p.51 |
| 2.6 Coupon Package | Effective period end date note | PPT 註記 Same with end date of effective period??，需確認 end date rule。 | p.54 |
| 2.7 Coupon Trigger Rule | Rule execution logic | 月派發日期、會員級別、coupon quantity 會影響自動派券，需確認 current trigger behavior。 | p.56–p.57 |
| 2.8 Survey | Questions / Reward setup | PPT 搜尋結果不足以完全確認題目與獎賞邏輯，需按實際 campaign design 確認。 | p.59–p.60 |

---

# 19. Chatbot 回答規則

1. 回答時要指出 Sub-section、Field／UI Item、Status、建議值及前台影響。
2. 不可將列表頁的「顯示／操作欄位」誤稱為建立 Asset 時必填。
3. 「視乎需要／活動／Type」必須同時說明觸發條件。
4. 「建議必填」不可回答成系統強制必填；應說明為前台內容或圖片展示需要。
5. 不可自行提供未確認的 Import File 格式、檔案大小限制或圖片限制。
6. Bingo 及 Coupon Package 被教學標示為 Not in use，回答操作前要提示先確認 Production 支援狀態。
7. Quantity、Entitlement、Coupon Trigger Rule、Survey Reward 等派發邏輯不可單靠欄位名稱推斷。
8. 不可推斷 Amount Range 1–3、Promotion Message 或來源標示 `???` 的欄位用途。
9. 不可將建議 Default 當成所有 Merchant 的固定設定；Tier、倍率、有效期及獎賞必須跟已確認 Merchant Rules。
10. 如資料未在本文件確認，應回答：「現有已確認 Assets 教學未有清楚定義，需向相關 Team 確認。」

---

# 20. 常見問題

## Q1：Assets 包括哪些模組？

已確認範圍包括 Points、Discount Card、Bingo、Stamp、Coupon、Coupon Package、Coupon Trigger Rule 及 Survey。

## Q2：Image 標示「建議必填」代表系統一定強制上載嗎？

不一定。「建議必填」代表圖片通常會影響前台展示，並非已確認的系統強制驗證。多處來源建議約 1MB，但部分模組的實際限制仍待確認。

## Q3：每個 Brand 是否需要 Basic Membership Tier？

是。已確認資料指出每個 Brand 至少需要建立一個 Basic Tier，並設定為 Welcome Pack。

## Q4：Discount Level 如何設定？

來源例子為 Basic = 1、Silver = 2、Gold = 3、VIP = 4。實際層級應跟 Merchant 已確認的 Tier Structure 一致。

## Q5：Coupon 的 Expiry Type 有甚麼分別？

可按 Exact Date 或 Effective Day 計算。選擇 Effective Day 時，需要填寫會員收到 Coupon 後的有效日數。

## Q6：Quantity 與 Entitlement 應該點填？

現有資料只確認兩個欄位分別與總數／派發數量及每位會員權益有關；完整 Quota 計算及限制仍需跟 Campaign Rule／Tech 確認。

## Q7：Bingo 及 Coupon Package 可以直接使用嗎？

不應直接假設可以。教學標示兩個模組 Not in use，雖然保留完整欄位，但使用前需確認現時 Production 是否支援。

## Q8：Coupon Trigger Rule 的 Day of Month 何時需要填？

只在所選 Type 涉及每月指定日期派發時使用，例如每月 1 號或 15 號。實際執行邏輯需按現行 Trigger Rule 確認。

---

**最後更新**：2026-07-17  
**資料狀態**：230 項已確認；12 項待進一步確認  
**適用角色**：Account Servicing、Marketing、營運人員、Customer Service
