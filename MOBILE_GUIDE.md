# 📱 安卓手机端完整操作指南

## 你现在的情况

你的仓库 `Lucky090820.github.io` 里放的是 Hexo 构建后的**静态文件**（HTML/CSS/JS），
现在要改成放**源码**，让 GitHub Actions 自动构建部署。

---

## 🔄 一次性迁移操作

### 第 1 步：清空仓库（保留 .git）

在 Termux 或电脑上执行：
```bash
cd Lucky090820.github.io
rm -rf * .* 2>/dev/null || true
# 保留 .git 目录
```

如果只用电���浏览器，那就：
1. 进仓库 Settings → 最底下 Danger Zone → Delete repository
2. 重新建一个同名仓库 `Lucky090820.github.io`

### 第 2 步：上传本包的所有文件

把 `hexo-blog-source/` 里的所有文件和文件夹，
按相同结构上传到 GitHub 仓库根目录。

⚠️ 注意：以 `.` 开头的文件和文件夹（如 `.github/`、`.gitignore`）
在 GitHub 网页上创建时，直接输入完整名称即可。

### 第 3 步：开启 GitHub Pages (Actions 模式)

1. 仓库 → **Settings** → **Pages**
2. **Source** → 选 **GitHub Actions**
3. 点 **Save**

### 第 4 步：等 1-2 分钟

打开 **Actions** 标签页，看到绿色 ✅ 就成功了！
访问 `https://Lucky090820.github.io` 看效果。

---

## ✍️ 以后写文章（纯手机浏览器）

### 方法：GitHub 网页直接新建文件

1. 打开仓库 `github.com/Lucky090820/Lucky090820.github.io`
2. 进 `source/_posts/` 目录
3. 点右上角 **Add file → Create new file**
4. 文件名填：`我的新文章.md`
5. 内容写：

```markdown
---
title: 我的新文章
date: 2026-07-23
tags: [生活, 随笔]
categories: 日常
---

正文写这里...

## 小标题

内容内容内容
```

6. 拉到底 → **Commit changes**
7. 等 1-2 分钟 → 博客自动更新 ✨

---

## 🖼️ 如何上传图片

### 头像
1. 进 `source/img/avatar/` 目录
2. 点 **Add file → Upload files**
3. 上传你的头像图片，命名为 `avatar.jpg`
4. Commit → 自动生效

### 封面图
1. 进 `source/img/banner/`
2. 上传封面大图，命名为 `banner.jpg`
3. 推荐尺寸 1920×1080

---

## 🎨 如何修改主题配置

### 改社交链接
1. 打开仓库根目录的 `_config.anzhiyu.yml`
2. 点铅笔图标 ✏️ 编辑
3. 找到 `social:` 部分，加上你的链接：

```yaml
social:
  Github: https://github.com/Lucky090820 || anzhiyu-icon-github
  BiliBili: https://space.bilibili.com/你的UID || anzhiyu-icon-bilibili
  QQ: tencent://Message/?Uin=你的QQ号 || anzhiyu-icon-qq
```

4. Commit → 等 1 分钟生效

### 改首页打字机文字
找到 `typed:` 部分，改 `strings:` 里的内容

### 改主题色
找到 `theme_color:` 部分，改 `main:` 和 `dark_main:` 的值

---

## 🔧 常见问题

**Q: Actions 显示红色 ❌ 失败了？**
A: 点进去看日志，最常见的原因：
- `package.json` 格式错误（检查有没有多余的逗号）
- 主题名称写错

**Q: 图片不显示？**
A: 检查图片路径，Markdown 里用 `/img/xxx.jpg` 引用

**Q: 怎么在手机上预览效果？**
A: 暂时只能 push 后看线上效果。或者用 Termux 本地跑 `hexo server`

**Q: 想加评论功能？**
A: 推荐 Waline（免费），需要额外注册服务，配好后改 `_config.anzhiyu.yml` 里的 `comment` 部分

---

## 📂 最终仓库结构

```
Lucky090820.github.io/
├── .github/workflows/deploy.yml    ← 自动部署
├── source/
│   ├── _posts/                     ← 文章放这里
│   │   ├── hello-world.md
│   │   └── my-first-post.md
│   ├── css/custom.css              ← 自定义样式
│   ├── img/
│   │   ├── avatar/avatar.jpg       ← 头像（你上传）
│   │   └── banner/banner.jpg       ← 封面（你上传）
│   ├── about/index.md              ← 关于页面
│   ├── categories/index.md
│   ├── tags/index.md
│   └── archives/index.md
├── scaffolds/
├── .gitignore
├── _config.yml                     ← Hexo 根配置
├── _config.anzhiyu.yml             ← 主题配置
├── package.json                    ← 依赖声明
├── manifest.json                   ← PWA 配置
└── README.md
```

---

**祝你博客搭建顺利！有问题随时问我 🎉**
