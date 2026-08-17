# Real Analysis Tutor

一个基于 ChatGPT Project 的实分析学习工作流。

它把职责分成三层：

- **Rudin**：你的主线教材。你按 Project 指定的范围自行阅读。
- **ChatGPT Project**：给出阅读建议、逐题测试、诊断回答，并在需要时用 Abbott、习题和解答作为辅助。
- **Notion**：唯一的长期学习记录，页面名称为 `Review Analysis`。

GitHub 只保存 Project 的运行文件和课程路线；日常学习不需要访问 GitHub，也不需要运行代码。

## 核心闭环

```text
进入 / 恢复章节并读取历史
        ↓
选择一个有限的 Rudin 阅读块
        ↓
你自行阅读
        ↓
你说“读完了”
        ↓
提出评估题并立即保存题目
        ↓
你回答后更新同一条记录
        ↓
诊断、反馈、必要时补充解释
        ↓
补救后独立验证
        ↓
检查章节 readiness
        ↓
继续本章 / 推进下一章
```

题目数量不是固定课程配置。回答稳定时提高问题层次；出现缺口时先补救并再次验证。只有核心定义/条件、概念边界、证明能力和迁移能力已有足够证据，而且重要缺口已完成补救与独立验证时，Project 才默认建议推进下一知识章节。用户始终可以主动跳章，但跳章不等于“已经验证掌握”。

## ChatGPT Project 装配

### 1. 新建 Project

在 ChatGPT 中新建一个 Project，例如命名为 `Real Analysis Tutor`。

### 2. 粘贴 Project Instructions

在 Project Settings 中使用以下最小 instructions：

```text
这是一个基于 Project 的实分析学习辅导系统。

以 project/00_PROJECT.md 为总入口，并按职责使用：
- project/01_LEARNING.md：阅读、提问、作答诊断和反馈；
- project/02_REVIEW.md：Review Analysis 章节页面的更新规则和章节 readiness；
- project/03_NOTION.md：Notion 页面结构、写入、题号和读取规则；
- project/04_CURRICULUM.md：Rudin 主线与 Abbott 辅助的章节路线。

Rudin 是用户实际阅读的主教材。进入或恢复章节时，先读取 `Review Analysis / RAxx` 的顶部状态和最近 Study Record，再选择下一段阅读。
默认先让用户阅读，再进行 closed-book、一次一题的自适应测试；这是默认节奏，不是不可覆盖的锁定流程。

`RAxx` 表示 Project 的 knowledge chapter；`Rudin Chapter n / Rudin 第 n 章` 表示教材章节。用户只说“第 n 章”且确有歧义时，先简短澄清，不要猜测。

Abbott、习题和解答是 Project 的辅助资源，不要默认增加第二套阅读任务。解答是可选的事后校验源：只有用户已经进行实质性尝试，或明确要求参考解 / 完整解时才查阅；普通提示不先查解答。

正式评估题一旦提出，就先在对应章节页建立未回答记录；用户首次回答后完成同一条记录。记录成为 COMPLETE 后，原始答案、判断和反馈不改写；同一轮修订追加 Revision，之后有意复测则新建 Retest record 并引用原题。
所有测试题、用户答案、掌握良好或存在缺口的证据都要保存到 Notion 的 Review Analysis 对应章节页面。

创建新评估题前重新读取章节页，优先恢复已有 OPEN 题，并使用下一个未占用的 Q number；多个 conversation 不得各自猜题号。
布置教材习题前先检查历史，避免无意重复；有意复测时明确标记 `Retest of RAxx/Qn — [目的]`。跨章节相关证据只保存轻量引用，不复制整条记录。
普通澄清性对话只在形成高价值结论时压缩记录，不要保存完整聊天 transcript。

默认只有在核心陈述、概念边界、证明/策略、迁移应用已有足够正向证据，且重要缺口已 remediation + independent verification 后才建议推进下一 knowledge chapter；否则 Next 继续留在当前章并说明缺什么。

不要创建后端、代码、额外数据库、题目实体、Attempt、Session、分数模型或命令语法。
```

### 3. 上传 Project Files

将以下文件作为 Project Files 上传：

```text
project/00_PROJECT.md
project/01_LEARNING.md
project/02_REVIEW.md
project/03_NOTION.md
project/04_CURRICULUM.md
```

再上传学习资料：

```text
Rudin 教材 PDF
Abbott 教材 PDF
Rudin / Abbott 习题或解答 PDF（如有）
个人笔记或章节索引 Markdown（如有）
```

不要把 README 当作运行规则；它是装配和维护说明。GitHub 仓库也不是日常学习资料源。

### 4. 准备 Notion

连接一个能够执行写入操作的 Notion 连接，并新建一个顶层页面：

```text
Review Analysis
```

在其下创建 `RA00`–`RA11` 章节子页面。页面模板、字段和写入规则见 [`project/03_NOTION.md`](project/03_NOTION.md)。

如果只有只读 Notion 同步，Project 可以回答问题，但不能可靠完成本项目要求的长期留存；不要把未成功写入的内容说成“已保存”。正式评估题的初始记录或后续更新任何一次失败，都必须明确告知用户尚未可靠保存。

### 5. 用验收场景检查装配

按 [`acceptance/SCENARIOS.md`](acceptance/SCENARIOS.md) 做一次人工验收。通过后即可开始学习。

## 日常使用

只使用自然语言，不需要命令或参数。

```text
开始 RA01。
```

Project 应进入 knowledge chapter RA01，并先给出 Rudin 阅读范围、阅读重点和暂缓内容。

```text
开始 Rudin 第 3 章。
```

Project 应根据课程映射和历史，在该教材章对应的 RA05 / RA06 中选择当前应该继续的 knowledge chapter。

如果只说：

```text
开始第三章。
```

而当前上下文无法判断你指 RA03 还是 Rudin Chapter 3，Project 应只做一次简短澄清，不自行猜测。

```text
Rudin 这一段我读完了。
```

Project 应直接进入 closed-book 测试，一次只问一个主要问题，不先把本节总结一遍。

```text
我不理解这里为什么要用 supremum。
```

Project 可以暂时切换到解释模式；解释后默认回到测试，确认你能独立使用该概念。

```text
继续测试。
```

恢复当前章节的自适应提问。

```text
查看 RA05 当前记录。
```

Project 应先读取 `Review Analysis` 中的章节页面，再总结当前稳定能力、缺口、历史证据和下一步，不只依赖当前聊天记忆。

## 什么需要保存

每个评估题都要在对应章节页面中保留：

- `Question`：完整题目；
- `Source`：Rudin、Abbott、习题、用户题目或自拟题，以及已知的章节/题号；
- `My Answer`：用户原始回答；
- `Assessment`：原始回答的 `CORRECT`、`PARTIAL`、`INCORRECT` 或 `UNVERIFIED` 判断；
- `Feedback`：判断依据、做得好的地方和最早的实质性缺口；
- `Issue`：需要时使用 `CONCEPT`、`STRATEGY`、`LOGIC`、`RIGOR`、`EXECUTION`；
- `Revision`、`Revision Assessment`、`Revision Feedback`：同一轮反馈后的修正，追加在原记录中，不能覆盖原始判断；
- `Retest`：之后重新独立做同题时建立新的 Q record，并写 `Retest of RAxx/Qn — [目的]`。

掌握好的回答同样保存，因为它们是进入下一章节或判断稳定性的正向证据。

普通的解释性聊天不逐字复制。只有当讨论产生了以后值得检索的结论时，才在章节页追加一个精炼的 `Concept Note`。

## 学习资料要求

优先使用可搜索、带可靠文本层的原生 PDF 或 Markdown。扫描 PDF 只有在 OCR 文字层经过检查时才适合作为长期 Project Source。公式、表格或图片无法可靠读取时，应让用户提供对应页或截图，不要凭记忆补写教材内容。

文件大小和数量以当前 ChatGPT Project 界面及账户套餐的实际限制为准，不把某个会变化的数字写入学习规则。

## 仓库结构

```text
.
├── README.md
├── project/
│   ├── 00_PROJECT.md
│   ├── 01_LEARNING.md
│   ├── 02_REVIEW.md
│   ├── 03_NOTION.md
│   └── 04_CURRICULUM.md
└── acceptance/
    └── SCENARIOS.md
```

此版本不包含服务、脚本、Notion API client、题库、JSON schema、CI 或统计 dashboard。
