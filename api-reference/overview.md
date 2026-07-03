# API 參考概述

## 標簽
`#api` `#reference` `#endpoints`

## 基本信息

- **Base URL**：`https://api.storellet.com/api`
- **認證方式**：JWT Bearer Token
- **數據格式**：JSON
- **字符編碼**：UTF-8

## 認證

### 獲取 Token

```bash
# 登錄獲取 Token
POST /api/auth/login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "your_password"
}
```

**響應**：
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "expiresIn": 2592000,
  "user": {
    "id": "507f1f77bcf86cd799439011",
    "email": "user@example.com",
    "role": "editor"
  }
}
```

### 使用 Token

```bash
# 在請求頭中包含 Token
GET /api/content
Authorization: Bearer YOUR_TOKEN
```

## 主要端點

### 內容管理

| 方法 | 端點 | 描述 | 權限 |
|------|------|------|------|
| GET | `/api/content` | 獲取內容列表 | 所有用戶 |
| POST | `/api/content` | 創建內容 | Editor+, Author |
| GET | `/api/content/:id` | 獲取單個內容 | 所有用戶 |
| PUT | `/api/content/:id` | 更新內容 | Editor+, Author（自己的）|
| DELETE | `/api/content/:id` | 刪除內容 | Admin |
| PUT | `/api/content/:id/submit` | 提交審核 | Editor+, Author |
| PUT | `/api/content/:id/approve` | 批准內容 | Editor+, Reviewer |
| PUT | `/api/content/:id/publish` | 發布內容 | Editor+ |

### AI 功能

| 方法 | 端點 | 描述 | 權限 |
|------|------|------|------|
| POST | `/api/ai/generate` | AI 生成內容 | Editor+, Author |
| POST | `/api/ai/improve` | AI 優化內容 | Editor+, Author |
| POST | `/api/ai/translate` | AI 翻譯 | Editor+, Author |

### 用戶管理

| 方法 | 端點 | 描述 | 權限 |
|------|------|------|------|
| GET | `/api/users` | 獲取用戶列表 | Admin |
| POST | `/api/users` | 創建用戶 | Admin |
| PUT | `/api/users/:id` | 更新用戶 | Admin |
| DELETE | `/api/users/:id` | 刪除用戶 | Admin |

## 請求示例

### 創建內容

```bash
curl -X POST https://api.storellet.com/api/content \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "我的第一篇文章",
    "contentType": "article",
    "content": "這是文章內容...",
    "language": "zh-CN",
    "category": "技術",
    "tags": ["教程", "入門"]
  }'
```

### AI 生成內容

```bash
curl -X POST https://api.storellet.com/api/ai/generate \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "prompt": "寫一篇關於 SEO 的文章",
    "contentType": "article",
    "language": "zh-CN",
    "length": 1000,
    "tone": "專業"
  }'
```

## 響應格式

### 成功響應

```json
{
  "success": true,
  "data": {
    "id": "507f1f77bcf86cd799439011",
    "title": "文章標題",
    "content": "文章內容..."
  }
}
```

### 錯誤響應

```json
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "驗證失敗",
    "details": [
      {
        "field": "title",
        "message": "標題不能為空"
      }
    ]
  }
}
```

## 速率限制

- **默認限制**：100 請求/分鐘
- **Burst 限制**：200 請求/分鐘
- **超出限制**：返回 429 狀態碼

## 版本控制

API 使用 URL 版本控制：
- **當前版本**：v1
- **Base URL**：`https://api.storellet.com/api/v1`

## 支持

- **文檔**：https://docs.storellet.com
- **狀態頁面**：https://status.storellet.com
- **技術支持**：support@storellet.com

---

**相關文檔**：[常見錯誤](../troubleshooting/common-errors.md)
**最後更新**：2026-07-03
