# Rudin + Abbott 统一实分析路线

## 1. Route Principles

本文件是静态课程地图，不是学习记录。

- **Rudin 是主线**：用户默认只需要按 Project 指定范围阅读 Rudin；
- **Abbott 是辅助**：用于动机、直觉、另一种证明组织或补救性解释，不默认增加第二套阅读任务；
- **习题是证据**：测试题从 Rudin / Abbott 习题和自拟题中动态选择；
- **章节不是锁定顺序**：可以回退、跳过、暂停或重新测试；
- **不写死页码**：使用上传版本中的 chapter、section title、定理编号或习题编号；页码只有在当前 PDF 中可靠确认时才使用；
- **解答是可选校验源**：只有 substantive attempt 后或用户明确要求 reference/full solution 时才使用；普通 hint 不先查解答。

Rudin 决定课程的数学主线、定义框架和主要习题流。Abbott 只在相应知识节点上提供第二解释层。

### Chapter naming

`RAxx` 是本 Project 的 knowledge chapter；`Rudin Chapter n / Rudin 第 n 章` 是教材章节。一个 Rudin chapter 可能映射到多个 knowledge chapters，例如 Rudin Chapter 3 分成 RA05（sequences）和 RA06（series）。运行时解析规则见 `00_PROJECT.md`；本文件只提供映射关系。

## 2. Knowledge Chapters and Source Mapping

### RA00 — Proof Language

**目标**：建立后续实分析立即需要的证明语言，不单独扩展成逻辑课程。

**进入方式：diagnostic-first**

首次进入 RA00 时，不先布置一整段固定阅读。先用少量问题诊断定义展开、`∀/∃` 量词、命题否定、反例和证明策略；根据结果选择最小的 Rudin 阅读块。若证据不足，只定向调用 Abbott §1.2 中对应的缺口部分，随后用新的独立小题验证。若已有历史，先读取 `Review Analysis / RA00` 再决定是否需要阅读或复测。

**Rudin**

- Chapter 1 — `Introduction`：集合与基本论证语言；
- Chapter 2 开头的 Definition 2.1–2.2：function、image、inverse image，在需要时补充。

**Abbott support**

- §1.2 `Some Preliminaries`：sets、functions、logic、quantifiers、contradiction、contrapositive、induction。

**出口证据**

- 能展开定义并正确处理 `∀` / `∃`；
- 能写一个命题的否定；
- 能区分 direct proof、contradiction、contrapositive；
- 能完成短的集合/函数证明。

---

### RA01 — Real Numbers & Completeness

**Rudin primary** — Chapter 1

Core:

- `Ordered Sets`
- `Fields`
- `The Real Field`

Operational supplement:

- `The Extended Real Number System`
- `The Complex Field`
- `Euclidean Spaces`

Deferred on first pass:

- `Appendix`（Dedekind cuts / construction of `R`）

**Abbott support**

- §1.1 `Discussion: The Irrationality of √2`
- §1.3 `The Axiom of Completeness`
- §1.4 `Consequences of Completeness`

**核心关系**

```text
ordered field
→ least-upper-bound property
→ supremum / infimum
→ Archimedean property
→ density of Q
→ existence results such as nth roots
```

**出口证据**

- 能严格使用 upper bound、supremum、infimum；
- 能说明 maximum 与 supremum 的区别；
- 能在证明中识别何时真正使用 completeness；
- 能处理 Archimedean property 和 density arguments。

---

### RA02 — Countability and the Infinite

**Rudin primary** — Chapter 2

- `Finite, Countable, and Uncountable Sets`

**Abbott support**

- §1.4 `Consequences of Completeness` 中 cardinality / countability 部分
- §1.5 `Cantor's Theorem`

**出口证据**

- 能用 1–1 / onto / bijection 比较集合大小；
- 能构造 enumeration 或证明其不存在；
- 能处理 countable union；
- 能理解并复现 diagonal-type argument。

---

### RA03 — Metric Spaces and Topological Structure

**Rudin primary** — Chapter 2

- `Metric Spaces`

重点包括：metric、neighborhood、open/closed sets、limit points、closure、interior、dense sets、relative topology。

**Abbott support**

- §3.2 `Open and Closed Sets`：先在 `R` 上建立直觉；
- §8.2 `Metric Spaces and the Baire Category Theorem`：需要一般 metric-space 第二解释时使用。

**出口证据**

- 能从 metric definition 推出 neighborhood/open/closed 性质；
- 能处理 limit point、closure、interior；
- 能在 `R` 的直觉和一般 metric-space 定义之间转换。

---

### RA04 — Compactness, Perfectness & Connectedness

**Rudin primary** — Chapter 2

- `Compact Sets`
- `Perfect Sets`
- `Connected Sets`

**Abbott support**

- §3.1 `Discussion: The Cantor Set`
- §3.3 `Compact Sets`
- §3.4 `Perfect Sets and Connected Sets`

Optional enrichment:

- §3.5 `Baire's Theorem`

**出口证据**

- 能使用 open-cover compactness 和有限子覆盖；
- 能说明 compactness 与 sequential behavior 的关系；
- 能处理 perfect sets / Cantor set；
- 能用 connectedness 识别 interval structure。

---

### RA05 — Sequences and Completeness

**Rudin primary** — Chapter 3 前半

- `Convergent Sequences`
- `Subsequences`
- `Cauchy Sequences`
- `Upper and Lower Limits`
- `Some Special Sequences`

**Abbott support**

- §2.2 `The Limit of a Sequence`
- §2.3 `The Algebraic and Order Limit Theorems`
- §2.4 `The Monotone Convergence Theorem and a First Look at Infinite Series`
- §2.5 `Subsequences and the Bolzano–Weierstrass Theorem`
- §2.6 `The Cauchy Criterion`

**出口证据**

- 能精确写出 sequence convergence 的量词；
- 能否定 convergence statement；
- 能独立完成基本 `ε-N` proof；
- 能使用 subsequence / Bolzano–Weierstrass；
- 能解释 Cauchy criterion 与 completeness；
- 能处理 `lim sup` / `lim inf`。

---

### RA06 — Numerical Series

**Rudin primary** — Chapter 3 后半

- `Series`
- `Series of Nonnegative Terms`
- `The Number e`
- `The Root and Ratio Tests`
- `Power Series`
- `Summation by Parts`
- `Absolute Convergence`
- `Addition and Multiplication of Series`
- `Rearrangements`

**Abbott support**

- §2.1 `Discussion: Rearrangements of Infinite Series`
- §2.4 中 infinite series 的初次引入
- §2.7 `Properties of Infinite Series`
- §2.8 `Double Summations and Products of Infinite Series`

**说明**

这里学习 power series 的重点是**作为 series 的收敛问题**；它们作为函数的连续、微分、Taylor 展开等结构放到 RA10–RA11。

**出口证据**

- 能区分 convergence、absolute convergence、conditional convergence；
- 能选择并证明适用的 convergence test；
- 能处理 rearrangement / Cauchy product / summation by parts；
- 能判断 power series 的 convergence behavior。

---

### RA07 — Limits and Continuity

**Rudin primary** — Chapter 4

- `Limits of Functions`
- `Continuous Functions`
- `Continuity and Compactness`
- `Continuity and Connectedness`
- `Discontinuities`
- `Monotonic Functions`
- `Infinite Limits and Limits at Infinity`

**Abbott support**

Core:

- §4.1 `Discussion: Examples of Dirichlet and Thomae`
- §4.2 `Functional Limits`
- §4.3 `Combinations of Continuous Functions`
- §4.4 `Continuous Functions on Compact Sets`
- §4.5 `The Intermediate Value Theorem`

Optional enrichment:

- §4.6 `Sets of Discontinuity`

**出口证据**

- 能进行 `ε-δ` functional-limit proof；
- 能使用 sequential criterion；
- 能证明并应用 continuous image of compact/connected sets；
- 能正确使用 Extreme Value / uniform continuity / Intermediate Value arguments。

---

### RA08 — Differentiation

**Rudin primary** — Chapter 5

- `The Derivative of a Real Function`
- `Mean Value Theorems`
- `The Continuity of Derivatives`
- `L'Hopital's Rule`
- `Derivatives of Higher Order`
- `Taylor's Theorem`
- `Differentiation of Vector-valued Functions`

**Abbott support**

- §5.1 `Discussion: Are Derivatives Continuous?`
- §5.2 `Derivatives and the Intermediate Value Property`
- §5.3 `The Mean Value Theorem`
- §5.4 `A Continuous Nowhere-Differentiable Function`

**说明**

本章的 Taylor 内容是 finite-order Taylor theorem / remainder。Taylor **series** 放在 RA11。

**出口证据**

- 能从 derivative definition 构造证明；
- 能识别 MVT/Rolle hypotheses；
- 能理解 derivative 不必连续但具有 intermediate value property；
- 能使用 Taylor remainder 而不把 function 与 Taylor series 混同。

---

### RA09 — Riemann and Riemann–Stieltjes Integration

**Rudin primary** — Chapter 6

Core:

- `Definition and Existence of the Integral`
- `Properties of the Integral`
- `Integration and Differentiation`

Optional / later in the same chapter:

- `Rectifiable Curves`

**Abbott support** — Chapter 7 `The Riemann Integral`

- §7.1 `Discussion: How Should Integration be Defined?`
- §7.2 `The Definition of the Riemann Integral`
- §7.3 `Integrating Functions with Discontinuities`
- §7.4 `Properties of the Integral`
- §7.5 `The Fundamental Theorem of Calculus`

Optional enrichment:

- §7.6 `Lebesgue's Criterion for Riemann Integrability`

**Special reading bridge**

RA09 是少数允许 Abbott 主动先行的地方。第一次进入积分时，可以先用 Abbott §7.1–§7.2 建立 Riemann integral 的动机和 upper/lower sums，再进入 Rudin Chapter 6 的 Riemann–Stieltjes generalization。用户不需要把 Abbott Chapter 7 全部作为第二套必读。

**出口证据**

- 能用 upper/lower sums 或相应 criterion 判断 integrability；
- 能区分 Riemann 与 Riemann–Stieltjes 的角色；
- 能证明并使用 integral properties；
- 能准确说明 Fundamental Theorem of Calculus 的 hypotheses。

---

### RA10 — Sequences and Series of Functions

**Rudin primary** — Chapter 7，先到 Stone–Weierstrass 之前

- `Discussion of the Main Problem`
- `Uniform Convergence`
- `Uniform Convergence and Continuity`
- `Uniform Convergence and Integration`
- `Uniform Convergence and Differentiation`
- `Equicontinuous Families of Functions`

Deferred to RA11:

- `The Stone-Weierstrass Theorem`

**Abbott support**

- §6.1 `Discussion: Branching Processes`
- §6.2 `Uniform Convergence of a Sequence of Functions`
- §6.3 `Uniform Convergence and Differentiation`
- §6.4 `Series of Functions`

**出口证据**

- 能严格区分 pointwise 与 uniform convergence；
- 能判断何时 continuity / integration / differentiation 可与 limit 交换；
- 能使用 uniform Cauchy-style criteria；
- 能处理基本 equicontinuity arguments。

---

### RA11 — Approximation, Power Series & Special Functions

这是 Core Track 的 capstone，不是模糊的“综合题”章节。

**Rudin primary**

Chapter 7:

- `The Stone-Weierstrass Theorem`

Chapter 8 core:

- `Power Series`
- `The Exponential and Logarithmic Functions`
- `The Trigonometric Functions`
- `Fourier Series`

Optional enrichment from Chapter 8:

- `The Algebraic Completeness of the Complex Field`
- `The Gamma Function`

**Abbott support**

- §6.5 `Power Series`
- §6.6 `Taylor Series`
- §8.3 `Fourier Series`

**核心关系**

```text
uniform convergence
→ power-series regularity
→ Taylor series and its limits
→ approximation by polynomials
→ Stone-Weierstrass / Fourier viewpoints
```

**出口证据**

- 能证明 power series 在适当区域的 uniform convergence / termwise operations；
- 能区分 smooth、analytic、equal to Taylor series；
- 能理解 polynomial approximation 的数学问题；
- 能使用 Stone–Weierstrass 或 Fourier material 完成新的综合证明。

## 3. Recommended Reading Order

默认顺序为：

```text
RA00 → RA01 → RA02 → RA03 → RA04 → RA05 → RA06
     → RA07 → RA08 → RA09 → RA10 → RA11
```

这是知识依赖地图，不是锁定机制。用户可以回退、跳转、暂停或提前讨论后续内容。

Rudin Chapters 9–11（several variables、differential forms、Lebesgue theory）不属于当前 RA00–RA11 Core Track；需要时以后单独扩展，不在 v0 中预先增加更多运行实体。

## 4. Reading Block Rule

Project 不应把上面的 knowledge chapter 一次全部布置给用户。进入或恢复章节时，先读取 `Review Analysis / RAxx` 的顶部状态和最近 Study Record，再选择一个自然且有限的 Rudin reading block；没有历史时才使用该章节的首个自然 block。通常由相邻的一小组定义、定理或 section 构成。

布置教材习题前先检查历史，避免无意重复；若确有复测目的，按照 `01_LEARNING.md` / `03_NOTION.md` 新建 Retest record 并引用原题，不改写原来的 COMPLETE 记录。

例如 RA05 可以自然拆成：

```text
Block A
Convergent Sequences

Block B
Subsequences + Cauchy Sequences

Block C
Upper and Lower Limits + selected special sequences
```

具体切块由当前历史证据和教材结构决定，但不重新设计课程顺序。

## 5. Reading Assignment Template

```text
Chapter
RAxx — [name]

Rudin
[具体 chapter / section / theorem range]

Reading Focus
1. [核心定义与量词]
2. [定理的假设、结论和使用边界]
3. [需要自己重建的证明步骤]

Abbott Support
默认暂不要求阅读；若出现缺口，将调用 [对应 section / explanation direction]。RA00 若诊断显示 proof language 不足，只定向调用 Abbott §1.2 的相关部分，不把整节自动变成必读任务。

Deferred
[暂时不用的习题、证明或后续材料]

Completion Signal
读完后告诉我“这一段读完了”。
```

RA09 可以例外地先建议 Abbott §7.1–§7.2 作为 Riemann integral 的概念桥梁。

## 6. Chapter Completion Evidence

“完成章节”不是读完页数，也不是连续答对若干基础题，而是目前已有足够证据支持继续。**正式的默认 readiness contract 以 `02_REVIEW.md §8` 为准。** 本文件中的“出口证据”用于说明各章应该验证什么数学能力。

默认 readiness 至少要覆盖以下能力方向：

1. 核心定义、量词或关键定理条件的准确独立陈述；
2. 假设辨析、适用边界、例子或反例；
3. 独立短证明、证明骨架或策略选择；
4. 一道有区分度的 Rudin / Abbott 习题或综合问题，或者已有证明题已明显覆盖同等迁移能力；
5. 本章仍重要的 `PARTIAL` / `INCORRECT` 缺口必须经过 remediation，并由新的独立作答、Revision 或 Retest 验证修复。

解答 reference 不是完成章节的必需证据，也不应在用户没有 substantive attempt 时提前使用。“听懂了解释”本身也不是完成证据，除非随后有独立验证。

这些是能力覆盖方向，不是固定题数。一道高质量问题可以提供多类证据；若用户在基础问题上出现缺口，应先补救，不为了“完成四题”而继续升级。

默认 readiness 不成立时，`Next` 继续留在当前 knowledge chapter，并明确缺失的证据或待修复能力；用户仍可主动跳章，但该选择不能被记录成“已经验证掌握”。

## 7. Source Mapping Rule

如果实际上传版本与本文件的 section title 或编号不一致：

1. 以当前 Project Source 的目录和正文为准；
2. 保留本文件的知识关系，不强行使用错误页码；
3. 在阅读任务中写明实际确认的来源；
4. 无法确认时请求相关页或检查 Project Source，不凭记忆补齐。
