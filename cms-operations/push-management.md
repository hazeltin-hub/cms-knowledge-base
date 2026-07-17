# CMS Push 欄位及必填設定指南

## 標籤

#user-guide #push #marketing #field-reference #required-fields

## 文件用途

本文件整理 Storellet CMS `Push` 模組各頁面已確認的欄位、必填設定、用途及注意事項，供營運人員操作及 Chatbot 回答使用。

資料來源：`Storellet_CMS_UserGuide.pptx.pdf`，Push 章節 p.74–p.82，以及 `push_confirmed_fields.xlsx`。

> 重要：本文件只將來源中已清楚確認的內容列為正式設定。未確認的功能、CSV 格式及狀態值會獨立列於「待確認項目」，不可由 Chatbot 推斷。

---

## 必填狀態定義

| 狀態 | 意思 |
|---|---|
| 必填 | 建立或提交時必須填寫 |
| 視乎需要 | 視語言、目標對象或操作情況而定 |
| 選填 | 可按需要啟用或填寫 |
| 系統 | 系統自動產生，一般毋須手動修改 |
| 列表顯示 | 只在列表頁顯示，供查閱或核對 |
| 操作 | 頁面按鈕或操作入口，不是輸入欄位 |

---

# 1. Push Coupon

## 1.1 List all push coupon

| 欄位 | 類型 | 顯示／預設 | 用途及注意事項 |
|---|---|---|---|
| Coupon | 列表顯示 | Auto／現有 Coupon 名稱 | 顯示已建立的 Push Coupon；Create 時由 Coupon 欄位選擇 |
| Brand | 列表顯示 | Auto | 顯示 Push Coupon 所屬品牌 |
| Push Target | 列表顯示 | Auto | 顯示派發對象，可用作核對 Brand Members 或 Custom Brand Members |
| Push Date | 列表顯示 | Auto | 顯示排程派發日期及時間；推送前需核對 |
| Edit | 操作 | Click Edit | 修改 Push Coupon 詳情；只應在推送前修改，已推送後是否容許變更需按系統實際狀態確認 |

## 1.2 Create push coupon

| 欄位 | 是否必填 | 建議填寫／預設 | 用途及注意事項 |
|---|---|---|---|
| Brand | 必填 | 選擇 Coupon 所屬 Brand | 決定向哪個品牌的會員派發 Coupon；必須選擇正確品牌 |
| Coupon | 必填 | 選擇 Active Coupon | 決定派發哪一張 Coupon；建立前應先確認 Coupon 設定及有效期 |
| Quantity | 必填 | 例如 `1` | 決定每位目標會員收到的 Coupon 數量；需避免數量錯誤或重複派發 |
| Push Target | 必填 | Brand Members／Custom Brand Members | 決定派發對象；選 Custom Brand Members 時需要上載 CSV |
| Receivers | 視乎需要 | CSV file only；Member ID list | 只在 Push Target 選擇 Custom Brand Members 時使用；來源標示最多 400,000 rows，CSV 欄位格式仍待確認 |
| Push Date | 必填 | `YYYY/MM/DD` | 設定 Coupon 派發日期；推送前需確認活動日期及時區 |
| Push Time | 必填 | `HH:mm` | 設定 Coupon 派發時間；避免在不合適時段派發 |
| Create Date | 系統 | Auto | 顯示建立紀錄日期 |
| Last Update Date | 系統 | Auto | 顯示最近更新日期 |
| Last Update By | 系統 | Auto | 顯示最近更新人 |

### 建立前檢查

1. 核對 Brand。
2. 核對 Coupon 名稱、設定及有效期。
3. 確認 Quantity 是「每位目標會員收到的數量」。
4. 核對 Push Target。
5. 如選 Custom Brand Members，確認 Receivers CSV 名單正確，並不超過 400,000 rows。
6. 核對 Push Date 及 Push Time。

---

# 2. Batch Point Adjustment

## 2.1 List all point adjustment

| 欄位／操作 | 類型 | 顯示／預設 | 用途及注意事項 |
|---|---|---|---|
| Creation Date | 列表顯示 | Auto | 顯示批量積分調整的建立日期 |
| Scheduled Date | 列表顯示 | Auto | 顯示批量積分調整的排程日期；執行前需核對 |
| Brand | 列表顯示 | Auto | 顯示 Point Adjustment 所屬品牌 |
| Add New | 操作 | Click Add New | 建立新的 Batch Point Adjustment；批量加減分屬高風險操作，提交前應由另一位同事覆核 |

## 2.2 Create point adjustment

| 欄位 | 是否必填 | 建議填寫／預設 | 用途及注意事項 |
|---|---|---|---|
| Brand | 必填 | 選擇 Point Adjustment 所屬 Brand | 決定調整哪個品牌會員的積分；必須選擇正確品牌 |
| Scheduled Date | 必填 | `YYYY-MM-DD`／CMS Date Picker | 設定批量積分調整日期；需配合活動或補償派發安排 |
| Scheduled Time | 必填 | `HH:mm` | 設定批量積分調整時間；提交前需核對 |
| CSV | 必填 | Targeted Member ID + Point Adjustment | 指定受影響會員及調整分數；上載前必須核對 Member ID、加／減分方向及 Point Value。確實欄位名稱和格式仍待確認 |

### 建立前檢查

1. 核對 Brand。
2. 核對 Scheduled Date 及 Scheduled Time。
3. 核對 CSV 內的 Member ID。
4. 核對每項 Point Adjustment 的正負方向及數值。
5. 建議由另一位同事 Double Check 後才提交。

---

# 3. Notification

## 3.1 List all notification

| 欄位／操作 | 類型 | 顯示／預設 | 用途及注意事項 |
|---|---|---|---|
| Push Target | 列表顯示 | Auto | 顯示通知推送對象 |
| Type | 列表顯示 | Auto | 顯示 Notification Type，例如 Home、Promotion 或 Merchant |
| Message | 列表顯示 | Auto | 顯示通知內容摘要；推送前需核對文案 |
| Push Date | 列表顯示 | Auto | 顯示排程推送日期；推送前需核對 |
| Add New | 操作 | Click Add New | 建立新的 Notification；建立前需確認目標會員及推送渠道 |

## 3.2 Create Notification

| 欄位 | 是否必填 | 建議填寫／預設 | 用途及注意事項 |
|---|---|---|---|
| Push Target | 必填 | All Members／Brand Members／Custom with CSV | 決定通知對象；選 Custom 時需要匯入 CSV，推送前必須核對 Audience |
| Title (Eng) | 視乎需要 | 英文標題 | 英文 Inbox／Notification 標題；即使主要使用中文，亦建議填寫作 Fallback |
| Title (Chi) | 必填 | 中文標題 | 中文用戶主要看到的標題 |
| Message (Eng) | 視乎需要 | 英文內容 | 英文通知內容；即使主要使用中文，亦建議填寫作 Fallback |
| Message (Chi) | 必填 | 中文內容 | 中文通知內容；需檢查字數、連結及 Emoji 顯示 |
| Same Inbox Message | 選填 | Tick／Untick | 控制 Inbox Message 是否沿用相同內容；如 Push 與 Inbox 文案不同，需按實際頁面設定 |
| Image | 選填 | 建議約 1MB；Landscape Mode | 圖片顯示於 Message Section 上方；應使用橫圖及避免圖片文字太細 |
| Notification Type | 必填 | Home／Promotion／Merchant 等 | 將 Notification 分類；需按內容用途選擇 |
| Push Date | 必填 | `YYYY/MM/DD` | 設定通知推送日期；需配合 Campaign Schedule |
| Push Time | 必填 | `HH:mm` | 設定通知推送時間；避免在不合適時段推送 |
| Push Needed | 選填 | Tick／Untick | Tick 後訊息會在會員手機 Notification Bar 彈出 |
| Inbox Needed | 選填 | Tick／Untick | Tick 後訊息會出現在 Storellet App Inbox；如需要保留訊息記錄，建議啟用 |
| Highlighted Message Needed | 選填 | Tick／Untick | Tick 後訊息會在 Storellet App Homepage 頂部彈出，屬高曝光位置 |

## 3.3 三個訊息渠道的分別

| 設定 | 顯示位置 | 適合情況 |
|---|---|---|
| Push Needed | 手機 Notification Bar | 需要主動提醒會員 |
| Inbox Needed | Storellet App Inbox | 需要會員之後仍可翻查訊息 |
| Highlighted Message Needed | App Homepage 頂部 | 需要在 App 內高曝光顯示 |

以上三項均為選填，可按 Campaign 需要選擇。提交前應確認是否會造成重複曝光。

### 建立前檢查

1. 核對 Push Target 及 Audience。
2. 核對中英文 Title 和 Message。
3. 核對 Notification Type。
4. 核對 Push Date 及 Push Time。
5. 確認 Push、Inbox、Highlighted Message 三個渠道需要啟用哪些。
6. 如有圖片，確認為橫圖、檔案大小合適且文字清晰。

---

# 4. News

## 4.1 List all news

| 欄位／操作 | 類型 | 顯示／預設 | 用途及注意事項 |
|---|---|---|---|
| Brand | 列表顯示 | Auto | 顯示 News 所屬品牌 |
| Title | 列表顯示 | Auto | 顯示 News 標題 |
| Publish Date | 列表顯示 | Auto | 顯示 News 發佈日期；上架前需核對 |
| Edit | 操作 | Click Edit | 修改 News 詳情；已發佈內容修改後是否即時反映前台，需按系統實際行為確認 |

## 4.2 Create news

| 欄位 | 是否必填 | 建議填寫／預設 | 用途及注意事項 |
|---|---|---|---|
| Brand | 必填 | 選擇 Brand | 決定 News 所屬品牌；必須選擇正確品牌 |
| News Title (Eng) | 視乎需要 | 英文 News Title | 英文前台／Fallback 顯示；建議填寫 |
| News Title (Chi) | 必填 | 中文 News Title | 中文前台顯示的 News 標題 |
| Description (Eng) | 視乎需要 | 英文描述 | 顯示於 Latest News Section；建議填寫作 Fallback |
| Description (Chi) | 必填 | 中文描述 | 顯示於 Latest News Section |
| Image (Eng) | 視乎需要 | 英文圖；建議約 1MB；Landscape Mode | 顯示於 Latest News Section；如中英文共用同一圖片可按實際需要重用 |
| Image (Chi) | 必填 | 中文圖；建議約 1MB；Landscape Mode | 顯示於 Latest News Section；應使用橫圖及避免圖片文字太細 |
| Publish Date | 必填 | `YYYY/MM/DD` | 設定 News 發佈日期；需配合 Content Schedule |
| Publish Time | 必填 | `HH:mm` | 設定 News 發佈時間；需配合 Content Schedule |
| Status | 必填 | Active／Inactive／Suspended | 控制 News 狀態；正式上架使用 Active，其他狀態的實際用途應按內部安排確認 |
| Create Date | 系統 | Auto | 顯示建立紀錄日期 |
| Last Update Date | 系統 | Auto | 顯示最近更新日期 |

### 建立前檢查

1. 核對 Brand。
2. 核對中英文標題及描述。
3. 核對圖片語言、方向、檔案大小及清晰度。
4. 核對 Publish Date 及 Publish Time。
5. 正式上架前確認 Status 為 Active。

---

# 5. 待 Tech／CRM 確認項目

以下內容在現有教學資料中未有足夠說明，Chatbot 應回答「尚待確認」，不可自行提供格式或預設值。

| 模組 | 畫面／範圍 | 待確認內容 |
|---|---|---|
| Push Coupon | Create push coupon | `Bypass Internal Third Party Event Tracking (ex: Braze)` 的預設值、用途、適用場景及影響 |
| Batch Point Adjustment | List all point adjustment | `Number of Record` 的準確定義；可能與匯入行數或受影響會員數有關，但未確認 |
| Batch Point Adjustment | List all point adjustment | `Status` 的可用狀態值，以及是否可由 CMS 操作 |
| Push Coupon | Receivers CSV | CSV 欄位名稱、Delimiter、是否需要 Header；目前只確認為 Member ID List 及最多 400,000 rows |
| Batch Point Adjustment | CSV | CSV 欄位名稱、加減分格式、是否需要 Reason／Remark 及其他欄位 |

---

# 6. Chatbot 回答規則

1. 回答欄位問題時，應指出所屬 Submodule、Screen、欄位名稱及必填狀態。
2. 「視乎需要」不可直接回答為必填或選填，必須同時說明觸發條件。
3. 系統欄位應說明為 Auto，一般毋須手動修改。
4. 不可將列表顯示欄位當成建立頁面的輸入欄位。
5. 不可自行推斷 CSV Header、格式、狀態值、檔案大小上限或第三方追蹤邏輯。
6. 如問題涉及待確認項目，應明確回答：「現有已確認資料未有清楚定義，需向 Tech／CRM Team 確認。」
7. Push Coupon 的 Quantity 是每位目標會員收到的 Coupon 數量，不是整個任務的總派發量。
8. Receivers CSV 目前只確認最多 400,000 rows；不可回答為 100,000 users 或 10MB，除非有新資料確認。

---

# 7. 常見問題

## Q1：Custom Brand Members 是否一定要上載 CSV？

是。Create push coupon 選擇 Custom Brand Members 時，Receivers 欄位需要上載 CSV。現時只確認 CSV 是 Member ID List，並最多 400,000 rows；詳細欄位格式仍待確認。

## Q2：Push Coupon 的 Quantity 是甚麼？

Quantity 代表每位目標會員收到的 Coupon 數量，例如填寫 `1`，即每位合資格目標會員收到 1 張 Coupon。

## Q3：Notification 的英文 Title 和 Message 是否必填？

已確認資料將兩項列為「視乎需要」。如主要使用中文，仍建議填寫英文內容作 Fallback；中文 Title 及 Message 為必填。

## Q4：Push Needed、Inbox Needed 和 Highlighted Message Needed 有甚麼分別？

- Push Needed：在會員手機 Notification Bar 彈出。
- Inbox Needed：顯示於 Storellet App Inbox。
- Highlighted Message Needed：顯示於 App Homepage 頂部。

三項均為選填，可按 Campaign 需要選擇。

## Q5：Batch Point Adjustment 的 CSV 格式是甚麼？

現時只確認 CSV 需要包含 Targeted Member ID 及 Point Adjustment。確實欄位名稱、正負數格式及其他欄位仍待 Tech 確認，因此不可自行提供 CSV Template。

## Q6：News 上架需要哪些必填欄位？

必填欄位包括 Brand、News Title (Chi)、Description (Chi)、Image (Chi)、Publish Date、Publish Time 及 Status。英文標題、描述及圖片屬視乎需要，但建議提供作英文前台或 Fallback 使用。

---

**最後更新**：2026-07-17  
**資料狀態**：57 項已確認；5 項待進一步確認  
**適用角色**：營運人員、Marketing、Account Servicing、Customer Service
