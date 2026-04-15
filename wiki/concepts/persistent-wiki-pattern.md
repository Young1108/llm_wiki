---
title: "持久化 Wiki 模式"
type: concept
tags: [知识管理, llm, wiki, 模式]
created: 2026-04-15
updated: 2026-04-15
sources: [llm-wiki]
related: [rag, knowledge-compounding, obsidian, vannevar-bush]
---

# 持久化 Wiki 模式

这是一种面向个人或团队知识管理的设计模式：让 LLM Agent **持续增量地构建和维护一个结构化 wiki**，而不是只在用户提问时临时去原始文档里做检索和回答。

---

## 核心思想

大多数“LLM + 文档”的系统本质上都在使用 [[concepts/rag|RAG（检索增强生成）]]：先在提问时检索相关片段，再据此生成答案，最后把中间工作全部丢掉。这样做的结果是，知识不会沉淀，LLM 每次都要重新从头拼装答案。

持久化 Wiki 模式完全不同。新的来源到来时，LLM 不只是“索引一下”，而是会：

- 读取并理解来源
- 写一页结构化摘要
- 把新信息整合进既有实体页与概念页
- 标出它与旧主张之间的矛盾
- 更新整体综合判断

最终形成的不是一次性答案，而是一个 **不断复利增长的知识中间层**：来源越多、提问越多，wiki 越丰富。[高]

---

## 三层结构

| 层级 | 说明 | 谁负责 |
|------|------|--------|
| **原始来源** | 不可修改的输入材料，如文章、论文、笔记、图片 | 人类负责提供 |
| **Wiki** | 由 LLM 生成和维护的摘要、实体页、概念页、分析页 | LLM 负责维护 |
| **Schema** | 用 `AGENTS.md` 这类文件定义结构、约定与工作流 | 人类与 LLM 共同演化 |

---

## 三类操作

**摄取** - 处理新的来源。一次摄取通常会生成 1 个来源摘要页，并同时更新多页相关实体与概念内容；如有冲突，需直接标注。

**问答** - 基于现有 wiki 回答问题。先读 `index.md` 找页面，再综合回答并附引用。若回答本身有长期价值，应回写到新的分析页中，让探索本身也形成沉淀。

**巡检** - 定期健康检查。寻找矛盾、过时内容、孤儿页、缺失页面、缺失交叉链接和信息空白。由于 LLM 的维护成本极低，这类巡检可以频繁进行。[高]

---

## 为什么这个模式成立

> "Humans abandon wikis because the maintenance burden grows faster than the value. LLMs don't get bored, don't forget to update a cross-reference, and can touch 15 files in one pass." - [[sources/llm-wiki|LLM Wiki：一种用于个人知识库的模式]]

知识管理真正让人放弃的，通常不是阅读或思考，而是后续维护：补链接、改摘要、同步多个页面、记录矛盾。这部分工作会随着页面数增长而迅速膨胀。LLM 正好把这部分成本压到极低，因此 wiki 才有机会真正长期活下去。

---

## 人类与 LLM 的分工

| 人类 | LLM |
|------|-----|
| 选择和提供来源 | 总结并提取关键信息 |
| 提出好问题 | 建立交叉引用并归档答案 |
| 思考这些信息意味着什么 | 维护多页之间的一致性 |
| 浏览和探索 wiki | 发现并标注矛盾 |
| 指引分析方向 | 更新索引和日志 |

---

## 一个非常贴切的比喻

> "Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase." - [[sources/llm-wiki|LLM Wiki：一种用于个人知识库的模式]]

人在 Obsidian 中实时浏览知识库结构和内容，LLM 则像程序员一样持续修改文件。两者配合起来，知识库就像一个被不断重构和扩展的代码库。

---

## 历史背景

这一模式与 [[entities/vannevar-bush|范内瓦·布什]] 在 1945 年提出的 Memex 在精神上高度相似：都是个人维护的知识储存系统，都强调文档之间的关联路径。不同之处在于，布什时代无法解决维护成本，而今天 LLM 让这件事变得现实。

---

## 相关概念

- [[concepts/rag|RAG（检索增强生成）]] - 当前最主要的对照方案
- [[concepts/knowledge-compounding|知识复利]] - 该模式最关键的结果性质
- [[entities/obsidian|Obsidian]] - 推荐的浏览与可视化工具
