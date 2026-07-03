# 常見錯誤及解決方案

## 標簽
`#error` `#troubleshooting` `#api`

## API 錯誤

### 401 Unauthorized

**錯誤信息**：
```json
{
  "error": "Unauthorized",
  "message": "Invalid or expired token",
  "code": 401
}
```

**原因**：
- JWT Token 已過期
- Token 格式錯誤
- API 密鑰無效

**解決方案**：
```javascript
// 1. 刷新 Token
POST /api/auth/refresh
{
  "refreshToken": "your_refresh_token"
}

// 2. 重新登錄
POST /api/auth/login
{
  "email": "user@example.com",
  "password": "password"
}

// 3. 更新請求頭
headers: {
  "Authorization": "Bearer NEW_TOKEN"
}
```

### 403 Forbidden

**錯誤信息**：
```json
{
  "error": "Forbidden",
  "message": "Insufficient permissions",
  "code": 403
}
```

**原因**：
- 用戶角色權限不足
- 嘗試訪問受保護的資源
- API 令牌權限不足

**解決方案**：
1. 檢查用戶角色權限
2. 聯系管理員申請權限
3. 確認訪問的資源是否存在

### 404 Not Found

**錯誤信息**：
```json
{
  "error": "Not Found",
  "message": "Resource not found",
  "code": 404
}
```

**原因**：
- 資源 ID 不存在
- 路徑錯誤
- 資源已被刪除

**解決方案**：
```javascript
// 檢查資源是否存在
GET /api/content/{id}

// 如果返回 404，說明資源不存在
// 請檢查 ID 是否正確
```

### 429 Too Many Requests

**錯誤信息**：
```json
{
  "error": "Too Many Requests",
  "message": "Rate limit exceeded",
  "code": 429,
  "retryAfter": 60
}
```

**原因**：
- API 調用頻率超限
- 短時間內發送過多請求

**解決方案**：
1. 等待 `retryAfter` 指定的時間（秒）
2. 實現指數退避重試
3. 優化請求頻率

```javascript
// 重試策略
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

**錯誤信息**：
```json
{
  "error": "Internal Server Error",
  "message": "An unexpected error occurred",
  "code": 500
}
```

**原因**：
- 服務器內部錯誤
- 數據庫連接失敗
- 第三方服務故障

**解決方案**：
1. 檢查服務器日志
2. 驗證請求數據格式
3. 聯系技術支持

## 性能問題

### 響應時間過長

**症狀**：API 響應時間超過 5 秒

**可能原因**：
- 數據庫查詢慢
- 網絡延遲
- 服務器負載高

**優化建議**：
1. 使用查詢限制和分頁
2. 添加適當的索引
3. 啟用緩存
4. 使用 CDN

```javascript
// 優化查詢
GET /api/content?limit=10&page=1&fields=title,excerpt,status

// 啟用緩存
headers: {
  "Cache-Control": "max-age=3600"
}
```

## 數據問題

### 數據同步失敗

**症狀**：多渠道發布時部分渠道失敗

**解決方案**：
1. 檢查第三方 API 密鑰
2. 驗證網絡連接
3. 查看發布日志
4. 手動重新發布

---

**相關文檔**：[API 參考](../api-reference/endpoints.md)
**最後更新**：2026-07-03
