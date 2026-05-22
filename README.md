# 赛博胖氪 - Hexo Blog Project

## 版本历史

| 版本 | 日期 | 提交 | 修改内容 |
|------|------|------|----------|
| 1.0.0 | 2026-05-21 | 981ce68 | 初始版本，Hexo 8.1.2 + Chic 主题 |
| 1.0.1 | 2026-05-21 | b7f952b | 集成 Waline 评论系统，隐藏 Powered by 文字 |
| 1.1.0 | 2026-05-21 | 690e01e | 文章重新排序，新增 404 页面，修复样式问题 |
| 1.2.0 | 2026-05-21 | - | 本地图片迁移、图片格式优化 (PNG/JPG→WebP)、内容清理 |
| 1.3.0 | 2026-05-22 | - | SEO 全面优化、结构化数据完善 |
| 1.4.0 | 2026-05-22 | - | 移动端样式优化，修复归档/文章页面溢出问题 |

## 项目信息

- **名称**: 赛博胖氪
- **域名**: https://www.windowsplus.cn/
- **主题**: Chic (自定义版本)
- **Hexo版本**: 8.1.2
- **Node版本**: 6.0+
- **文章数量**: 166 篇

## 目录结构

```
D:\PKBlog\
├── .claude/          # Claude Code 配置
├── .github/          # GitHub 配置
├── _config.yml       # Hexo 站点配置
├── db.json           # Hexo 数据库
├── package.json      # 项目依赖
├── source/           # 站点源文件
│   ├── _posts/       # 博客文章 (166篇，已按时间排序)
│   ├── images/       # 文章图片资源
│   ├── 404.md        # 404页面
│   ├── about/        # 关于页面
│   ├── category/     # 分类页面
│   └── tag/          # 标签页面
├── themes/           # 主题
│   └── Chic/         # Chic 主题 (本地修改版)
│       ├── layout/   # 模板文件
│       │   ├── _partial/head.ejs    # SEO 头部模板
│       │   └── _page/post.ejs        # 文章页模板
│       └── source/   # 主题资源
│           ├── css/  # 样式文件
│           └── image/# 主题图片
└── public/           # 生成的静态文件 (由 .gitignore 忽略)
```

## SEO 配置 (v1.3.0)

### 已实现的 SEO 功能

| 功能 | 说明 |
|------|------|
| **sitemap** | 已生成 sitemap.xml 和 baidusitemap.xml |
| **robots.txt** | 正确配置，禁止抓取敏感目录 |
| **canonical URL** | 所有页面都有，防止重复内容 |
| **Open Graph** | og:title/og:url/og:description/og:image |
| **Twitter Cards** | summary_large_image 类型 |
| **JSON-LD** | WebSite + BlogPosting 结构化数据 |
| **移动端适配** | viewport 正确配置 |
| **文章级 meta** | 每篇文章自动提取前150字符作为 description |
| **文章级图片** | 自动提取文章第一张图片作为 og:image |

### SEO 标签分布

| 页面 | og:* | twitter:* | canonical | JSON-LD |
|------|------|-----------|-----------|---------|
| 首页 | 5 | 3 | ✅ | 1 |
| 文章页 | 5 | 3 | ✅ | 2 |
| 分类页 | 5 | 3 | ✅ | 0 |
| 标签页 | 5 | 3 | ✅ | 0 |
| 归档页 | 5 | 3 | ✅ | 0 |

### 分类体系

| 分类 | 数量 | 说明 |
|------|------|------|
| 工具 | 58 | 软件工具类文章 |
| 软件 | 39 | 桌面应用类文章 |
| 网站 | 24 | 网站资源类文章 |
| 系统 | 22 | Windows 系统类文章 |
| 笔记 | 14 | 教程笔记类文章 |
| 资源 | 9 | 资源素材类文章 |

## 最近修改内容

### 2026-05-22 v1.4.0 - 移动端样式优化

**修改文件**:
- `themes/Chic/source/css/media.styl` - 修复移动端溢出问题
- `themes/Chic/source/css/_page/archive.styl` - 归档列表布局优化

**修复内容**:
- 归档页面移动端添加左右内边距，内容不贴边界
- 年份标题 h3 添加顶部内边距，防止被遮挡
- 文章页面移动端 `.main` 添加 `width: 100%; box-sizing: border-box`
- `.post-content p` 添加 `word-break: break-all` 处理长文件名换行
- `.archive-item-link` 从 `display: block` 改为 `display: flex`

### 2026-05-22 v1.3.0 - SEO 全面优化

**修改内容**:
- `themes/Chic/layout/_partial/head.ejs` - 优化 SEO 头部标签
- `themes/Chic/layout/_page/post.ejs` - 移除重复的 og: 标签
- 删除所有文章的 `index_img` 字段，改为自动提取
- 优化 `og:image` 为文章内容第一张图片

**SEO 改进**:
- 添加 canonical 标签到所有页面，防止重复内容
- 添加 Twitter Cards 配置 (summary_large_image)
- 文章 description 改为自动提取内容前150字符
- og:image 改为从文章内容自动提取（无图用默认 favicon）
- subtitle 改为动态显示（文章页：标题 - 副标题）
- 移除文章页重复的 og: 标签
- 清理所有文章的 front matter，只保留必要字段

**Front Matter 规范**:
```yaml
---
title: 文章标题
date: 2024-05-22 10:00:00
tags: [标签1, 标签2]
categories: [分类]
keywords: [标签1, 标签2]
---
```

### 2026-05-21 v1.2.0 - 本地图片迁移与格式优化

**修改内容**:
- `source/_posts/` - 所有文章按发布时间重新排序并重命名 (1.md ~ 168.md)
- `source/images/` - 新增本地图片文件夹 (906张 WebP/GIF 图片)
- `source/images/` - 图片从远程 CDN 迁移到本地
- `source/images/` - PNG/JPG/JPEG 图片转换为 WebP 格式
- `source/images/` - 移除所有 `-m` 后缀的图片文件名
- `source/images/` - 图片压缩优化 (193MB → 121MB)
- `source/_posts/` - 移除所有文章中的"资源加速"内容
- `source/_posts/` - 所有标题层级统一调整 (h4→h3, h3→h2, h2不变)

**清理内容**:
- 移除所有文章中的 `{% gi %}` / `{% endgi %}` 图库标签 (4篇文章)
- 移除所有文章中的 `{% fold %}` / `{% endfold %}` 折叠标签 (9篇文章)
- 移除所有文章中的"资源加速"相关引用 (26篇文章)
- 删除旧文章 165, 168 (共2篇)

**功能说明**:
- 图片本地化：所有文章图片从 `https://img.pknote.top/blog/` 迁移到本地 `/images/` 目录
- 格式统一：所有图片转换为 WebP 格式（GIF 除外），体积减少约 37%
- 标题规范：三级标题改为二级，四级标题改为三级

### 2026-05-21 v1.1.0 - 文章排序与 404 页面

**修改文件**:
- `source/_posts/` - 所有文章按发布时间重新排序并重命名 (1.md ~ 168.md)
- `themes/Chic/layout/404.ejs` - 新增 404 页面
- `themes/Chic/source/css/_page/404.styl` - 404 页面样式
- `themes/Chic/source/css/style.styl` - 引入 404 样式
- `themes/Chic/layout/_page/post.ejs` - 修复评论框位置冲突
- `themes/Chic/source/css/_page/_post/post_nav.styl` - 修复文章导航浮动问题
- `_config.yml` - 新增 `post_copyright_enable` 配置

**功能说明**:
- 文章按发布时间的倒序重新排序并重命名为数字编号 (1~168)
- 新增自定义 404 页面，包含返回首页和返回上一页按钮
- 修复文章页上一页/下一页与评论框位置冲突问题

### 2026-05-21 - Waline 评论系统集成

**修改文件**:
- `themes/Chic/layout/_page/post.ejs` - 添加 Waline 评论组件
- `themes/Chic/_config.yml` - 添加 Waline 配置选项
- `themes/Chic/README.md` - 更新文档说明

**功能说明**:
- 在文章页底部添加 Waline 评论区
- 使用 @waline/client@2 CDN
- 支持暗色模式
- 配置地址: https://waline.windowsplus.cn/

**配置方法** (`themes/Chic/_config.yml`):
```yaml
# Waline Comment System
waline:
  enable: true
  serverURL: https://waline.windowsplus.cn/
  darkMode: true
```

## npm 脚本命令

| 命令 | 说明 |
|------|------|
| `npm run build` | 生成静态网站 |
| `npm run clean` | 清理缓存和 public 目录 |
| `npm run deploy` | 部署网站 |
| `npm run server` | 启动本地服务器 |

## 部署说明

1. 运行 `npm run clean && npm run build` 生成静态文件
2. 将 `public` 目录内容部署到服务器
3. 或使用 `npm run deploy` (需配置 deploy 参数)

## 注意事项

- `public/` 目录由 `.gitignore` 忽略，不需要提交
- 数据库文件 `db.json` 由 `.gitignore` 忽略
- 主题修改已通过 git 跟踪