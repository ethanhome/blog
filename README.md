# AI Agent 博客 - Hugo 站点

Hugo 静态站点，部署在 GitHub Pages。

## 本地开发

### 安装 Hugo
```bash
# macOS
brew install hugo

# Linux (已安装)
hugo version

# Windows (Chocolatey)
choco install hugo-extended
```

### 启动开发服务器
```bash
hugo server --buildDrafts
```

访问 http://localhost:1313 查看站点。

### 创建新文章
```bash
# 创建普通文章
hugo new content/posts/article-title.md

# 创建特定栏目文章
hugo new content/history/my-article.md
hugo new content/agents/my-article.md
hugo new content/column/my-article.md
hugo new content/trends/my-article.md
```

## 部署

### GitHub Pages 自动部署

推送到 `main` 分支后，GitHub Actions 会自动构建并部署。

```bash
git add .
git commit -m "Update content"
git push origin main
```

### 手动部署
```bash
# 构建站点
hugo --minify

# public 目录就是构建结果
# 可以部署到任何静态托管服务
```

## 配置

### 修改站点信息
编辑 `hugo.toml`：
- 修改 `baseURL` 为你的 GitHub Pages 地址
- 修改 `title` 为你的博客标题
- 修改菜单和社交链接

### 主题定制
- 主题位于 `themes/PaperMod/`
- 不要直接修改主题文件
- 通过 `hugo.toml` 配置主题选项
- 自定义样式可以创建 `static/css/custom.css`

## 内容组织

```
content/
├── _index.md           # 首页
├── agents/             # 个人助理军团
├── history/            # 发展史
├── column/             # 个人能力培养
├── trends/             # 热点趋势
└── wechat/             # 微信公众号
```

## 文章元数据

每篇文章开头需要包含元数据：

```markdown
---
title: "文章标题"
date: 2026-02-09
draft: false
categories: ["发展史"]
tags: ["GPT", "AI"]
---
```

## 注意事项

1. **子模块**：PaperMod 主题作为 git 子模块管理
   - 克隆时使用 `git clone --recursive`
   - 更新主题：`git submodule update --remote`

2. **图片资源**：放在 `static/images/` 目录

3. **代码高亮**：Hugo 默认支持，使用 ``` 代码块即可

4. **中文支持**：已配置为 `zh-CN`，无需额外设置

## GitHub Pages 设置

1. 在 GitHub 仓库设置中启用 Pages
2. 选择 `gh-pages` 分支作为源
3. 等待 Actions 完成部署

## 相关链接

- [Hugo 文档](https://gohugo.io/documentation/)
- [PaperMod 主题文档](https://github.com/adityatelange/hugo-PaperMod/wiki)
- [GitHub Pages 文档](https://docs.github.com/en/pages)
