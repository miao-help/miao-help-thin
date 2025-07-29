# GitHub Pages 部署说明

## 📋 部署概述

本项目使用GitHub Actions自动部署到GitHub Pages，实现持续集成和自动发布。

## 🚀 自动部署配置

### GitHub Actions 工作流
- **文件位置**：`.github/workflows/deploy.yml`
- **触发条件**：推送到 `main` 或 `master` 分支
- **部署目录**：`design/` 文件夹
- **部署分支**：`gh-pages`

### 部署流程
1. 代码推送到main分支
2. GitHub Actions自动触发部署
3. 将`design/`目录内容部署到`gh-pages`分支
4. GitHub Pages从`gh-pages`分支提供服务

## 📁 项目结构

```
miao-help-thin/
├── .github/workflows/deploy.yml    # GitHub Actions配置
├── design/                         # 部署目录
│   ├── 00-index.html              # 主页面
│   └── 403.html                   # 错误页面
├── index.html                      # 根目录重定向
└── README.md                       # 项目说明
```

## 🔧 手动部署步骤

### 1. 启用GitHub Pages
1. 进入仓库设置 (Settings)
2. 找到 "Pages" 选项
3. 设置 Source 为 "GitHub Actions"

### 2. 推送代码
```bash
git add .
git commit -m "Add GitHub Pages deployment"
git push origin main
```

### 3. 查看部署状态
1. 进入仓库的 "Actions" 标签页
2. 查看 "Deploy to GitHub Pages" 工作流
3. 等待部署完成

### 4. 访问网站
部署完成后，访问：`https://your-username.github.io/miao-help-thin/`

## 🛠️ 本地开发

### 本地预览
```bash
# 启动本地服务器
cd design
python -m http.server 8000

# 访问：http://localhost:8000/00-index.html
```

### 测试部署
```bash
# 修改代码后测试
git add .
git commit -m "Update design"
git push origin main

# 等待几分钟后查看部署结果
```

## 📊 部署状态

- ✅ **自动部署**：已配置
- ✅ **HTTPS**：GitHub Pages自动提供
- ✅ **自定义域名**：可配置（可选）
- ✅ **缓存优化**：GitHub Pages自动处理

## 🔍 故障排除

### 常见问题

1. **部署失败**
   - 检查GitHub Actions日志
   - 确保`design/`目录存在
   - 验证文件权限

2. **页面无法访问**
   - 确认GitHub Pages已启用
   - 检查部署分支设置
   - 等待几分钟让DNS生效

3. **样式加载失败**
   - 检查CDN链接是否可访问
   - 确认HTML文件路径正确

### 联系支持
如有部署问题，请检查：
- GitHub Actions日志
- 仓库设置中的Pages配置
- 网络连接状态

---

**© 2025 喵星助手 - GitHub Pages部署配置** 