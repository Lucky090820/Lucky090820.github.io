# Lucky's Hexo Blog (AnZhiyu Theme)

## 目录结构说明

```
Lucky090820.github.io/
├── .github/
│   └── workflows/
│       └── deploy.yml          ← GitHub Actions 自动部署
├── scaffolds/                   ← 文章模板（可留空，Actions 会处理）
├── source/
│   ├── _posts/
│   │   ├── hello-world.md       ← 示例文章1
│   │   └── my-first-post.md     ← 示例文章2
│   ├── css/
│   │   └── custom.css           ← 自定义样式
│   ├── img/
│   │   ├── avatar/              ← 放头像
│   │   └── banner/              ← 放封面图
│   └── about/
│       └── index.md             ← 关于页面
├── _config.yml                  ← Hexo 根配置
├── _config.anzhiyu.yml          ← 主题配置
├── package.json                 ← 依赖声明（Actions 自动 npm install）
├── .gitignore                   ← 忽略 node_modules 等
└── README.md
```

## 快速开始

### 方式一：GitHub Actions 自动部署（推荐）

1. 把整个仓库内容 push 到 GitHub
2. Settings → Pages → Source 选 "GitHub Actions"
3. 以后只需要在 `source/_posts/` 里添加 .md 文件
4. push 后自动构建部署，1-2 分钟上线

### 方式二：本地构建（Termux / 电脑）

```bash
npm install
npx hexo clean && npx hexo generate
# 产物在 public/ 目录
```

## 写文章

在 `source/_posts/` 下新建 `.md` 文件：

```markdown
---
title: 文章标题
date: 2026-07-23
tags: [标签1, 标签2]
categories: 分类名
cover: /img/banner/banner.jpg
---

正文内容写这里...
```

## 修改主题配置

编辑 `_config.anzhiyu.yml`，常用项：
- `theme_color` → 配色
- `darkmode` → 暗黑模式
- `menu` → 导航菜单
- `social` → 社交链接
- `typed.strings` → 首页打字机文字
- `live2d` → 看板娘开关和模型

## 自定义样式

编辑 `source/css/custom.css`，改完自动生效。
