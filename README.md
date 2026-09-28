# 小虎的博客

这是 [actyoung.github.io](https://actyoung.github.io/) 的源码仓库。站点使用
GitHub Pages 原生支持的 Jekyll 构建，不依赖前端框架或数据库。

## 写一篇文章

在 `_posts` 下创建 `YYYY-MM-DD-slug.md`：

```markdown
---
layout: post
title: "文章标题"
date: 2026-09-28 12:00:00 +0800
description: "一句话摘要，会显示在首页和分享卡片中。"
---

正文使用 Markdown 编写。
```

文件名中的日期决定文章 URL，front matter 中的 `date` 决定页面展示时间。

## 本地预览

Ruby 环境可使用 GitHub Pages 官方依赖预览：

```bash
gem install bundler
bundle install
bundle exec jekyll serve
```

浏览器打开 <http://127.0.0.1:4000>。修改内容后 Jekyll 会自动重新构建。

## 发布

提交并推送到 `master` 分支。GitHub Pages 会构建站点，发布结果可在仓库的
Actions 或 Settings > Pages 中查看。

## 目录

```text
_layouts/       页面与文章布局
_posts/         Markdown 文章
assets/css/     当前站点样式
about.md        关于页
feed.xml        RSS 订阅
sitemap.xml     搜索引擎站点地图
```
