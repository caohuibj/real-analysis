# Review Analysis and Chapter Readiness

## 1. Purpose

`Review Analysis / RAxx` 是每个 knowledge chapter 的 durable learning record。

本文件规定：

- 顶部 Current Assessment 如何更新；
- Study Record 如何追加；
- reading lifecycle 与 Q lifecycle 如何解释；
- 什么证据足以支持 chapter readiness；
- Abbott / Analysis123 enrichment 如何进入 evidence，而不变成额外 syllabus。

## 2. Page-Level Current State

每个 RA 页顶部至少维护：

```text
Current Assessment
[当前总体判断]

Current Strengths
- ...

Current Weaknesses
- ...

Next
[下一步]
```

顶部状态是当前压缩判断，不替代下面的历史记录。

更新原则：

- 只根据实际 evidence 更新；
- 不因一次解释“听懂了”直接删除 weakness；
- blocker 只有在 remediation + independent verification 后才能关闭；
- 新 evidence 可以来自 Rudin、Abbott、Analysis123 或 self-authored assessment，只要诊断目标和 prerequisite 合理。

## 3. Study Record

Study Record 按时间追加，主要包含两类正式记录：Reading Block 与 Assessment Q。

### 3.1 Reading Block

```text
Reading Block — [date]
Rudin:
[chapter / sections / theorem range]

Reading Focus:
- ...

Deferred within this RA:
- ...

Reading State:
ASSIGNED / COMPLETED

Assigned:
YYYY-MM-DD

Completed:
YYYY-MM-DD / —
```

`Deferred within this RA` 只表示当前 block 暂不读。它不是 optional，也不能越过 owning RA readiness 继续悬空。

Abbott / Analysis123 tutor push 不建立 Reading Block。

### 3.2 Assessment Q

```text
Q[number] — [date] — OPEN / COMPLETE
Source:
[Rudin / Abbott / Analysis123 / self-authored / user-provided]

Question:
...

Target Evidence:
...

My Answer:
...

Assessment:
CORRECT / PARTIAL / INCORRECT / UNVERIFIED

Evidence:
...

Feedback:
...
```

Revision 追加在同一 COMPLETE record；later Retest 新建独立 Q。

## 4. Reading Lifecycle Review

恢复章节时：

1. fetch exact RA page；
2. 查找最近 `Reading State: ASSIGNED`；
3. 有未完成 block 时优先恢复；
4. 没有未完成 block 时，再根据 `04_CURRICULUM.md` 的 owning scope 检查还有哪些 Rudin exposition 未覆盖；
5. 只有 owning scope 全部完成，才允许把 Core Coverage 判为 complete。

### Rudin ownership rule

`04_CURRICULUM.md` 为每个 Rudin exposition section 指定唯一 owning RA。

因此：

- Chapter 1 Appendix 不能因为首轮暂缓就永久跳过；
- `Rectifiable Curves` 不能因放在后置 block 就在 RA09 ready 时仍未读；
- Chapter 8 Algebraic Completeness / Gamma 不能作为永久 optional；
- 类似后置 sections 都必须在 owning RA readiness 前完成。

Rudin exercises 不属于机械全覆盖要求；exercise evidence 按教学价值选择。

## 5. Assessment Record Review

### OPEN

正式问题已提出但用户尚未完成首次作答。

新正式问题之前必须先检查是否有 OPEN；有则优先恢复。

### COMPLETE

用户已完成首次作答或明确跳过/放弃。

- 有独立作答：可判 CORRECT / PARTIAL / INCORRECT；
- 无独立作答：`UNVERIFIED`。

### Revision

Revision 保留原始 answer/assessment/feedback，只追加修订判断。

Revision 是 local repair evidence，不是 independent verification。

### Retest

之后新时间点的独立复测建立新 Q，并引用原问题。

## 6. Evidence Types

Chapter review 至少区分以下 evidence：

### Definition / theorem-condition evidence

是否能独立准确陈述定义、量词、hypotheses 与 conclusion。

### Boundary / example / counterexample evidence

是否真正理解适用边界，而非只会复述定理。

### Proof / strategy evidence

是否能组织证明、选择关键 lemma、定位真正使用的条件。

### Transfer / application evidence

是否能把已掌握的 Rudin idea 用到新情境。

可来自：

- Rudin exercise；
- Abbott counterexample / alternate formulation；
- Analysis123 application / geometry / technique / exercise；
- self-authored transfer problem。

来源本身不决定 evidence 强度；独立性、diagnostic fit 与 mathematical correctness 才决定。

## 7. Tutor-Side Enrichment in Review

Abbott / Analysis123 是 tutor-side sources。

它们的内容是否“都已经推送”**不作为单个 RA readiness checklist**。否则课程会把 enrichment 错变成第二套 syllabus。

但它们有三种 review 作用：

1. **Positive evidence**：自包含的 transfer/application question 可提供正式 evidence；
2. **Diagnostic evidence**：新情境中暴露出的 Rudin core weakness 必须认真处理；
3. **Curriculum coverage feedback**：如果某个有价值的 mapped atom 长期没有合适时机使用，应在未来 curriculum maintenance 中处理，而不是在 Notion 增加新状态字段。

FORWARD material 如果测试的是未学 advanced theory，不能把失败误判为 Rudin core weakness。

## 8. Chapter Readiness Contract

默认只有同时满足以下条件，当前 RA 才 ready：

### 8.1 Core Coverage

`04_CURRICULUM.md` 指定给本 RA 的 **全部 Rudin exposition scope** 已由 `COMPLETED` reading blocks 覆盖。

- 当前 block 的 `Deferred within this RA` 若仍未回收，则 Core Coverage 不完整；
- 不存在跨 RA / 跨课程的悬空 Rudin deferred backlog；
- Rudin exercises 不要求机械全做。

### 8.2 Chapter-Specific Exit Evidence

`04_CURRICULUM.md` 为该 RA 列出的出口能力已经有直接 evidence，而不是只靠“整体感觉不错”。

### 8.3 Core Definition / Theorem Conditions

关键定义、量词、theorem hypotheses/conclusion 有独立正确 evidence。

### 8.4 Boundary / Example / Counterexample

至少有足以区分机械记忆与真实理解的边界类 evidence。

### 8.5 Proof / Strategy

至少有独立 proof skeleton、短证明或策略选择 evidence。

### 8.6 Transfer / Application

至少有一个有区分度的新情境 evidence。来源可以是 Rudin、Abbott、Analysis123 或 self-authored problem。

### 8.7 Core Weakness Closure

仍重要的 `PARTIAL` / `INCORRECT` weakness 必须：

```text
remediation
+ independent verification
```

Revision alone 不能关闭 blocking weakness。

## 9. Readiness Outcomes

### READY

满足 §8 的全部条件：

- 更新 `Current Assessment`；
- Strengths 记录可迁移的稳定能力；
- Weaknesses 只保留非阻塞或尚待长期观察的点；
- `Next` 可以推进下一 knowledge chapter。

### NOT READY

任一核心条件缺失：

- `Next` 留在当前 RA；
- 明确缺失的是 Rudin reading coverage、definition evidence、boundary evidence、proof evidence、transfer evidence，还是 unresolved blocker；
- 不为了“已经做了很多题”而误判 ready。

### USER-INITIATED SKIP

用户可主动跳转，但必须保留当前 Not Ready 状态；不能把用户选择跳过写成 readiness evidence。

## 10. Cross-Chapter Evidence

有用的旧 evidence 不复制完整答案，只写轻量引用：

```text
Cross-Chapter Evidence — from RAxx / Qn (YYYY-MM-DD): [compressed conclusion]
```

跨章节 evidence 可以减少重复测试，但不能用模糊印象替代当前 chapter-specific exit evidence。

## 11. Updating Current Assessment

完成一个 reading block / assessment cycle 后，根据最新 evidence 压缩顶部状态。

### Strengths

只写稳定且可检索的能力，例如：

- 正确区分 uniform / pointwise convergence；
- 能独立检查 IFT 的 invertibility condition；
- 能把 compactness 用于 global uniform control。

### Weaknesses

写具体能力，不写笼统“基础不牢”。例如：

- 会陈述 DCT，但仍会漏掉 dominating integrable function 的要求；
- Revision 后能修复，但尚无 independent verification。

### Next

Next 必须可执行：

- `Continue RA07 — next Rudin block: Discontinuities`；
- `Retest RA05/Q4 weakness with a new Cauchy problem`；
- `Advance to RA12`。

## 12. Review Integrity

- Notion page latest fetch 是状态 authority；
- search snippet 不能决定 readiness；
- 不覆盖 COMPLETE 原始 answer/assessment/feedback；
- 不把 explanation exposure 当 mastery；
- 不把 unfinished tutor enrichment 当 core reading debt；
- 不把 unfinished Rudin exposition 当 optional enrichment；
- 不创建额外数据库或 mastery schema。