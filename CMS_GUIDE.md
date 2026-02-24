# JCL Travel Website - 后台管理系统配置指南

## ✅ 已完成配置

1. ✅ 网站代码已推送到 GitHub
2. ✅ Decap CMS 配置文件已创建
3. ✅ GitHub Actions 自动部署已配置

## 📋 下一步：启用 GitHub Pages

### 第一步：启用 GitHub Pages
1. 访问你的仓库：**https://github.com/lx2059/jcl-travel/settings/pages**
2. 在 **Source** 部分，确保选择：
   - **Deploy from a branch**
   - Branch: **main**
   - Folder: **/ (root)**
3. 点击 **"Save"**

### 第二步：等待自动部署
1. 访问 **https://github.com/lx2059/jcl-travel/actions**
2. 你会看到一个正在运行的部署任务（GitHub Actions）
3. 等待部署完成（大约 2-3 分钟）
4. 完成后，你的网站将通过 GitHub Pages 访问

### 第三步：配置 Git Gateway（Decap CMS 认证）

**重要：** Decap CMS 需要 Git Gateway 来进行身份验证。由于我们使用 GitHub Pages（而不是 Netlify），我们需要使用替代方案：

#### 选项 A：使用 GitHub 个人访问令牌（推荐）

1. **创建个人访问令牌：**
   - 访问：https://github.com/settings/tokens
   - 点击 **"Generate new token (classic)"**
   - Token 名称：`JCL Travel CMS`
   - 勾选权限：**repo** (Full control of private repositories)
   - 点击 **"Generate token"**
   - **复制并保存令牌**（只显示一次！）

2. **访问后台管理系统：**
   - 访问：`https://lx2059.github.io/jcl-travel/admin/`
   - 第一次访问会提示你登录
   - 使用你的 GitHub 账号授权即可

#### 选项 B：使用 Netlify Git Gateway（更简单）

如果你想使用更简单的 Git Gateway 认证：

1. 访问 **https://www.netlify.com/** 并注册（免费）
2. 点击 **"Add new site"** → **"Import an existing project"**
3. 选择 **GitHub**，授权 Netlify 访问你的仓库
4. 选择 **lx2059/jcl-travel** 仓库
5. 构建设置：
   - Build command: `hugo`
   - Publish directory: `public`
6. 点击 **"Deploy site"**
7. 部署完成后，在 Netlify 后台：
   - 进入 **"Site settings"** → **"Identity"**
   - 点击 **"Enable Identity"**
   - 进入 **"Registration"** → 选择 **"Open"** 或 **"Invite only"**
   - 进入 **"Git Gateway"** → 点击 **"Enable Git Gateway"**
8. 访问 `https://你的网站.netlify.app/admin/` 即可使用后台

## 🎯 使用后台管理系统

### 访问后台
- 地址：`https://lx2059.github.io/jcl-travel/admin/`（GitHub Pages）
- 或：`https://你的网站.netlify.app/admin/`（Netlify）

### 可管理的内容

1. **页面管理**
   - 首页：修改标题、副标题、描述、Hero 图片
   - 关于我们：编辑公司介绍
   - 联系我们：更新联系方式

2. **旅游线路**
   - 添加新路线
   - 编辑现有路线（标题、价格、天数、描述、图片等）
   - 设置亮点、包含/不包含项目

3. **目的地**
   - 添加新目的地
   - 编辑目的地信息

### 上传图片
- 在编辑页面时，点击图片字段即可上传
- 图片会自动保存到 `static/images/uploads/` 目录
- 建议图片大小：< 500KB（系统会自动压缩）

### 发布更改
1. 在后台编辑内容
2. 点击 **"Save"** 保存草稿
3. 点击 **"Publish"** 发布更改
4. GitHub Actions 会自动重新部署网站（约 1-2 分钟）

## 📞 技术支持

如有任何问题，请随时联系我！

---

**项目状态：** 后台管理系统已配置完成，等待 GitHub Pages 启用后即可使用。
