# Rudin + Abbott 统一实分析路线

## 1. Route Principles

本文件是静态课程地图，不是学习记录。

- **Rudin 是主线**：每次阅读任务首先指定 Rudin 的章节、小节或定理范围；
- **Abbott 是辅助**：用于动机、直觉、另一种证明组织或补救性解释；
- **习题是证据**：测试题从 Rudin / Abbott 习题和自拟题中动态选择；
- **章节不是锁定顺序**：可以回退、跳过、暂停或重新测试；
- **不写死页码**：章节编号和页码以用户上传的教材版本为准。

## 2. Knowledge Chapters

| ID | 知识章节 | Rudin 主线 | Abbott 辅助 | 主要出口证据 |
|---|---|---|---|---|
| RA00 | Proof Language | 预备：定义、量词、反例、证明结构 | 用于建立 proof-writing 习惯 | 能展开定义、写否定、区分“证明”和“说明” |
| RA01 | Real Numbers & Completeness | 实数系统、序结构、上确界性质 | 实数公理、完备性动机 | 能使用 supremum / infimum 并说明假设 |
| RA02 | Countability | 集合、映射、可数性相关材料与习题 | 相关章节或补充材料 | 能构造映射、判断可数性并给出反例 |
| RA03 | Metric Topology | 开集、闭集、邻域、极限点等基本拓扑 | Basic Topology of R；需要时使用 metric-space 解释 | 能在定义和序列语言之间转换 |
| RA04 | Compactness & Connectedness | 紧致性、覆盖、聚点、连通性 | Basic Topology of R 的直觉与证明 | 能使用有限子覆盖、序列刻画和连通性结构 |
| RA05 | Sequences | 数列极限、子列、Cauchy、上极限/下极限相关材料 | Sequences and Series | 能写量词、证明极限性质、构造反例 |
| RA06 | Series | 数项级数、收敛判别、绝对/条件收敛 | Sequences and Series | 能区分收敛概念并选择判别工具 |
| RA07 | Continuity | 连续、均匀连续、极值和介值性质 | Functional Limits and Continuity | 能进行 ε-δ 证明并使用紧致性推论 |
| RA08 | Differentiation | 导数、中值定理、Taylor 型结论 | The Derivative | 能识别假设、构造证明、处理反例 |
| RA09 | Integration | Riemann / Riemann–Stieltjes 积分的定义与性质 | Riemann–Stieltjes Integral | 能区分可积性、估计和积分交换条件 |
| RA10 | Function Sequences | 函数列/函数项级数、逐点与一致收敛 | Sequences and Series of Functions | 能处理一致收敛及其与极限操作的关系 |
| RA11 | Approximation & Synthesis | 选取已上传教材中的综合题、近似材料和后续相关章节 | 用于补直觉、比较证明和综合复习 | 能跨章节选工具并完成一题新的综合问题 |

`RA11` 是综合阶段，不要求把某个后续章节强行归入“近似”。如果上传版本没有对应材料，就使用前面章节的综合习题和证明任务。

## 3. Recommended Reading Order

默认顺序为：

```text
RA00 → RA01 → RA02 → RA03 → RA04 → RA05 → RA06
     → RA07 → RA08 → RA09 → RA10 → RA11
```

这只是认知地图，不是锁定的课程流程。实际学习时可以：

- 在 RA03–RA04 之间来回验证拓扑与紧致性；
- 在 RA05–RA06 之间先学数列再学级数；
- 在 RA07–RA10 中根据当前目标调整顺序；
- 任何时候回到旧章节进行补题。

## 4. Reading Assignment Template

Project 每次只发一个有限阅读块：

```text
Chapter
RAxx — [name]

Rudin
[具体章节 / 小节 / 定理范围]

Reading Focus
1. [核心定义与量词]
2. [定理的假设、结论和使用边界]
3. [需要自己重建的证明步骤]

Abbott Support
暂不要求阅读；若出现缺口，将调用 [相关解释方向]。

Deferred
[暂时不用的习题、证明或后续材料]

Completion Signal
读完后告诉我“这一段读完了”。
```

## 5. Chapter Completion Evidence

“完成章节”不是读完页数，而是目前已有足够证据支持继续。通常需要覆盖：

1. 一个核心定义或定理的准确陈述；
2. 一个假设辨析、例子或反例；
3. 一个短证明、证明骨架或工具选择；
4. 一个 Rudin / Abbott 习题或综合问题（是否需要由前面回答决定）。

这四类是能力覆盖方向，不是固定题数。若用户在基础问题上出现缺口，应先补救，不为了“完成四题”而继续升级。

## 6. Source Mapping Rule

如果不同教材的章节编号与本表不一致：

1. 以用户上传版本中的标题、定理名和目录为准；
2. 保留本表的知识关系，不强行使用错误页码；
3. 在阅读任务中写明具体来源；
4. 无法确认时请求用户提供目录或相关页，不凭记忆补齐。

