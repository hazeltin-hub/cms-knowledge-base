# CMS 公司品牌管理指南

## 標簽
#user-guide #company #brand #shop #beginner

## 概述

本文檔介紹如何管理 Storellet CMS 的組織架構，包括公司、組（品牌）和店鋪的管理。

---

## 🏢 訪問公司管理

### 步驟 1：進入公司管理頁面

1. 登錄 CMS 系統
2. 點擊頂部導航的**"公司"**或**"Company"**
3. 系統會跳轉到公司管理首頁
   ```
   URL: /cms/company
   ```

### 步驟 2：查看公司列表

頁面會顯示：
- 公司總數
- 公司列表
- 排序選項

---

## 🏢 所有公司（All Companies）

### 什麼是公司

公司（Company）是 CMS 組織架構的頂層，代表一個企業或組織。每個公司可以有多個組（Group/品牌）。

### 查看公司列表

訪問路徑：點擊左側菜單 **"All Companies"**

顯示所有公司的表格視圖：

| 列名 | 說明 | 排序 |
|------|------|------|
| **ID** | 公司唯一標識符 | ✅ 可排序 |
| **Name** | 公司全名 | ✅ 可排序 |
| **Join Date** | 公司加入系統的日期（格式：日 月 年） | ✅ 可排序 |
| **Status** | 公司當前狀態（Active/Inactive） | ✅ 可排序 |
| **Edit** | 編輯按鈕 | ❌ 不可排序 |

### 表格功能

#### 篩選功能
- **Company 下拉菜單**：默認顯示 "Show All"
- 可按公司名稱或其他條件篩選

#### 排序功能
- 點擊列標題進行排序
- 支持升序/降序切換
- 排序圖標：↑ 升序，↓ 降序

#### 操作按鈕
- **Add New**（右上角）：創建新公司
- **Edit**（每行）：編輯對應公司

### 創建公司

#### 步驟 1：點擊 Add New

1. 在公司列表頁面右上角
2. 點擊藍色的 **"Add New"** 按鈕
3. 系統會顯示公司創建表單

#### 步驟 2：填寫公司信息

表單字段：

| 字段名稱 | 字段類型 | 必填 | 說明 |
|----------|----------|------|------|
| **Name** | 文本輸入 | ✅ | 公司全名 |
| **Join Date** | 日期選擇器 | ✅ | 公司加入日期 |
| **Status** | 下拉菜單/單選 | ✅ | Active（啟用）/ Inactive（停用） |

**自動生成字段**：
- **ID**：系統自動生成，不可編輯
- **創建時間**：系統自動記錄

#### 步驟 3：保存公司

1. 填寫完所有必填字段
2. 點擊 **"Save"** 或 **"Submit"** 按鈕
3. 系統會驗證並保存公司信息
4. 返回公司列表，新公司會顯示在列表中

### 編輯公司

#### 步驟 1：選擇要編輯的公司

1. 在公司列表中找到要編輯的公司
2. 點擊該公司行的 **"Edit"** 按鈕

#### 步驟 2：修改公司信息

編輯表單字段：

| 字段名稱 | 可編輯 | 說明 |
|----------|--------|------|
| **Name** | ✅ | 可修改公司名稱 |
| **Join Date** | ✅ | 可修改加入日期 |
| **Status** | ✅ | 可修改公司狀態 |
| **ID** | ❌ | 不可編輯（系統生成） |

#### 步驟 3：保存修改

1. 修改所需字段
2. 點擊 **"Save"** 按鈕
3. 系統會更新公司信息
4. 返回公司列表，修改後的信息會立即顯示

### 排序功能

支持按以下字段排序：
- **ID**：按公司 ID 排序
- **名稱**：按公司名稱排序
- **加入日期**：按加入日期排序
- **狀態**：按狀態排序

**排序方式**：
- 升序（A→Z，1→10）
- 降序（Z→A，10→1）

### 創建公司

#### 步驟 1：點擊新建

1. 在公司列表頁面
2. 點擊**"新建公司"**或**"Add"**
   ```
   URL: /cms/company/0 (or /cms/company/{id} with id <= 0)
   ```

#### 步驟 2：填寫公司信息

**基本信息**：
- **公司名稱**：輸入公司的全稱
- **加入日期**：選擇公司加入系統的日期
- **狀態**：
  - `1` = 啟用
  - `0` = 禁用
- **創建日期**：默認當前時間

#### 步驟 3：保存公司

1. 點擊**"保存"**或**"Submit"** (operation=submit)
   ```
   URL: /cms/company/{id} (POST with opt=submit)
   ```
2. 系統會創建公司

### 編輯公司

1. 在公司列表中找到要編輯的公司
2. 點擊公司 ID 進入編輯頁面
   ```
   URL: /cms/company/{id}
   ```
3. 修改公司信息
4. 點擊**"保存"**

**注意事項**：
- ✅ 可以修改公司名稱
- ✅ 可以更改公司狀態
- ⚠️ 禁用公司會影響所有關聯的品牌和店鋪

---

## 🏷️ 公司組（Company Groups）

### 訪問公司組管理

1. 在公司管理頁面左側菜單
2. 點擊**"Company Groups"**
3. 系統會顯示所有公司組
   ```
   URL: /cms/company/group
   ```

### 查看公司組列表

顯示所有公司組的表格視圖：

| 列名 | 說明 | 排序 |
|------|------|------|
| **ID** | 組唯一標識符 | ✅ 可排序 |
| **Name** | 組/品牌名稱 | ✅ 可排序 |
| **Company** | 所屬公司名稱 | ✅ 可排序 |
| **Status** | 組狀態（Active/Inactive） | ✅ 可排序 |
| **Edit** | 編輯按鈕 | ❌ 不可排序 |

### 表格功能

#### 篩選功能
- **Company 下拉菜單**：默認顯示 "Show All"
- 可按公司名稱或其他條件篩選

#### 排序功能
- 點擊列標題進行排序
- 支持升序/降序切換
- 排序圖標：↑ 升序，↓ 降序

#### 操作按鈕
- **Add New**（右上角）：創建新公司組
- **Edit**（每行）：編輯對應公司組

### 創建公司組

#### 步驟 1：點擊 Add New

1. 在公司組列表頁面右上角
2. 點擊藍色的 **"Add New"** 按鈕
3. 系統會顯示公司組創建表單
   ```
   URL: /cms/company/group/0
   ```

#### 步驟 2：填寫基本信息

**基本設置部分**：

| 字段名稱 | 字段類型 | 必填 | 說明 |
|----------|----------|------|------|
| **Group Name** | 文本輸入 | ✅ | 組/品牌名稱 |
| **Company** | 下拉菜單 | ✅ | 選擇所屬公司 |
| **Status** | 下拉菜單/單選 | ✅ | Active（啟用）/ Inactive（停用） |

**自動生成字段**：
- **ID**：系統自動生成，不可編輯
- **創建時間**：系統自動記錄
- **更新時間**：系統自動記錄

#### 步驟 3：配置技術設置（可選）

**忠誠度引擎設置**：
- 配置積分系統相關參數
- 設置會員等級規則
- 配置積分過期規則

**促銷引擎設置**：
- 配置優惠券系統參數
- 設置促銷活動規則
- 配置折扣計算邏輯

**電子收據設置**：
- 啟用/禁用電子收據功能
- 配置收據格式
- 設置發送選項

#### 步驟 4：保存公司組

1. 填寫完所有必填字段
2. 配置所需技術設置
3. 點擊 **"Save"** 或 **"Submit"** 按鈕
4. 系統會驗證並保存公司組信息
5. 返回公司組列表，新組會顯示在列表中

### 編輯公司組

#### 步驟 1：選擇要編輯的公司組

1. 在公司組列表中找到要編輯的組
2. 點擊該組行的 **"Edit"** 按鈕
   ```
   URL: /cms/company/group/{id}
   ```

#### 步驟 2：修改公司組信息

**可編輯字段**：

| 字段名稱 | 可編輯 | 說明 |
|----------|--------|------|
| **Group Name** | ✅ | 可修改組名稱 |
| **Company** | ⚠️ | 可修改所屬公司（需謹慎操作） |
| **Status** | ✅ | 可修改組狀態 |
| **技術設置** | ✅ | 可修改所有技術配置 |
| **ID** | ❌ | 不可編輯（系統生成） |

#### 步驟 3：保存修改

1. 修改所需字段
2. 點擊 **"Save"** 按鈕
3. 系統會更新公司組信息
4. 返回公司組列表，修改後的信息會立即顯示

### 公司組狀態管理

#### 狀態類型

根據 Group.java 模型，系統支持以下狀態：

| 狀態 | 常量值 | 顯示名稱 | 說明 |
|------|--------|----------|------|
| **啟用** | status_active = 0 | Active | 組正常運行 |
| **停用** | status_inactive = 1 | Inactive | 組已停用 |
| **暫停** | status_suspend = 2 | Suspend | 組暫停使用 |

#### 啟用公司組

1. 打開公司組編輯頁面
2. 將狀態設為 **Active**
3. 點擊**"保存"**

**啟用後**：
- ✅ 用戶可以注冊
- ✅ 積分和優惠券功能正常
- ✅ 所有服務可用

#### 停用公司組

1. 打開公司組編輯頁面
2. 將狀態設為 **Inactive**
3. 點擊**"保存"**

**停用後**：
- ⚠️ 新用戶無法注冊
- ⚠️ 積分和優惠券功能暫停
- ⚠️ 用戶無法訪問
- ✅ 歷史數據保留

### 技術配置選項

#### 基本配置
- **積分比例** (pointRatio)：設置積分兌換比例
- **會員限制** (memberLimit)：設置會員數量上限
- **等級** (grade)：組等級（標準/白金）

#### 付款參數
- Stripe 集成設置
- 服務費用配置
- 貨幣代碼設置

#### 自定義參數
- 電子郵件需求設置
- 地區限制配置
- 新聞訂閱選項

### 數據結構分析

基於 Group.java 模型，公司組包含以下核心數據：

**核心字段**：
```java
private int id;                    // 組 ID
private String name;               // 組名稱
private String nameZh;             // 中文名稱
private int companyId;             // 所屬公司 ID
private int status;                // 狀態
private Long createDate;           // 創建日期
private Long lastUpdateDate;       // 最後更新日期
private String lastUpdateBy;       // 最後更新者
```

**配置字段**：
```java
private String logo;               // Logo 圖片
private String backgroundImage;    // 背景圖片
private String description;        // 描述
private String pointRatio;         // 積分比例
private Integer grade;             // 等級
private Integer memberLimit;       // 會員限制
```

**技術參數**：
```java
private Map<String, Object> paymentParams;  // 付款參數
private Map<String, Object> customParams;   // 自定義參數
private Integer userPointExpiryType;        // 積分過期類型
```

---

## 🏷️ 品牌管理（Brands）

### 訪問品牌管理

1. 在公司管理頁面左側菜單
2. 點擊**"Brands"**
3. 系統會顯示所有品牌
   ```
   URL: /cms/company/brand
   ```

### 查看品牌列表

顯示所有品牌的表格視圖：

| 列名 | 說明 | 排序 |
|------|------|------|
| **ID** | 品牌唯一標識符 | ✅ 可排序 |
| **Name** | 品牌名稱 | ✅ 可排序 |
| **Logo** | 品牌 Logo 圖片縮略圖 | ❌ 不可排序 |
| **Group** | 所屬公司組名稱 | ✅ 可排序 |
| **Status** | 品牌狀態（Active/Inactive） | ✅ 可排序 |
| **Edit** | 編輯按鈕 | ❌ 不可排序 |

### 表格功能

#### 篩選功能
- **Group 下拉菜單**：按公司組篩選品牌
- **Status 篩選**：按狀態篩選
- **關鍵詞搜索**：搜索品牌名稱

#### 排序功能
- 點擊列標題進行排序
- 支持升序/降序切換

#### 操作按鈕
- **Add New**（右上角）：創建新品牌
- **Edit**（每行）：編輯對應品牌

### 創建品牌

#### 步驟 1：點擊 Add New

1. 在品牌列表頁面右上角
2. 點擊藍色的 **"Add New"** 按鈕
3. 系統會顯示品牌創建表單
   ```
   URL: /cms/company/brand/0
   ```

#### 步驟 2：填寫基本信息

**基本設置部分**：

| 字段名稱 | 字段類型 | 必填 | 說明 |
|----------|----------|------|------|
| **Brand Name** | 文本輸入 | ✅ | 品牌名稱 |
| **Brand Name (中文)** | 文本輸入 | ❌ | 品牌中文名稱 |
| **Group** | 下拉菜單 | ✅ | 選擇所屬公司組 |
| **Status** | 下拉菜單 | ✅ | Active（啟用）/ Inactive（停用）/ Invisible（不可見） |
| **Display Sequence** | 數字輸入 | ❌ | 顯示順序 |

**Logo 和圖片**：
- **Logo**：上傳品牌 Logo 圖片
- **Background Image**：背景圖片
- **Cover**：封面圖片

**聯系信息**：
- **CS Email**：客戶服務郵箱
- **Info URL**：資訊頁面 URL
- **Info URL (中文)**：資訊頁面中文 URL

#### 步驟 3：配置品牌設置

**積分設置**：
- **Point Ratio**：積分兌換比例
- **Max Earn Per Day**：每日最大積分獲取限制
- **Max Earn Per Week**：每週最大積分獲取限制
- **Max Earn Per Day For POS**：POS 每日最大積分限制
- **Max Earn Per Week For POS**：POS 每週最大積分限制

**顯示設置**：
- **Category**：品牌分類
- **Color**：品牌顏色設置
- **Code**：品牌代碼
- **Tab**：標籤頁設置

**時間設置**：
- **Join Date**：加入日期
- **Expiry Date**：到期日期
- **Create Date**：創建日期（自動生成）
- **Last Update Date**：最後更新日期（自動生成）

#### 步驟 4：配置高級設置（可選）

**二維碼設置**：
- **QR Encryption Key**：QR 加密密鑰
- **Display Code Type**：顯示碼類型

**交易信息設置**：
- **Close Transaction Message Above QR1**：QR 上方交易信息1
- **Close Transaction Message Above QR2**：QR 上方交易信息2
- **Close Transaction Message Below QR1**：QR 下方交易信息1
- **Close Transaction Message Below QR2**：QR 下方交易信息2

**品牌信息設置**：
- **Message 1**：品牌信息1
- **Message 2**：品牌信息2
- **Message 3**：品牌信息3
- **Message 1 (中文)**：品牌信息1（中文）
- **Message 2 (中文)**：品牌信息2（中文）
- **Message 3 (中文)**：品牌信息3（中文）

**推廣設置**：
- **Promotion Message**：推廣信息
- **Promotion Message (中文)**：推廣信息（中文）
- **Promoted**：是否推廣

#### 步驟 5：保存品牌

1. 填寫完所有必填字段
2. 配置所需設置
3. 點擊 **"Save"** 按鈕
4. 系統會驗證並保存品牌信息
5. 返回品牌列表，新品牌會顯示在列表中

### 編輯品牌

#### 步驟 1：選擇要編輯的品牌

1. 在品牌列表中找到要編輯的品牌
2. 點擊該品牌行的 **"Edit"** 按鈕
   ```
   URL: /cms/company/brand/{id}
   ```

#### 步驟 2：修改品牌信息

**可編輯字段**：

| 字段名稱 | 可編輯 | 說明 |
|----------|--------|------|
| **基本信息** | ✅ | 品牌名稱、Logo、狀態等 |
| **Group** | ⚠️ | 可修改所屬組（需謹慎操作） |
| **積分設置** | ✅ | 可修改所有積分相關設置 |
| **圖片** | ✅ | 可更新 Logo、背景圖、封面 |
| **ID** | ❌ | 不可編輯（系統生成） |
| **時間戳** | ❌ | 不可編輯（系統自動） |

#### 步驟 3：保存修改

1. 修改所需字段
2. 點擊 **"Save"** 按鈕
3. 系統會更新品牌信息
4. 返回品牌列表，修改後的信息會立即顯示

### 品牌狀態管理

#### 狀態類型

根據 Brand.java 模型，系統支持以下狀態：

| 狀態 | 常量值 | 顯示名稱 | 說明 |
|------|--------|----------|------|
| **啟用** | status_active = 0 | Active | 品牌正常運行 |
| **停用** | status_inactive = 1 | Inactive | 品牌已停用 |
| **不可見** | status_invisible = 3 | Invisible | 品牌不可見 |

#### 啟用品牌

1. 打開品牌編輯頁面
2. 將狀態設為 **Active**
3. 點擊**"保存"**

**啟用後**：
- ✅ 用戶可以查看品牌
- ✅ 積分和優惠券功能正常
- ✅ 所有服務可用

#### 停用品牌

1. 打開品牌編輯頁面
2. 將狀態設為 **Inactive**
3. 點擊**"保存"**

**停用後**：
- ⚠️ 用戶無法查看品牌
- ⚠️ 積分和優惠券功能暫停
- ⚠️ 品牌信息不可見
- ✅ 歷史數據保留

#### 設置為不可見

1. 打開品牌編輯頁面
2. 將狀態設為 **Invisible**
3. 點擊**"保存"**

**不可見後**：
- ⚠️ 品牌不會在用戶端顯示
- ✅ 管理員仍可在 CMS 中管理
- ✅ 數據和配置保留

### 品牌數據結構

基於 Brand.java 模型，品牌包含以下核心數據：

**核心字段**：
```java
private int id;                      // 品牌 ID
private String name;                 // 品牌名稱
private String nameZh;               // 中文名稱
private int groupId;                 // 所屬組 ID
private int displaySequence;         // 顯示順序
private int status;                  // 狀態
private Long createDate;             // 創建日期
private Long joinDate;               // 加入日期
private Long expiryDate;             // 到期日期
private Long lastUpdateDate;        // 最後更新日期
private String lastUpdateBy;          // 最後更新者
```

**圖片和媒體**：
```java
private String logo;                 // Logo 圖片
private String backgroundImage;      // 背景圖片
private String cover;                // 封面圖片
private List<String> thumbnails;     // 縮圖列表
```

**積分配置**：
```java
private String pointRatio;           // 積分比例
private int maxEarnPerDay;           // 每日最大獲取
private int maxEarnPerWeek;           // 每週最大獲取
private int maxEarnPerDayForPos;      // POS 每日限制
private int maxEarnPerWeekForPos;     // POS 每週限制
```

**聯系信息**：
```java
private String csEmail;              // 客服郵箱
private String url;                   // 品牌 URL
private String urlZh;                // 品牌 URL（中文）
private String infoUrl;              // 資訊 URL
private String infoUrlZh;            // 資訊 URL（中文）
```

**顯示配置**：
```java
private String category;             // 分類
private List<Map<String, String>> color;  // 顏色設置
private String code;                 // 品牌代碼
private Integer tab;                 // 標籤頁
```

**品牌信息**：
```java
private String message1;             // 品牌信息1
private String message2;             // 品牌信息2
private String message3;             // 品牌信息3
private String message1Zh;           // 品牌信息1（中文）
private String message2Zh;           // 品牌信息2（中文）
private String message3Zh;           // 品牌信息3（中文）
private String promotionMessage;     // 推廣信息
private String promotionMessageZh;   // 推廣信息（中文）
```

**交易配置**：
```java
private String closeTransactionMessageAboveQR1;   // QR 上方信息1
private String closeTransactionMessageAboveQR2;   // QR 上方信息2
private String closeTransactionMessageBelowQR1;   // QR 下方信息1
private String closeTransactionMessageBelowQR2;   // QR 下方信息2
```

**特殊功能**：
```java
private Integer byPasscode;           // 密碼繞過
private String qrEncryptionKey;       // QR 加密密鑰
private Integer displayCodeType;       // 顯示碼類型
private Boolean stampOnly;           // 僅印花
private Boolean isExternal;          // 外部品牌
private Boolean isShowBottomBar;     // 顯示底部欄
private boolean promoted;              // 推廣
```

---

## 🏷️ 組/品牌管理（Group/Brand）

### 什麼是組/品牌

組（Group）對應品牌（Brand），一個公司可以有多個品牌。每個品牌代表一個獨立的業務單元，擁有獨立的：
- 用戶數據
- 積分系統
- 優惠券系統
- 印花卡系統

### 訪問組管理

1. 在公司管理頁面
2. 點擊**"組"**或**"Group"**
3. 系統會顯示所有組
   ```
   URL: /cms/company/group
   ```

### 查看組列表

顯示所有組：

| 字段 | 說明 |
|------|------|
| **組 ID** | 組唯一標識 |
| **組名稱** | 組/品牌名稱 |
| **公司** | 所屬公司 |
| **積分比例** | 積分兌換比例 |
| **會員數量** | 該組的會員總數 |
| **狀態** | 啟用/禁用 |
| **操作** | 編輯 |

### 搜索組

**關鍵詞搜索**：
1. 在搜索框輸入關鍵詞
2. 系統會搜索：
   - 組名稱
   - 組 ID
3. 顯示匹配結果

### 排序功能

支持按以下字段排序：
- **ID**：按組 ID 排序
- **名稱**：按組名稱排序
- **積分比例**：按積分比例排序
- **公司**：按所屬公司排序
- **會員數量**：按會員數量排序
- **狀態**：按狀態排序

### 創建組

#### 步驟 1：點擊新建

1. 在組列表頁面
2. 點擊**"新建組"**或**"Add"**
   ```
   URL: /cms/company/group/0
   ```

#### 步驟 2：填寫組信息

**基本信息**：
- **組名稱**：輸入組/品牌的名稱
- **公司**：選擇所屬公司
- **積分比例**：設置積分兌換比例（例如：100 積分 = 1 元）
- **狀態**：
  - `1` = 啟用
  - `0` = 禁用

**高級設置**：
- **貨幣**：選擇組使用的貨幣
- **語言**：選擇默認語言
- **時區**：選擇時區

#### 步驟 3：保存組

1. 點擊**"保存"**
   ```
   URL: /cms/company/group/{id} (POST with opt=submit)
   ```
2. 系統會創建組

### 編輯組

1. 在組列表中找到要編輯的組
2. 點擊組 ID 進入編輯頁面
   ```
   URL: /cms/company/group/{id}
   ```
3. 修改組信息
4. 點擊**"保存"**

**可修改的信息**：
- ✅ 組名稱
- ✅ 積分比例
- ✅ 狀態
- ⚠️ 修改積分比例會影響積分計算

### 組的狀態管理

#### 啟用組

1. 打開組編輯頁面
2. 將狀態設為 **1**（啟用）
3. 點擊**"保存"**

**啟用後**：
- ✅ 用戶可以注冊
- ✅ 可以正常使用積分和優惠券
- ✅ 可以查看報表

#### 禁用組

1. 打開組編輯頁面
2. 將狀態設為 **0**（禁用）
3. 點擊**"保存"**

**禁用後**：
- ⚠️ 新用戶無法注冊
- ⚠️ 積分和優惠券功能暫停
- ⚠️ 用戶無法查看信息
- ✅ 歷史數據保留

---

## 🏪 店鋪管理（Shop）

### 什麼是店鋪

店鋪（Shop）屬於某個品牌，代表具體的實體店或線上店鋪。每個店鋪有獨立的：
- 店鋪設置和密碼
- 店鋪員工權限
- 交易數據記錄
- 地理位置信息
- 支付方式配置

### 訪問店鋪管理

1. 在公司管理頁面
2. 點擊**"店鋪"**或**"Shops"**
3. 系統會顯示所有店鋪
   ```
   URL: /cms/company/shop
   ```

### 查看店鋪列表

#### 表格結構

店鋪列表顯示以下字段：

| 字段 | 說明 | 可排序 |
|------|------|--------|
| **ID** | 店鋪唯一標識符 | ✅ 可排序 |
| **Name** | 店鋪名稱 | ✅ 可排序 |
| **Group** | 所屬公司組名稱 | ✅ 可排序 |
| **Brand** | 所屬品牌名稱 | ✅ 可排序 |
| **Status** | 店鋪狀態（Active/Inactive/Hidden） | ✅ 可排序 |
| **Edit** | 編輯按鈕 | ❌ 不可排序 |

### 表格功能

#### 篩選功能
- **Group 下拉菜單**：按公司組篩選店鋪
- **Brand 下拉菜單**：按品牌篩選店鋪
- **Status 篩選**：按狀態篩選
- **關鍵詞搜索**：搜索店鋪名稱或 ID

#### 排序功能
- 點擊列標題進行排序
- 支持升序/降序切換

#### 操作按鈕
- **Add New**（右上角）：創建新店鋪
- **Edit**（每行）：編輯對應店鋪

### 創建店鋪

#### 步驟 1：點擊 Add New

1. 在店鋪列表頁面右上角
2. 點擊藍色的 **"Add New"** 按鈕
3. 系統會顯示店鋪創建表單
   ```
   URL: /cms/company/shop/0
   ```

#### 步驟 2：填寫基本信息

**基本設置部分**：

| 字段名稱 | 字段類型 | 必填 | 說明 |
|----------|----------|------|------|
| **Shop Name** | 文本輸入 | ✅ | 店鋪名稱 |
| **Shop Name (中文)** | 文本輸入 | ❌ | 店鋪中文名稱 |
| **Brand** | 下拉菜單 | ✅ | 選擇所屬品牌 |
| **Status** | 下拉菜單 | ✅ | Active（啟用）/ Inactive（停用）/ Hidden（隱藏） |
| **Reference ID** | 文本輸入 | ❌ | 外部參考 ID |
| **Passcode** | 文本輸入 | ❌ | 店鋪密碼（用於 POS 系統） |

#### 步驟 3：填寫地址和聯系信息

**地址信息**：
- **Address**：店鋪英文地址
- **Address (中文)**：店鋪中文地址
- **District**：地區編碼
- **District Name**：地區名稱
- **District Name (中文)**：地區中文名稱
- **Region**：區域（例如：Hong Kong Island、Kowloon、New Territories）
- **Region (中文)**：區域中文名稱

**聯系信息**：
- **Telephone**：店鋪電話
- **Fax**：傳真號碼（可選）

#### 步驟 4：設置地理位置

**地理坐標**：
- **Longitude**：經度坐標（默認：114.2096478）
- **Latitude**：緯度坐標（默認：22.3156595）
- **Geo**：[經度, 緯度] 坐標數組

#### 步驟 5：設置營業信息

**營業時間**：
- **Opening Hours**：英文營業時間說明
- **Opening Hours (中文)**：中文營業時間說明
- 例如："Mon-Fri 10:00-22:00, Sat-Sun 09:00-23:00"

#### 步驟 6：配置技術參數（可選）

**支付配置**：
- **Payment Methods**：支持的支付方式列表
- 可選支付方式：現金、信用卡、電子支付等

**集成配置**：
- **External Queue Shop Code**：外部排隊系統店鋪代碼
- **POS Shop Code**：POS 系統店鋪代碼
- **Inline Branch ID**：Inline 預訂分支 ID

**自定義參數**：
- **Custom**：自定義 JSON 參數對象
- **Key**：店鋪唯一密鑰
- **Default Show**：是否默認顯示

#### 步驟 7：保存店鋪

1. 填寫完所有必填字段
2. 配置所需設置
3. 點擊 **"Save"** 按鈕
4. 系統會驗證並保存店鋪信息
5. 返回店鋪列表，新店鋪會顯示在列表中

### 編輯店鋪

#### 步驟 1：選擇要編輯的店鋪

1. 在店鋪列表中找到要編輯的店鋪
2. 點擊該店鋪行的 **"Edit"** 按鈕
   ```
   URL: /cms/company/shop/{id}
   ```

#### 步驟 2：修改店鋪信息

**可編輯字段**：

| 字段名稱 | 可編輯 | 說明 |
|----------|--------|------|
| **基本信息** | ✅ | 店鋪名稱、品牌、狀態等 |
| **地址信息** | ✅ | 可修改所有地址相關字段 |
| **聯系信息** | ✅ | 可更新電話、傳真 |
| **地理位置** | ✅ | 可修改坐標 |
| **營業時間** | ✅ | 可修改營業時間說明 |
| **Brand** | ⚠️ | 可修改所屬品牌（需謹慎操作） |
| **ID** | ❌ | 不可編輯（系統生成） |
| **時間戳** | ❌ | 不可編輯（系統自動） |

#### 步驟 3：保存修改

1. 修改所需字段
2. 點擊 **"Save"** 按鈕
3. 系統會更新店鋪信息
4. 返回店鋪列表，修改後的信息會立即顯示

### 店鋪狀態管理

#### 狀態類型

根據 Shop.java 模型，系統支持以下狀態：

| 狀態 | 常量值 | 顯示名稱 | 說明 |
|------|--------|----------|------|
| **啟用** | status_active = 0 | Active | 店鋪正常運作 |
| **停用** | status_inactive = 1 | Inactive | 店鋪已停用 |
| **隱藏** | status_hidden = 2 | Hidden | 店鋪隱藏不顯示 |

#### 啟用店鋪

1. 打開店鋪編輯頁面
2. 將狀態設為 **Active**
3. 點擊**"保存"**

**啟用後**：
- ✅ 用戶可以查看店鋪
- ✅ 可以在店鋪進行交易
- ✅ 店鋪員工可以正常工作
- ✅ 顯示在應用店鋪列表中

#### 停用店鋪

1. 打開店鋪編輯頁面
2. 將狀態設為 **Inactive**
3. 點擊**"保存"**

**停用後**：
- ⚠️ 用戶無法查看店鋪
- ⚠️ 無法在店鋪進行新交易
- ⚠️ 店鋪員工無法登錄
- ✅ 歷史交易數據保留
- ✅ 可隨時重新啟用

#### 隱藏店鋪

1. 打開店鋪編輯頁面
2. 將狀態設為 **Hidden**
3. 點擊**"保存"**

**隱藏後**：
- ⚠️ 店鋪不在用戶端顯示
- ✅ 管理員仍可在 CMS 中管理
- ✅ 數據和配置保留
- ✅ 仍在后台運行但不對用戶可見

### 店鋪數據結構

基於 Shop.java 模型，店鋪包含以下核心數據：

**核心字段**：
```java
private int id;                      // 店鋪 ID
private int brandId;                 // 所屬品牌 ID
private String referenceId;          // 外部參考 ID
private String name;                 // 店鋪名稱
private String nameZh;               // 店鋪中文名稱
private int status;                  // 狀態
private Long createDate;             // 創建日期
private Long lastUpdateDate;        // 最後更新日期
private String lastUpdateBy;          // 最後更新者
```

**地址和位置**：
```java
private String address;              // 英文地址
private String addressZh;            // 中文地址
private Integer district;            // 地區編碼
private String districtName;         // 地區名稱
private String districtNameZh;       // 地區中文名稱
private String region;               // 區域
private String regionZh;             // 區域（中文）
private List<Double> geo;            // [經度, 緯度] 坐標
```

**聯系信息**：
```java
private String tel;                  // 電話
private String fax;                  // 傳真
private String passcode;             // 店鋪密碼
```

**營業信息**：
```java
private String openingHours;         // 英文營業時間
private String openingHoursZh;       // 中文營業時間
```

**技術參數**：
```java
private String key;                  // 店鋪密鑰
private Map<String, Object> custom;  // 自定義參數
private Boolean defaultShow;         // 默認顯示
private List<PaymentMethod> paymentMethods;  // 支付方式
private Multilingual route;          // 多語言路由
```

**集成代碼**：
```java
private String externalQueueShopCode;  // 外部排隊系統代碼
private String posShopCode;            // POS 系統代碼
private String inlineBranchId;         // Inline 預訂分支 ID
```

**計算字段**：
```java
private Integer distanceInMeter;      // 距離（米）
public double getLongitude()          // 經度（從 geo 獲取）
public double getLatitude()           // 緯度（從 geo 獲取）
```

---

## 🌟 特色項目（Featured Items）

### 什麼是特色項目

特色項目（Featured Items）用於在應用首頁展示推薦的促銷活動、品牌或店鋪。特色項目支持：
- 時段控制（開始/結束時間）
- 優先級排序
- 品牌關聯
- 多語言圖片
- 跳轉鏈接

### 訪問特色項目

1. 在公司管理頁面
2. 點擊**"特色項目"**或**"Featured Items"**
3. 系統會顯示所有特色項目
   ```
   URL: /cms/company/featuredItem
   ```

### 查看特色項目列表

#### 表格結構

特色項目列表顯示以下字段：

| 字段 | 說明 | 可排序 |
|------|------|--------|
| **ID** | 特色項目唯一標識符 | ✅ 可排序 |
| **Campaign Name** | 活動/項目名稱 | ✅ 可排序 |
| **Image** | 項目圖片縮略圖 | ❌ 不可排序 |
| **Brand** | 關聯品牌名稱 | ✅ 可排序 |
| **Section** | 屬示區域/分類 | ✅ 可排序 |
| **Priority** | 優先級順序 | ✅ 可排序 |
| **Start Date** | 開始日期 | ✅ 可排序 |
| **End Date** | 結束日期 | ✅ 可排序 |
| **Edit** | 編輯按鈕 | ❌ 不可排序 |

### 表格功能

#### 篩選功能
- **Brand 下拉菜單**：按品牌篩選特色項目
- **Section 下拉菜單**：按區域/分類篩選
- **關鍵詞搜索**：搜索活動名稱或 ID

#### 排序功能
- 點擊列標題進行排序
- 支持升序/降序切換
- 常用排序：按 Priority（優先級）、Start Date（開始日期）

#### 操作按鈕
- **Add New**（右上角）：創建新特色項目
- **Edit**（每行）：編輯對應特色項目

### 創建特色項目

#### 步驟 1：點擊 Add New

1. 在特色項目列表頁面右上角
2. 點擊藍色的 **"Add New"** 按鈕
3. 系統會顯示特色項目創建表單
   ```
   URL: /cms/company/featuredItem/0
   ```

#### 步驟 2：填寫基本信息

**基本設置部分**：

| 字段名稱 | 字段類型 | 必填 | 說明 |
|----------|----------|------|------|
| **Campaign Name** | 文本輸入 | ✅ | 活動/項目名稱 |
| **Brand** | 下拉菜單 | ✅ | 選擇關聯品牌 |
| **Section** | 文本輸入 | ❌ | 屬示區域/分類（例如：home、campaign） |
| **Link** | 文本輸入 | ✅ | 點擊跳轉鏈接（例如：campaign://123） |

**時段設置**：
- **Start Date/Time**：設置特色項目開始顯示的時間
- **End Date/Time**：設置特色項目結束顯示的時間
- 時間格式：YYYY-MM-DD HH:mm

**優先級設置**：
- **Priority**：數字越小優先級越高（例如：1, 2, 3...）
- 相同優先級按創建時間排序

#### 步驟 3：上傳圖片

**圖片設置**：
- **Image (English)**：上傳英文版特色項目圖片
- **Image (中文)**：上傳中文版特色項目圖片

**圖片要求**：
- 建議尺寸：1080x1080 像素（正方形）
- 或 1080x1920 像素（豎版）
- 支持格式：JPEG、PNG
- 文件大小：不超過 5MB
- 建議使用高質量圖片以獲得最佳展示效果

#### 步驟 4：時段和優先級配置（可選）

**時段控制**：
1. 選擇開始日期和時間
2. 選擇結束日期和時間
3. 系統會在該時段內顯示特色項目
4. 如不設置，默認永久顯示

**優先級說明**：
- Priority = 1：最高優先級，會顯示在最前面
- Priority = 2：次高優先級
- Priority = 3、4、5...：依此類推
- 相同 Priority 按創建時間排序

#### 步驟 5：保存特色項目

1. 填寫完所有必填字段
2. 上傳所需圖片
3. 配置時段和優先級
4. 點擊 **"Save"** 按鈕
5. 系統會驗證並保存特色項目信息
6. 返回特色項目列表，新項目會顯示在列表中

### 編輯特色項目

#### 步驟 1：選擇要編輯的特色項目

1. 在特色項目列表中找到要編輯的項目
2. 點擊該項目行的 **"Edit"** 按鈕
   ```
   URL: /cms/company/featuredItem/{id}
   ```

#### 步驟 2：修改特色項目信息

**可編輯字段**：

| 字段名稱 | 可編輯 | 說明 |
|----------|--------|------|
| **基本信息** | ✅ | 活動名稱、品牌、區域等 |
| **圖片** | ✅ | 可更新英文和中文圖片 |
| **鏈接** | ✅ | 可修改跳轉鏈接 |
| **時段** | ✅ | 可修改開始/結束時間 |
| **優先級** | ✅ | 可修改優先級順序 |
| **Brand** | ⚠️ | 可修改關聯品牌（需謹慎） |
| **ID** | ❌ | 不可編輯（系統生成） |

#### 步驟 3：保存修改

1. 修改所需字段
2. 點擊 **"Save"** 按鈕
3. 系統會更新特色項目信息
4. 返回特色項目列表，修改後的信息會立即顯示

### 特色項目管理

#### 時段管理

**設置有效時段**：
1. 打開特色項目編輯頁面
2. 設置 Start Date/Time
3. 設置 End Date/Time
4. 點擊**"保存"**

**時段效果**：
- ✅ 在時段內，項目會正常顯示
- ⚠️ 超過結束時間後，項目不再顯示
- ✅ 歷史數據保留，可修改時段重新啟用

**永久顯示**：
- 不設置開始和結束時間
- 項目會一直顯示到手動禁用或刪除

#### 優先級管理

**調整顯示順序**：
1. 編輯需要調順序的特色項目
2. 修改 Priority 數字
3. 數字越小，顯示位置越靠前
4. 點擊**"保存"**

**優先級建議**：
- 重要活動：Priority 1-5
- 普通活動：Priority 6-10
- 長期展示：Priority 11-20

#### 圖片管理

**更新圖片**：
1. 進入特色項目編輯頁面
2. 找到圖片上傳區域
3. 選擇新的圖片文件
4. 點擊上傳按鈕
5. 新圖片會替換舊圖片

**多語言圖片**：
- Image (English)：英文用戶看到的圖片
- Image (中文)：中文用戶看到的圖片
- 可根據語言設計不同的圖片內容

### 特色項目數據結構

基於 FeaturedItem.java 模型，特色項目包含以下核心數據：

**核心字段**：
```java
private String id;                  // 特色項目 ID（MongoDB ObjectId）
private String campaignName;         // 活動/項目名稱
private Integer brandId;            // 關聯品牌 ID
private String section;             // 屬示區域/分類
private Integer priority;           // 優先級順序
private String link;                // 跳轉鏈接
```

**時段控制**：
```java
private Long startDatetime;         // 開始時間（Unix timestamp）
private Long endDatetime;           // 結束時間（Unix timestamp）
```

**圖片資源**：
```java
private String img;                 // 英文版圖片 URL
private String imgZh;               // 中文版圖片 URL
```

**鏈接格式示例**：
- 活動頁面：`campaign://123`
- 品牌頁面：`brand://456`
- 店鋪頁面：`shop://789`
- 外部鏈接：`https://example.com`

**顯示邏輯**：
- 首先按 Priority（優先級）排序
- 相同 Priority 按創建時間排序
- 只顯示當前時間在 Start 和 End 之間的項目
- 根據用戶語言顯示對應的圖片（img 或 imgZh）

### 最佳實踐

#### 特色項目規劃

**數量建議**：
- ✅ 首頁建議 3-5 個特色項目
- ❌ 避免過多特色項目影響用戶體驗
- ✅ 定期更新保持新鮮感

**優先級設置**：
- ✅ 重要活動設置較小 Priority（1-5）
- ✅ 普通展示設置較大 Priority（6-10）
- ✅ 預留一些 Priority 數字供緊急插入

**時段設置**：
- ✅ 活動類項目設置明確的開始和結束時間
- ✅ 長期展示可設置較長時段或不設置
- ⚠️ 注意時區設置，確保時間正確

#### 圖片設計

**尺寸建議**：
- 正方形：1080x1080 像素
- 豎版：1080x1920 像素
- 避免使用橫版圖片

**內容建議**：
- 突出活動主題
- 包含清晰的文字說明
- 使用高對比度顏色
- 避免過於複雜的設計

**多語言處理**：
- 英文圖片：針對英文用戶設計
- 中文圖片：針對中文用戶設計
- 兩種語言可以有不同的設計風格

#### 鏈接設置

**內部鏈接**：
- 活動頁面：`campaign://{campaignId}`
- 品牌頁面：`brand://{brandId}`
- 店鋪頁面：`shop://{shopId}`

**外部鏈接**：
- 完整 URL：`https://example.com`
- 確保鏈接有效且可訪問
- 避免使用失效的鏈接

---

## 🖼️ 品牌圖片管理

### 什麼是品牌圖片

品牌圖片用於品牌在應用中的展示，包括：
- Logo
- 封面圖
- 促銷圖片

### 上傳品牌圖片

#### 步驟 1：進入圖片管理

1. 在品牌編輯頁面
2. 找到**"圖片管理"**部分
3. 系統會顯示已上傳的圖片

#### 步驟 2：上傳圖片

1. 點擊**"選擇圖片"**
2. 選擇圖片文件
3. 輸入圖片描述（可選）
4. 點擊**"上傳"**
   ```
   URL: /cms/company/brand/{brandId}/{imageName}
   ```

#### 圖片要求

**Logo**：
- 建議尺寸：512x512 像素
- 格式：PNG（支持透明背景）
- 大小：不超過 2MB

**封面圖**：
- 建議尺寸：1080x1920 像素
- 格式：JPEG、PNG
- 大小：不超過 5MB

### 刪除品牌圖片

1. 在圖片列表中找到要刪除的圖片
2. 點擊**"刪除"**
   ```
   URL: /cms/company/brand/{brandId}/{imageName} (DELETE)
   ```
3. 確認刪除

**注意事項**：
- ⚠️ 刪除圖片會影響正在使用該圖片的地方
- ⚠️ 刪除前確認沒有其他配置引用該圖片

---

## 🔗 組織架構關系

### 層級結構

CMS 的組織架構分為三層：

```
公司 (Company)
  └─ 組/品牌 (Group/Brand)
      └─ 店鋪 (Shop)
```

### 示例

**公司**：ABC 零售集團

**組/品牌**：
- Brand A（服裝品牌）
- Brand B（餐飲品牌）
- Brand C（美妝品牌）

**店鋪**：
- Brand A 下：
  - Store A1（中環店）
  - Store A2（銅鑼灣店）
- Brand B 下：
  - Store B1（尖沙咀店）

### 數據隔離

不同層級之間的數據隔離：

| 層級 | 隔離內容 |
|------|----------|
| **公司** | 完全獨立，所有數據隔離 |
| **組/品牌** | 用戶、積分、優惠券、印花卡獨立 |
| **店鋪** | 交易、員工、庫存獨立 |

---

## 🎯 最佳實踐

### 組織架構設計

#### 公司設置

**原則**：
- ✅ 一個企業實體 = 一個公司
- ✅ 避免創建過多公司
- ✅ 公司用於區分不同企業

#### 組/品牌設置

**原則**：
- ✅ 一個業務品牌 = 一個組
- ✅ 品牌之間需要數據獨立
- ✅ 不同會員體系使用不同組

**何時需要多個組**：
- 品牌完全獨立
- 不同的會員體系
- 不同的積分規則
- 不同的營銷活動

#### 店鋪設置

**原則**：
- ✅ 一個實體店 = 一個店鋪
- ✅ 線上店也可以創建為店鋪
- ✅ 店鋪用於區分交易和員工

### 命名規范

#### 公司命名

- ✅ 使用企業法定名稱
- ✅ 例如："ABC Retail Limited"
- ❌ 避免使用縮寫或代號

#### 組/品牌命名

- ✅ 使用品牌官方名稱
- ✅ 例如："BrandA"、"BrandB Premium"
- ❌ 避免使用模糊名稱

#### 店鋪命名

- ✅ 包含品牌 + 地區
- ✅ 例如："BrandA Central"、"BrandB TST"
- ❌ 避免使用編號

### 狀態管理

#### 啟用/禁用原則

**公司級別**：
- ⚠️ 禁用公司會禁用所有下屬品牌和店鋪
- ✅ 僅在公司完全停止運營時禁用

**組/品牌級別**：
- ✅ 品牌不再運營時禁用
- ✅ 數據保留可查看歷史

**店鋪級別**：
- ✅ 店鋪關閉時禁用
- ✅ 重新開張時重新啟用

---

## 🔧 常見問題

### Q: 如何修改公司名稱？

**A**：
1. 進入公司管理頁面
2. 找到要修改的公司
3. 點擊公司 ID 進入編輯頁面
4. 修改公司名稱
5. 點擊**"保存"**

### Q: 如何添加新品牌？

**A**：
1. 進入組管理頁面
2. 點擊**"新建組"**
3. 填寫品牌信息
4. 選擇所屬公司
5. 點擊**"保存"**

### Q: 如何查看某個品牌的所有店鋪？

**A**：
1. 進入店鋪管理頁面
2. 使用品牌篩選
3. 選擇要查看的品牌
4. 系統會顯示該品牌的所有店鋪

### Q: 禁用品牌後數據會丟失嗎？

**A**：
- ✅ 數據不會丟失
- ✅ 歷史數據完整保留
- ✅ 可以隨時重新啟用
- ⚠️ 禁用期間新功能暫停

### Q: 如何更改品牌的積分比例？

**A**：
1. 進入組管理頁面
2. 找到要修改的品牌
3. 點擊品牌 ID 進入編輯頁面
4. 修改積分比例
5. 點擊**"保存"**

**注意事項**：
- ⚠️ 修改積分比例會影響積分計算
- ⚠️ 已發放的積分不會重新計算
- ⚠️ 修改後新生效

### Q: 可以為一個品牌創建多個店鋪嗎？

**A**：
- ✅ 可以
- ✅ 沒有數量限制
- ✅ 每個店鋪獨立管理交易和員工

### Q: 如何刪除店鋪？

**A**：
1. 進入店鋪編輯頁面
2. 滾動到頁面底部
3. 點擊**"刪除"**
4. 確認刪除

**注意事項**：
- ⚠️ 刪除操作不可逆
- ⚠️ 歷史交易數據保留
- ⚠️ 店鋪員工會被移除

---

## 🎓 快速參考

### URL 速查

| 功能 | URL |
|------|-----|
| **公司列表** | `/cms/company` |
| **編輯公司** | `/cms/company/{id}` |
| **組列表** | `/cms/company/group` |
| **編輯組** | `/cms/company/group/{id}` |
| **店鋪列表** | `/cms/company/shop` |
| **編輯店鋪** | `/cms/company/shop/{id}` |
| **特色項目** | `/cms/company/featuredItem` |

### 狀態值

| 狀態 | 值 |
|------|-----|
| **啟用** | 1 |
| **禁用** | 0 |

---

**相關文檔**：
- [用戶管理指南](./user-management.md)
- [員工管理指南](./staff-management.md)
- [應用配置管理](./application-management.md)

**代碼參考**：
- [CompanyAction 代碼參考](../cms-code-reference/CompanyAction-reference.md)

---

# 🆕 Branded App 詳細設定指南

## Branded App 完整設定流程

### Step 1: 啟用 Brand Profile

**目的：** 啟用 Branded Profile 功能

**操作步驟：**
1. 前往 **Company > Brands**
2. 選擇目標 Brand
3. ✅ **Tick "Enable Brand Profile"**
4. 儲存後就會有 Branded Profile 顯示

**檢查：**
- [ ] Brand Profile 已啟用
- [ ] Branded Profile 區塊顯示正常

### Step 2: 設置背景圖

**設定位置：** Company > Brands > Branded App > Thumbnail

**操作步驟：**
1. 在 Branded App 區塊找到 **Thumbnail**
2. 📷 **上傳背景圖**
3. 儲存設定

**圖片建議：**
- 解析度：建議高解析度圖片
- 格式：JPG/PNG
- 大小：約 1MB（參考其他 Assets 模組）

### Step 3: 設置條款及細則

**設定位置：** Company > Brands > Branded App > Terms and Conditions

**要求：** 必須填寫三種語言版本

**語言版本：**
- 🇬🇧 **英文版本**
- 🇨🇳 **中文版本**
- 🌍 **其他語言版本**（按需要）

**操作步驟：**
1. 找到 **Terms and Conditions** 區塊
2. 填寫英文 T&C
3. 填寫中文 T&C
4. 如需要，填寫其他語言 T&C
5. 儲存設定

### Step 4: 設置簡介

**設定位置：** Company > Brands > Short Description (Local Language)

**操作步驟：**
1. 找到 **Short Description (Local Language)** 欄位
2. 📝 **填寫品牌簡介**
3. 儲存設定

**內容建議：**
- 品牌定位
- 核心特色
- 目標客群
- 品牌故事（簡短）

### Step 5: 設置 App IDs

**設定位置：** Company > Brands > Branded App

**需要的 App IDs：**
- 📱 **Android App ID** (AOS)
- 📱 **iOS App ID**

**操作步驟：**
1. 在 Branded App 區塊找到 App IDs 設定
2. 輸入 **Android App ID**
3. 輸入 **iOS App ID**
4. 儲存設定

**ID 來源：**
- Google Play Store URL (Android)
- Apple App Store URL (iOS)

---

## Branded App 類型選擇

### Non Storellet Only vs Storellet Only

| Brand 類型 | 設定選項 | 說明 | 適用 Brand |
|---|---|---|---|
| **自有 App** | Non Storellet Only | 使用自有 Brand App，非 Storellet 系統 | KFC、PHD |
| **Storellet App** | Storellet Only | 使用 Storellet App | 其他大部分 Brand |

**設定位置：** 在 Brand 設定頁面的 App 類型選項

**設定建議：**
- KFC/PHD → 選擇 **Non Storellet Only**
- 其他 Brand → 選擇 **Storellet Only**

---

## Brand 進階設定

### 人均消費上下限

**設定位置：** Brand > Lower Price & Higher Price

| 設定欄位 | 說明 | 用途 | 參考範圍 |
|---|---|---|---|
| **Lower Price** | 人均消費下限 | 設定最低消費金額參考 | 按品牌定位 |
| **Higher Price** | 人均消費上限 | 設定最高消費金額參考 | 按品牌定位 |

**操作步驟：**
1. 前往目標 Brand 設定頁面
2. 找到 **Lower Price** 欄位
3. 輸入適當金額
4. 找到 **Higher Price** 欄位
5. 輸入適當金額
6. 儲存設定

**使用情況：**
- 前台顯示人均消費範圍
- 會員分群參考
- 營商分析參考

---

## 操作檢查清單

### Branded App 設定檢查

- [ ] Brand Profile 已啟用
- [ ] 背景圖已上傳至 Thumbnail
- [ ] T&C 已填寫三種語言版本
- [ ] Short Description 已填寫
- [ ] Android App ID 已設置
- [ ] iOS App ID 已設置
- [ ] App 類型選擇正確（Non Storellet/Storellet）
- [ ] 前台顯示測試

### Brand 設定檢查

- [ ] Lower Price 已設定
- [ ] Higher Price 已設定

---

**最後更新**：2026-07-17
**適用角色**：系統管理員、運營人員
