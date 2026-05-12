---
id: style-005
root: false
title: Decision 节点 — 多选项对比与结论
summary: 适合需要在多个明确选项之间做出选择的决策场景
type: decision
status: completed
edges:
  - target: style-001
    type: from
    summary: 节点类型说明
created: '2026-05-12T14:48:29.971Z'
---
# Decision 节点 — 多选项对比与结论

Decision 节点用于在已知选项之间做出选择。与 Explore 不同，这里问题已经收敛，核心工作是对比和选择。

常见写法示例：

**决策问题**
需要在什么之间做选择？

**选项**
- 选项 A：优点 / 缺点 / 适用条件
- 选项 B：优点 / 缺点 / 适用条件
- 选项 C：...

**评估标准**
用什么维度来判断哪个更好？

**结论**
选择了什么，理由是什么。

讨论结束后将 status 更新为 decided。
