# Learning Workflow

## 1. Scope

本文件定义一次 RA 学习过程如何运行：阅读、提问、诊断、反馈、补救、Revision、Retest 与 tutor-side enrichment。

默认主循环：

```text
USER READS RUDIN
→ CLOSED-BOOK RETRIEVAL
→ DIAGNOSE
→ REMEDIATE（如需要）
→ INDEPENDENT VERIFY（核心弱点如需要）
→ TRANSFER / APPLICATION
→ READINESS CHECK
```

用户实际 reading burden 始终是 Rudin。Abbott 与 Analysis123 由 ChatGPT 在对话中按需推送。

## 2. Reading Assignment

### 2.1 Reading source

正式 reading block 只从 Rudin 指定。

进入/恢复 `RAxx` 前必须读取最新 `Review Analysis / RAxx`：

- 有 `Reading State: ASSIGNED`：恢复同一个 block；
- 没有未完成 block：根据 `04_CURRICULUM.md` 的 Rudin owning scope 和历史选择下一个有限 block；
- owning RA 中仍有 deferred Rudin exposition：优先在后续 block 回收，不能把它留到 RA readiness 之后。

### 2.2 Assignment template

```text
Rudin
[具体 chapter / section / theorem range]

Reading Focus
1. [定义、量词或结构]
2. [关键 theorem hypotheses / conclusion]
3. [proof skeleton 或需要自己重建的步骤]

Deferred within this RA
[当前 block 暂不读、但本 RA readiness 前必须覆盖的 Rudin exposition]

Tutor-side plan
- Abbott: [可能的 concept / proof / boundary push]
- Analysis123: [可能的 inline / transfer / forward / deepen push]

Completion Signal
读完后告诉我“这一段读完了”。
```

不要要求用户另读 Abbott / Analysis123。需要其中内容时直接在 chat 中提供自包含版本。

### 2.3 Completion

用户明确说读完后：

1. 先把同一个 reading block 从 `ASSIGNED` 更新为 `COMPLETED`；
2. 记录完成日期；
3. 再进入 assessment。

Reading completion 不等于 mastery evidence。

## 3. Tutor-side Source Use

### 3.1 Abbott

Abbott 可以主动使用，不必等到用户答错。

优先用途：

- `CONCEPT`：为什么这样定义、问题从哪里来；
- `PROOF`：为什么证明采用这种组织；
- `BOUNDARY`：反例、直觉失败、条件必要性；
- `TRANSFER`：另一种表述或相邻问题。

Abbott 的解释应围绕当前 Rudin node，不顺着 Abbott 自己的章节路线另开课程。

### 3.2 Analysis123

Analysis123 作为 enrichment / application / exercise source，使用 `04_CURRICULUM.md` 的 routing：

- `INLINE`：当前 Rudin 概念的短应用/几何解释；
- `TRANSFER`：Rudin core 初步掌握后，用新情境验证迁移；
- `FORWARD`：建立后续分析的位置感；
- `DEEPEN`：activation gate 满足后回访先前 forward atom。

复合 section 必须按 atom 使用，不得因“§11 已经挂到 RA10”就把 compactness、uniform continuity、uniform convergence 等不同内容一次性灌给用户。

高阶 Analysis123 内容正式推送前，检查：

1. 当前 atom 的 concept anchor；
2. activation gate / prerequisite 是否满足；
3. 当前聊天是否提供了足够的自包含背景；
4. 它是 enrichment，还是准备成为正式 assessment evidence。

### 3.3 Forward material

FORWARD 的目标是建立 connection，不是提前开一门新课。

如果 prerequisite 尚不足，只推最小可理解的 idea/example；不得要求完整 theorem proof。若以后 activation gate 满足，可 DEEPEN。

### 3.4 DEEPEN evidence ownership

DEEPEN 的 activation gate 只决定 advanced atom 何时可以完整展开，不决定正式 Q 应存在哪个 RA。

- 如果 DEEPEN formal question 主要验证某个既有 Rudin capability，先确定 `Primary RA`，并在 `Target Evidence` 中明确写出；正式 Q 存在该 Primary RA；
- 若当前 conversation 位于别的 RA，可在该页面追加 `Cross-Chapter Evidence`，但不复制完整 Q record；
- 若只是 advanced exposition / exploration，不以 Rudin mastery evidence 为目标，默认不创建 formal Q；必要时只压缩成 Concept Note；
- 不因为 activation gate 在 RA20，就把所有 late-gated questions 自动归到 RA20。

## 4. Assessment Design

默认 closed-book，一次一个主要问题。

### Level A — Definition / Retrieval

检查定义、量词、定理 hypotheses/conclusion。

### Level B — Boundary / Example / Counterexample

检查适用边界、反例、条件必要性。

### Level C — Proof / Strategy

检查 proof skeleton、关键 lemma、策略选择和独立推理。

### Level D — Transfer / Application

把已学 Rudin idea 放到新情境中；可以来自 Rudin exercise、自拟题、Abbott、Analysis123。

### Level E — Synthesis

需要组合本 RA 多个 ideas 或跨章节 evidence 的综合问题。

题目不按固定数量机械推进。一道高质量问题可以提供多类 evidence；一旦暴露核心缺口，优先补救而不是为了“做满题数”继续升级。

## 5. Question Selection

正式题来源优先级不是固定排名，而按诊断目标选择：

- **Rudin**：core theorem/exercise 与 canonical formulation；
- **Abbott**：概念辨析、proof organization、counterexample、alternate formulation；
- **Analysis123**：application、geometry、technique、经典结果、transfer exercise；
- **Self-authored**：精确针对当前 weakness 或未覆盖 evidence；
- **User-provided**：用户指定题目。

正式题来自 Abbott / Analysis123 时：

- 必须把题干与必要背景完整放进 chat；
- 不要求用户打开对应教材；
- 题目 Source 明确记录；
- 若题目实际测试的是尚未学习的 advanced theory，不得拿失败结果反推 Rudin core weakness；
- 若题目只是在新外壳中使用已掌握 Rudin skill，则可作为 transfer evidence。

如果是 cross-RA DEEPEN question，在真正成为 formal assessment 前先决定 Primary RA；如果无法明确它主要验证哪个已经拥有的 Rudin capability，则通常应保持 enrichment/exploration，而不是为了持久化而强行创建 formal Q。

布置任何教材/讲义题前先检查 Study Record，避免无意重复。若有意复测，则创建新的 Retest record 并引用旧 Q。

## 6. Formal Question Lifecycle

### 6.1 Before asking a new question

必须重新 fetch 最新目标章节页：

1. 普通题的目标页是当前 RA；cross-RA DEEPEN formal question 的目标页是其 Primary RA；
2. 若目标页已有 `OPEN` Q，优先恢复；
3. 否则使用下一个未占用 Q number；
4. 不依赖聊天记忆猜题号。

### 6.2 OPEN

正式 assessment question 一旦提出，立即写入：

```text
Q[number] — [date] — OPEN
Source: [Rudin / Abbott / Analysis123 / self-authored / user-provided]
Question: ...
Target Evidence: ...
```

cross-RA DEEPEN 时，`Target Evidence` 必须包含 `Primary RA = RAxx`。

### 6.3 First answer

用户首次回答后完成同一 record 为 `COMPLETE`，填写原始：

- `My Answer`
- `Assessment`
- `Evidence`
- `Feedback`

之后这些原始字段不再覆盖。

### 6.4 No attempt

用户说“不会”、跳过、放弃，或没有独立尝试直接要完整解：

```text
Assessment: UNVERIFIED
```

不要把“未形成独立证据”写成 `INCORRECT`。

## 7. Assessment Labels

### CORRECT

核心论证正确，条件使用准确，足以形成正向 evidence。小型表达问题若不影响数学有效性可在 Feedback 中指出。

### PARTIAL

有 substantive progress，但存在会影响完整性/严谨性的缺口。

### INCORRECT

有独立尝试，但核心结论、关键条件或主要论证错误。

### UNVERIFIED

没有足够独立作答证据，不能判成 CORRECT/PARTIAL/INCORRECT。

## 8. Feedback Format

默认反馈聚焦四件事：

```text
What works
指出已经成立的部分和可保存 evidence。

First critical gap
指出第一处实质性缺口；无独立尝试时说明 evidence 缺失，而不是伪造错误。

Why it matters
说明该缺口为什么影响结论、严谨性或 readiness。

Minimal repair / Next question
给足以继续思考的最小修复，随后决定是否需要 Revision、Retest 或新题。
```

正确回答也要写简短 `Evidence`，具体说明用户独立展示了什么能力。

默认不立即给完整标准证明。只有用户请求、连续补救仍无法推进，或完整证明本身是学习目标时才展开。

## 9. Revision and Independent Verification

同一轮反馈后修改当前题：

- 原始 `My Answer` / `Assessment` / `Feedback` 保留；
- 追加 `Revision`；
- 追加 `Revision Assessment` / `Revision Feedback`；
- 后续继续修订仍追加，不覆盖。

Revision 只证明当前 scaffold 下的 local repair。

如果原 weakness 会阻塞 chapter readiness：

- Revision 即使 `CORRECT`，仍需新的独立题、Retest 或其他 genuinely unscaffolded answer；
- 只有 independent verification 后才关闭该 blocker。

如果 weakness 只是局部、非核心的小错误，Revision 可以结束当前题目的修复。

之后的新时间点重新独立做同题，按 Retest 新建 Q record，不追加到旧 Revision。

## 10. Remediation

补救顺序优先最小化：

1. 让用户重述定义/条件；
2. 给一个局部提示或反例；
3. Abbott conceptual/proof push；
4. Analysis123 中更直观或更具体的应用/例子；
5. 必要时完整解释或证明；
6. 用新的独立问题验证。

补救材料不自动成为 mastery evidence。

## 11. Chapter Readiness Evidence

本文件只说明 assessment 层的 evidence；最终 contract 以 `02_REVIEW.md` 为准。

默认需要：

- **Core coverage**：当前 RA owning 的全部 Rudin exposition 已读完；`Deferred` Rudin 内容必须先回收；
- **Definition/theorem conditions**：独立准确；
- **Boundary/example/counterexample**：有直接 evidence；
- **Proof/strategy**：有独立 evidence；
- **Transfer/application**：至少有一项有区分度的新情境 evidence；
- **Weakness closure**：重要 PARTIAL/INCORRECT 已 remediation + independent verification。

Transfer/application 可以来自 Rudin、Abbott、Analysis123 或 self-authored question。Analysis123 本身不构成额外 syllabus requirement；它的独立题若有效测试当前 Rudin skill，则 evidence 完全有效。

## 12. Source and Solution Reliability

- **Rudin 的 mathematical content、原始 numbering 与 formal theorem conditions 是 overlapping core 的课程 reference；当前 Project Rudin PDF 是 retypeset/modified working copy，不把其逐字 wording/notation 当作不可质疑的 authority；可疑处核对原版 Rudin或其他可靠来源；**
- Abbott 用于教学解释，不替代 Rudin theorem conditions；
- Analysis123 的目录只作 locator；正式使用高阶 theorem/题目前读取正文并核对 prerequisite；
- Analysis123 存在笔误，出现可疑结论时不得凭目录或记忆补全；
- **Solution Guide 是 non-canonical post-attempt verification support；** 只在 substantive attempt 后或明确要求 reference/full solution 时使用；若与 Rudin formal content、已核验条件或独立正确论证冲突，不以 guide 覆盖前者；
- 普通 hint 不先查 solution。

## 13. Persistence Timing

正式 assessment 的持久化顺序：

1. **Question asked → immediately OPEN**；
2. **First answer → same record COMPLETE**；
3. **Same-turn repair → append Revision**；
4. **Later independent retest → new Q record**。

Reading lifecycle 与 Q lifecycle 分开；reading completion 不直接产生 mastery assessment。
