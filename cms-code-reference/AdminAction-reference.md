# CMS 管理员模块 (AdminAction) 代码参考

## 标签
#code-reference #admin #cms #backend

## 📍 源代码位置

```
storellet-legacy-global-backend-develop/
└── api/src/main/java/com/storellet/cms/AdminAction.java
```

**代码行数**：617 行
**主要功能**：管理员账户管理、员工管理、权限控制

---

## 🔗 主要 API 端点

### 管理员账户管理

| 端点 | 方法 | 功能 | 代码行 |
|------|------|------|--------|
| `/cms/admin/index` | GET | 管理员首页 | 32-36 |
| `/cms/admin` | GET | 管理员列表 | 246-262 |
| `/cms/admin/user` | GET | 管理员列表（同上） | 246-262 |
| `/cms/admin/user/{id}` | GET/POST | 编辑/创建管理员 | 403-566 |
| `/cms/admin/user/get-groups` | GET | 获取用户组 | 277-342 |
| `/cms/admin/staff/shop/{brandId}` | GET | 获取店铺列表 | 264-275 |

### Boss App 账户管理

| 端点 | 方法 | 功能 | 代码行 |
|------|------|------|--------|
| `/cms/admin/bossAppAccount` | GET | Boss 账户列表 | 38-59 |
| `/cms/admin/bossAppAccount/{id}` | GET | 编辑 Boss 账户 | 61-86 |
| `/cms/admin/bossAppAccount/{id}` | POST | 保存 Boss 账户 | 88-130 |

### 员工管理

| 端点 | 方法 | 功能 | 代码行 |
|------|------|------|--------|
| `/cms/admin/staff` | GET | 员工列表 | 132-163 |
| `/cms/admin/staff/{id}` | GET | 编辑员工 | 165-186 |
| `/cms/admin/staff/{id}` | POST | 保存员工 | 188-244 |

---

## 👤 数据模型

### Admin (管理员)

```java
public class Admin {
  // 基本信息
  private String id;              // 管理员 ID
  private String username;        // 用户名
  private String password;        // 密码（加密）
  private String email;           // 邮箱
  private String phone;           // 电话
  private String displayName;      // 显示名称
  private String title;           // 职位
  private String department;      // 部门

  // 权限相关
  private List<String> permissions;  // 权限列表
  private List<Integer> group;      // 组 ID 列表
  private List<Integer> company;   // 公司 ID 列表
  private List<Integer> brand;      // 品牌 ID 列表
  private List<String> appIds;      // 应用 ID 列表

  // 状态
  private Integer status;          // 状态 (1=active, 0=inactive)
  private Long createDate;         // 创建时间
  private Long lastPasswordModifyDate;  // 最后修改密码时间

  // 特殊权限
  private Boolean whiteLabelOnly;  // 仅白标
  private Boolean isStorelletAdmin; // Storellet 超级管理员
}
```

### Staff (员工)

```java
public class Staff {
  private String id;
  private Integer groupId;
  private Integer brandId;
  private Integer shopId;
  private String displayName;
  private String username;
  private String password;
  private String phone;
  private List<String> permissions;
  private Integer status;
  private Long createDate;
  private Long lastPasswordModifyDate;
  private Map<String, Object> setting;  // 员工设置
}
```

### BossAppAccount (Boss 应用账户)

```java
public class BossAppAccount {
  private String id;
  private String displayName;
  private String username;
  private String password;
  private List<Integer> brandIds;    // 关联的品牌
  private List<String> permissions;
  private Integer status;
  private Long createDate;
  private Long lastPasswordModifyDate;
}
```

---

## 🔐 权限系统

### 权限检查

系统使用两种拦截器检查权限：

1. **AdminCheckPermissionSessionInterceptor**
   - 检查管理员会话权限
   - 验证用户是否已登录

2. **AdminLoggingInterceptor**
   - 记录管理员操作日志
   - 审计追踪

### 权限类型

```java
// CMS 权限
String permission_loginCMS = "loginCMS";

// 其他权限通过 permissions 参数动态设置
```

### 权限验证逻辑

```java
// 代码行 494-497
if(userAadmin.getIsStorelletAdmin()){
  Boolean isStorelletAdmin = ServletRequestUtils.getBooleanParameter(req, "isStorelletAdmin", Boolean.FALSE);
  admin.setIsStorelletAdmin(isStorelletAdmin);
}
```

**只有 Storellet 超级管理员才能设置其他人成为超级管理员**

---

## 📝 核心业务逻辑

### 创建/更新管理员 (代码行 403-566)

**流程**：

1. **获取参数**
   ```java
   String username = req.getParameter("username");
   String password = req.getParameter("password");
   String email = req.getParameter("email");
   String[] permission_cms = req.getParameterValues("permission_cms");
   int[] groups = req.getParameterValues("groupId");
   int[] companies = req.getParameterValues("companyId");
   String[] appIds = req.getParameterValues("appIds");
   ```

2. **验证用户名唯一性**
   ```java
   // 如果是新建，检查用户名是否已存在
   // 如果是编辑，检查是否与其他用户冲突
   Staff tmpStaff = super.getAdminService().getStaffByUsername(username);
   if (tmpStaff == null || (!id.equals("0") && tmpStaff.getId().equals(id))) {
       // 可以保存
   }
   ```

3. **处理组和品牌**
   ```java
   // 获取组对应的所有品牌
   List<Brand> brandList = super.getMerchantService().listBrandsByGroupIds(groupIds, ...);

   // 如果选择了所有组，添加特殊标记 0
   if (groupIds.size() == allGroups.size()) {
       groupIds.add(0);      // 0 表示全部
       brandIds.add(0);
   }
   ```

4. **保存数据**
   ```java
   if (admin.getId() == null)
       success = super.getAdminService().save(admin);      // 新建
   else
       success = super.getAdminService().update(admin);    // 更新
   ```

5. **更新会话**（如果修改自己的账户）
   ```java
   if (id.equals(currCmsUser.getId())) {
       req.getSession(true).setAttribute("_admin", admin);
   }
   ```

### 获取组列表 (代码行 277-342)

**特殊逻辑**：

```java
// 超级管理员 vs 普通管理员
if (admin != null && admin.getCompany().contains(0)) {
    // 超级管理员：可以看到所有组和公司
    companies = super.getMerchantService().listAllGroup(...);
    groups = super.getMerchantService().listAllCompany(...);
} else {
    // 普通管理员：只能看到被授权的组和公司
    companies = super.getMerchantService().listCompanyByIds(companyIdList);
    groups = super.getMerchantService().listGroupByCompanyId(companyIdList, ...);
}
```

---

## 🎨 视图映射

| 视图路径 | 功能 | 代码行 |
|---------|------|--------|
| `/cms/admin/bossAppAccount` | Boss 账户列表页 | 58 |
| `/cms/admin/bossAppAccountEdit` | 编辑 Boss 账户 | 85 |
| `/cms/admin/staff` | 员工列表页 | 162 |
| `/cms/admin/staffEdit` | 编辑员工 | 185 |
| `editView` | 编辑管理员（动态） | 565 |
| `indexView` | 管理员首页（动态） | 35 |

---

## 🔍 常见问题和注意事项

### Q: 组 ID 和品牌 ID 的关系？

**A**:
- 一个**组 (Group)** 包含多个**品牌 (Brand)**
- 选择组时，会自动获取该组下的所有品牌
- 特殊标记：`0` 表示"全部"

**示例**：
```
Group A → [Brand 1, Brand 2, Brand 3]
Group B → [Brand 4, Brand 5]

如果选择 Group A，会自动获取 Brand 1, 2, 3
```

### Q: 为什么检查用户名唯一性？

**A**: 防止用户名冲突
```java
Staff tmpStaff = super.getAdminService().getStaffByUsername(username);
if (tmpStaff == null || (!id.equals("0") && tmpStaff.getId().equals(id))) {
    // 只有在用户名未被使用，或者是编辑自己时才允许保存
}
```

### Q: 如何实现密码修改追踪？

**A**:
```java
if (password != null && !password.trim().equals("")) {
    admin.setLastPasswordModifyDate(System.currentTimeMillis());
    admin.setPassword(password);
}
```

系统会记录**最后修改密码的时间**，用于：
- 密码过期策略
- 安全审计
- 强制密码重置

### Q: `setting` 字段是什么？

**A**: JSON 格式的自定义设置
```java
Map<String, Object> settingMap = new HashMap<>();
ObjectMapper mapper = new ObjectMapper();
settingMap = mapper.readValue(setting, Map.class);
staff.setSetting(settingMap);
```

用于存储员工的个性化配置。

---

## 🛠️ API 调用示例

### 创建管理员

```bash
# 创建新管理员
POST /cms/admin/user/add?operation=submit
Content-Type: application/x-www-form-urlencoded

username=admin_user&password=secure123&email=admin@example.com
&displayName=管理员&title=系统管理员&department=IT
&permission_cms=loginCMS&groupId=1&companyId=1&status=1
```

### 获取用户组

```bash
# JSON API
GET /cms/admin/user/get-groups?id=admin123&companyId=1
Accept: application/json

# 返回格式
{
  "公司A": [
    {"id": 1, "name": "组1", "selected": true},
    {"id": 2, "name": "组2", "selected": false}
  ]
}
```

### 获取店铺列表

```bash
GET /cms/admin/staff/shop/10
Accept: application/json

# 返回格式
{
  "101": "店铺A",
  "102": "店铺B",
  "103": "店铺C"
}
```

---

## 🔗 相关模块

- **StaffAction** - 员工管理
- **LoginAction** - 登录认证
- **AdminServiceKt** - 管理员服务层
- **MultiActionControllerBase** - 基础控制器

---

## 📊 统计信息

- **总代码行数**：617 行
- **API 端点数**：15 个
- **数据模型**：3 个主要模型
- **主要功能**：管理员管理、员工管理、Boss 应用账户

---

## 💡 使用建议

### 对于 Chatbot 回答问题

当用户问以下问题时，可以参考这个文档：

- "如何创建管理员账户？"
- "管理员有哪些权限？"
- "如何设置用户组和品牌？"
- "Boss 应用账户是什么？"
- "如何修改员工信息？"

### 代码位置

如果需要查看详细实现：
```
/Users/hazeltin/projects/Knowledge Hub/storellet-legacy-global-backend-develop/
api/src/main/java/com/storellet/cms/AdminAction.java
```

---

**最后更新**：2026-07-03
**源代码版本**：legacy-global-backend
**文档版本**：1.0

---

## 🎯 下一步

可以继续添加其他模块的参考文档：
- StaffAction - 员工管理详细说明
- MembershipAction - 会员管理
- CampaignAction - 营销活动
- DashboardAction - 仪表板

需要我为哪个模块创建参考文档吗？
