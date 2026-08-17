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

Project 可以根据新证据改写顶部四个区块。`Study Record` 的历史证据遵守 append-only 语义：reading block 可以从 `ASSIGNED` 完成到 `COMPLETED`；题目 `OPEN` 记录在首次回答前允许原地完成；题目成为 `COMPLETE` 后，原始答案、判断和反馈不得改写，只能追加 Revision，或者用新的 Retest record 形成新的时间点证据。

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

Reading State:
ASSIGNED

Completed:
—
```

### Reading lifecycle

- 新 reading block 一旦正式布置，立即写 `Reading State: ASSIGNED`；
- 用户明确说“这一段读完了”或等价完成信号后，更新**同一个** reading block 为 `Reading State: COMPLETED`，并把 `Completed` 写为实际日期；
- `COMPLETED` 后不再改回 `ASSIGNED`；如果之后有意重读，应创建新的 dated Reading Block；
- `COMPLETED` 只表示用户确认完成阅读，不是 mastery evidence；后续 assessment 仍然必要；
- 恢复章节时，如果最近存在 `ASSIGNED` reading block，优先恢复它，不创建重复 reading block，也不假设用户已经读完。

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
[题目刚提出时写“等待回答”；之后写用户原始回答或真实的不会、跳过、放弃、请求完整解等状态]

Assessment
[原始判断：CORRECT / PARTIAL / INCORRECT / UNVERIFIED；题目刚提出时暂留空]

Feedback
[原始判断的证据、做得好的地方、第一处关键缺口、为什么重要和最小修复；若没有独立作答，说明尚无可验证 mastery evidence]

Issue
CONCEPT / STRATEGY / LOGIC / RIGOR / EXECUTION；没有足够独立作答证据时通常留空

Retest
No；如果是后续有意复测，写 `Retest of RAxx/Qm — [目的]`

Solution Reference
Not consulted；或写“substantive attempt 后核对 / 用户明确要求 reference/full solution 后核对 / unavailable”

Revision
[同一轮反馈后的后续修订；没有时删除该段或写“无”]

Revision Assessment
[对修订后的同一题重新判断]

Revision Feedback
[修订是否修复原缺口，以及新的最小修复]
```

字段是记录语义，不是要求用户填写表单。Project 应在对话中自然完成并写入。

### 写入细则

- 创建正式新题前，先重新读取对应章节最新的 `Study Record`；若有当前应继续的 `OPEN` 题，优先恢复，不重复创建；
- 若确需新题，找到已存在的最大 `Q[number]`，分配下一个未使用编号；若写入时发现页面已由另一 conversation 更新或编号冲突，重新读取后再分配；
- 正式评估题一旦提出，立即写入同一条 `OPEN` 记录：`Question`、`Source`、`Record State: OPEN`、`My Answer: 等待回答`；
- 用户首次回答、明确说“不会”、跳过、请求完整解或放弃后，填充这条记录的 `My Answer`、`Assessment`、`Feedback` 和必要的 `Issue`，并把 `Record State` 改为 `COMPLETE`；
- 如果用户没有提供可判断的独立答案，例如明确说“不会”、跳过、放弃或在独立尝试前直接请求完整解，`Assessment` 使用 `UNVERIFIED`，Feedback 写明“尚无独立掌握证据”；不要把未作答伪装成 `INCORRECT`；
- `OPEN → COMPLETE` 是同一条记录正常的首次完成，不算覆盖历史；
- 记录成为 `COMPLETE` 后，原始 `My Answer`、原始 `Assessment` 和原始 `Feedback` 固定不变；
- `CORRECT` 记录正向证据，不要只保存错误；
- `PARTIAL` 或 `INCORRECT` 才在确有诊断价值时写 `Issue`；
- `UNVERIFIED` 也用于来源或提取可靠性不足；无论是哪种原因，都不能算 readiness 的正向证据；
- 解答是可选校验源：substantive attempt 后或用户明确要求 reference/full solution 后才查阅；普通 hint 不先查解答；解答不可用时不阻塞流程；
- 用户在同一轮反馈后修改同一道题时，在这个 `COMPLETE` 记录下追加 `Revision`、`Revision Assessment`、`Revision Feedback`，不改写原始字段；
- 之后重新独立做同一道教材题属于 Retest：创建新的 Q record，并在 `Retest` 写 `Retest of RAxx/Qm — [目的]`，不要把新时间点证据塞进旧题 Revision；
- 不要删除原始回答、原始判断或原始反馈，不要用最终证明覆盖第一次作答。

### Revision 与 Retest 的边界

```text
Revision
= 同一轮 assessment 中，用户根据当前反馈继续修同一道题
= 追加在原 Q record

Retest
= 之后的新时间点重新独立接受同题或等价题验证
= 新建新的 Q record，并引用原 Q
```

这样既保留学习轨迹，又不需要 Attempt / Session entity。

## 5. Cross-Chapter Evidence

当一个章节中的评估证据对另一个章节也有诊断价值时，在受影响章节的 `Study Record` 中追加一行：

```markdown
Cross-Chapter Evidence — from RAxx / Q[number] (YYYY-MM-DD)
[一句话说明该证据支持或暴露的能力]
```

只保存指向来源题目的轻量引用；完整题目、答案、原始判断、反馈和修订仍只保留在来源章节。不要创建跨章节数据库、复制整条题目记录或把引用当成新的 assessment。

如果后来产生 Retest，新 Retest 有自己的 Q number；需要引用新的时间点证据时，引用新的 Q record，而不是悄悄改写旧引用。

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

- Project 实际布置的 reading block，以及它的 `ASSIGNED → COMPLETED` 状态；
- Project 实际布置并进入 assessment 的问题（题目提出时先写 `OPEN` 记录）；
- 用户对每道题的原始回答或真实的未答/不会/跳过/放弃/直接请求完整解状态；
- `CORRECT`、`PARTIAL`、`INCORRECT`、`UNVERIFIED` 的原始判断（能够形成判断时）；
- 反馈、Issue、Revision、Retest 和正向证据；
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
3. 保留可复制的 reading block、题目、答案和反馈内容；
4. 连接恢复后先重新读取章节页，再补写或完成原记录，避免产生重复 reading block 或重复 Q number。

## 8. Retrieval Rules

```text
进入或恢复章节
→ 先读取对应章节页顶部、最近 Study Record、ASSIGNED reading block、OPEN 题目、Retest 记录和跨章节引用，再选择下一步

未完成 reading block
→ 若最近 Reading State = ASSIGNED，优先恢复该 block；只有明确 COMPLETED 后才进入后续 assessment / next reading

创建正式新题
→ 再次读取最新 Study Record，确认 OPEN 状态并分配下一个未使用 Q number

当前章节掌握情况
→ 读取对应章节页顶部和最近 Study Record

某一道题的历史
→ 读取该题的完整记录和 Revision

某项能力是否稳定
→ 同时查看原 assessment、后续 Revision / Retest 和其他迁移题证据

长期薄弱点
→ 汇总各章节的 Current Weaknesses，并回看相关题目证据

已经掌握的内容
→ 读取 Current Strengths 和 CORRECT 记录
```

纯查询不创建新题目或新记录。

### Q number concurrency boundary

多个 conversation 可以顺序恢复同一个 knowledge chapter，但 v1 不提供同一 RAxx 中两个 conversation 同时创建正式题目的原子锁。创建新题前必须重新读取最新页面；如果发现竞争更新或编号冲突，重新分配，不覆盖已有记录。不要为此引入 Session / Question database。

## 9. Connection Requirement

本结构依赖一个允许 Project 执行 Notion 写入的连接。只有实际写入动作返回成功后，Project 才能说 reading block、题目或学习记录已经保存。