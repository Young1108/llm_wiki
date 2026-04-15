---
title: "总览"
type: overview
tags: [知识管理, llm, wiki]
created: 2026-04-15
updated: 2026-04-15
sources: [llm-wiki]
related: [persistent-wiki-pattern, rag, knowledge-compounding, obsidian]
---

# 总览

本 wiki 聚焦于一种由 **LLM 持续维护的个人知识库模式**。与主流的 [[concepts/rag|RAG（检索增强生成）]] 不同，这种方式不把 LLM 仅仅当作“对原文做检索后即时回答”的工具，而是让它持续构建和维护一个结构化、可交叉引用、可长期演化的知识库。

---

## 核心论点

主流的 LLM 文档问答模式存在一个关键缺陷：每次提问都要从头重新推导知识，结果无法累积。相比之下，[[concepts/persistent-wiki-pattern|持久化 Wiki 模式]] 让 LLM 逐步构建互相链接的页面网络，把新来源整合进既有页面中，让知识随着每次摄取和提问而不断形成 **复利**。

这一模式真正成立的关键在于：人类最不愿长期承担的那部分工作，例如整理、交叉引用、更新摘要、标记冲突，恰好是 LLM 非常擅长且边际成本极低的工作。

---

## 当前知识库状态

**已摄取来源：** 1  
**已建立页面：** 7  
**最近一次摄取：** 2026-04-15 - `llm-wiki.md`（创始来源）

### 已建立的核心概念
- [[concepts/persistent-wiki-pattern|持久化 Wiki 模式]] - 本知识库当前的中心主题
- [[concepts/rag|RAG（检索增强生成）]] - 主要的对照方案，也是行业默认范式
- [[concepts/knowledge-compounding|知识复利]] - 这一模式最重要的价值机制

### 已建立的关键实体
- [[entities/obsidian|Obsidian]] - 推荐的浏览与可视化工具
- [[entities/vannevar-bush|范内瓦·布什]] - Memex 概念的历史前驱

---

## 待继续研究的问题

- 持久化 Wiki 模式与其他 PKM 体系（Roam、Logseq、Zettelkasten）相比，有哪些本质差别？
- `index.md` 目录导航在多大规模下会失效？引入 qmd 之类搜索工具的阈值是什么？
- 多模态来源（带图 PDF、音频、视频转录）有哪些更好的处理方式？
- 现实中是否已经有可参考的落地案例？
- 这种由 LLM 维护的 wiki 会在什么情况下退化或失真？

---

## 后续观察主题

随着更多来源被摄取，这个总览页将持续记录新的主题、关键张力、主要共识以及仍未解决的问题。
