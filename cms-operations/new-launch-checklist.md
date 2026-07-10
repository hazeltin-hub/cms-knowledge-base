# CMS 新上架流程 - Company Tab 必填位檢查清單

## 標簽
`#operation` `#workflow` `#launch` `#checklist` `#beginner`

## 概述
本文檔提供新品牌上架至Storellet CMS的完整流程，重點列出所有必填位和檢查要點，確保上架過程順利完成。

---

## 📋 上架前準備

### 📁 所需資料準備清單
- [ ] **公司資料**
  - [ ] 公司註冊名稱（中英文）
  - [ ] 合作開始日期
  - [ ] 公司營業執照/商業登記（如需要）

- [ ] **品牌資料**
  - [ ] 品牌名稱（中英文）
  - [ ] 品牌Logo（1:1，建議1MB以下）
  - [ ] 品牌背景圖（建議1MB以下）
  - [ ] 品牌商戶名稱（首字母代碼）
  - [ ] 品牌網站URL（如有）

- [ ] **分店資料**
  - [ ] 分店名稱（中英文）
  - [ ] 分店地址（中英文）
  - [ ] 分店電話
  - [ ] 分店營業時間
  - [ ] GPS坐標（經度-緯度）

- [ ] **營運資料**
  - [ ] 積分比例設定
  - [ ] 會員條款（T&C HTML格式）
  - [ ] 客戶服務email
  - [ ] 推廣資料（如有）

---

## 🚀 新上架流程步驟

### 步驟 1: 創建 Company (公司)

#### 🔵 必填位檢查清單

| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Company Name** | ✅ | 公司註冊名 | 例如：Crozz Limited |
| **Join Date** | ✅ | 合作開始日 | 格式：DD-MM-YYYY |
| **Status** | ✅ | Active | 上線必須設為Active |

#### 🟢 系統自動生成（無需填寫）
- Company ID
- Create Date
- Last Update Date
- Last Update By

#### ✅ 完成檢查
- [ ] 公司名稱正確無誤
- [ ] Join Date 準確
- [ ] Status 設為 Active
- [ ] 公司已成功出現在列表中

---

### 步驟 2: 創建 Company Group (公司組)

#### 🔵 必填位檢查清單

**基本信息**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Group Name (English)** | ✅ | 英文組名 | 建議與品牌命名一致 |
| **Group Name (Local Language)** | ✅ | 中文組名 | 客戶前台會見到 |
| **Company** | ✅ | 選擇所屬公司 | 必須選擇正確的公司 |
| **Grade** | ✅ | Standard | 如無特別要求用Standard |

**圖片資料**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Group Logo** | 建議必填 | Merchant/Group logo | 建議清晰logo，<2MB |

**積分設定**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Point Ratio** | ✅ | 例如：$1 = 1 point(s) | 必須以文字/數值形式輸入 |
| **Member No. Limit** | ✅ | -1 | -1代表unlimited |
| **CS App Point Limit** | ✅ | -1 | -1代表unlimited |

**條款設定**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Terms & Conditions (English)** | ✅ | HTML格式 | 適用於整個group |
| **Terms & Conditions (Local Language)** | ✅ | HTML格式 | 中文版條款 |

**營運設定**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Status** | ✅ | Active | 上線必須設為Active |

#### 🟡 重要選填位（建議填寫）
- **Enable Master Brand**: 多品牌共用時啟用
- **Email Needed**: 視乎註冊要求
- **Privacy Policy**: 如app/web需要顯示

#### ⚠️ 常見錯誤
- ❌ 忘記選擇正確的Company
- ❌ Point Ratio格式錯誤（必須文字格式）
- ❌ Member No. Limit不設為-1
- ❌ T&C不是HTML格式

#### ✅ 完成檢查
- [ ] Group歸屬正確的公司
- [ ] 積分比例格式正確
- [ ] 會員限制設為-1
- [ ] T&C已添加（HTML格式）
- [ ] Status設為Active
- [ ] Group已成功出現在列表中

---

### 步驟 3: 創建 Brand (品牌)

#### 🔵 必填位檢查清單

**基本信息**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Brand Name (English)** | ✅ | 英文品牌名 | 前台可見 |
| **Brand Name (Local Language)** | ✅ | 中文品牌名 | 前台可見 |
| **Brand Code** | ✅ | 商戶名首字母 | 例如：CA（Crozz A） |
| **Group** | ✅ | 選擇所屬組 | 必須選擇正確的group |
| **Display Sequence** | ✅ | 數字 | 按內部排序規則 |
| **Tab** | ✅ | 0或1 | 0=Popular, 1=Premium |
| **Restaurant Category** | ✅ | 餐廳類別 | 例如：Cafe |

**品牌識別**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Brand Logo** | ✅ | 1:1 logo | 建議1MB以下 |
| **Tag** | 建議必填 | 品牌關鍵詞 | 包含品牌名、菜式、地區等 |

**積分限制**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Max Point Earn Per Invoice** | ✅ | 99999 | 每張單最大積分 |
| **Max. Time of Earn Point per Day** | ✅ | 999 | 每日賺分次數上限 |
| **Max. Time of Earn Point per Week** | ✅ | 999 | 每週賺分次數上限 |
| **Max. Time of Earn Point per Day For POS** | ✅ | 1 | POS每日賺分次數 |
| **Max. Time of Earn Point per Week For POS** | ✅ | 1 | POS每週賺分次數 |

**時間設定**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Join Date** | ✅ | 品牌開始日 | 配合上線時間 |
| **Expiry Date** | ✅ | 品牌到期日 | 長期可設遠期日期 |

**功能設定**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Show Point Or Stamp on App** | 建議必填 | Yes | PPT建議設為Yes |
| **Enable Brand Profile** | 建議必填 | Tick | 啟用品牌頁 |
| **Show Redemption Page on App** | 視乎需要 | Yes | 有優惠券時開啟 |

**營運設定**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Status** | ✅ | Active | 上線必須設為Active |

#### 🟡 重要選填位（建議填寫）
- **Background Image on Dashboard**: 建議必填，品牌背景圖
- **Customer Service Email**: 建議必填，CS email
- **Website (English)**: 品牌網站
- **Background Colour 1/2/3**: App UI色系
- **Text Colour 1/2/3**: App UI文字色

#### ⚠️ 常見錯誤
- ❌ 忘記選擇正確的Group
- ❌ Tab設置錯誤（0或1）
- ❌ 積分限制設置過低
- ❌ 忘記上傳Logo
- ❌ Join/Expiry Date設定錯誤
- ❌ 功能開關忘記設置

#### ✅ 完成檢查
- [ ] Brand歸屬正確的Group
- [ ] Tab和Category設置正確
- [ ] Logo已上傳且清晰
- [ ] 積分限制設置合理
- [ ] 時間設定準確
- [ ] 功能開關已啟用
- [ ] Status設為Active
- [ ] Brand已成功出現在列表中

---

### 步驟 4: 創建 Shop (分店)

#### 🔵 必填位檢查清單

**基本信息**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Shop Name (English)** | ✅ | 英文分店名 | 前台可見 |
| **Shop Name (Local Language)** | ✅ | 中文分店名 | 前台可見 |
| **Reference ID** | ✅ | 001開始 | 與merchant確認 |
| **Brand** | ✅ | 選擇所屬品牌 | 必須選擇正確 |

**地區設定**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Region (English)** | ✅ | HK Island/Kowloon/New Territories | 三選一 |
| **Region (Local Language)** | ✅ | 香港島/九龍/新界 | 對應英文 |
| **District (English)** | ✅ | 例如：Kwun Tong | 地區名稱 |
| **District (Local Language)** | ✅ | 例如：觀塘 | 對應英文 |

**位置資訊**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Geo Location** | 建議必填 | 經度 - 緯度 | 格式：114.2096478 - 22.3156595 |
| **Address (English)** | ✅ | 英文地址 | 前台可見 |
| **Address (Local Language)** | ✅ | 中文地址 | 前台可見 |

**聯絡資訊**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Telephone** | 建議必填 | 分店電話 | 前台可見 |
| **Opening Hours (English)** | 建議必填 | 10:00 - 22:00 | 前台可見 |
| **Opening Hours (Local Language)** | 建議必填 | 10:00 - 22:00（星期一至日） | 中文版 |

**營運設定**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Status** | ✅ | Active | 上線必須設為Active |

#### 🟡 重要選填位
- **Fax**: 傳真號碼（如有）
- **Passcode**: 分店操作密碼（視乎需要）
- **Default Show**: 是否預設顯示

#### ⚠️ 常見錯誤
- ❌ Geo Location格式錯誤（必須：經度 - 緯度）
- ❌ 忘記選擇正確的Brand
- ❌ Region選擇錯誤
- ❌ 地址格式不統一
- ❌ 電話號碼格式錯誤

#### ✅ 完成檢查
- [ ] Shop歸屬正確的Brand
- [ ] Region和District對應正確
- [ ] Geo Location格式準確
- [ ] 地址中英文完整
- [ ] 電話和營業時間已填寫
- [ ] Status設為Active
- [ ] Shop已成功出現在列表中
- [ ] Shop在前台地圖顯示正確

---

### 步驟 5: 創建 Featured Items (選填)

#### 🔵 必填位檢查清單

**基本信息**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Campaign Name** | ✅ | 活動名稱 | 建議與活動名一致 |
| **Section** | ✅ | 選擇出現位置 | 決定顯示位置 |
| **Brand** | ✅ | 選擇所屬品牌 | 必須選擇正確 |

**圖片資料**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Image (English)** | ✅ | 英文活動圖 | 1080x1080px建議 |
| **Image (Local Language)** | ✅ | 中文活動圖 | 如同圖可重用 |

**時間設定**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Start Date** | ✅ | 顯示開始日 | 可早於活動開始日 |
| **End Date** | ✅ | 顯示結束日 | 與活動期間對齊 |

**排序設定**：
| 字段 | 必填 | 建議填寫 | 檢查要點 |
|------|------|----------|----------|
| **Priority** | ✅ | -1 | 數字越小優先級越高 |

#### ⚠️ 常見錯誤
- ❌ Start/End Date時間錯誤
- ❌ 忘記選擇Section
- ❌ Priority設置錯誤
- ❌ 圖片尺寸不符

#### ✅ 完成檢查
- [ ] Featured Item歸屬正確的Brand
- [ ] Section選擇正確
- [ ] 時間設定準確
- [ ] 圖片已上傳
- [ ] Priority設置合理
- [ ] Featured Item已成功出現在列表中

---

## 📊 完整上架檢查清單

### 🎯 最終驗證步驟

#### Company 層級
- [ ] Company已創建且Status為Active
- [ ] Company資訊完整無誤

#### Group 層級
- [ ] Group已創建且Status為Active
- [ ] Group歸屬正確的Company
- [ ] 積分比例設定正確
- [ ] T&C已添加（HTML格式）
- [ ] 會員限制設為-1

#### Brand 層級
- [ ] Brand已創建且Status為Active
- [ ] Brand歸屬正確的Group
- [ ] Logo和圖片已上傳
- [ ] 積分限制設置合理
- [ ] 功能開關已啟用
- [ ] 時間設定準確

#### Shop 層級
- [ ] 至少有一個Shop已創建
- [ ] Shop歸屬正確的Brand
- [ ] Geo Location設定準確
- [ ] 地址和聯絡資訊完整
- [ ] Status設為Active

#### Featured Items 層級（選填）
- [ ] 如有需要，Featured Items已創建
- [ ] 時間和Priority設定正確
- [ ] 圖片已上傳

---

## 🧪 上架後測試

### 功能測試清單
- [ ] **前台註冊測試**: 新用戶能否成功註冊
- [ ] **積分功能測試**: 積分是否能正常獲取和使用
- [ ] **地圖顯示測試**: 分店在地圖上是否正確顯示
- [ ] **多語言測試**: 中英文切換是否正常
- [ ] **品牌頁測試**: 品牌頁面資訊是否完整

### 資料驗證
- [ ] **公司資訊**: 檢查公司名稱和描述
- [ ] **品牌資訊**: 檢查品牌名稱、Logo、描述
- [ ] **分店資訊**: 檢查地址、電話、營業時間
- [ ] **聯絡資訊**: 檢查CS email和聯絡方式

---

## ⚠️ 上架常見問題與解決方案

### 問題 1: Group積分比例無效
**原因**: Point Ratio格式錯誤
**解決**: 必須使用文字格式，例如"$1 = 1 point(s)"

### 問題 2: 品牌Logo不顯示
**原因**: 圖片格式或大小不符
**解決**: 使用1:1比例，小於1MB的PNG/JPG

### 問題 3: 分店地圖位置錯誤
**原因**: Geo Location格式錯誤
**解決**: 使用"經度 - 緯度"格式，例如"114.2096478 - 22.3156595"

### 問題 4: 會員無法註冊
**原因**: Status設為Inactive或T&C未添加
**解決**: 確保Status為Active且T&C已添加

### 問題 5: 積分無法獲取
**原因**: 積分限制設置過低或功能未開啟
**解決**: 檢查積分限制設定和"Show Point Or Stamp on App"設置

---

## 📞 支援與聯絡

### 上架過程中遇到問題？
- **技術支援**: 聯絡系統管理員
- **業務諮詢**: 聯絡產品經理
- **緊急問題**: 聯絡客戶服務團隊

### 相關文檔
- [Company Brand Management 指南](./company-brand-management.md)
- [Company Brand FAQ](../customer-faq/company-brand-faq.md)
- [問題追蹤文檔](./company-brand-issues-tracker.md)

---

**創建日期**: 2026-07-09
**最後更新**: 2026-07-09
**適用於**: Storellet CMS 新品牌上架
**版本**: 1.0