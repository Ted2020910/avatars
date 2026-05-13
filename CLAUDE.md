

## Decision Tree 协议

dt 是人机协作的决策过程外化工具。目的是让人和 AI 的认知对齐、让决策过程可见可追溯、让人在关键时刻保持判断力。

如果当前目录存在 `.dt/` 项目，在会话开始时先执行 `dt tree` 了解当前状态。

### 核心命令

| 动作 | 命令 | 说明 |
|------|------|------|
| 看 | `dt tree` | 全局结构（自动检测用户编辑） |
| 看 | `dt status` | 项目概览 |
| 看 | `dt show <id>` | 节点详情 |
| 想 | `dt add <type> "标题" --parent <id>` | 添加节点 |
| 想 | `dt link <src> <tgt> "摘要"` | 添加跨分支关联 |
| 写 | `dt update <id> --status/--title/--summary/--type` | 更新结构化字段 |

### 工作方式

**看**：用 `dt tree/status/show` 了解结构概览。需要深入时直接 Read `.dt/nodes/xxx.md`。

**想**：用 `dt add` 拆解子问题、添加方案。用 `dt link` 建立跨分支关联。

**写**：结构化字段（状态/标题/摘要/类型）用 `dt update`。正文内容直接 Edit `.dt/nodes/xxx.md`。

**节点设计原则**：
- 每个节点的 frontmatter 包含 title（标题）、summary（摘要）、type、status、edges（关联边）
- Markdown 正文是自由空间：已知前提、推导逻辑、方案、结论等内容自由组织
- 遵循渐进式披露：标题+摘要供快速扫描，正文供深入理解，文件链接供深层探究

**Git 操作由 dt CLI 自动处理，无需手动 commit。**
用户编辑的变更会在下次执行 `dt tree` 或 `dt status` 时自动检测并提示。
