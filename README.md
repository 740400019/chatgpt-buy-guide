# ChatGPT 购买指南（chatgpt-buy-guide）

Jekyll + GitHub Pages 静态站点，给 [openobt.com](https://openobt.com) 做 SEO 外链 / 导流的卫星站。

## 项目说明

- **目标 URL**：https://740400019.github.io/chatgpt-buy-guide/
- **主题**：自定义（无需 Gemfile，GitHub Pages 内置 gem 即可 build）
- **插件**：jekyll-sitemap、jekyll-seo-tag、jekyll-feed（GitHub Pages 默认启用）
- **文章数**：12 篇高质量中文长文（1500-3000 字 / 篇）

## 目录结构

```
chatgpt-buy-guide/
├── _config.yml          # 站点配置
├── _layouts/            # 模板
│   ├── default.html
│   ├── post.html
│   └── home.html
├── _includes/           # 公共片段
│   ├── head.html
│   ├── header.html
│   └── footer.html
├── _posts/              # 12 篇文章（YYYY-MM-DD-slug.md）
├── assets/css/main.css  # 自定义样式（无依赖）
├── index.md             # 首页
├── about.md             # 关于页
├── robots.txt           # 搜索引擎
├── 404.html             # 错误页
└── README.md            # 本文件
```

## 本地预览（可选）

GitHub Pages 会自动 build，本地预览**不是必需**的。如果想本地预览：

```bash
# 1. 安装 Ruby + Bundler（macOS 自带）
gem install bundler jekyll

# 2. 在项目目录创建临时 Gemfile（仅本地预览用，不要提交）
cat > Gemfile <<EOF
source "https://rubygems.org"
gem "github-pages", group: :jekyll_plugins
EOF

# 3. 安装依赖
bundle install

# 4. 启动本地服务
bundle exec jekyll serve

# 5. 浏览器打开 http://127.0.0.1:4000/chatgpt-buy-guide/

# 预览完成后删除 Gemfile / Gemfile.lock，不要提交到仓库
rm Gemfile Gemfile.lock
```

## 推到 GitHub

```bash
cd /Users/axie/Desktop/chatgpt-buy-guide

git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/740400019/chatgpt-buy-guide.git
git push -u origin main
```

如果远程 repo 还没创建，先在 GitHub 网页上 `New repository`：

- Repository name：**chatgpt-buy-guide**
- Public（必须公开，免费 GitHub Pages 才能用）
- 不要勾 `Add a README file`、`Add .gitignore`、`Choose a license`（让本地的覆盖）

创建好之后再执行上面的命令。

## 启用 GitHub Pages

1. 打开仓库 https://github.com/740400019/chatgpt-buy-guide
2. 顶栏 **Settings** → 左侧 **Pages**
3. **Source**: Deploy from a branch
4. **Branch**: `main` / `(root)`
5. **Save**
6. 等 1-2 分钟首次 build
7. 访问 **https://740400019.github.io/chatgpt-buy-guide/**

GitHub Pages build 状态可以在仓库的 **Actions** 标签里看（绿勾 = 成功）。

## 提交 Google Search Console

1. 进入 https://search.google.com/search-console
2. **Add property** → **URL prefix**
3. 输入 `https://740400019.github.io/chatgpt-buy-guide/`
4. **验证方法选择 HTML 文件**：
   - 下载 GSC 给的 `googleXXXXXX.html` 文件
   - 放到本地项目根目录（和 `index.md` 同级）
   - `git add googleXXXXXX.html && git commit -m "Add GSC verification" && git push`
   - 等 GitHub Pages 重新 build（1-2 分钟）
   - 回 GSC 点 **Verify**
5. 验证通过后提交 sitemap：
   - GSC 左侧菜单 **Sitemaps**
   - 输入 `sitemap.xml`（jekyll-sitemap 自动生成）
   - 完整 URL 是 `https://740400019.github.io/chatgpt-buy-guide/sitemap.xml`
   - **Submit**

## 提交 Bing Webmaster Tools（可选，提升收录）

1. 访问 https://www.bing.com/webmasters
2. 用 Google 账号登录，可以直接从 GSC 导入
3. 同样添加资源 + 提交 sitemap

## 站点配置说明

主要配置都在 `_config.yml`：

- `title`：站点标题
- `description`：站点描述（会变成首页 meta description）
- `url` + `baseurl`：完整 URL = url + baseurl，必须正确否则资源加载错误
- `shop`：主站信息（footer / 商品卡片引用）
- `products`：6 个商品（修改这里会同步到所有页面的商品卡片）

## 文章列表（12 篇）

| 文件名 | URL | 主关键词 |
|---|---|---|
| 2026-05-09-chatgpt-product-comparison.md | /chatgpt-product-comparison/ | ChatGPT 价格对比 |
| 2026-05-09-chatgpt-buying-channels-2026.md | /chatgpt-buying-channels-2026/ | ChatGPT 怎么买 |
| 2026-05-09-chatgpt-payment-methods-china.md | /chatgpt-payment-methods-china/ | ChatGPT 支付宝 |
| 2026-05-09-chatgpt-account-banned-prevention.md | /chatgpt-account-banned-prevention/ | ChatGPT 封号 |
| 2026-05-09-gpt5-vs-claude4-vs-gemini2.md | /gpt5-vs-claude4-vs-gemini2/ | GPT5 vs Claude |
| 2026-05-09-chatgpt-pro-200-worth-it.md | /chatgpt-pro-200-worth-it/ | Pro 200 值不值 |
| 2026-05-09-chatgpt-price-comparison-table.md | /chatgpt-price-comparison-table/ | ChatGPT 多少钱 |
| 2026-05-09-chatgpt-for-students-saving.md | /chatgpt-for-students-saving/ | ChatGPT 学生 |
| 2026-05-09-chatgpt-team-tutorial.md | /chatgpt-team-tutorial/ | Team 教程 |
| 2026-05-09-chatgpt-api-vs-plus.md | /chatgpt-api-vs-plus/ | ChatGPT API |
| 2026-05-09-chatgpt-mobile-app-guide.md | /chatgpt-mobile-app-guide/ | ChatGPT App |
| 2026-05-09-chatgpt-coupon-discount-truth.md | /chatgpt-coupon-discount-truth/ | ChatGPT 优惠码 |

## 后续维护

### 添加新文章

在 `_posts/` 下新建 `YYYY-MM-DD-slug.md`，frontmatter 模板：

```yaml
---
layout: post
title: "..."
description: "..."
keywords: "..."
date: 2026-XX-XX
permalink: /:slug/
---
```

push 后 GitHub Pages 自动重新 build。

### 修改商品 / 主站信息

只改 `_config.yml` 里的 `shop` 和 `products` 字段，不需要动 layouts。

### 修改样式

所有样式在 `assets/css/main.css`，约 300 行，无依赖。

## 常见问题

**Q：CSS 不生效 / 样式错位？**

检查 `_config.yml` 里的 `baseurl: /chatgpt-buy-guide` 是否正确。如果 repo 名变了要同步改。

**Q：sitemap.xml 在哪？**

GitHub Pages build 完成后自动生成，URL 是 `https://740400019.github.io/chatgpt-buy-guide/sitemap.xml`。

**Q：build 失败？**

去 GitHub 仓库 Actions 标签看错误信息。最常见的是 frontmatter YAML 格式错误（缩进、引号）。

**Q：能用自定义域名吗？**

可以。在 GitHub Pages 设置里加 Custom domain，并在仓库根目录加一个 `CNAME` 文件（内容是域名）。同时改 `_config.yml` 的 `url` 和 `baseurl`。

## 联系

- 主站：https://openobt.com
- 客服微信：doucco
- Telegram：https://t.me/fanbii
