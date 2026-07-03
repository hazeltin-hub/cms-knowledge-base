# 用户管理指南

## 标签
`#operation` `#beginner` `#user`

## 概述

本文档介绍如何在 Storellet CMS 中管理用户账户和权限。

## 用户角色

Storellet CMS 有 4 种用户角色：

| 角色 | 权限 | 描述 |
|------|------|------|
| Admin | 完全访问 | 可以管理所有内容和用户 |
| Editor | 创建、编辑、发布、批准 | 可以创建和发布内容，批准其他人的内容 |
| Author | 创建、编辑 | 只能创建和编辑自己的内容 |
| Reviewer | 审核、批准 | 可以审核内容并批准发布 |

## 创建用户

### 步骤

1. 登录 CMS 管理后台
2. 进入"用户管理"页面
3. 点击"添加用户"按钮
4. 填写用户信息：
   - 邮箱地址（必填）
   - 姓名
   - 角色
   - 部门
5. 点击"保存"

### 用户权限配置

```json
{
  "admin": ["all"],
  "editor": ["content.create", "content.edit", "content.publish", "content.approve"],
  "author": ["content.create", "content.edit.own"],
  "reviewer": ["content.review", "content.approve"]
}
```

## 常见问题

### Q: 如何批量导入用户？

使用批量导入功能：
1. 准备 CSV 文件，格式：`email,name,role,department`
2. 在用户管理页面点击"批量导入"
3. 上传 CSV 文件
4. 系统会自动发送邀请邮件

### Q: 用户忘记密码怎么办？

用户可以：
1. 在登录页面点击"忘记密码"
2. 输入注册邮箱
3. 查收密码重置邮件

管理员可以：
1. 在用户管理页面找到该用户
2. 点击"重置密码"
3. 系统会发送重置邮件

## 最佳实践

- 定期审查用户权限
- 禁用不活跃用户
- 使用强密码策略
- 启用双因素认证（2FA）

---

**相关文档**：[内容发布指南](./content-publishing.md)
**最后更新**：2026-07-03
