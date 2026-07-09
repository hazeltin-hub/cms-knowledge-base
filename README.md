# CMS Knowledge Base

## 📚 概述

這是 Storellet CMS 的官方知識庫，用於支持內部團隊和客戶服務。

## 🎯 用途

- **內部培訓**：新員工學習 CMS 操作
- **客戶支持**：快速查找客戶問題答案
- **故障排除**：解決常見技術問題
- **API 參考**：開發集成指南
- **智能問答**：通過 Chatbot 獲取即時答案

## ✨ 已完成模塊

### 操作指南（9個）

#### 基礎操作
- **登錄指南** - 登錄步驟、密碼管理、錯誤處理
- **密碼重置指南** - 3種重置方法、安全最佳實踐

#### 用戶與權限管理
- **員工管理** - 員工CRUD、權限設置、密碼管理
- **會員管理** - 會員信息、積分、優惠券、印花卡管理

#### 數據分析與報表
- **儀表板使用** - 數據查看、篩選、下鑽、導出
- **報表與分析** - 概覽報表、自定義報表、數據導出

#### 系統配置
- **應用配置管理** - 前端頁面、圖片、標簽、地區、POS密鑰、PMS集成

#### 營銷與組織
- **推送管理** - 優惠券推送、積分批量調整、推送通知、新聞推送
- **公司品牌管理** - 公司、組/品牌、店鋪、特色項目管理（含5個完整子模塊）

### 公司品牌管理詳細內容

**完整覆蓋的5個子模塊**：
1. **All Companies** - 公司管理、創建、編輯、狀態管理
2. **Company Groups** - 組管理、數據模型、會員限制
3. **Brands** - 品牌管理、積分設置、多語言配置
4. **Shops** - 店鋪管理、地理位置、支付配置、集成設置
5. **Featured Items** - 特色項目管理、時段控制、優先級設置

### 代碼參考（1個）

- **AdminAction** - 400+行詳細代碼參考，15個API端點分析

### FAQ 和問題追蹤（2個）

- **Company Brand FAQ** - 基於實際Excel教學材料的35個FAQ問題
- **Company Brand 問題追蹤** - 正式launch後的問題追蹤和改進機制

## 📊 統計

- **操作指南數量**：9個
- **代碼參考數量**：1個
- **FAQ 文檔數量**：1個（35個問題）
- **問題追蹤文檔**：1個
- **實際驗證的 Fields**：150+ 個（基於Excel教學材料）
- **文檔總行數**：10,000+ 行
- **Company tab 子模塊**：5個（All Companies、Company Groups、Brands、Shops、Featured Items）
- **覆蓋模塊**：登錄、密碼、員工、會員、儀表板、報表、應用配置、推送、完整組織架構

## 📁 結構

```
cms-knowledge-base/
├── cms-operations/          # CMS 操作指南（9個核心模塊）
│   ├── login-guide.md               # 登錄指南
│   ├── password-reset-guide.md     # 密碼重置指南
│   ├── staff-management.md         # 員工管理指南
│   ├── dashboard-guide.md          # 儀表板使用指南
│   ├── membership-management.md    # 會員管理指南
│   ├── report-analytics-guide.md   # 報表與分析指南
│   ├── application-management.md   # 應用配置管理指南
│   ├── push-management.md          # 推送管理指南
│   └── company-brand-management.md  # 公司品牌管理指南
├── cms-code-reference/     # CMS 代碼參考文檔
│   └── AdminAction-reference.md     # AdminAction 代碼參考
├── customer-faq/            # 客戶常見問題
├── troubleshooting/         # 故障排除
└── api-reference/           # API 參考文檔
```

## 🔄 如何更新

1. 在相應文件夾創建新文檔
2. 使用清晰的 Markdown 格式
3. 添加適當的標簽和關鍵詞
4. 提交 PR 進行審查

## 🔍 搜索技巧

- 使用文件名中的關鍵詞搜索
- 查看每個文檔的標簽部分
- Chrome Extension 會自動匹配相關內容

---

**最後更新**：2026-07-09
**維護者**：Storellet Team
