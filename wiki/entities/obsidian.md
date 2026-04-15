---
title: "Obsidian"
type: entity
tags: [工具, 笔记, markdown, pkm]
created: 2026-04-15
updated: 2026-04-15
sources: [llm-wiki]
related: [persistent-wiki-pattern]
---

# Obsidian

Obsidian 是一款本地优先的 Markdown 笔记应用。在 [[concepts/persistent-wiki-pattern|持久化 Wiki 模式]] 中，它承担的是 **浏览与可视化层** 的角色：LLM 负责编辑文件，你则在 Obsidian 中阅读、跳转、检查结构。

**官网：** https://obsidian.md

---

## 在 LLM Wiki 模式中的角色

> "Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase." - [[sources/llm-wiki|LLM Wiki：一种用于个人知识库的模式]]

一个典型工作方式是：

- 一边开着 LLM Agent，让它持续修改 wiki 文件
- 另一边开着 Obsidian，实时查看页面变化
- 通过链接、图谱和页面内容跟踪知识库的演进

---

## 为什么它特别适合这个模式

### 图谱视图（Graph View）

可以把整个 wiki 以节点关系图的形式可视化出来。哪些页面是枢纽、哪些页面是孤儿页，会一眼看出来。这对于理解知识库结构尤其重要。

### Wikilink

Obsidian 原生支持 `[[page-name]]` 链接语法，这正是本 wiki 的核心交叉引用形式。尚未创建的链接还能作为“待补页面”的提醒。

### Dataview 插件

可以基于 YAML frontmatter 做类似查询的聚合展示，例如“列出所有 `llm` 相关概念页并按更新时间排序”。前提是页面 frontmatter 持续保持结构化。

### Marp 插件

可以把带有 `marp: true` 的 Markdown 页面当作幻灯片渲染，适合把 wiki 内容直接转成展示材料。

---

## 推荐设置

- **Attachment folder path** 设置为 `raw/assets/`，让网页抓取后的图片统一落在原始来源目录下
- 给 **Download attachments for current file** 绑定快捷键，例如 `Ctrl+Shift+D`，便于把文章中的远程图片下载到本地

---

## 相关工具

- **Obsidian Web Clipper** - 浏览器扩展，可将网页直接转成 Markdown 并放入 `raw/`
- **qmd** - 当 wiki 规模超出 `index.md` 纯目录导航能力后，可作为本地搜索引擎补位
