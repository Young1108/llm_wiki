# Wiki 日志

记录本 wiki 中发生过的所有操作。默认使用追加式记录。

**格式：** `## [YYYY-MM-DD] <类型> | <标题>`
**推荐类型：** `初始化` · `摄取` · `问答` · `巡检` · `规范更新`

查看最近日志可使用：`rg "^## \\[" log.md`

---

## [2026-04-15] 摄取 | LLM Wiki：一种用于个人知识库的模式

- 来源文件：`raw/llm-wiki.md`
- 摘要页面：[[sources/llm-wiki|LLM Wiki：一种用于个人知识库的模式]]
- 新建页面：
  - [[concepts/persistent-wiki-pattern|持久化 Wiki 模式]] - 核心模式
  - [[concepts/rag|RAG（检索增强生成）]] - 作为对照的主流方案
  - [[concepts/knowledge-compounding|知识复利]] - 该模式的关键性质
  - [[entities/obsidian|Obsidian]] - 推荐的浏览工具
  - [[entities/vannevar-bush|范内瓦·布什]] - Memex 的历史参照
- 更新页面：[[overview|总览]]、[[index|Wiki 索引]]
- 关键新增判断：
  - 持久化 wiki 会把知识预先编译并持续维护；RAG 则在每次提问时重新推导
  - 一次摄取通常会触达 10-15 个页面；有价值的问答也可以回写为新页面
  - 布什在 1945 年提出的 Memex 已经具备类似愿景，但未解决维护成本问题；LLM 解决了这一点
- 待继续研究：
  - `index.md` 适用于多大规模，何时需要搜索引擎
  - 与其他 PKM 体系的比较
  - 该模式的失效边界与退化方式

---

## [2026-04-15] 初始化 | Wiki 初始化

- 已创建目录结构：`raw/`、`raw/assets/`、`wiki/`
- 已写入规范文件：`AGENTS.md`
- 已创建目录文件：`wiki/index.md`
- 已开始记录日志：`wiki/log.md`
- 当前状态：可以开始摄取第一个来源

---

## [2026-04-15] 规范更新 | 全库改为中文写作

- 已将 `wiki/` 下现有页面内容统一翻译为中文
- 已将 `AGENTS.md` 更新为中文规范
- 后续默认使用简体中文进行摘要、分析、日志与问答沉淀
- 文件名、slug、`type`、`sources`、`related` 等结构标识保持英文稳定
