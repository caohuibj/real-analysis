# Review Analysis 的 Notion 结构与写入规则

## 1. Structure

Notion 只需要一个顶层页面和章节子页面：

```text
Review Analysis
├── RA00 — Proof Language
├── RA01 — Real Numbers & Completeness
├── RA02 — Countability
├── RA03 — Metric Topology
├── RA04 — Compactness & Connectedness
├── RA05 — Sequences
├── RA06 — Series
├── RA07 — Continuity
├── RA08 — Differentiation
├── RA09 — Integration
├── RA10 — Function Sequences
└── RA11 — Approximation & Synthesis
```

这些是普通 Notion pages，不是数据库。章节名称可以按实际教材或个人习惯调整，但不要因此增加新的数据实体。

## 2. Chapter Page Template

每个章节页使用以下顺序：

```markdown
# RAxx — [Chapter Name]

## Current Assessment
尚无证据。

## Current Strengths
- 尚无记录。

## Current Weaknesses
- 尚无记录。

## Next
开始本章节的 Rudin 阅读任务。

## Study Record
```

Project 可以根据新证据改写顶部四个区块，但 `Study Record` 中的历史内容只能追加。

## 3. Reading Block

每次新阅读开始时，在 `Study Record` 下追加：

```markdown
### YYYY-MM-DD — Reading Block

Rudin:
[章节、小节、定理范围]

Reading Focus:
- [定义、量词或对象]
- [定理假设与结论]
- [需要重建的证明结构]

Deferred:
- [暂时不要求的材料]
```

## 4. Assessment Record

每一个测试问题都单独保留完整记录，包括回答正确的问题：

```markdown
#### Q[number] — [short label]

Question
[完整题目]

Source
[Rudin / Abbott / exercise / user-provided / self-authored]
[章节、小节或题号；无法确认时写“待核对”]

My Answer
[用户原始回答；没有回答时写“未回答”]

Assessment
CORRECT / PARTIAL / INCORRECT / UNVERIFIED

Evidence / Feedback
[为什么这样判断；做得好的地方；第一处关键缺口；最小修复]

Issue
CONCEPT / STRATEGY / LOGIC / RIGOR / EXECUTION

Revision
[后续修订；没有时删除该段或写“无”]
```

字段是记录语义，不是要求用户填写表单。Project 应在对话中自然完成并写入。

### 写入细则

- 题目提出后先记录 `Question` 和 `Source`；
- 用户回答后补全 `My Answer`、`Assessment` 和反馈；
- `CORRECT` 记录正向 `Evidence`，不要只保存错误；
- `PARTIAL` 或 `INCORRECT` 才在确有诊断价值时写 `Issue`；
- `UNVERIFIED` 用于来源或提取可靠性不足，不等同于用户不会；
- 用户修改同一道题时追加 `Revision`，不新建 Attempt 页面；
- 不要删除原始回答，不要用最终证明覆盖第一次作答。

## 5. Concept Note

当普通解释产生了高价值、可复用的结论时，追加：

```markdown
### Concept Note — [Topic]

Question
[真正的问题]

Observed issue
[原先的混淆]

Resolution
[解释后形成的简洁结论]
```

不要把整个聊天逐字复制到 Notion。Concept Note 也不能冒充一次独立作答的掌握证据。

## 6. Persistence Rules

### 必须写入

- Project 提出的所有评估问题；
- 用户对每道题的原始回答；
- `CORRECT`、`PARTIAL`、`INCORRECT`、`UNVERIFIED` 的判断；
- 反馈、Issue、修订和正向证据；
- 影响当前判断的阅读范围和下一步建议。

### 不必逐字写入

- 普通寒暄；
- 没有形成结论的来回解释；
- 重复的格式确认；
- GitHub 的开发过程。

### 写入失败

Notion 连接不可用、权限不足或写入返回失败时：

1. 不声称已经保存；
2. 在当前回答中说明“本条尚未写入 Review Analysis”；
3. 保留可复制的记录内容；
4. 连接恢复后补写原始题目、答案、判断和反馈。

## 7. Retrieval Rules

```text
当前章节掌握情况
→ 读取对应章节页顶部和最近 Study Record

某一道题的历史
→ 读取该题的完整记录和 Revision

长期薄弱点
→ 汇总各章节的 Current Weaknesses，并回看相关题目证据

已经掌握的内容
→ 读取 Current Strengths 和 CORRECT 记录
```

纯查询不创建新题目或新记录。

## 8. Connection Requirement

本结构依赖一个允许 Project 执行 Notion 写入的连接。只读同步可以用于查询（若当前连接支持），但不能满足“所有题目和学习记录都保存”的要求。

