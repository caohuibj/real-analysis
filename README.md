# Real Analysis Project

这是一个基于 ChatGPT Project 的实分析学习系统。

核心模型：

```text
Rudin
= 唯一用户阅读教材
= 唯一 curriculum spine

Abbott
= ChatGPT 背后的概念 / 证明组织素材库

数学分析之课程讲义 Analysis123
= ChatGPT 背后的应用 / 拓展 / 技巧 / 习题素材库

ChatGPT
= 围绕当前 Rudin 节点，把这些来源组织成一次自包含学习体验
```

即：**one textbook, multiple teaching sources**。

## What this project does

- 按 Rudin Chapters 1–11 组织完整路线；
- 每次只布置有限的 Rudin reading block；
- 所有 Rudin exposition 都要覆盖，包括 Chapter 1 Appendix、Rectifiable Curves、Algebraic Completeness、Gamma 等常被课程省略的内容；
- 用户读完后进行 closed-book assessment；
- Abbott 主动用于 why / intuition / proof organization / counterexamples；
- Analysis123 按 knowledge / skill / application atoms 拆解并路由到合适 RA，在 chat 中推送；
- 正式 evidence、Revision、Retest、Next 持久化到 Notion `Review Analysis`；
- Solution Guide 只在 substantive attempt 后或用户明确要求 reference/full solution 时使用。

## Repository structure

```text
project/
  00_PROJECT.md
  01_LEARNING.md
  02_REVIEW.md
  03_NOTION.md
  04_CURRICULUM.md

acceptance/
  SCENARIOS.md
```

文件职责：

- `00_PROJECT.md`：总边界、材料角色、hard constraints；
- `01_LEARNING.md`：reading / assessment / remediation / tutor push；
- `02_REVIEW.md`：Review Analysis 更新与 chapter readiness；
- `03_NOTION.md`：Notion 页面结构和生命周期；
- `04_CURRICULUM.md`：Rudin owning scope、RA route、Abbott coverage、Analysis123 routing；
- `acceptance/SCENARIOS.md`：行为验收场景。

## Required project files

在 ChatGPT Project 中上传：

1. Rudin — *Principles of Mathematical Analysis*；
2. Abbott — *Understanding Analysis*；
3. `数学分析之课程讲义Analysis123.pdf`；
4. Rudin Solution Guide（可选，但建议提供作 post-attempt verification）；
5. 本仓库 `project/` 下五个规则文件。

### Material roles

用户实际阅读：**Rudin only**。

Abbott 和 Analysis123 不作为额外 reading assignment。ChatGPT 会把需要的概念解释、例子、应用或题目直接放到聊天里。

Abbott 应尽量完整利用其概念教学价值，但不要求用户顺读 Abbott。

Analysis123 采用两层 coverage：

- section locator：保证每个正式 section / homework / exam 有归宿；
- significant atom routing：复合 section 拆成不同 knowledge/skill/application atoms，避免“整节挂一次”造成素材遗漏。

高阶 Analysis123 内容使用 concept anchor + activation gate：可以在较早 RA 做 bounded forward preview，等 prerequisite 满足后再 deepen，避免全部挤到 RA20。

## Notion setup

建立父页面：

```text
Review Analysis
```

其下建立普通页面：

```text
RA00 ... RA20
```

具体名称见 `project/03_NOTION.md` / `project/04_CURRICULUM.md`。

运行时进入某个 RA 前必须能 fetch 对应 exact chapter page。Notion search 只用于 locator，不能代替 full page fetch 做状态判断。

## Default learning flow

```text
RESUME
→ READ RUDIN
→ ASSESS
→ REMEDIATE（如需要）
→ VERIFY（核心弱点如需要）
→ ADVANCE / CONTINUE
```

### Reading lifecycle

正式 Rudin block：

```text
ASSIGNED → COMPLETED
```

用户说“读完了”之后，必须先更新同一个 block 为 COMPLETED，再进入 assessment。

`Deferred within this RA` 只表示当前 block 暂缓；属于该 RA 的 Rudin exposition 必须在 chapter readiness 前由后续 block 回收。不存在“整个课程以后再补”的悬空 Rudin backlog。

### Assessment lifecycle

```text
Question asked
→ OPEN record

First answer
→ same record COMPLETE

Same-turn correction
→ append Revision

Later independent re-test
→ new Retest Q
```

无独立尝试时记 `UNVERIFIED`，不记 `INCORRECT`。

Revision 是 local repair evidence。会阻塞 readiness 的核心 weakness 即使 Revision 已改对，仍需要 independent verification。

## Chapter readiness

默认推进下一 RA 前需要：

- 当前 RA owning 的全部 Rudin exposition reading 已完成；
- chapter-specific exit evidence；
- 核心 definition/theorem conditions evidence；
- boundary/example/counterexample evidence；
- proof/strategy evidence；
- transfer/application evidence；
- 重要 core weaknesses 已 remediation + independent verification。

Abbott / Analysis123 还没有把所有映射素材全部推送，不自动阻塞当前 RA；这是 tutor-side curriculum coverage responsibility，不是额外 user syllabus。

但是 enrichment question 如果真实暴露 Rudin core weakness，该 evidence 有效。

## Curriculum outline

当前 knowledge route：

```text
RA00 → RA01 → ... → RA11
     → RA12 → RA13 → RA14
     → RA15 → RA16 → RA17
     → RA18 → RA19 → RA20
```

Rudin mapping：

```text
Ch1  → RA01
Ch2  → RA02–RA04
Ch3  → RA05–RA06
Ch4  → RA07
Ch5  → RA08
Ch6  → RA09
Ch7  → RA10–RA11
Ch8  → RA11
Ch9  → RA12–RA14
Ch10 → RA15–RA17
Ch11 → RA18–RA20
```

RA00 是 proof-language entry，不代表 Rudin Chapter 0。

## Source reliability

- Rudin 是 curriculum 和 overlapping formal theorem 的 canonical source；
- Abbott 用于概念教学，不替代 Rudin formal conditions；
- Analysis123 高阶内容正式推送前需要查看对应正文，不能只凭目录标题补 theorem；
- 课程讲义本身存在笔误，尤其后半部分，遇到冲突必须核对；
- Solution Guide 只作 post-attempt verification。

## Acceptance

主要行为场景见：

```text
acceptance/SCENARIOS.md
```

其中包括：reading resume、OPEN/COMPLETE、Revision/Retest、UNVERIFIED、full Rudin coverage、RA12–RA20 persistence、Abbott/Analysis123 tutor-only sourcing、atom routing 与 advanced-material anti-sink checks。