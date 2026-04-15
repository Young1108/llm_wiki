---
title: "LLM Wiki：一种用于个人知识库的模式"
type: source
tags: [知识管理, llm, wiki, rag, obsidian]
created: 2026-04-15
updated: 2026-04-15
sources: [llm-wiki]
related: [persistent-wiki-pattern, rag, knowledge-compounding, obsidian, vannevar-bush]
---

# LLM Wiki：一种用于个人知识库的模式

**来源文件：** `raw/llm-wiki.md`  
**文档类型：** 思路 / 模式说明文档（面向 LLM Agent 的指导文本）  
**作者：** 未知（使用第一人称写作，带有个人实践视角）  
**时间：** 约 2026 年

---

## 这篇文档在讲什么

它提出了一种使用 LLM Agent 来 **构建并维护持久化个人知识库** 的设计模式。这里的知识库不是临时检索结果，而是一组由 LLM 持续整理和更新的 Markdown 页面。与把 LLM 仅当作查询时的 [[concepts/rag|RAG（检索增强生成）]] 检索器不同，这种模式强调“先整合，再回答”。

---

## 关键主张 / 核心发现

- **RAG 会在每次提问时重新推导知识。** 它不会自然积累结果。需要跨 5 篇以上文档做细腻综合的问题，成本高且不稳定。
- **Wiki 是一个持久、可复利的中间层。** 页面之间的交叉引用、矛盾标注和阶段性综合会被提前编译并持续维护，而不是每次提问时临时拼接。
- **整体由三层构成：** 原始来源（不可变）→ wiki（由 LLM 维护）→ schema（如 `AGENTS.md` 这样的工作规范）。
- **有三类核心操作：** 摄取来源、回答问题、健康巡检。一次摄取通常会触达 10-15 个页面。
- **人类的职责是：** 筛选来源、提出好问题、思考意义。**LLM 的职责是：** 总结、归档、交叉引用、维护一致性。
- **这个 wiki 本质上只是一个 Markdown 仓库。** 可以天然享受 Git 的版本管理、分支与协作能力。
- **问答结果也应沉淀回 wiki。** 有价值的比较、分析和洞见不应消失在聊天记录里，而应成为新的长期页面。
- **有两个关键索引文件：** `index.md` 负责内容导航，`log.md` 负责时间线记录。
- **它与 [[entities/vannevar-bush|范内瓦·布什]] 的 Memex 愿景有明显亲缘关系。** 区别在于，Memex 没解决维护成本，而 LLM 恰好解决了这件事。[高]

---

## 值得保留的原文引述

> "The wiki is a persistent, compounding artifact. The cross-references are already there. The contradictions have already been flagged. The synthesis already reflects everything you've read."

这句话概括了该模式的核心优势：知识不是每次都重新推导，而是被预先组织、持续增量维护。

> "Humans abandon wikis because the maintenance burden grows faster than the value. LLMs don't get bored, don't forget to update a cross-reference, and can touch 15 files in one pass."

这句点出了为什么传统 wiki 容易半途而废，也解释了为什么 LLM 在这个场景里有结构性优势。

> "The human's job is to curate sources, direct the analysis, ask good questions, and think about what it all means. The LLM's job is everything else."

这是本模式对“人机分工”的最清晰定义。

> "In practice, I have the LLM agent open on one side and Obsidian open on the other. The LLM makes edits based on our conversation, and I browse the results in real time. Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase."

这句话提供了非常具体的操作画面，也基本定义了本 wiki 的工作方式。

---

## 文档提到的应用场景

1. **个人场景** - 目标管理、健康、心理、自我成长；把日记、文章、播客笔记组织起来
2. **研究场景** - 持续数周或数月地追踪一个主题，并形成不断演进的论点
3. **读书场景** - 按章节整理内容，建立角色、主题、情节与关联页面
4. **团队 / 商业场景** - 用 Slack、会议纪要、客户访谈等持续喂养内部 wiki
5. **其他场景** - 竞品分析、尽调、旅行规划、课程笔记、兴趣专题等

---

## 文档中提到的工具

| 工具 | 角色 |
|------|------|
| [[entities/obsidian|Obsidian]] | 浏览与可视化 wiki；可使用图谱、Dataview、Marp 插件 |
| Obsidian Web Clipper | 浏览器扩展；把网页转成 Markdown 后放进 `raw/` |
| qmd | 本地 Markdown 搜索引擎；支持 CLI 与 MCP，可在规模增长后接管检索 |
| Marp | Markdown 幻灯片格式；适合把分析直接转成演示稿 |
| Dataview | 基于 frontmatter 做查询与动态列表展示 |
| Git | 为整个 wiki 提供版本历史与协作能力 |

---

## 文档提出的开放问题

- `index.md` 这种基于目录页的导航在多大规模下会失效，并需要 qmd 之类搜索引擎接手？
- 多模态来源（带图 PDF、音频转录等）应该如何更系统地处理？
- wiki 页面最合适的粒度是什么？太细会造成噪音，太粗又会丢失交叉引用价值。
- 这种模式与 Roam、Logseq、Zettelkasten 等个人知识管理体系相比，有何本质区别？

---

## 与当前 wiki 的关系

这是本知识库的 **创始来源**。它不仅提供了核心思想，也定义了当前这个 wiki 自己正在遵循的工作方式。
