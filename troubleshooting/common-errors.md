# 常见错误及解决方案

## 标签
`#error` `#troubleshooting` `#api`

## API 错误

### 401 Unauthorized

**错误信息**：
```json
{
  "error": "Unauthorized",
  "message": "Invalid or expired token",
  "code": 401
}
```

**原因**：
- JWT Token 已过期
- Token 格式错误
- API 密钥无效

**解决方案**：
```javascript
// 1. 刷新 Token
POST /api/auth/refresh
{
  "refreshToken": "your_refresh_token"
}

// 2. 重新登录
POST /api/auth/login
{
  "email": "user@example.com",
  "password": "password"
}

// 3. 更新请求头
headers: {
  "Authorization": "Bearer NEW_TOKEN"
}
```

### 403 Forbidden

**错误信息**：
```json
{
  "error": "Forbidden",
  "message": "Insufficient permissions",
  "code": 403
}
```

**原因**：
- 用户角色权限不足
- 尝试访问受保护的资源
- API 令牌权限不足

**解决方案**：
1. 检查用户角色权限
2. 联系管理员申请权限
3. 确认访问的资源是否存在

### 404 Not Found

**错误信息**：
```json
{
  "error": "Not Found",
  "message": "Resource not found",
  "code": 404
}
```

**原因**：
- 资源 ID 不存在
- 路径错误
- 资源已被删除

**解决方案**：
```javascript
// 检查资源是否存在
GET /api/content/{id}

// 如果返回 404，说明资源不存在
// 请检查 ID 是否正确
```

### 429 Too Many Requests

**错误信息**：
```json
{
  "error": "Too Many Requests",
  "message": "Rate limit exceeded",
  "code": 429,
  "retryAfter": 60
}
```

**原因**：
- API 调用频率超限
- 短时间内发送过多请求

**解决方案**：
1. 等待 `retryAfter` 指定的时间（秒）
2. 实现指数退避重试
3. 优化请求频率

```javascript
// 重试策略
async function fetchWithRetry(url, options, maxRetries = 3) {
  for (let i = 0; i < maxRetries; i++) {
    try {
      const response = await fetch(url, options);
      if (response.status === 429) {
        const retryAfter = response.headers.get('Retry-After');
        await new Promise(resolve => setTimeout(resolve, (retryAfter || 60) * 1000));
        continue;
      }
      return response;
    } catch (error) {
      if (i === maxRetries - 1) throw error;
    }
  }
}
```

### 500 Internal Server Error

**错误信息**：
```json
{
  "error": "Internal Server Error",
  "message": "An unexpected error occurred",
  "code": 500
}
```

**原因**：
- 服务器内部错误
- 数据库连接失败
- 第三方服务故障

**解决方案**：
1. 检查服务器日志
2. 验证请求数据格式
3. 联系技术支持

## 性能问题

### 响应时间过长

**症状**：API 响应时间超过 5 秒

**可能原因**：
- 数据库查询慢
- 网络延迟
- 服务器负载高

**优化建议**：
1. 使用查询限制和分页
2. 添加适当的索引
3. 启用缓存
4. 使用 CDN

```javascript
// 优化查询
GET /api/content?limit=10&page=1&fields=title,excerpt,status

// 启用缓存
headers: {
  "Cache-Control": "max-age=3600"
}
```

## 数据问题

### 数据同步失败

**症状**：多渠道发布时部分渠道失败

**解决方案**：
1. 检查第三方 API 密钥
2. 验证网络连接
3. 查看发布日志
4. 手动重新发布

---

**相关文档**：[API 参考](../api-reference/endpoints.md)
**最后更新**：2026-07-03
