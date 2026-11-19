# Portfolio Deployment Guide — GitHub Pages 一键部署指南

> 将 portfolio.html 部署为在线专业作品集页面的完整步骤  
> 耗时：约15分钟 | 费用：免费

---

## Step 1: 准备GitHub账号

1. 前往 https://github.com/signup 注册账号（如已有则跳过）
2. 创建一个新仓库，命名为 `geopersonal` 或 `{yourname}-portfolio`
3. 仓库设为 **Public**（GitHub Pages需要公共仓库）
4. 勾选 "Add a README file"（可选）

---

## Step 2: 上传文件

### 方式A：网页界面上传（最简单）

1. 打开刚创建的仓库
2. 点击 "Add file" → "Upload files"
3. 拖入 `portfolio.html`（和任何其他静态资源文件）
4. 填写Commit message: "Initial portfolio deployment"
5. 点击 "Commit changes"

### 方式B：Git命令行上传（推荐长期维护）

```bash
# 克隆仓库
git clone https://github.com/YOUR_USERNAME/geopersonal.git
cd geopersonal

# 复制portfolio.html到本地目录
cp E:/geo/knowledge_base/deliverables/portfolio.html .

# 提交并推送
git add portfolio.html
git commit -m "Deploy GEO portfolio v1"
git push origin main
```

---

## Step 3: 启用GitHub Pages

1. 进入仓库 Settings（设置页面）
2. 左侧菜单找到 **Pages**
3. Branch 选择：**main**（或 master）
4. Folder 选择：**/(root)**
5. 点击 **Save**

等待约1-2分钟，你会看到：
```
Your site is live at https://YOUR_USERNAME.github.io/geopersonal/
```

---

## Step 4: 自定义域名（可选进阶）

如果你想使用自己的域名（如 `geo.yourname.com`）：

1. 购买域名（Namecheap/Cloudflare/Godaddy等）
2. 在GitHub Pages设置中添加CNAME记录：
   ```
   CNAME geopersonal.github.io
   ```
3. 在域名注册商的DNS面板添加：
   ```
   @    CNAME  yourusername.github.io.
   www  CNAME  yourusername.github.io.
   ```

---

## 验证清单

部署完成后，逐项检查：

- [ ] 页面能正常加载（无404错误）
- [ ] CSS样式正确渲染（配色、字体）
- [ ] 所有卡片内容显示正常
- [ ] 表格数据清晰可读
- [ ] 在手机上测试响应式布局正常
- [ ] 无任何broken image links
- [ ] Title标签显示正确（浏览器tab标题）

---

## 持续更新流程

每次修改portfolio.html后，同步更新线上版本：

```bash
# 修改本地文件后...
git add portfolio.html
git commit -m "Update portfolio - {简要描述}"
git push origin main
```

GitHub会自动重新构建并部署，通常30秒内生效。无需任何额外操作。

---

## 备选托管方案

如果GitHub Pages不可用，以下替代方案同样免费：

| 平台 | 网址 | 特点 |
|-----|------|------|
| Netlify | netlify.com | 拖拽即部署，自动HTTPS |
| Vercel | vercel.com | 极速CDN，适合动态站点 |
| Cloudflare Pages | pages.cloudflare.com | 全球CDN，免费额度充裕 |
| Surge.sh | surge.sh | 一行命令：`surge portfolio.html` |

**推荐**: Netlify（最简单）或 GitHub Pages（最稳定）
