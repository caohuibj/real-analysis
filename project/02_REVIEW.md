# Review Analysis 章节复盘规则

## 1. Scope

`Review Analysis` 不是第二套题库，也不是一个数值化进度系统。它是一个顶层 Notion 页面，下面每个知识章节有一个子页面；每个章节页同时保存：

- 当前掌握判断；
- 已经证明稳定的能力；
- 当前缺口；
- 下一步建议；
- 按时间追加的学习记录。

## 2. Chapter Page Top

每个章节页顶部固定保留四个区块：

```text
## Current Assessment
当前整体判断，用自然语言描述。

## Current Strengths
已经通过回答或证明验证的能力。

## Current Weaknesses
需要继续观察、补救或复测的缺口。

## Next
下一次建议阅读、问题层次、复测方向或下一 knowledge chapter。
```

不要用 `87%`、`mastery = 0.8` 等数字替代判断。可以使用 `STABLE`、`PARTIAL`、`UNVERIFIED` 这些简短词，但必须附带证据说明。

## 3. Study Record

所有 reading blocks、评估题和用户的有效回答按时间保存在 `## Study Record`。正式评估题在提出时先建立 `OPEN` 记录，首次回答后完成同一条记录。

这里的历史规则是 **append-only at the evidence level**：

- reading block 新布置时写 `Reading State: ASSIGNED`，用户明确完成后把同一 block 更新为 `COMPLETED`；`COMPLETED` 后不再改回 `ASSIGNED`；
- `OPEN → COMPLETE` 是同一条题目记录的首次完成过程，可以填充原先空着的答案、判断和反馈；
- 一旦题目记录成为 `COMPLETE`，原始 `My Answer`、`Assessment`、`Feedback` 不再删除或改写；
- 同一轮反馈后的修改作为 `Revision` 追加到该记录；
- 之后再次独立做同一道教材题属于 `Retest`，必须新建新的 dated assessment record，并引用原题；
- 已经形成的历史证据不删除、不覆写成“最终正确版本”。

普通解释不自动变成评估题。跨章节相关性使用轻量引用，不复制另一页的完整答案。

一次学习可以先有一个阅读块：

```text
### 2026-08-17 — Reading Block

Rudin:
[本次阅读范围]

Reading Focus:
- [重点一]
- [重点二]

Reading State:
ASSIGNED / COMPLETED

Completed:
YYYY-MM-DD / —
```

恢复章节时，最近仍为 `ASSIGNED` 的 reading block 表示已经布置但尚未明确完成，应优先继续该 block，而不是猜测用户已经读完或直接布置下一段。

随后逐题追加。题目格式见 `03_NOTION.md`。

### Retest semantics

如果教材习题在历史中已经出现：

- 无意重复：不要再布置；
- 同一轮根据反馈继续修：使用原题的 `Revision`；
- 之后有意复测：创建新的 Q record，写 `Retest of RAxx/Qm — [purpose]`，保留两个时间点的独立证据。

Revision 与 Retest 的证据角色不同：Revision 证明当前题目在反馈后被局部修复；Retest 或新的无提示问题可以提供后续 independent verification。若一个重要核心弱点会阻塞 chapter readiness，Revision alone 不能关闭该 blocker。

## 4. Evidence Rules

### 正向证据

以下内容要进入 `Current Strengths` 或题目记录的 `Evidence`：

- 独立写出正确的定义和量词；
- 能准确说出定理假设；
- 能选择合适的证明策略；
- 能独立完成证明或构造反例；
- Revision 后当前题目的逻辑或严谨性缺口确实被修复（local repair evidence）；
- 在 Retest、新问题或其他不依赖当前提示的情境中再次稳定使用同一能力（independent verification）。

### 负向证据

以下内容要进入 `Current Weaknesses` 或题目记录的 `Issue`：

- 概念或定理条件混淆；
- 不知道证明从哪里开始；
- 量词、否定或蕴含方向错误；
- 关键一步以“显然”代替论证；
- 估计、代数或符号执行失败。

一次偶然错误不应被写成稳定的长期缺陷。当前判断要区分“本题暴露的问题”和“跨题、跨次学习仍然出现的问题”。

`UNVERIFIED` 表示当前缺少可作为 mastery evidence 的独立证据。它既可以来自无法可靠核对的来源，也可以来自用户明确说“不会”、跳过、放弃或在没有独立尝试时直接要求完整解。后一类情况不是 `INCORRECT`，因为没有可判断的错误答案；同样也不能作为 readiness 的正向证据。

## 5. Updating the Page

每次完成有诊断价值的测试后：

1. 完成当前题目的长期记录；如果是新的 assessment 或 Retest，则追加新的 Q record；如果是 Revision，则只追加到原记录；
2. 更新与本次证据直接相关的 `Current Strengths`；
3. 更新或合并 `Current Weaknesses`，避免把同一个根本问题重复写很多遍；
4. 根据 Chapter Readiness contract 更新 `Next`；
5. 保留旧判断在历史记录中，不把历史改写成“从来没有出错”；
6. 如果本次证据与另一章节有关，在相关章节的 `Study Record` 追加 `Cross-Chapter Evidence — from RAxx / Qn (date): ...`；源记录仍是唯一完整证据，不复制整条记录。

如果本次回答没有改变对章节的判断，只需完成题目记录，不要为了形式重复重写顶部。

Reading block 的状态更新不等于 mastery evidence：`COMPLETED` 只说明用户明确表示该段已经读完，不能替代后续 assessment。

## 6. Concept Notes

普通澄清性对话默认不保存 transcript。只有在解释形成以后值得检索的结论时，才追加：

```text
### Concept Note — [主题]

Question
[用户真正困惑的点]

Observed issue
[此前混淆了什么]

Resolution
[最终理解或可复用的判断]
```

Concept Note 不是评估题，不能替代用户独立回答产生的证据。

## 7. Returning to a Chapter

用户再次进入章节时：

1. 定位对应的 `Review Analysis / RAxx` 页面；如果先通过 Notion search 找到页面，search 结果只作为 locator，必须再 fetch 该 exact chapter page，不能用 search highlight / snippet 判断当前状态；
2. 从最新 fetch 的页面读取顶部当前判断（包括 `Current Assessment`、`Current Strengths`、`Current Weaknesses` 和 `Next`）；
3. 读取最近的 Study Record，并检查是否有 `Reading State: ASSIGNED` 的未完成 reading block、`OPEN` 题目、Retest 记录或跨章节引用；
4. 若有未完成的 `ASSIGNED` reading block，优先恢复它；如果该 block 已明确 `COMPLETED`，再根据 assessment history 决定后续；
5. 找出尚未验证的弱点和已有的正向证据；
6. 若有当前应继续的 `OPEN` 题，且没有更早需要完成的阅读状态问题，优先恢复它，不创建重复题；
7. 再决定是继续当前 block、先补救、进行 Retest，还是选择新的 reading block；
8. 设计下一道能区分“真正稳定”和“刚刚听懂”的题；
9. 不要求用户重新提交整页历史。

没有历史时，才依据 `04_CURRICULUM.md` 从该章节的首个自然 block 开始。

如果用户问“我最近主要有什么问题”，读取各章节页面中的 `Current Weaknesses` 和最近记录；如果只问某一道题，定位到该题记录，不要用泛泛的章节判断代替。

## 8. Chapter Readiness

READ → ASSESS → REMEDIATE → VERIFY → ADVANCE 是默认节奏，不是锁定机制。默认建议进入下一 knowledge chapter 时，必须同时有足够的**内容覆盖**与**能力证据**，不能只因为阅读范围结束或连续几题答对。

### 默认 readiness contract

Project 默认只有在以下条件都满足时，才把章节视为 **ready to advance**：

1. **Core coverage**：`04_CURRICULUM.md` 中该 knowledge chapter 的 core reading scope 已经通过一个或多个 `COMPLETED` reading blocks 覆盖，并且该章列出的 chapter-specific `出口证据` 已有直接证据覆盖。明确标为 optional / deferred 的材料可以不阻塞推进，但应在 `Current Assessment` 中注明；不能因为只掌握了一个早期 reading block 就把整章判为 ready；
2. **Core statement evidence**：核心定义、量词结构或关键定理假设/结论已有独立正确证据；
3. **Boundary evidence**：至少有一项概念区分、适用条件、例子或反例证据，能表明不是只会背陈述；
4. **Proof evidence**：至少有一项独立短证明、证明骨架或策略选择证据；
5. **Transfer evidence**：至少有一道有区分度的 Rudin / Abbott 习题或综合问题，或者现有证明题已经明显覆盖同等迁移能力；
6. **Gap closure**：本章当前仍重要的 `PARTIAL` / `INCORRECT` 缺口已经经过 remediation。Revision 可以作为该题已修复的 local repair evidence；如果该缺口是阻塞 readiness 的重要核心弱点，还必须通过新的独立题、Retest 或其他 genuinely unscaffolded answer 完成 independent verification，不能仅凭同轮 Revision 关闭；
7. **No explanation-only or unverified mastery**：没有关键能力仍只基于“听懂解释”或 `UNVERIFIED` 状态而缺少独立验证。

这些是能力和内容覆盖条件，不是固定题数，也不是要求每章机械做七题。一个高质量问题可以同时覆盖多个 chapter-specific 出口证据和多个能力类别；若某项在该章节确实不适用，应在 `Current Assessment` 中说明为什么。

### readiness 结果

- **Ready**：`Current Assessment` 写明 core coverage 和当前能力证据足以继续，`Next` 可以指向下一 knowledge chapter；
- **Not ready**：`Current Assessment` 保持 `PARTIAL` 或 `UNVERIFIED` 等语言判断，`Next` 必须留在本章并明确缺失的是 reading/content coverage、独立证据还是待修复问题；
- **User override**：用户始终可以主动跳到其他章节，但这只能记录为学习路径选择，不能写成“本章已验证掌握”。

建议进入下一章只表示目前证据足够支持继续，不表示旧章节永远不会复习。

## 9. Cross-Chapter Evidence References

跨章节证据只使用普通 Markdown 行，不创建新的数据结构：

```markdown
Cross-Chapter Evidence — from RA05 / Q12 (2026-08-17)
[一句话说明该题对当前章节的稳定能力或薄弱点提供了什么证据]
```

目标章节可以在 `Current Strengths` 或 `Current Weaknesses` 中引用这条记录，但完整题目、答案、原始判断和修订只保留在来源章节。若原题被修订，引用仍指向同一条 `Q[number]` 记录；若之后出现 Retest，则新 Retest 有自己的 Q number，可作为新的时间点证据单独引用。

## 10. Q Number Integrity

`Q[number]` 是章节页内的轻量引用标识，不是独立实体。为了支持一个章节拆成多个 conversation：

1. 创建任何正式新题前重新读取该章节最新的 `Study Record`；如果先通过 search 定位页面，先 fetch exact chapter page；
2. 若有当前应恢复的 `OPEN` 题，优先恢复；
3. 否则找到最大已存在 Q number，使用下一个未占用编号；
4. 如果写入时发现页面刚被另一 conversation 更新或编号已占用，重新读取后再分配；
5. 不允许多个 conversation 仅根据各自聊天记忆猜测“下一题号”。

v1 支持的是跨 conversation 的顺序恢复，不承诺同一 RAxx 中两个 conversation 同时创建正式题目的原子并发安全。应避免这种同时写入；发生竞争时以最新章节页为准重新读取和分配。

这样保持跨章节引用稳定，同时不引入 Question database 或 Session entity。

## 11. No Extra Entities

章节页内部的 reading block、题目、答案、反馈、修订和 Issue 都是 Markdown 记录，不创建：

```text
Question database
Attempt database
Session database
Issue database
Score field
```

这样可以保持 `Review Analysis` 既能完整留存证据，又不需要维护一个没有实际消费者的 schema。