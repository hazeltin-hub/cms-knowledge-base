# CMS Coupon Operations 進階操作指南

## 標籤

#user-guide #coupon #operations #batch-operations #advanced #confirmed

## 文件用途

本文件整理 Storellet CMS Coupon 模組的進階操作設定、批次操作、Tier 相關規則及 Braze 整合設定，供 Account Servicing、Marketing 及營運人員使用。

資料來源：同事操作筆記及現場操作確認。

---

## 重要概念定義

### Coupon Type 類型

| Type | 數值 | 說明 |
|---|---|---|
| Freebie | 0 | 免費產品/服務優惠 |
| Item Discount | 1 | 指定產品折扣優惠 |
| Receipt Discount | 2 | 賬單折扣優惠 |

### Dispatch on Join 設定規則

**重要規則：**
- **有分 Tier 的 Birthday Coupon/Monthly Coupon** - 不可以 tick "Dispatch on join"
- **新會員不會自動收到** - 除非所有 Tier Member 都收到相同的生日 Offer
- **避免錯誤派發** - 防止新會員獲得不應得的生日/每月優惠

---

## 1. Coupon PUSH 設定與 Braze 整合

### 1.1 第三方事件追蹤設定

#### Bypass Internal Third Party Event Tracking

| 情況 | 設定要求 | 說明 |
|---|---|---|
| **無 Braze 設定的 Brand** | ✅ **需要 tick** | CMS 直接派發，不經 Braze |
| **KFC/PHD** | ❌ **唔需要 tick** | 使用自有 Braze 帳戶 |
| **其他有 Braze 的 Brand** | ❌ **唔需要 tick** | 經 Braze 派發 |

**設定邏輯：**
- **Coupon 派畀所有 Brand Member** 同時無 Set Braze → 請 CMS 派果時 tick Bypass Internal Third Party Event Tracking
- **現有 Coupon/Discount** - 會顯示 "default"，代表發送去兩個 Braze 帳戶

#### Monthly Trigger Rule 設定

**Submit To 3rd Party Event Tracking:**
- ✅ **Untick** 建議設定
- 🎯 **排查功能** - 可以排查客人 Account 裡面有無張 Coupon，有就不再派發

---

## 2. Branded App 特殊要求

### 2.1 Brand App 類型選擇

| Brand 類型 | 設定選項 | 適用範圍 |
|---|---|---|
| **KFC/PHD** | Non Storellet Only | 自有 App，非 Storellet 系統 |
| **其他 Brand** | Storellet Only | 使用 Storellet App |

### 2.2 Branded App 設置步驟

#### Step 1: 啟用 Brand Profile
1. 前往 **Company > Brands**
2. 選擇目標 Brand
3. ✅ **Tick "Enable Brand Profile"**
4. 就會有 Branded Profile 顯示

#### Step 2: 設置背景圖
1. 前往 **Company > Brands > Branded App > Thumbnail**
2. 📷 **上傳背景圖**

#### Step 3: 設置條款及細則
1. 前往 **Company > Brands > Branded App > Terms and Conditions**
2. 📝 **填寫三種語言版本**：
   - 英文版本
   - 中文版本
   - 其他語言版本（如需要）

#### Step 4: 設置簡介
1. 前往 **Company > Brands > Short Description (Local Language)**
2. 📝 **填寫品牌簡介**

#### Step 5: 設置 App IDs
1. 前往 **Company > Brands > Branded App**
2. 📱 **加入對應的 App IDs**：
   - **Android App ID** (AOS)
   - **iOS App ID**

---

## 3. Application Config 設定

### 3.1 年齡範圍設定

**設定位置：** Application > Config > Age Range

**年齡分段：**
```
12-17
18-25
26-30
31-35
36-40
41-50
51-64
65-100
```

**操作步驟：**
1. 前往 **Application > Config**
2. 找到 **Age Range** 設定
3. 設置年齡分段（按 Group 需求）
4. 儲存設定

### 3.2 FAQ 設定要求

**設定位置：** Application > Config

**要求：**
- ✅ **必須填寫 FAQ 內容**
- 📝 **建議多語言版本**
- 🎯 **包含常見問題及答案**

---

## 4. Brand 進階設定

### 4.1 人均消費上下限

**設定位置：** Brand > Lower Price & Higher Price

| 設定欄位 | 說明 | 用途 |
|---|---|---|
| **Lower Price** | 人均消費下限 | 設定最低消費金額參考 |
| **Higher Price** | 人均消費上限 | 設定最高消費金額參考 |

**操作步驟：**
1. 前往目標 Brand 設定頁面
2. 找到 **Lower Price** 欄位
3. 找到 **Higher Price** 欄位
4. 輸入適當金額
5. 儲存設定

---

## 5. Tier Card 與 Coupon 互動規則

### 5.1 Tier Card 自動折扣

**重要規則：**
- ✅ **Tier Card 設定折扣率後** → 自動生效
- 💳 **持卡人自動享受折扣** → 無需额外 Coupon
- 🎯 **與其他 Coupon 的互動**：

| 情況 | 處理方式 |
|---|---|
| **客人要用其他 Coupon** | 前線需要 Cancel 個 Discount 先用得 |
| **Tier 折扣 + Coupon 折扣** | 需要前線手動處理衝突 |
| **優先級問題** | Tier 折扣通常優先於一般 Coupon |

### 5.2 升級與續會金額設定

**參考案例：牛舞**

不同 Tier 的升級、續會所需金額可能不同，建議：
- 📋 **參考現有成功案例**
- 💰 **按營商需求設定**
- 🎯 **測試升級流程**

---

## 6. Coupon Eshop Product 設定

### 6.1 Product Group 顯示邏輯

**重要規則：**
- ❗ **設置 Eshop Product Group** 時要注意：
- 🛒 **Eshop Product Type** 要設成 "Product Group Item"
- 👁️ **Active 佢都唔會 Show 出嚟**

**設定步驟：**
1. 前往 Coupon 設定
2. 設置 **Eshop Product Group**
3. 確認 **Eshop Product Type** = "Product Group Item"
4. Active Coupon
5. 確認前台顯示邏輯

---

## 7. Coupon Entitlement 設定

### 7.1 數量限定功能

**Entitlement 欄位用途：**
- 📊 **限定 Coupon 可以派幾多張**
- 🎯 **控制派發總量**
- 👥 **設定每人限領數量**

**設定考量：**
- Campaign 總預算
- 每人限領數量
- Coupon 類型（Freebie vs Discount）

---

## 8. Deep Link Creation

### 8.1 Deep Link 設定步驟

**Step 1: 啟用 Deep Link**
- ✅ **Tick "Create Deep Link"**

**Step 2: 選擇 Link 類型**

| Link 類型 | 說明 | 使用情況 |
|---|---|---|
| **Public** | 淨係 generate 一條 Link | 通用推廣連結 |
| **Individual** | Unique Link（每人一條） | 個人化優惠連結 |

**Step 3: 設定數量**
- 🔢 **決定需要幾多數量**
- 📊 **按 Target Audience 大小**

**Step 4: 生成連結**
- 🔗 **Gen Link 成 QR Code**
- 📱 **比佢客戶使用**
- ✅ **自己試拎一次先**

---

## 9. User Favour Batch Operations

### 9.1 批量 Coupon 操作功能

**功能位置：** User Favour Batch Operation

**主要功能：**
- 🔄 **批量轉 Coupon Status**
- 📅 **批量設置起始/終結時間**
- 📊 **批量處理多個 Member**

---

## 10. Coupon Batch Operations 詳細步驟

### 10.1 Expire - 過期 Coupon 處理

**操作目的：** 將 Del Coupon/轉做 Used 嗰堆 Member ID 批量處理

**操作步驟：**

1. **準備 CSV 檔案**
   - 📄 **整理需要過期的 Member ID**
   - 📊 **儲存成 CSV 格式**

2. **初始化操作**
   - 前往 **Coupon Batch Operation**
   - 選擇 **"Expire"** 功能
   -塞入 **CSV 檔案**
   - 選擇 **Brand**
   - 選擇 **Coupon**
   - 按 **「Initialize」**

3. **設定日期條件**
   - 📅 **要填日子嗰堆係 OR option**
   - 🎯 **選 "Active On" 填寫**
   - 📝 **例子：Coupon 係 2026年3月1日生效** → 寫「3月1日」
   - ⏰ **時間無關係**

4. **完成操作**
   - 寫 **Remark**
   - 按 **「Execute」**

**重要提示：**
- ❗ **Use Expire Before 呢個 Logic 唔會搵埋張 Coupon 係咪 Active 緊**
- ✅ **只係按日期條件處理**

### 10.2 Used - 轉做已使用處理

**操作目的：** 將 Coupon 狀態轉做 "Used"

**操作步驟：**

1. **準備 CSV 檔案**
   - 📄 **整理需要轉做 Used 的 Member ID**
   - 📊 **儲存成 CSV 格式**

2. **初始化操作**
   - 前往 **Coupon Batch Operation**
   - 選擇 **"Used"** 功能
   - 塞入 **CSV 檔案**
   - 選擇 **Brand**
   - 選擇 **Coupon**
   - 按 **「Initialize」**

3. **設定日期條件**
   - 📅 **要填日子嗰堆係 OR option**
   - 🎯 **選其中一個填寫**
   - 📝 **例子：**
     - Active On 係 2026年3月1日
     - 如有幾張 Coupon 係 2026年3月31日
     - 可以揀其中一個日期填寫

4. **完成操作**
   - 寫 **Remark**
   - 按 **「Execute」**

### 10.3 Dispatch - 重新派發 Coupon

**操作目的：** 派發自帶起始時間的 Coupon

**操作步驟：**

1. **準備 CSV 檔案**
   - 📄 **整理需要收到 Coupon 的 Member ID**
   - 📊 **儲存成 CSV 格式**

2. **初始化操作**
   - 前往 **Coupon Batch Operation**
   - 選擇 **"Dispatch"** 功能
   - Upload **Member ID CSV**
   - 選擇 **Brand**
   - 選擇 **Coupon**
   - 按 **「Initialize」**

3. **設定時間**
   - 📅 **選新的開始時間**
   - 📅 **選新的結束時間**
   - ⏰ **按 Campaign 需要設定**

4. **完成操作**
   - 寫 **Remark**
   - 按 **「Execute」**

### 10.4 Update - 更新 Coupon 設定

**操作目的：** 修改已派發的 Coupon 設定

**使用情況：**
- 派左兩張 Coupon，要收起一張
- 修改 Coupon 有效期
- 調整 Coupon 數量

**操作步驟：**

1. **準備 CSV 檔案**
   - 📄 **整理需要更新的 Member ID**
   - 📊 **儲存成 CSV 格式**

2. **初始化操作**
   - 前往 **Coupon Batch Operation**
   - 選擇 **"Update"** 功能
   - Upload **Member ID CSV**
   - 選擇 **Brand**
   - 選擇 **Coupon**
   - 按 **「Initialize」**

3. **修改設定**
   - 調整需要更改的欄位
   - 設定新的時間/數量

4. **完成操作**
   - 寫 **Remark**
   - 按 **「Execute」**

---

## 11. Trigger Rules 重要設定

### 11.1 Birthday Point Bonus Trigger Rule

**功能：** 1個月 Birthday Point Bonus

**設定注意：**
- 🆕 **有新店要 Check Trigger Rule 裡面加新店**
- 📍 **確保所有新店都加入 Trigger Rule**
- 🎯 **避免遺漏新店會員**

**檢查清單：**
- [ ] 確認所有新店都已加入 Trigger Rule
- [ ] 測試 Birthday Point Bonus 派發
- [ ] 確認不同會員級別的設定

---

## 12. 操作最佳實踐

### 12.1 Coupon 派發前檢查

**檢查清單：**
- [ ] 確認 Coupon Type 正確
- [ ] 核對 Target Audience
- [ ] 驗證 Dispatch on Join 設定
- [ ] 檢查 Braze 整合設定
- [ ] 確認 Tier Card 互動邏輯
- [ ] 測試 Deep Link (如適用)

### 12.2 批量操作前準備

**準備工作：**
- [ ] 備份相關 Member ID 資料
- [ ] 驗證 CSV 檔案格式
- [ ] 確認操作權限
- [ ] 準備 Rollback 方案

### 12.3 Branded App 設定驗證

**驗證項目：**
- [ ] Brand Profile 已啟用
- [ ] 背景圖已上傳
- [ ] T&C 已填寫三種語言
- [ ] App IDs 已正確設置
- [ ] 前台顯示正常

---

**最後更新**：2026-07-17
**資料狀態**：已確認操作筆記整理
**適用角色**：Account Servicing、Marketing、營運人員