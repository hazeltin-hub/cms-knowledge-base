# API 参考概述

## 标签
`#api` `#reference` `#endpoints`

## 基本信息

- **Base URL**：`https://api.storellet.com/api`
- **认证方式**：JWT Bearer Token
- **数据格式**：JSON
- **字符编码**：UTF-8

## 认证

### 获取 Token

```bash
# 登录获取 Token
POST /api/auth/login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "your_password"
}
```

**响应**：
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
# 在请求头中包含 Token
GET /api/content
Authorization: Bearer YOUR_TOKEN
```

## 主要端点

### 内容管理

| 方法 | 端点 | 描述 | 权限 |
|------|------|------|------|
| GET | `/api/content` | 获取内容列表 | 所有用户 |
| POST | `/api/content` | 创建内容 | Editor+, Author |
| GET | `/api/content/:id` | 获取单个内容 | 所有用户 |
| PUT | `/api/content/:id` | 更新内容 | Editor+, Author（自己的）|
| DELETE | `/api/content/:id` | 删除内容 | Admin |
| PUT | `/api/content/:id/submit` | 提交审核 | Editor+, Author |
| PUT | `/api/content/:id/approve` | 批准内容 | Editor+, Reviewer |
| PUT | `/api/content/:id/publish` | 发布内容 | Editor+ |

### AI 功能

| 方法 | 端点 | 描述 | 权限 |
|------|------|------|------|
| POST | `/api/ai/generate` | AI 生成内容 | Editor+, Author |
| POST | `/api/ai/improve` | AI 优化内容 | Editor+, Author |
| POST | `/api/ai/translate` | AI 翻译 | Editor+, Author |

### 用户管理

| 方法 | 端点 | 描述 | 权限 |
|------|------|------|------|
| GET | `/api/users` | 获取用户列表 | Admin |
| POST | `/api/users` | 创建用户 | Admin |
| PUT | `/api/users/:id` | 更新用户 | Admin |
| DELETE | `/api/users/:id` | 删除用户 | Admin |

## 请求示例

### 创建内容

```bash
curl -X POST https://api.storellet.com/api/content \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "我的第一篇文章",
    "contentType": "article",
    "content": "这是文章内容...",
    "language": "zh-CN",
    "category": "技术",
    "tags": ["教程", "入门"]
  }'
```

### AI 生成内容

```bash
curl -X POST https://api.storellet.com/api/ai/generate \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "prompt": "写一篇关于 SEO 的文章",
    "contentType": "article",
    "language": "zh-CN",
    "length": 1000,
    "tone": "专业"
  }'
```

## 响应格式

### 成功响应

```json
{
  "success": true,
  "data": {
    "id": "507f1f77bcf86cd799439011",
    "title": "文章标题",
    "content": "文章内容..."
  }
}
```

### 错误响应

```json
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "验证失败",
    "details": [
      {
        "field": "title",
        "message": "标题不能为空"
      }
    ]
  }
}
```

## 速率限制

- **默认限制**：100 请求/分钟
- **Burst 限制**：200 请求/分钟
- **超出限制**：返回 429 状态码

## 版本控制

API 使用 URL 版本控制：
- **当前版本**：v1
- **Base URL**：`https://api.storellet.com/api/v1`

## 支持

- **文档**：https://docs.storellet.com
- **状态页面**：https://status.storellet.com
- **技术支持**：support@storellet.com

---

**相关文档**：[常见错误](../troubleshooting/common-errors.md)
**最后更新**：2026-07-03
