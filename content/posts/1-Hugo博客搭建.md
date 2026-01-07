+++
date = '2026-01-07T20:27:33+08:00'
draft = false
title = 'Hugo搭建博客'
+++

# 快速搭建博客
## 第一步：安装 Hugo
在 Mac 上，最推荐的方式是使用 Homebrew。
1. 打开 Terminal（终端）。
2. 输入以下命令安装 Hugo：
```
brew install hugo
```
3. 验证安装是否成功：
```
hugo version
```

## 第二步：创建博客项目
1. 在本地选一个文件夹存放博客
```
cd ~/Documents
hugo new site my-blog
cd my-blog
```

2. 初始化 Git 仓库（用于管理主题和后续部署）
```
git init
```

## 第三步：添加 PaperMod 主题
我们使用 Git 子模块（Submodule）的方式添加主题，这样方便以后更新。
1. 下载主题
```
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

2. 在项目根目录找到 hugo.toml（或 config.toml），用 VS Code 或记事本打开，添加一行配置
```
theme = "PaperMod"
```

## 第四步：撰写第一篇文章
1. 使用命令行创建新文章
```
hugo new posts/my-first-post.md
```

2. 此时在 content/posts/ 目录下会生成一个 .md 文件。打开它，你会看到
```
---
title: "My First Post"
date: 2026-01-07T10:00:00+08:00
draft: true
---
这里写你的正文内容。
```
重要提示：draft: true 表示是草稿，预览时默认不显示。你可以改为 false，或者在启动服务器时加上 -D 参数。

## 第五步：本地预览
在终端执行：
```
hugo server -D
```
现在打开浏览器访问 http://localhost:1313，你就能看到你的 PaperMod 博客了！