# Acceptance Scenarios

这些场景用于检查 Project 是否遵守 `00_PROJECT.md`–`04_CURRICULUM.md`。

## 1. Resume Assigned Reading

**Given** `Review Analysis / RA05` 存在 `Reading State: ASSIGNED` 的未完成 Rudin block。  
**When** 用户说“继续 RA05”。  
**Then** Project 必须恢复该 block，而不是创建新的 reading assignment。

## 2. Complete Reading Before Assessment

**Given** 当前 block 为 ASSIGNED。  
**When** 用户说“这段读完了”。  
**Then** 先把同一 block 更新为 COMPLETED 并记录日期，再进入 assessment。

## 3. Reading Completion Is Not Mastery

**When** 用户完成 reading block。  
**Then** 不因“读完”直接把 RA 标为 mastered/ready；仍需 assessment evidence。

## 4. Question Becomes OPEN Immediately

**When** Project 提出一条正式 assessment question。  
**Then** 同步在 exact RA page 创建 `Qn — OPEN`，再等待答案。

## 5. First Answer Completes Same Record

**Given** Qn 为 OPEN。  
**When** 用户首次回答。  
**Then** 更新同一 Qn 为 COMPLETE；不创建第二条 answer record。

## 6. COMPLETE Is Immutable

**Given** Qn 已 COMPLETE。  
**When** 用户修改答案。  
**Then** 原始 My Answer / Assessment / Feedback 保留，只追加 Revision。

## 7. Revision Is Not Independent Verification

**Given** 一个 blocking weakness 在反馈后 Revision 已 CORRECT。  
**Then** weakness 仍需新题、Retest 或其他 genuinely unscaffolded answer 才能关闭。

## 8. Later Retest Is a New Q

**Given** 用户之后重新独立做旧题。  
**Then** 创建新的 Q record，并写 `Retest of RAxx/Qn`；不追加到旧 Revision。

## 9. No Attempt Is UNVERIFIED

**When** 用户说“不会”、跳过、放弃，或无独立尝试直接要完整解。  
**Then** 完成当前 OPEN Q，但 Assessment = UNVERIFIED，不写 INCORRECT。

## 10. Re-fetch Before New Question

**When** Project 准备提出新的正式问题。  
**Then** 重新 fetch exact RA page；有 OPEN 先恢复，否则扫描现有 Q number 后分配下一个未占用编号。

## 11. Notion Search Is Locator Only

**Given** 章节页通过 Notion search 找到。  
**Then** 必须 fetch exact page 后才能判断 Current Assessment、Next、Reading State、OPEN 或 Q number。

## 12. Failed Notion Write Is Not Claimed Saved

**When** Notion write 未成功。  
**Then** Project 不得声称“已保存”。

## 13. Solution Guide After Attempt Only

**When** 用户只要普通 hint 且已有题干。  
**Then** 不先查 Solution Guide。  
**When** 用户已有 substantive attempt 或明确要 reference/full solution。  
**Then** 可以使用 Solution Guide。

## 14. Sole User-Facing Textbook

**When** Project 安排正式 reading。  
**Then** reading source 必须是 Rudin。Abbott / Analysis123 不产生 reading block。

## 15. Abbott Can Be Proactive

**Given** 用户当前没有答错，但 Rudin 表述非常压缩。  
**When** Abbott 有明显更好的 motivation / proof organization。  
**Then** Project 可以主动在 chat 中推送 Abbott conceptual layer，而不要求用户另读 Abbott。

## 16. Analysis123 Push Is Self-Contained

**When** 使用 Analysis123 的例子、应用或习题。  
**Then** chat 中提供完成任务所需的题干与背景；不要求用户打开讲义寻找上下文。

## 17. Tutor-Side Question Can Produce Evidence

**Given** 一道 Analysis123 transfer question 只使用已经掌握的 Rudin tools。  
**When** 用户独立正确完成。  
**Then** 它可以作为正式 transfer evidence。

## 18. Advanced Failure Does Not Falsely Become Core Weakness

**Given** 一个 FORWARD question 实际依赖尚未学习的 advanced theory。  
**When** 用户不会。  
**Then** 不得把失败直接写成 Rudin core weakness。

## 19. Enrichment Can Expose a Real Core Weakness

**Given** Analysis123 只是给已学 Rudin theorem 换了新外壳。  
**When** 用户因漏掉该 theorem 的核心 hypothesis 而失败。  
**Then** 该 weakness 是真实 evidence，可以阻塞 readiness。

## 20. Rudin Appendix Must Be Covered

**Given** RA01 前几个 blocks 已完成，但 Chapter 1 Appendix 尚未读。  
**Then** RA01 Core Coverage 仍不完整；必须在 RA01 后续 Rudin block 中覆盖 Appendix 后才能默认 ready。

## 21. Rectifiable Curves Must Be Covered

**Given** RA09 已完成积分主干，但 `Rectifiable Curves` 尚未读。  
**Then** RA09 默认不能以 full Rudin coverage 为由推进。

## 22. Chapter 8 Late Sections Must Be Covered

**Given** RA11 已学 Power Series / exp-log / trig / Fourier，但 Algebraic Completeness 或 Gamma 尚未完成。  
**Then** RA11 Rudin Core Coverage 仍未完成；这些 sections 不能永久 optional。

## 23. Deferred Is Within the Owning RA

**When** reading assignment 写 `Deferred within this RA`。  
**Then** 它只表示当前 block 暂缓；不能把该 Rudin exposition 留到 owning RA readiness 之后。

## 24. Full Rudin Ownership Audit

**When** 对 `04_CURRICULUM.md` 做 curriculum review。  
**Then** Rudin Chapters 1–11 的每个 exposition section 都应有且只有一个 owning RA；Exercises 不要求机械全做。

## 25. Chapter Ready

**Given** owning RA 的全部 Rudin exposition 已 COMPLETED，chapter-specific exit evidence、definition/theorem conditions、boundary、proof/strategy、transfer evidence 齐全，且 blocking weaknesses 已 remediation + independent verification。  
**Then** Project 可以把 Next 推进下一 RA。

## 26. Chapter Not Ready

**Given** 任一情况存在：未完成 Rudin owning scope、缺关键 evidence、或仍有 blocking weakness。  
**Then** Next 留在当前 RA，并明确缺什么。

## 27. User May Skip Without Being Marked Ready

**When** 用户主动要求跳章。  
**Then** 允许跳转，但原 RA 不因用户选择而被记录为 ready。

## 28. Analysis123 Section Locator Is Not Enough for Composite Sections

**Given** Analysis123 §11 同时包含 compactness/Lebesgue number、uniform continuity、pointwise vs uniform convergence、`C([a,b])`。  
**Then** routing 必须拆成：RA04 / RA07 / RA10 的不同 atoms；不能只写“§11 → RA10”就视为 coverage 完成。

## 29. Decimal Research Is Split by Skill

**Given** Analysis123 §43.1 同时包含 DCT exercises 与 decimal representation / interval / measure material。  
**Then** DCT atoms 路由 RA19；representation/cardinality atoms 路由 RA02；Borel/measure atoms路由 RA18；不能整节绑到单一 RA。

## 30. Composite Homework Is Routed Item-by-Item Before Use

**Given** §29.3、§72.1、§86.x 等综合题组。  
**When** Project 选择具体题目。  
**Then** 必须重新判断该 item 的 prerequisite、concept anchor 和诊断目标，不能因整套题有 section locator 就一次性推送。

## 31. Analysis123 Significant Material Has an Anchor

**When** curriculum audit 覆盖 Analysis123。  
**Then** 每个正式 section/homework/exam 有 locator；每个显著 concept/skill/application cluster 还应有 concept anchor；行政文本与纯重复内容除外。

## 32. Concept Anchor and Activation Gate Are Distinct

**Given** 一个 advanced atom 的核心 idea 与 RA04 compactness 强相关，但完整理解需要 RA20 Hilbert background。  
**Then** 可以在 RA04 做 bounded FORWARD preview，activation gate 设为 RA20 后 DEEPEN；不能因为 gate 在 RA20 就把它简单归类为“RA20 内容”。

## 33. RA20 Is Not an Advanced-Material Sink

**When** review §§58–86。  
**Then** distributions/generalized derivatives 应连接 RA08/RA14/RA17/RA18，convolution 连接 RA10/RA19，Fourier transform 连接 RA11/RA19/RA20，compact spectral theory 连接 RA04/RA20，microlocal locality/Fourier/local geometry 分别连接 RA03/RA11/RA13/RA14；RA20 主要承担满足 Hilbert/L2 prerequisite 后的 activation/deepening，而不是所有 advanced atom 的唯一 anchor。

## 34. RA12–RA20 Have Durable Pages

**Given** curriculum 已进入 RA12–RA20。  
**When** runtime 首次进入其中任一 RA。  
**Then** `Review Analysis / RAxx` exact page 必须存在并可 fetch；不能因旧 setup 只建到 RA11 而绕过 Notion lifecycle。

## 35. Rudin Chapter 9 Split Is Logical

**Then** Ch9 默认拆分为：RA12 linear maps/differentiability；RA13 contraction + inverse/implicit/rank；RA14 determinant + higher derivatives + differentiation of integrals。每个 section 只属于一个 owning RA。

## 36. Rudin Chapter 10 Split Is Logical

**Then** Ch10 默认拆分为：RA15 integration/primitive/partition/change of variables；RA16 differential forms/simplexes/chains；RA17 Stokes/closed-exact/vector analysis。

## 37. Rudin Chapter 11 Split Is Logical

**Then** Ch11 默认拆分为：RA18 measure construction/measurability/simple functions；RA19 integration + convergence machinery；RA20 Riemann comparison/complex integration/L2。

## 38. Abbott Coverage Is Pedagogical, Not Reading Completion

**When** Abbott coverage ledger 说某 section 已映射。  
**Then** 表示 tutor 应有意识利用其独特教学价值；不要求用户逐页阅读或为 Abbott 创建 COMPLETED reading state。

## 39. Analysis123 Coverage Is Curriculum-Level, Not Notion Schema

**Then** 不创建 `Analysis123 Coverage` database/checkbox/mastery entity。Routing 保存在 `04_CURRICULUM.md`；Notion 只保存实际发生的正式学习记录。

## 40. Source Conflict Handling

**Given** Analysis123 与 Rudin overlapping core 的 theorem condition / definition 存在冲突或疑点。  
**Then** 先核对正文；Rudin mathematical content / formal conditions 作为课程 reference。Analysis123 独有高阶内容也必须核对正文，不能凭目录补全。

## 41. Retypeset Rudin Copy Is Not Byte-Level Canonical

**Given** 当前 Project Rudin PDF 的 foreword 说明它是重新 typeset 的 working copy，并主动修改过 notation / wording / layout，也可能引入新的 typo。  
**When** 某处 wording、notation 或排版看起来与 theorem intent 不一致。  
**Then** 不把该 PDF 的逐字文本当作绝对 authority；保持 Rudin 原始 numbering 与 mathematical content 为课程基准，并在需要时核对原版 Rudin或其他可靠来源。

## 42. Solution Guide Is Non-Canonical Verification

**Given** Solution Guide 是独立作者自行撰写的 exercise solutions，并明确可能存在 typo/mistake。  
**When** guide 与 Rudin formal content、已核验条件或独立正确论证冲突。  
**Then** guide 不得覆盖更高优先级证据；它只作为 post-attempt verification support。

## 43. DEEPEN Formal Question Uses Primary Evidence Owner

**Given** 一个 advanced atom 在 RA20 才满足 activation gate，但 formal DEEPEN question 实际主要验证 RA04 compactness capability。  
**When** Project 决定把它作为正式 assessment。  
**Then** `Target Evidence` 写明 `Primary RA = RA04`，先 fetch RA04 并在那里分配/创建 Q；RA20 如需记录只追加 `Cross-Chapter Evidence`，不能因为 gate 在 RA20 就把正式 Q 自动归档到 RA20。

## 44. Advanced Exploration Need Not Create a Formal Q

**Given** DEEPEN 内容主要是 advanced exposition / exploration，当前目标不是形成任何 Rudin readiness/mastery evidence。  
**When** Project 进行解释、示例或讨论。  
**Then** 默认不创建 formal Q；普通解释不逐字持久化，只有形成长期值得检索的稳定结论时才可写 Concept Note。
