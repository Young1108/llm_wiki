# LLM Wiki（中文知识库）

个人知识库，由 LLM Agent 负责构建和维护。你负责提供来源和提问，Agent 负责所有整理、交叉引用和更新工作。

默认情况下，`wiki/` 下的页面、摘要、问答沉淀、日志与综述都使用简体中文；`raw/` 中的原始来源保持原文不动。

---

## 目录结构

```
LLM wiki/
├── AGENTS.md          ← Agent 工作规范（核心配置文件）
├── README.md          ← 本文件
├── raw/               ← 原始来源文档（不可修改）
│   └── assets/        ← 本地下载的图片
└── wiki/              ← Agent 生成和维护的知识库
    ├── index.md       ← 所有页面的目录
    ├── log.md         ← 操作日志（只追加）
    ├── overview.md    ← 整体综述
    ├── sources/       ← 每个来源的摘要页
    ├── entities/      ← 人物、组织、产品、地点等
    ├── concepts/      ← 概念、框架、方法论等
    └── analyses/      ← 比较分析、深度研究等
```

---

## 工作流

### 添加新来源（Ingest）

1. 将文件放入 `raw/`（支持 .md、.pdf、.txt、图片等）
2. 告诉 Agent：`ingest [文件名]` 或 `请处理 raw/xxx.md`
3. Agent 将：读取来源 → 与你讨论要点 → 写摘要页 → 更新所有相关实体/概念页 → 更新 index.md → 在 log.md 中记录

### 提问（Query）

直接提问即可。Agent 会先读 `wiki/index.md` 找相关页面，并默认用中文综合答复；如答案值得长期保留，会询问是否将其存入 `wiki/analyses/`。

### 健康检查（Lint）

告诉 Agent：`lint` 或 `检查 wiki 健康状态`。Agent 将检查矛盾、孤立页面、缺失交叉引用等问题。

---

## 推荐工具

- **Obsidian** — 用于浏览和可视化 wiki（打开 `LLM wiki/` 文件夹作为 Vault）
  - 启用 **Graph View** 查看页面连接关系
  - 安装 **Dataview** 插件以查询 frontmatter
  - 安装 **Marp** 插件以渲染幻灯片
- **Obsidian Web Clipper** — 浏览器扩展，将网页转为 markdown 保存到 `raw/`
- **Git** — wiki 是普通 markdown 文件，可用 git 做版本管理

---

## 核心原则

- `raw/` 下的文件**不可修改**，是唯一的事实来源
- `wiki/` 下的所有内容由 Agent 全权负责，你只负责阅读
- `log.md` 只追加，永不编辑历史记录
- `index.md` 在每次操作后立即更新
- 文件名、slug 与 frontmatter 的结构字段保持稳定；中文化主要发生在标题、正文、摘要和日志内容中

---

_基于 [Andrej Karpathy: llm-wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) 模式构建。_

_v2拓展： [Andrej Karpathy: llm-wiki](https://github.com/nashsu/llm_wiki) `_

_其他wiki： [nashsu: llm-wiki](https://github.com/nashsu/llm_wiki) `_
