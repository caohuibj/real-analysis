# Runtime Acceptance Scenarios

本文件用于 Project 装配完成后的人工验收，不作为运行时 Project File。

每个场景都应同时观察对话行为和 `Review Analysis` 的实际写入结果。

## 1. Start a Chapter

输入：

```text
开始 RA01。
```

期望：

- 明确把 `RA01` 当作 knowledge chapter，而不是 Rudin Chapter 1 的别名；
- 先读取 `Review Analysis / RA01` 的顶部状态和最近 Study Record；
- 根据历史选择有限的 Rudin 阅读范围；没有历史时才使用首个自然 reading block；
- 说明阅读重点和暂缓内容；
- 不立即把整章讲完；
- 本身不创建评估题记录（除非随后正式提出评估题）。

## 2. Reading Completion

前提：用户已完成 Project 指定的 Rudin 范围。

输入：

```text
这一段读完了。
```

期望：

- 进入 closed-book 测试；
- 第一次只提出一个主要问题；
- 出新题前重新读取章节最新 Study Record，确认没有应恢复的 `OPEN` 题并分配下一个未使用 Q number；
- 正式提出问题时立即在 `Review Analysis / RA01` 建立 `OPEN` 记录，包含 `Question`、`Source` 和“等待回答”；
- 不先输出整节总结或完整答案。

## 3. Immediate Question Persistence

输入：Project 正式提出第一个评估题，但用户暂时没有回答。

期望：

- 题目已经在对应章节页中有 `OPEN` 记录；
- 记录包含完整 `Question`、`Source`、`Record State: OPEN` 和“等待回答”；
- Notion 写入失败时明确告知用户尚未可靠保存；
- 恢复章节时先读取这条 OPEN 记录，而不是重新创建同一题。

## 4. Correct Answer as Positive Evidence

输入：用户准确写出一个定义，并正确处理量词。

期望：

- 判断为 `CORRECT`；
- 简短说明证据；
- 更新同一条已存在的 `OPEN` 记录，写入原回答、`Assessment` 和 `Feedback`，并把 `Record State` 改为 `COMPLETE`；
- 将正向证据写入对应章节页；
- 根据证据进入更高层次问题，而不是重复同一道基础题。

## 5. Partial Proof

输入：用户证明的核心想法正确，但缺少关键估计。

期望：

- 判断为 `PARTIAL`；
- 指出第一处关键缺口；
- 需要时标记 `RIGOR` 或 `STRATEGY`；
- 给出最小修复方向和下一道验证题；
- 将原始回答、反馈和判断写入章节页；
- 在缺口未经独立验证修复前，不把章节默认推进为 ready。

## 6. Incorrect Quantifier or Concept

输入：用户交换了 ε 和 N 的量词顺序，或误用了定理条件。

期望：

- 判断为 `INCORRECT`；
- 标记 `LOGIC` 或 `CONCEPT`；
- 不机械罗列由第一处错误造成的所有后果；
- 先补救，再重新验证；
- 原始回答不能被修订覆盖；
- “听懂解释”本身不能关闭该缺口。

## 7. Adaptive Difficulty

前提 A：用户连续准确回答定义、条件和短证明。

期望：

- 跳过无区分度的重复题；
- 进入反例、综合证明或 Rudin 习题。

前提 B：用户在基础问题上不稳定。

期望：

- 暂停升级；
- 调用必要的 Abbott 解释或 Project Source 片段；
- 通过新的短题确认是否修复；
- 若需要使用已做过的教材题，创建新的 Retest record，写 `Retest of RAxx/Qm — [目的]`，不改写原记录；
- 普通 hint 不先查 solution；solution 只在 substantive attempt 后或用户明确要求 reference/full solution 时使用。

## 8. Revision of the Same Problem

输入：用户在当前反馈后立即修改同一道证明。

期望：

- 使用同一条题目记录；
- 保留第一次 `My Answer`、原始 `Assessment` 和原始 `Feedback`；
- 追加 `Revision`、`Revision Assessment` 和 `Revision Feedback` 并重新判断；
- 不创建 Attempt、Session 或第二个问题页面；
- 不把这次同轮修订错误标记成 Retest。

## 9. Ordinary Explanation

输入：

```text
为什么紧致性会推出有界性？
```

期望：

- 进行正常解释；
- 默认不创建评估题记录；
- 如果讨论形成高价值可复用结论，可以追加一个精炼 `Concept Note`；
- 不复制完整聊天 transcript。

## 10. Historical Query

输入：

```text
我最近在 RA05 的主要问题是什么？哪些能力已经稳定？
```

期望：

- 先读取 `Review Analysis / RA05`；
- 综合 `Current Strengths`、`Current Weaknesses`、原 assessment、Revision / Retest 和最近题目证据；
- 不只依赖当前聊天记忆；
- 查询本身不创建新题目或新记录。

## 11. Source Uncertainty

输入：引用一个 Project 无法可靠解析的扫描页、公式或图片。

期望：

- 标记为 `UNVERIFIED` 或明确说明来源无法核对；
- 请求用户提供相关页或截图；
- 不凭记忆编造定理条件、页码或公式。

## 12. Notion Write Failure

前提：Notion 连接无写权限或写入失败。

期望：

- 对话可以继续，但明确告知记录尚未保存；
- 不声称已写入 `Review Analysis`；
- 保留可复制的题目、答案和反馈内容，以便连接恢复后补写；
- 连接恢复后先重新读取章节页再分配 Q number，避免重复编号。

## 13. Minimality Check

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

## 14. Cross-Chapter Evidence

输入：RA05 中的一道证明题同时暴露了 RA00 的量词问题。

期望：

- RA05 的原题、回答、判断和反馈仍只保留在 RA05 的原记录；
- RA00 的 Study Record 追加一行 `Cross-Chapter Evidence — from RA05 / Q[number] (date): ...`；
- 不复制完整题目，不创建跨章节数据库或新的 evidence entity。

## 15. RA00 Diagnostic-First

输入：

```text
开始 RA00。
```

期望：

- 先读取 `Review Analysis / RA00` 历史；
- 无历史时先做少量定义、量词、否定和证明策略诊断，而不是直接布置整段固定教材；
- 只有诊断显示缺口时，才定向调用 Abbott §1.2 的相关部分；
- 解释或阅读后用新的独立小题验证，不把“听懂”当作掌握证据。

## 16. Default Workflow Can Be Overridden

输入：

```text
这次不要先读书，直接给我一道综合题；或者只给我一个 hint。
```

期望：

- Project 尊重用户对学习模式的最新请求，不把 READ → ASSESS → REMEDIATE → VERIFY 当作锁定状态机；
- 如果仍提出正式评估题，依然立即建立 `OPEN` 记录并在回答后完成同一条记录；
- 用户只请求普通 hint 时，不自动创建 assessment record，也不先查 solution。

## 17. Rudin Chapter Routing

输入：

```text
开始 Rudin 第 3 章。
```

期望：

- 不把它解释成 RA03；
- 根据 `04_CURRICULUM.md` 识别 Rudin Chapter 3 覆盖 RA05（sequences）与 RA06（series）；
- 读取 RA05 / RA06 的历史；
- 从最早尚未完成或当前应该继续的 knowledge chapter 开始；
- 给出该 unit 的有限 Rudin reading block。

## 18. Ambiguous Bare Chapter Number

输入：

```text
开始第三章。
```

前提：当前 conversation 没有已经建立的 RA 或 Rudin 命名语境。

期望：

- 不自行猜测；
- 只问一次简短澄清，例如“你指 RA03，还是 Rudin Chapter 3？”；
- 澄清后直接进入对应流程，不要求额外命令格式。

如果当前 conversation 已明确一直使用 Rudin chapter number，则后续“第三章”可以沿用该语境，不重复无意义澄清。

## 19. Retest Creates New Evidence

前提：RA05/Q7 是一个已经 `COMPLETE` 的 Rudin 教材题。

输入：用户一周后要求重新做这道题以检查是否真的掌握。

期望：

- 保留 RA05/Q7 完整不变；
- 重新读取最新 Study Record，并分配新的未占用 Q number，例如 Q12；
- Q12 的 `Retest` 写 `Retest of RA05/Q7 — 检查间隔后的独立掌握`；
- 用户的新回答、Assessment 和 Feedback 写在 Q12；
- 不把新回答追加成 Q7 的 Revision。

## 20. Multi-Conversation Q Number Allocation

前提：RA06 在 conversation A 和 conversation B 中都可以继续学习；当前 Notion 最新题号为 Q12。

过程：conversation A 先创建 Q13；conversation B 随后准备创建正式新题。

期望：

- conversation B 出题前重新读取 RA06 最新 Study Record；
- 看到 Q13 已存在后使用 Q14，而不是根据旧聊天记忆也创建 Q13；
- 如果存在当前应继续的 OPEN Q13，则优先恢复它，而不是创建 Q14；
- 不创建 Session / Conversation entity 来解决编号问题。

## 21. Chapter Ready to Advance

前提：某章节已经有以下证据：

- 核心定义/定理条件准确；
- 能处理一个必要条件或反例；
- 独立完成一个短证明；
- 在一道有区分度的教材题或综合题中成功迁移；
- 早先的关键 `PARTIAL` 缺口已经经过 remediation，并在新的独立作答或 Retest 中验证修复。

期望：

- `Current Assessment` 明确说明当前证据足以继续，而不是只写“做完了”；
- `Current Strengths` 对应到实际题目证据；
- 旧错误仍保留在历史，不被抹掉；
- `Next` 可以指向下一 knowledge chapter；
- 不需要机械凑固定题数或 mastery score。

## 22. Chapter Not Ready to Advance

前提：用户已经读完本章 reading blocks，也答对了若干定义题，但仍有一个核心证明能力只得到 `PARTIAL`，之后只听过解释，没有独立验证。

期望：

- 不因为“教材读完了”或“多数题答对”就宣布本章完成；
- `Current Assessment` 保持 `PARTIAL` 或 `UNVERIFIED` 等合适语言判断；
- `Current Weaknesses` 保留该证明缺口；
- `Next` 继续留在当前章，给出最小补救和独立验证方向；
- 如果用户明确要求跳到下一章，可以跳转，但记录为用户路径选择，不写成该章已验证掌握。
