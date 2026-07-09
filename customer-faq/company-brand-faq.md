# Company Brand 管理 FAQ

## 標簽
`#faq` `#company` `#brand` `#shop` `#group`

## 概述
本文檔收集Company Brand管理系統的常見問題，基於實際CMS操作和PPT教學材料整理。

---

## 🏢 公司相關問題

### Q1: 如何創建新公司？
**A**:
1. 登錄CMS系統
2. 點擊"Company" → "All Companies"
3. 點擊"Add New"按鈕
4. 填寫必填信息：
   - **Company Name** (必填): 公司註冊/內部公司名，例如"Crozz Limited"
   - **Join Date** (必填): 建立日期/合作開始日
   - **Status** (必填): 設為"Active"
5. 點擊"Save"

**系統自動生成**：
- Company ID、Create Date、Last Update Date、Last Update By

### Q2: 公司狀態有哪些？如何切換？
**A**:
- **Active**: 公司正常運作，所有功能可用
- **Inactive**: 公司已停用，功能暫停但數據保留

**切換方法**：
1. 進入公司編輯頁面
2. 修改Status字段
3. 點擊"Save"

### Q3: 公司和Group/Brand有什麼分別？
**A**:
- **Company**: 最頂層，代表一個企業實體
- **Group**: 公司下的部門/品牌組，一個公司可有多個Group
- **Brand**: Group下的具體品牌，一個Group可有多個Brand
- **Shop**: Brand下的分店，一個Brand可有多個Shop

**結構**: Company → Group → Brand → Shop

---

## 🏢 Company Groups 相關問題

### Q4: 如何創建新的Company Group？
**A**:
1. 進入"Company" → "Company Groups"
2. 點擊"Add New"
3. 填寫基本資訊：
   - **Group Name (English)** (必填): 英文group name
   - **Group Name (Local Language)** (必填): 中文group name
   - **Company** (必填): 選擇所屬公司
   - **Grade** (必填): 設為"Standard"
4. 上傳圖片：
   - **Group Logo** (建議必填): Merchant/Group logo
   - **Registration Image** (選填): 背景/註冊圖
5. 設置積分：
   - **Point Ratio** (必填): 例如"$1 = 1 point(s)"
   - **Member No. Limit** (必填): 設為"-1"(unlimited)
   - **CS App Point Limit** (必填): 設為"-1"
6. 添加T&C：
   - **Terms & Conditions (English)** (必填): HTML格式
   - **Terms & Conditions (Local Language)** (必填): HTML格式
7. 點擊"Save"

### Q5: Group的積分比例如何設置？
**A**:
- **Point Ratio** (必填): 必須以文字/數值形式輸入，例如"$1 = 1 point(s)"
- **Display Point Ratio** (選填): 前台顯示用，可留空

**注意**: 積分比例影響整個Group下所有品牌的積分計算。

### Q6: Enable Master Brand何時使用？
**A**:
- 當多個品牌共用tier card/coupon時使用
- 需要特別的品牌架構時啟用
- 一般情況保持untick

### Q7: Member No. Limit設置建議？
**A**:
- 建議設為**"-1"** (代表unlimited)
- 除非有特殊會員數量限制需求
- 影響Group可容納的會員總數

---

## 🏷️ Brands 相關問題

### Q8: 如何創建新品牌？
**A**:
1. 進入"Company" → "Brands"
2. 點擊"Add New"
3. 填寫基本資訊：
   - **Brand Name (English)** (必填): 英文品牌名
   - **Brand Name (Local Language)** (必填): 中文品牌名
   - **Brand Code** (必填): 商戶名英文首字母
   - **Group** (必填): 選擇所屬Group
   - **Display Sequence** (必填): 數字排序
   - **Tab** (必填): "0 = popular，1 = premium"
   - **Restaurant Category** (必填): 例如"Cafe"
4. 添加Tag：
   - **Tag** (建議必填): 品牌相關keyword
   - **Geo Tag** (選填): 地理tag
5. 上傳圖片：
   - **Brand Logo** (必填): 1:1 logo，建議1MB
   - **Background Image on Dashboard** (建議必填): 品牌背景圖，建議1MB
6. 設置時間：
   - **Join Date** (必填): 品牌開始日期
   - **Expiry Date** (必填): 品牌到期日
7. 配置積分限制：
   - **Max Point Earn Per Invoice** (必填): 每張單可賺最多積分，例如"99999"
   - **Max. Time of Earn Point per Day** (必填): 每日可賺積分次數上限，設為"999"
   - **Max. Time of Earn Point per Week** (必填): 每週可賺積分次數上限，設為"999"
   - **Max. Time of Earn Point per Day For POS** (必填): POS每日賺分次數上限，設為"1"
   - **Max. Time of Earn Point per Week For POS** (必填): POS每週賺分次數上限，設為"1"
8. 設置顏色：
   - **Background Colour 1/2/3** (視乎設計): App UI色系
   - **Text Colour 1/2/3** (視乎設計): App UI文字色
9. 添加聯絡資訊：
   - **Customer Service Email** (建議必填)
   - **Website (English)** (選填)
   - **Website (Local Language)** (選填)
10. 設置功能：
    - **Show Point Or Stamp on App** (建議必填): 設為"Yes"
    - **Enable Brand Profile** (建議必填): Tick
    - **Show Redemption Page on App** (視乎需要): 設為"Yes"
11. 點擊"Save"

### Q9: 品牌狀態Active/Inactive/Invisible有什麼區別？
**A**:
- **Active**: 品牌正常運作，前台可見
- **Inactive**: 品牌已停用，前台不可見但數據保留
- **Invisible**: 品牌隱藏，管理員仍可管理但用戶看不到

### Q10: Tab欄位如何設置？
**A**:
- **0**: Popular tab
- **1**: Premium tab
- 用於控制品牌在前台的分類顯示

### Q11: Max. Time of Earn Point設置建議？
**A**:
- **一般情況**:
  - Max. Time of Earn Point per Day: "999"
  - Max. Time of Earn Point per Week: "999"
- **POS情況**:
  - Max. Time of Earn Point per Day For POS: "1"
  - Max. Time of Earn Point per Week For POS: "1"
- **影響**: 控制會員每日/每週可賺積分的次數上限

### Q12: External Links如何配置？
**A**:
**格式**: Key、Sort、Text、Type、URL、Icon
- **Key**: 鏈接唯一標識
- **Sort**: 排序數字
- **Text**: 顯示文字
- **Type**: 鏈接類型
- **URL**: 目標URL
- **Icon**: 圖片(建議50×50)

### Q13: Coupon Code Display Type如何選擇？
**A**:
- **Member ID and Coupon ID**: 默認顯示方式
- 需跟POS redeem flow一致
- 影響優惠券碼在前台的顯示邏輯

### Q14: Enable Brand Profile何時使用？
**A**:
- **建議**: 一般情況下Tick
- **用途**: 啟用品牌頁面顯示
- **影響**: 如果app/web要見brand profile，必須啟用

---

## 🏪 Shops 相關問題

### Q15: 如何創建新分店？
**A**:
1. 進入"Company" → "Shops"
2. 點擊"Add New"
3. 填寫基本資訊：
   - **Shop Name (English)** (必填): 英文分店名
   - **Shop Name (Local Language)** (必填): 中文分店名
   - **Reference ID** (必填): 與merchant confirm/由001開始
   - **Brand** (必填): 選擇所屬品牌
4. 設置地區：
   - **Region (English)** (必填): Hong Kong Island/Kowloon/New Territories
   - **Region (Local Language)** (必填): 香港島/九龍/新界
   - **District (English)** (必填): 例如Kwun Tong
   - **District (Local Language)** (必填): 例如觀塘
5. 設置位置：
   - **Geo Location** (建議必填): 格式為"經度 - 緯度"
6. 填寫地址：
   - **Address (English)** (必填): 英文地址
   - **Address (Local Language)** (必填): 中文地址
7. 添加聯絡資訊：
   - **Telephone** (建議必填): 分店電話
   - **Fax** (選填): Fax number
   - **Opening Hours (English)** (建議必填): 例如"10:00 - 22:00"
   - **Opening Hours (Local Language)** (建議必填): 例如"10:00 - 22:00（星期一至日）"
8. 設置操作：
   - **Passcode** (視乎操作): 分店passcode
   - **Default Show** (視乎需要): Tick/Untick
   - **Status** (必填): 設為"Active"
9. 點擊"Save"

### Q16: Geo Location格式要求？
**A**:
- **格式**: "經度 - 緯度"
- **示例**: "114.2096478 - 22.3156595"
- **用途**: Google Map顯示位置
- **重要性**: 影響分店在地圖上的顯示準確性

### Q17: Reference ID如何設置？
**A**:
- **建議**: 如無特別要求由001開始
- **格式**: 數字，例如001, 002, 003
- **重要性**: 分店識別ID，需與merchant確認
- **注意**: 同一品牌下不應重複

### Q18: Region選項有哪些？
**A**:
- **Hong Kong Island** (香港島)
- **Kowloon** (九龍)
- **New Territories** (新界)
- **用途**: 前台分區顯示，分店列表tab分類

### Q19: Passcode什麼時候需要？
**A**:
- **需要**: 當分店需要特定passcode進行操作時
- **不需**: 如果沒有特殊操作驗證需求
- **重要性**: 需跟merchant/operation flow確認

---

## 🌟 Featured Items 相關問題

### Q20: 如何創建特色項目？
**A**:
1. 進入"Company" → "Featured Items"
2. 點擊"Add New"
3. 填寫基本資訊：
   - **Campaign Name** (必填): Campaign名稱
   - **Section** (必填): 選擇出現section
   - **Brand** (必填): 選擇所屬品牌
4. 上傳圖片：
   - **Image (English)** (必填): 英文圖片
   - **Image (Local Language)** (必填): 中文圖片(如同圖可重用)
5. 設置時間：
   - **Start Date** (必填): 顯示開始日(可早於campaign start date)
   - **End Date** (必填): 顯示結束日(需同campaign period對齊)
6. 設置排序：
   - **Priority** (必填): 數字，例如"-1"
7. 點擊"Save"

### Q21: Priority如何設置？
**A**:
- **數字越小**: 優先級越高
- **常用值**: "-1"為高優先級
- **重要性**: 需跟section的排序邏輯一致
- **影響**: 控制featured item在前台的顯示順序

### Q22: Section如何選擇？
**A**:
- **用途**: 控制featured item出現在哪個section
- **重要性**: 必須選擇正確的section
- **影響**: 決定featured item在前台的顯示位置

### Q23: Start Date和End Date如何設置？
**A**:
- **Start Date**: 可早於campaign start date
- **End Date**: 需同campaign period對齊
- **重要性**: 控制featured item的顯示期間
- **建議**: 配合實際活動時間設定

---

## 🔧 高級配置問題

### Q24: Carousel如何配置？
**A**:
**格式**: YouTube/Image、Sort、URL
- **YouTube**: 影片連結
- **Image**: 圖片URL
- **Sort**: 排序數字
- **URL**: 點擊後跳轉URL
- **用途**: 品牌頁carousel顯示

### Q25: Background Colour和Text Colour如何配置？
**A**:
**Colour 1**: 影響主要區域背景和文字
**Colour 2**: 影響button/label和相關文字
**Colour 3**: 影響內容區背景和文字

**注意**:
- 需留意對比度和readability
- 影響前台UI的色系
- 建議與品牌顏色一致

### Q26: Branded App相關fields何時使用？
**A**:
**Branded App專用fields**:
- **Branded App Link**: App連結
- **Thumbnails**: App縮圖
- **Branded App Terms and Conditions**: App T&C
- **Is Show Bottom Bar**: App底部欄顯示

**使用時機**: 只有當項目有Branded App時需要填寫

---

## 📱 前台顯示相關問題

### Q27: Tag和Geo Tag的用途？
**A**:
- **Tag**: 品牌相關keyword，搜尋時會命中brand
  - 建議加入品牌名、菜式、地區等
- **Geo Tag**: 地區搜尋/分類用
  - 視乎前台是否使用

### Q28: Short Description何時需要？
**A**:
- **需要**: 當品牌頁面有簡介顯示時
- **不需要**: 如果前台沒有相關顯示區域
- **建議**: 有前台顯示時填寫，可留空

### Q29: Recommendation Dishes的用途？
**A**:
- **用途**: 推介菜式
- **顯示位置**: recommendation section
- **重要性**: 前台品牌頁可見
- **格式**: 菜式名稱/描述

---

## ⚠️ 常見錯誤和注意事項

### Q30: 創建Brand時最常見的錯誤？
**A**:
1. **Tab設置錯誤**: 忘記設置0或1
2. **積分限制設置過低**: 影響正常積分獲取
3. **顏色對比度不足**: 影響前台可讀性
4. **忘記上傳Logo**: 影響品牌識別
5. **Join/Expiry Date設定錯誤**: 影響品牌有效期

### Q31: 創建Shop時最常見的錯誤？
**A**:
1. **Geo Location格式錯誤**: 不是"經度 - 緯度"格式
2. **忘記選擇正確的Brand**: 影響分店歸屬
3. **Region選擇錯誤**: 影響前台分類
4. **電話格式錯誤**: 影響用戶聯繫
5. **Status忘記設為Active**: 分店不會顯示

### Q32: Featured Items最常見的錯誤？
**A**:
1. **Priority設置錯誤**: 影響顯示順序
2. **Start/End Date時間錯誤**: 影響顯示期間
3. **忘記選擇Section**: featured item不會顯示
4. **圖片尺寸不符**: 影響顯示效果
5. **Brand選擇錯誤**: 影響歸屬和顯示

---

## 🎯 最佳實踐

### Q33: Brand創建的最佳順序？
**A**:
1. **先準備**: Logo、背景圖、品牌資料
2. **基本資訊**: 品牌名稱、代碼、所屬Group
3. **分類設置**: Tab、Category、Tag
4. **圖片上傳**: Logo、背景圖、其他圖片
5. **積分配置**: 各項積分限制
6. **聯絡資訊**: Email、Website
7. **功能設置**: 各項功能開關
8. **測試驗證**: 前台顯示檢查

### Q34: 如何確保所有必填fields都已完成？
**A**:
**檢查清單**:
- ✅ Company/Group/Brand名稱(英文和中文)
- ✅ 所屬上級關係正確
- ✅ 積分相關設定完成
- ✅ 圖片已上傳
- ✅ 時間設定正確
- ✅ Status設為Active
- ✅ 必要的聯絡資訊已填寫

### Q35: 創建完成後如何驗證？
**A**:
1. **檢查列表**: 新建項目是否出現在列表中
2. **前台驗證**: 在app/web檢查顯示
3. **功能測試**: 測試相關功能是否正常
4. **資料驗證**: 確認所有資料正確顯示

---

**最後更新**: 2026-07-09
**基於**: 實際CMS操作和PPT教學材料
**適用**: Storellet CMS Company Brand Management