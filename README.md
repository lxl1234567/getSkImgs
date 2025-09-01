# 森空岛表情包下载页面

这是一个用于下载森空岛表情包的静态网页，支持在 GitHub Pages 上部署。

## 功能特性

- 🎭 展示森空岛各种表情包系列
- 👀 点击卡片预览表情包内容
- 📱 响应式设计，支持移动端
- 🌐 自动检测部署环境
- 📥 智能下载处理

## 部署到 GitHub Pages

### 方法一：直接部署

1. 将此仓库推送到 GitHub
2. 在仓库设置中启用 GitHub Pages
3. 选择部署分支（通常是 `main` 或 `master`）
4. 访问生成的页面链接

### 方法二：使用 GitHub Actions 自动部署

1. 在仓库根目录创建 `.github/workflows/deploy.yml` 文件：

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    
    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-ghpages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./getSkImgs
```

## 环境检测

页面会自动检测运行环境：

- **GitHub Pages 环境**：使用内置的备用数据，显示环境提示
- **本地环境**：尝试连接 API 获取最新数据

## 限制说明

### GitHub Pages 环境下的限制

1. **图片加载**：由于 CORS 策略，部分图片可能无法正常显示
2. **文件下载**：无法直接下载外部链接的文件，会显示手动下载提示
3. **API 请求**：无法发送跨域请求到外部 API

### 解决方案

1. **图片问题**：使用备用图片或 CDN 服务
2. **下载问题**：提供手动下载链接
3. **API 问题**：使用内置的备用数据

## 本地开发

1. 克隆仓库到本地
2. 使用本地服务器运行（如 Live Server）
3. 页面会自动尝试连接 API 获取最新数据

## 技术栈

- HTML5
- CSS3 (Grid, Flexbox, 渐变)
- JavaScript (ES6+, Fetch API)
- 响应式设计

## 浏览器支持

- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

## 更新日志

- v1.0.0: 初始版本，支持基本功能
- v1.1.0: 添加 GitHub Pages 环境检测
- v1.2.0: 优化下载体验和错误处理

## 许可证

MIT License
