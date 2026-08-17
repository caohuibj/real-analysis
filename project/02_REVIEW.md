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
下一次建议阅读、问题层次或复测方向。
```

不要用 `87%`、`mastery = 0.8` 等数字替代判断。可以使用 `STABLE`、`PARTIAL`、`UNVERIFIED` 这些简短词，但必须附带证据说明。

## 3. Study Record

所有评估题和用户的有效回答按时间追加到 `## Study Record`。历史记录只追加，不覆盖、不删除。

一次学习可以先有一个阅读块：

```text
### 2026-08-17 — Reading Block

Rudin:
[本次阅读范围]

Reading Focus:
- [重点一]
- [重点二]
```

随后逐题追加。题目格式见 `03_NOTION.md`。

## 4. Evidence Rules

### 正向证据

以下内容要进入 `Current Strengths` 或题目记录的 `Evidence`：

- 独立写出正确的定义和量词；
- 能准确说出定理假设；
- 能选择合适的证明策略；
- 能独立完成证明或构造反例；
- 修改后真正修复了先前的逻辑或严谨性缺口。

### 负向证据

以下内容要进入 `Current Weaknesses` 或题目记录的 `Issue`：

- 概念或定理条件混淆；
- 不知道证明从哪里开始；
- 量词、否定或蕴含方向错误；
- 关键一步以“显然”代替论证；
- 估计、代数或符号执行失败。

一次偶然错误不应被写成稳定的长期缺陷。当前判断要区分“本题暴露的问题”和“跨题、跨次学习仍然出现的问题”。

## 5. Updating the Page

每次完成有诊断价值的测试后：

1. 追加完整题目记录；
2. 更新与本次证据直接相关的 `Current Strengths`；
3. 更新或合并 `Current Weaknesses`，避免把同一个根本问题重复写很多遍；
4. 更新 `Next`；
5. 保留旧判断在历史记录中，不把历史改写成“从来没有出错”。

如果本次回答没有改变对章节的判断，只需追加题目记录，不要为了形式重复重写顶部。

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

1. 读取页面顶部当前判断；
2. 读取最近的 Study Record；
3. 找出尚未验证的弱点和已有的正向证据；
4. 设计下一道能区分“真正稳定”和“刚刚听懂”的题；
5. 不要求用户重新提交整页历史。

如果用户问“我最近主要有什么问题”，读取各章节页面中的 `Current Weaknesses` 和最近记录；如果只问某一道题，定位到该题记录，不要用泛泛的章节判断代替。

## 8. Chapter Readiness

不设置锁定或强制顺序。Project 可以建议进入下一章，但用户始终可以：

- 回到旧章节复测；
- 跳到另一个章节；
- 暂停当前章节；
- 只请求解释而不进行测试。

建议进入下一章只表示目前证据足够支持继续，不表示旧章节永远不会复习。

## 9. No Extra Entities

章节页内部的题目、答案、反馈、修订和 Issue 都是 Markdown 记录，不创建：

```text
Question database
Attempt database
Session database
Issue database
Score field
```

这样可以保持 `Review Analysis` 既能完整留存证据，又不需要维护一个没有实际消费者的 schema。

