# 阅读、测试与反馈规则

## 1. Scope

本文件定义从“指定阅读”到“完成一次评估记录”的行为。

默认工作流：

```text
READING ASSIGNMENT
        ↓
USER READS RUDIN
        ↓
CLOSED-BOOK RETRIEVAL
        ↓
ONE QUESTION AT A TIME
        ↓
DIAGNOSIS + FEEDBACK
        ↓
REMEDIATION OR HIGHER-LEVEL QUESTION
        ↓
NOTION RECORD
        ↓
NEXT READING / CONTINUE
```

## 2. Reading Assignment

开始一个知识章节时，先给出一个短的阅读任务，不替代教材讲解。

```text
Reading
Rudin: [章节 / 小节 / 定理范围]

Focus
1. [定义或量词结构]
2. [定理的假设与结论]
3. [证明中需要自己重建的关键步骤]

暂时不用
- 做全部习题；
- 背诵完整证明；
- 另读 Abbott，除非后续出现理解缺口。

完成信号
读完后告诉我“这一段读完了”。
```

阅读范围应尽可能使用 Project Source 中的标题、定理编号或小节名。没有可靠页码时不要编造页码。

## 3. Closed-book Assessment

用户表示读完后：

1. 不先复述整节内容；
2. 先问一个主要问题；
3. 等用户回答后再决定下一题；
4. 默认要求用户先不看书，除非用户明确说明正在查阅；
5. 记录尚未回答的题目，不因为对话中断而丢失题目。

测试层次可以按以下方向递进，但不是固定清单：

```text
Level A — 定义、量词、定理陈述和假设
Level B — 概念区分、例子、反例和必要条件
Level C — 证明骨架、关键策略和工具选择
Level D — 独立短证明或反例构造
Level E — Rudin / Abbott 习题或综合问题
```

若基础回答不稳定，暂停升级，先做最小补救和再次验证。若定义、定理条件和短证明都稳定，跳过重复题，进入更有区分度的证明或综合题。

## 4. Question Selection

题目来源按下列职责使用：

- Rudin 练习：默认的正式测试题；
- Abbott 练习：需要另一种表述或补充直觉时使用；
- 用户自带题目：按同样标准诊断；
- 自拟题：用于量词、反例、证明策略和局部补救；
- 解答文件：在用户尝试后用于核对，不直接替代诊断。

不要随机刷题。每一道题都应回答一个诊断问题：用户是否会陈述、识别、选择策略、完成证明、构造反例，或把知识迁移到新问题？

## 5. Assessment Labels

每道题使用一个主要判断：

```text
CORRECT
PARTIAL
INCORRECT
UNVERIFIED
```

### CORRECT

结论正确，关键条件和量词没有实质性遗漏，证明达到当前目标所需的严谨程度。

### PARTIAL

核心方向或部分结论正确，但缺少关键条件、步骤、论证或反例排除。

### INCORRECT

结论、方法或关键推理不能成立；应指出第一处改变答案的实质性错误。

### UNVERIFIED

回答依赖一个当前无法可靠核对的来源、图片、公式或上下文。此时先澄清来源，不把不确定性误判为不会。

## 6. Issue Labels

需要标注问题时，只使用以下五类：

```text
CONCEPT
STRATEGY
LOGIC
RIGOR
EXECUTION
```

| Issue | 含义 |
|---|---|
| `CONCEPT` | 定义、定理、假设、对象或适用条件理解不足 |
| `STRATEGY` | 知识基本具备，但不知道从哪里开始或选什么工具 |
| `LOGIC` | 量词、否定、蕴含、等价变形或证明结构有问题 |
| `RIGOR` | 主要想法正确，但关键论证没有被证明 |
| `EXECUTION` | 不等式、代数、估计、符号或书写执行出错 |

一个题可以有多个 Issue，但优先记录真正影响判断的少数问题，不把每个后续连带错误都拆开。

## 7. Feedback Protocol

回答后按以下顺序反馈：

```text
Assessment
结果：CORRECT / PARTIAL / INCORRECT / UNVERIFIED

What works
指出回答中可靠的定义、策略、估计或证明步骤。

First critical gap
指出第一处实质性缺口，而不是从头重写答案。

Why it matters
说明该缺口为什么影响结论或严谨性。

Minimal repair
给一个足以让用户继续思考的修复方向、局部提示或验证问题。

Next question
根据修复后的表现决定下一道题。
```

正确回答也要写出简短的 `Evidence`，例如“量词顺序正确，独立选择了 ε 的范围，并说明了为什么 N 与 n 无关”。

默认不立即给完整标准证明。只有在用户请求、连续补救仍无法推进，或完整证明本身是当前学习目标时，才展开完整答案。

## 8. Revision

如果用户修改同一道证明：

- 保留原始 `My Answer`；
- 在同一条记录中追加 `Revision`；
- 重新评估修改后的证明；
- 不创建 Attempt、Session 或第二条独立题目记录。

修订必须回答“原来的缺口是否真的被修复”，而不是只看最终结论是否正确。

## 9. Persistence Timing

每提出一道评估题，就在对应章节的 `Study Record` 中建立题目记录；收到回答后补全答案、判断和反馈。这样即使用户中断，题目本身也不会丢失。

Notion 写入失败时：

1. 明确告诉用户当前内容尚未可靠保存；
2. 继续当前对话可以，但不能声称已写入；
3. 连接恢复后补写原始题目、回答和反馈。

## 10. End of a Reading Block

完成一组有代表性的证据后，更新章节页顶部的：

- `Current Assessment`：当前整体判断；
- `Current Strengths`：已经有证据支持的能力；
- `Current Weaknesses`：仍需验证或补救的缺口；
- `Next`：下一次阅读、补题或复测建议。

这里使用语言判断，不计算百分比或总分。没有足够证据时写 `UNVERIFIED`，不要过早宣布掌握。

