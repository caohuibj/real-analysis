# Notion Persistence Rules

## 1. Purpose

Notion `Review Analysis` 是本 Project 的 durable learning record。

本文件只定义现有页面结构、reading lifecycle、assessment lifecycle、读取/写入规则。不创建新的数据库或额外 mastery schema。

## 2. Review Analysis Structure

`Review Analysis` 下按 knowledge chapter 建普通页面：

```text
RA00 — Proof Language
RA01 — Real Numbers & Completeness
RA02 — Countability and the Infinite
RA03 — Metric Spaces and Topological Structure
RA04 — Compactness, Perfectness & Connectedness
RA05 — Sequences and Completeness
RA06 — Numerical Series
RA07 — Limits and Continuity
RA08 — Differentiation
RA09 — Riemann and Riemann–Stieltjes Integration
RA10 — Sequences and Series of Functions
RA11 — Approximation, Power Series & Special Functions
RA12 — Multivariable Linear Structure & Differentiability
RA13 — Contraction, Inverse / Implicit / Rank Theorems
RA14 — Determinants, Higher Derivatives & Parameter Dependence
RA15 — Integration in Euclidean Space & Change of Variables
RA16 — Differential Forms, Simplexes & Chains
RA17 — Stokes, Closed / Exact Forms & Vector Analysis
RA18 — Measurable Structure & Measure Construction
RA19 — Lebesgue Integration, Convergence & Product Measures
RA20 — Riemann Comparison, Complex Integration & L2 / Functional Viewpoint
```

页面名和 exact RA mapping 以 `04_CURRICULUM.md` 为准。

在 runtime 真正进入某个 RA 之前，对应 `Review Analysis / RAxx` 页面必须存在并可 fetch。若缺页，应先创建/修复该普通页面，而不是绕过 durable state 直接开始正式学习。

## 3. Chapter Page Template

```text
# RAxx — [name]

Current Assessment
[当前总体判断]

Current Strengths
- ...

Current Weaknesses
- ...

Next
[下一步]

Study Record

[dated reading / assessment records appended below]
```

顶部字段是当前压缩状态；Study Record 是不可随意覆盖的历史。

## 4. Read Before Acting

进入/恢复章节时：

1. 如果需要，用 Notion search 找到 `Review Analysis / RAxx`；
2. search 只作 locator；
3. 必须 fetch exact chapter page；
4. `Current Assessment`、`Next`、`Reading State`、`OPEN` Q 和 Q number 都以最新完整 fetch 为准。

创建新正式 assessment question 前，再 fetch 一次最新章节页，避免多个 conversation 各自猜题号。

## 5. Reading Block Record

正式 reading block 永远是 Rudin block。

```text
Reading Block — YYYY-MM-DD

Rudin
[chapter / section / theorem range]

Reading Focus
- ...

Deferred within this RA
- [当前 block 暂不读，但 owning RA readiness 前必须覆盖的 Rudin exposition]

Reading State
ASSIGNED / COMPLETED

Assigned
YYYY-MM-DD

Completed
YYYY-MM-DD / —
```

### Lifecycle

新 block 正式布置：

```text
Reading State: ASSIGNED
```

用户明确读完：更新 **同一个 block**：

```text
Reading State: COMPLETED
Completed: YYYY-MM-DD
```

恢复章节时，存在 `ASSIGNED` block 就优先恢复，不建立新 block。

### Deferred semantics

`Deferred within this RA` 不是 optional list。

- 它只表示当前 block 暂缓；
- `04_CURRICULUM.md` 中属于该 RA 的 Rudin exposition 最终必须由后续 block 覆盖；
- 如果仍有 unresolved Rudin deferred，Core Coverage 不能判 complete；
- Abbott / Analysis123 tutor pushes 不记成 Reading Block。

## 6. Assessment Record

正式问题提出时立即创建：

```text
Q[number] — YYYY-MM-DD — OPEN

Source
[Rudin / Abbott / Analysis123 / self-authored / user-provided]

Question
[完整题目]

Target Evidence
[definition / boundary / proof / transfer / ...]
```

如果题目来自 Abbott / Analysis123，`Question` 必须保存足够的自包含题干；不依赖用户另开教材才能知道题目是什么。

## 7. Completing an OPEN Record

用户首次回答后，在同一 record 中补齐并改为 COMPLETE：

```text
Q[number] — YYYY-MM-DD — COMPLETE

Source
...

Question
...

Target Evidence
...

My Answer
[原始首次回答]

Assessment
CORRECT / PARTIAL / INCORRECT / UNVERIFIED

Evidence
[可长期检索的正向 evidence]

Feedback
[首次反馈]
```

### No-attempt rule

用户明确不会、跳过、放弃，或无独立尝试直接要求完整解：

```text
Assessment: UNVERIFIED
```

不要写成 INCORRECT。

## 8. COMPLETE Immutability

一旦 record 成为 COMPLETE：

- 原始 `My Answer` 不覆盖；
- 原始 `Assessment` 不覆盖；
- 原始 `Feedback` 不覆盖；
- 后续修改只追加 Revision；
- later independent retest 建新 Q。

## 9. Revision

同一轮反馈后的修改追加在原 Q 下：

```text
Revision — [optional timestamp]
[用户修订]

Revision Assessment
CORRECT / PARTIAL / INCORRECT

Revision Feedback
[原缺口是否修复]
```

多次 Revision 按顺序继续追加。

Revision 是 local repair evidence，不自动等于 independent verification。若原 weakness 会阻塞 chapter readiness，即使 Revision CORRECT，也要后续新独立题/Retest 验证。

## 10. Retest

later independent retest 新建 Q：

```text
Q[new number] — YYYY-MM-DD — OPEN
Retest of RAxx/Qn — [目的]
Source
...
Question
...
```

之后按正常 lifecycle COMPLETE。

不得把 later retest 追加成旧题的 Revision。

## 11. Q Number Allocation

新正式问题之前：

1. fetch latest exact RA page；
2. 检查是否有 OPEN；
3. 有 OPEN：恢复，不新建；
4. 无 OPEN：扫描已用 Q numbers；
5. 使用下一个未占用 number。

不能根据当前聊天记忆猜 Q number。

## 12. Tutor-Side Evidence

Abbott / Analysis123 的普通解释聊天默认不逐字保存。

以下情况需要持久化：

- 形成正式 assessment question；
- 用户对 tutor-pushed application/transfer 做了独立 substantive answer；
- 暴露了新的 core weakness；
- 形成值得长期检索的 Concept Note；
- 产生 cross-chapter evidence。

不要创建“Abbott Coverage”“Analysis123 Coverage”之类新的 Notion 状态表。完整素材 routing 属于 `04_CURRICULUM.md` 的静态 curriculum responsibility。

## 13. Current State Update

一轮正式学习后，根据 evidence 更新顶部：

### Current Assessment

压缩当前 readiness 判断，不写成长篇日志。

### Current Strengths

只保存稳定、具体、可迁移的能力。

### Current Weaknesses

保存具体 blocker / uncertainty，并标明若只完成 Revision 但尚未 independent verification。

### Next

必须可执行，例如：

```text
Continue RA11 — next Rudin block: Algebraic Completeness
Retest RA05/Q4 Cauchy weakness
Advance to RA12
```

如果当前 RA owning 的 Rudin exposition 仍有未完成 block/Deferred，Next 不应默认推进下一 RA。

## 14. Cross-Chapter Evidence

使用轻量引用：

```text
Cross-Chapter Evidence — from RAxx / Qn (YYYY-MM-DD): [compressed conclusion]
```

不复制完整答案，不创建新实体。

## 15. Concept Notes

普通解释性聊天不保存。

只有形成长期值得检索的数学结论时，可压缩为 Concept Note，例如：

```text
Concept Note — [date]
[稳定结论 / recurring distinction / reusable proof idea]
```

Concept Note 不是 assessment evidence，除非另有独立作答支持。

## 16. Write Integrity

- 只有 Notion 工具实际返回成功后才能声称“已保存”；
- 写入失败时如实说明；
- 不因写入失败而假装状态已更新；
- 不创建 Question database、Attempt、Session、Score 或额外 mastery schema；
- 页面结构保持普通 chapter pages + Study Record。