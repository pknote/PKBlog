# 赛博胖氪 - Hexo Blog Project

## 项目信息

- **名称**: 赛博胖氪
- **域名**: https://www.windowsplus.cn/
- **主题**: Chic (自定义版本)
- **Hexo版本**: 8.1.2
- **Node版本**: 6.0+

## 目录结构

```
D:\CyberPK\
├── .claude/          # Claude Code 配置
├── .github/          # GitHub 配置
├── _config.yml       # Hexo 站点配置
├── db.json           # Hexo 数据库
├── package.json      # 项目依赖
├── source/           # 站点源文件
│   ├── _posts/       # 博客文章
│   ├── about/        # 关于页面
│   ├── category/     # 分类页面
│   └── tag/          # 标签页面
├── themes/           # 主题
│   └── Chic/         # Chic 主题 (本地修改版)
└── public/           # 生成的静态文件 (由 .gitignore 忽略)
```

## 最近修改内容

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

## 依赖插件

- hexo@8.1.2
- hexo-generator-archive
- hexo-generator-baidu-sitemap
- hexo-generator-category
- hexo-generator-feed
- hexo-generator-index
- hexo-generator-sitemap
- hexo-generator-tag
- hexo-renderer-ejs
- hexo-renderer-marked
- hexo-renderer-stylus
- hexo-server

## 部署说明

1. 运行 `npm run clean && npm run build` 生成静态文件
2. 将 `public` 目录内容部署到服务器
3. 或使用 `npm run deploy` (需配置 deploy 参数)

## 注意事项

- `public/` 目录由 `.gitignore` 忽略，不需要提交
- 数据库文件 `db.json` 由 `.gitignore` 忽略
- 主题修改已通过 git 跟踪