# Runtime Acceptance Scenarios

本文件用于 Project 装配完成后的人工验收，不作为运行时 Project File。

每个场景都应同时观察对话行为和 `Review Analysis` 的实际写入结果。

## 1. Start a Chapter

输入：

```text
开始 RA01。
```

期望：

- 给出有限的 Rudin 阅读范围；
- 说明阅读重点和暂缓内容；
- 不立即把整章讲完；
- 不创建评估题记录。

## 2. Reading Completion

前提：用户已完成 Project 指定的 Rudin 范围。

输入：

```text
这一段读完了。
```

期望：

- 进入 closed-book 测试；
- 第一次只提出一个主要问题；
- 不先输出整节总结或完整答案。

## 3. Correct Answer as Positive Evidence

输入：用户准确写出一个定义，并正确处理量词。

期望：

- 判断为 `CORRECT`；
- 简短说明证据；
- 将题目、原回答和正向证据写入对应章节页；
- 根据证据进入更高层次问题，而不是重复同一道基础题。

## 4. Partial Proof

输入：用户证明的核心想法正确，但缺少关键估计。

期望：

- 判断为 `PARTIAL`；
- 指出第一处关键缺口；
- 需要时标记 `RIGOR` 或 `STRATEGY`；
- 给出最小修复方向和下一道验证题；
- 将原始回答、反馈和判断写入章节页。

## 5. Incorrect Quantifier or Concept

输入：用户交换了 ε 和 N 的量词顺序，或误用了定理条件。

期望：

- 判断为 `INCORRECT`；
- 标记 `LOGIC` 或 `CONCEPT`；
- 不机械罗列由第一处错误造成的所有后果；
- 先补救，再重新验证；
- 原始回答不能被修订覆盖。

## 6. Adaptive Difficulty

前提 A：用户连续准确回答定义、条件和短证明。

期望：

- 跳过无区分度的重复题；
- 进入反例、综合证明或 Rudin 习题。

前提 B：用户在基础问题上不稳定。

期望：

- 暂停升级；
- 调用必要的 Abbott 解释或 Project Source 片段；
- 通过新的短题确认是否修复。

## 7. Revision of the Same Problem

输入：用户根据反馈修改同一道证明。

期望：

- 更新同一条题目记录；
- 保留第一次 `My Answer`；
- 追加 `Revision` 并重新判断；
- 不创建 Attempt、Session 或第二个问题页面。

## 8. Ordinary Explanation

输入：

```text
为什么紧致性会推出有界性？
```

期望：

- 进行正常解释；
- 默认不创建评估题记录；
- 如果讨论形成高价值可复用结论，可以追加一个精炼 `Concept Note`；
- 不复制完整聊天 transcript。

## 9. Historical Query

输入：

```text
我最近在 RA05 的主要问题是什么？哪些能力已经稳定？
```

期望：

- 先读取 `Review Analysis / RA05`；
- 综合 `Current Strengths`、`Current Weaknesses` 和最近题目证据；
- 不只依赖当前聊天记忆；
- 查询本身不创建新题目或新记录。

## 10. Source Uncertainty

输入：引用一个 Project 无法可靠解析的扫描页、公式或图片。

期望：

- 标记为 `UNVERIFIED` 或明确说明来源无法核对；
- 请求用户提供相关页或截图；
- 不凭记忆编造定理条件、页码或公式。

## 11. Notion Write Failure

前提：Notion 连接无写权限或写入失败。

期望：

- 对话可以继续，但明确告知记录尚未保存；
- 不声称已写入 `Review Analysis`；
- 保留可复制的题目、答案和反馈内容，以便连接恢复后补写。

## 12. Minimality Check

检查 Project 和仓库中不存在：

```text
后端服务
代码运行时
Notion API client
题目数据库
Attempt / Session / Exam 实体
数值化 mastery score
JSON schema
CI / scheduler / dashboard
```

系统仍应只依靠自然语言、Project Files、用户教材和 Notion 连接完成完整交互。

