# SinclairLin 的博客

基于 Astro Cactus 配置的个人博客，用来记录技术、折腾与生活。

## 站点配置

核心配置在 `src/site.config.ts`：

- `url`：生产环境域名，当前为 `https://sinclairlin.github.io`
- `title`：站点标题
- `author`：作者名
- `description`：站点简介，会用于 SEO、RSS 和社交分享
- `menuLinks`：顶部和底部导航

如果部署到非根路径，例如 `https://sinclairlin.github.io/my-blog/`，需要在 `astro.config.ts` 增加：

```ts
export default defineConfig({
  site: "https://sinclairlin.github.io",
  base: "/my-blog",
});
```

如果使用自定义根域名，则不需要设置 `base`。

## 写文章

文章放在 `src/content/post/`，支持 Markdown 和 MDX。

示例：

```md
---
title: "我的第一篇文章"
description: "简单介绍一下这篇文章讲什么"
publishDate: "2026-06-25"
tags: ["Astro", "博客"]
---

# 正文开始

这里写文章内容。
```

标签说明可放在 `src/content/tag/`，随记放在 `src/content/note/`。

## 常用命令

| 命令 | 说明 |
| --- | --- |
| `npm install` | 安装依赖 |
| `npm run dev -- --background` | 按项目约定在后台启动开发服务器 |
| `npm run build` | 构建生产站点到 `dist/`，并生成 Pagefind 搜索索引 |
| `npm run preview` | 本地预览生产构建 |
| `npm run check` | 运行 Astro 类型检查和 Biome 检查 |

## 部署检查

- 构建命令：`npm run build`
- 输出目录：`dist`
- Node.js：使用 `.nvmrc` 指定的版本
- 上线前替换 `public/social-card.png` 和 `public/icon.svg`
