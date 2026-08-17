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
└── RA11 — Approximation, Power Series & Special Functions
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

Record State
OPEN / COMPLETE

My Answer
[题目刚提出时写“等待回答”；之后写用户原始回答或真实的跳过、放弃、未回答状态]

Assessment
[原始判断：CORRECT / PARTIAL / INCORRECT / UNVERIFIED；题目刚提出时暂留空]

Feedback
[原始判断的证据、做得好的地方、第一处关键缺口、为什么重要和最小修复]

Issue
CONCEPT / STRATEGY / LOGIC / RIGOR / EXECUTION

Retest
No；如果是有意重复教材题，写 `Retest — [目的]`

Solution Reference
Not consulted；或写“substantive attempt 后核对 / 用户明确要求 reference/full solution 后核对 / unavailable”

Revision
[后续修订；没有时删除该段或写“无”]

Revision Assessment
[对修订后的同一题重新判断]

Revision Feedback
[修订是否修复原缺口，以及新的最小修复]
```

字段是记录语义，不是要求用户填写表单。Project 应在对话中自然完成并写入。

### 写入细则

- 正式评估题一旦提出，立即写入同一条 `OPEN` 记录：`Question`、`Source`、`Record State: OPEN`、`My Answer: 等待回答`；
- 用户回答、明确说“不会”、跳过、请求完整解或放弃后，更新这条记录的 `My Answer`、`Assessment`、`Feedback` 和必要的 `Issue`；
- 题目提出时不要伪造最终判断；`Assessment` 可以暂留空，直到形成可靠诊断；
- `CORRECT` 记录正向证据，不要只保存错误；
- `PARTIAL` 或 `INCORRECT` 才在确有诊断价值时写 `Issue`；
- `UNVERIFIED` 用于来源或提取可靠性不足，不等同于用户不会；
- 如果教材题在历史中已经出现，只有有意复测时才再次使用，并写 `Retest` 及目的；
- 解答是可选校验源：substantive attempt 后或用户明确要求 reference/full solution 后才查阅；普通 hint 不先查解答；解答不可用时不阻塞流程；
- 用户修改同一道题时追加 `Revision`、`Revision Assessment`、`Revision Feedback`，更新同一条记录，不新建 Attempt 页面；
- 不要删除原始回答、原始判断或原始反馈，不要用最终证明覆盖第一次作答。

## 5. Cross-Chapter Evidence

当一个章节中的评估证据对另一个章节也有诊断价值时，在受影响章节的 `Study Record` 中追加一行：

```markdown
Cross-Chapter Evidence — from RAxx / Q[number] (YYYY-MM-DD)
[一句话说明该证据支持或暴露的能力]
```

只保存指向来源题目的轻量引用；完整题目、答案、原始判断、反馈和修订仍只保留在来源章节。不要创建跨章节数据库、复制整条题目记录或把引用当成新的 assessment。

## 6. Concept Note

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

## 7. Persistence Rules

### 必须写入

- Project 实际布置并进入 assessment 的问题（题目提出时先写 `OPEN` 记录）；
- 用户对每道题的原始回答或真实的未答/放弃状态；
- `CORRECT`、`PARTIAL`、`INCORRECT`、`UNVERIFIED` 的原始判断（能够形成判断时）；
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

## 8. Retrieval Rules

```text
进入或恢复章节
→ 先读取对应章节页顶部、最近 Study Record、OPEN 题目、Retest 记录和跨章节引用，再选择 reading block 或下一题

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

## 9. Connection Requirement

本结构依赖一个允许 Project 执行 Notion 写入的连接。只读同步可以用于查询（若当前连接支持），但不能满足“所有题目和学习记录都保存”的要求。
