# 用戶管理指南

## 標簽
`#operation` `#beginner` `#user`

## 概述

本文檔介紹如何在 Storellet CMS 中管理用戶賬戶和權限。

## 用戶角色

Storellet CMS 有 4 種用戶角色：

| 角色 | 權限 | 描述 |
|------|------|------|
| Admin | 完全訪問 | 可以管理所有內容和用戶 |
| Editor | 創建、編輯、發布、批准 | 可以創建和發布內容，批准其他人的內容 |
| Author | 創建、編輯 | 只能創建和編輯自己的內容 |
| Reviewer | 審核、批准 | 可以審核內容並批准發布 |

## 創建用戶

### 步驟

1. 登錄 CMS 管理後台
2. 進入"用戶管理"頁面
3. 點擊"添加用戶"按鈕
4. 填寫用戶信息：
   - 郵箱地址（必填）
   - 姓名
   - 角色
   - 部門
5. 點擊"保存"

### 用戶權限配置

```json
{
  "admin": ["all"],
  "editor": ["content.create", "content.edit", "content.publish", "content.approve"],
  "author": ["content.create", "content.edit.own"],
  "reviewer": ["content.review", "content.approve"]
}
```

## 常見問題

### Q: 如何批量導入用戶？

使用批量導入功能：
1. 准備 CSV 文件，格式：`email,name,role,department`
2. 在用戶管理頁面點擊"批量導入"
3. 上傳 CSV 文件
4. 系統會自動發送邀請郵件

### Q: 用戶忘記密碼怎麼辦？

用戶可以：
1. 在登錄頁面點擊"忘記密碼"
2. 輸入注冊郵箱
3. 查收密碼重置郵件

管理員可以：
1. 在用戶管理頁面找到該用戶
2. 點擊"重置密碼"
3. 系統會發送重置郵件

## 最佳實踐

- 定期審查用戶權限
- 禁用不活躍用戶
- 使用強密碼策略
- 啟用雙因素認證（2FA）

---

**相關文檔**：[內容發布指南](./content-publishing.md)
**最後更新**：2026-07-03
