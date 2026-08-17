# Rudin 主线 + Tutor-side Enrichment 路线

## 1. Route Principles

本文件是静态课程地图，不是学习记录。

整个 Project 只有一条课程主线：**Rudin**。

```text
Rudin
= 决定学什么、按什么顺序学、用户实际阅读什么、core coverage 何时完成

Abbott
= tutor-side conceptual / proof-structure source
= 解释为什么这样想、直觉在哪里会失败、证明如何组织

《数学分析之课程讲义》（下称 Analysis123）
= tutor-side enrichment / application / exercise source
= 展示当前概念还能做什么、如何推广、如何连接几何/物理/后续分析

ChatGPT
= 以当前 Rudin 节点为中心，把三者组织成一次自包含的 RA 学习体验
```

核心原则：**one textbook, multiple teaching sources**。

### 1.1 User-facing reading

- 用户默认只阅读 Rudin；
- 正式 reading block 只从 Rudin 指定；
- Abbott 和 Analysis123 默认不创建额外 reading block；
- 需要 Abbott / Analysis123 的定义、例子、解释、背景或题目时，由 Project 在 chat 中直接提供完成当前任务所需的自包含内容；
- 不要求用户为了一个 enrichment prompt 离开 Rudin 去顺读第二本或第三本教材。

### 1.2 Rudin coverage

Rudin Chapters 1–11 全部属于本路线，不再区分 Analysis 1 / Analysis 2。

- RA00–RA11 保留现有主结构；
- Rudin Chapters 9–11 继续自然拆成 RA12+；
- Rudin 的 exposition sections 最终都应进入某个 core reading scope；
- `deferred` 只表示推迟到更合适的 reading block，不表示永久 optional；
- Rudin 习题仍按诊断价值动态选择，不要求机械完成每一道题。

### 1.3 Abbott coverage principle

Abbott 不决定课程顺序，但应尽量完整利用。

- Abbott 中与 Rudin curriculum 有实质联系的 discussion、core exposition、project section、counterexample 和高价值 exercise，都应映射到一个或多个 RA；
- 默认用途是 `CONCEPT`（动机/直觉）、`PROOF`（证明结构）、`BOUNDARY`（反例/边界）、`TRANSFER`（另一种表述或应用）；
- Abbott 可以主动用于教学，不必等到用户答错；但不得因此增加第二套必读课程；
- Abbott 的使用不能替代用户对 Rudin core 的独立 mastery evidence。

### 1.4 Analysis123 coverage principle

Analysis123 不按原讲义顺序成为第二条课程，而要**拆成 knowledge / skill / application atoms 后路由到最合适的 Rudin RA**。

- 每个正式 section、作业、习题课、考试或重要主题至少要有一个 RA anchor；
- 一节中若包含多个知识点，应拆分到不同 RA，而不是整节硬塞进一个 RA；
- 路由位置由 prerequisite、知识关系和训练价值决定，而不是由原讲义页码或学期顺序决定；
- 允许同一素材有 primary anchor 和 secondary anchor；
- Advanced material 可以以 `FORWARD` 方式提前建立联系，或在后续最合适的 RA 中作为 `TRANSFER` / `APPLICATION` 推送；
- Analysis123 本身不增加 core syllabus requirement；但如果 enrichment question 暴露出对 Rudin core 的真实弱点，该证据可以阻塞 readiness；
- 讲义明确包含笔误，尤其后半部分更需谨慎。凡与 Rudin 的定义、定理条件或可核对事实冲突时，以当前 Rudin source 为课程标准来源；Analysis123 的高阶内容在正式推送前应核对上下文，不凭目录标题补全细节。

### 1.5 Tutor-push timing

Analysis123 / Abbott 素材按以下时机使用：

```text
INLINE
= 当前 Rudin 概念刚出现时，用于建立动机、第二解释或最短应用

TRANSFER
= Rudin core 已初步掌握后，用新情境检验是否真正会用

FORWARD
= 现在只建立后续分析中的位置感，不要求当前掌握完整理论
```

`FORWARD` 本身不构成 readiness requirement；如果 Project 把某个 forward topic 正式升级为 assessment，则应明确它要诊断的是哪一个已经学过的 Rudin skill。

### 1.6 Chapter naming

`RAxx` 是本 Project 的 knowledge chapter；`Rudin Chapter n / Rudin 第 n 章` 是教材章节。一个 Rudin chapter 可以拆成多个 RA。运行时解析规则见 `00_PROJECT.md`。

---

## 2. Knowledge Chapters and Source Mapping

### RA00 — Proof Language

**目标**：建立后续分析立即需要的证明语言，不单独扩展成逻辑课程。

**进入方式：diagnostic-first**

首次进入 RA00 时先诊断定义展开、`∀/∃`、否定、反例、direct / contradiction / contrapositive 等，再决定是否需要最小 Rudin reading block。

**Rudin core**

- Chapter 1 — `Introduction` 中出现的集合、数系与基本论证语言；
- Chapter 2 Definition 2.1–2.2 的 function、image、inverse image，在需要时补充。

**Abbott conceptual layer**

- §1.2 `Some Preliminaries`：sets、functions、logic、quantifiers、contradiction、contrapositive、induction。

**Analysis123 tutor push**

- 将讲义中贯穿各章的“定义展开 → 量词 → 反例 / 证明”写法作为例题来源；
- 不把讲义的任何正式 section 设为 RA00 reading；
- 讲义后续大量多问式习题可以拆出短 proof-language drill，但必须保持当前数学背景自包含。

**出口证据**

- 能展开定义并正确处理 `∀` / `∃`；
- 能写命题否定；
- 能区分 direct proof、contradiction、contrapositive；
- 能完成短集合/函数证明。

---

### RA01 — Real Numbers & Completeness

**Rudin primary — Chapter 1**

Core:

- `Ordered Sets`
- `Fields`
- `The Real Field`
- `The Extended Real Number System`
- `The Complex Field`
- `Euclidean Spaces`

Later return within RA01:

- `Appendix` — Dedekind construction of `R`。首次可以 deferred，但在 Rudin 全路线完成前必须回来覆盖。

**Abbott conceptual layer**

- §1.1 `Discussion: The Irrationality of √2`
- §1.3 `The Axiom of Completeness`
- §1.4 `Consequences of Completeness`
- §8.4 `A Construction of R From Q` 作为 Dedekind / construction 的第二解释。

**Analysis123 tutor push**

- §1 实数的公理化描述；
- §2 区间套公理、确界原理中与 completeness 对照的内容；
- §3 Dedekind 分割；
- §6 指数/三角函数构造中的“从完备性构造具体对象”作为 `FORWARD/TRANSFER`；
- §29.3 寒假作业中与实数构造、完备性直接相关的题按 item 拆分后再使用。

**核心关系**

```text
ordered field
→ least-upper-bound property
→ supremum / infimum
→ Archimedean property
→ density of Q
→ existence / construction arguments
```

**出口证据**

- 能严格使用 upper bound、supremum、infimum；
- 能说明 maximum 与 supremum 的区别；
- 能识别证明中 completeness 的真正使用点；
- 能处理 Archimedean property 与 density arguments；
- 在 later return 中能解释 Dedekind construction 的目标与结构。

---

### RA02 — Countability and the Infinite

**Rudin primary — Chapter 2**

- `Finite, Countable, and Uncountable Sets`

**Abbott conceptual layer**

- §1.4 中 cardinality / countability；
- §1.5 `Cantor's Theorem`。

**Analysis123 tutor push**

- §3.1 作业：可数与不可数、Schröder–Bernstein；
- §25.1 中密度型 number-theoretic exercise 可作为 `TRANSFER`，但只在其 proof burden 不依赖未学技术时使用；
- §43.1 十进制小数研究中与 cardinality / representation 相关的子题作为 later transfer。

**出口证据**

- 能用 injection / surjection / bijection 比较集合大小；
- 能构造 enumeration 或证明其不存在；
- 能处理 countable union；
- 能复现 diagonal-type argument。

---

### RA03 — Metric Spaces and Topological Structure

**Rudin primary — Chapter 2**

- `Metric Spaces`

重点：metric、neighborhood、open/closed、limit point、closure、interior、dense、relative topology。

**Abbott conceptual layer**

- §3.2 `Open and Closed Sets`；
- §8.2 `Metric Spaces and the Baire Category Theorem` 中 metric-space language。

**Analysis123 tutor push**

- §2 中 distance-space language；
- §4–5 中 metric-space convergence 的统一表述；
- §7 中 complete metric / normed spaces、equivalent metrics / norms（completeness 部分与 RA05 交叉）；
- §10 开集、闭集、闭包、聚点、连续性的拓扑刻画；
- §10.1 作业；
- §12 距离空间完备化中的 construction idea（与 RA05 cross-anchor）；
- §12.1 “无穷多素数的拓扑证明”作为 topology transfer；
- §33.1 拓扑空间习题课作为 `FORWARD`：只抽取能由 metric-space language 支撑的部分，不提前要求一般拓扑全套理论。

**出口证据**

- 能从 metric definition 推出 neighborhood/open/closed 性质；
- 能处理 limit point、closure、interior、dense；
- 能在 `R` 的直觉和一般 metric-space 定义之间转换。

---

### RA04 — Compactness, Perfectness & Connectedness

**Rudin primary — Chapter 2**

- `Compact Sets`
- `Perfect Sets`
- `Connected Sets`

**Abbott conceptual layer**

- §3.1 `Discussion: The Cantor Set`
- §3.3 `Compact Sets`
- §3.4 `Perfect Sets and Connected Sets`
- §3.5 `Baire's Theorem`

**Analysis123 tutor push**

- §10 中 compact sets / limit points；
- §11 紧性、开覆盖、Heine–Borel、Lebesgue number；
- §12.2 连续函数环极大理想中 compactness 的角色，作为 `FORWARD/TRANSFER`；
- §16 space-filling curve 可用于测试 connectedness / compact-image intuition；
- §28 Baire category theorem；
- §50 Brouwer fixed-point theorem 的二维证明作为 `FORWARD`：强调 compactness / topology 的后续力量，不把 Brouwer theorem 本身设为本章 readiness requirement；
- §77–79 中 compact operators / spectral compactness 仅作远期 `FORWARD`，用于建立“compactness 从集合到算子”的迁移图景。

**出口证据**

- 能使用 open-cover compactness 和有限子覆盖；
- 能说明 compactness 与 sequential behavior 的关系；
- 能处理 perfect sets / Cantor set；
- 能用 connectedness 识别 interval structure；
- 能在新情境中识别“局部信息经 compactness 统一为有限/全局控制”的模式。

---

### RA05 — Sequences and Completeness

**Rudin primary — Chapter 3 前半**

- `Convergent Sequences`
- `Subsequences`
- `Cauchy Sequences`
- `Upper and Lower Limits`
- `Some Special Sequences`

**Abbott conceptual layer**

- §2.2 `The Limit of a Sequence`
- §2.3 `The Algebraic and Order Limit Theorems`
- §2.4 `The Monotone Convergence Theorem and a First Look at Infinite Series`
- §2.5 `Subsequences and the Bolzano–Weierstrass Theorem`
- §2.6 `The Cauchy Criterion`

**Analysis123 tutor push**

- §4 极限、Cauchy 列、metric convergence；
- §5 Cauchy criterion、vector sequences、Bolzano–Weierstrass、special limits；
- §7 complete metric / normed spaces 与 Picard fixed point 的 completeness viewpoint（Picard 主 anchor 在 RA13）；
- §12 metric completion；
- §29.3 中 sequence / convergence item 按题拆分。

**出口证据**

- 能精确写出 sequence convergence 的量词；
- 能否定 convergence statement；
- 能独立完成基本 `ε-N` proof；
- 能使用 subsequence / Bolzano–Weierstrass；
- 能解释 Cauchy criterion 与 completeness；
- 能处理 `lim sup` / `lim inf`。

---

### RA06 — Numerical Series

**Rudin primary — Chapter 3 后半**

- `Series`
- `Series of Nonnegative Terms`
- `The Number e`
- `The Root and Ratio Tests`
- `Power Series`
- `Summation by Parts`
- `Absolute Convergence`
- `Addition and Multiplication of Series`
- `Rearrangements`

**Abbott conceptual layer**

- §2.1 `Discussion: Rearrangements of Infinite Series`
- §2.4 中 series introduction；
- §2.7 `Properties of Infinite Series`
- §2.8 `Double Summations and Products of Infinite Series`

**Analysis123 tutor push**

- §4–5 中 series Cauchy criterion / absolute convergence；
- §6 double-index summation；
- §6.1 Riemann rearrangement、Cesàro summation；Banach–Mazur game 交叉到 RA04；
- §7 product series、Riemann ζ、Dirichlet / Abel tests；
- §7.1 primes reciprocal sum、Basel problem；
- §23 Leibniz `π/4` series historical connection；
- §23.1 `ζ(2)` irrationality；
- §25.1 number-theoretic density exercise 若主要依赖 series / summation 则在此 transfer；
- §29.3 中 series item 按题拆分。

**说明**

这里的 power series 重点是作为 numerical / coefficient convergence object；函数正则性与 Taylor structure 在 RA10–RA11 再处理。

**出口证据**

- 能区分 convergence / absolute / conditional convergence；
- 能选择并证明适用 convergence test；
- 能处理 rearrangement / Cauchy product / summation by parts；
- 能判断 power-series convergence behavior。

---

### RA07 — Limits and Continuity

**Rudin primary — Chapter 4**

全部 sections：

- `Limits of Functions`
- `Continuous Functions`
- `Continuity and Compactness`
- `Continuity and Connectedness`
- `Discontinuities`
- `Monotonic Functions`
- `Infinite Limits and Limits at Infinity`

**Abbott conceptual layer**

- §4.1 `Discussion: Examples of Dirichlet and Thomae`
- §4.2 `Functional Limits`
- §4.3 `Combinations of Continuous Functions`
- §4.4 `Continuous Functions on Compact Sets`
- §4.5 `The Intermediate Value Theorem`
- §4.6 `Sets of Discontinuity`

**Analysis123 tutor push**

- §8 function continuity；
- §9 metric-space continuity、IVT、elementary-function construction；
- §10 continuity 的 topological characterization；
- §11 uniform continuity 部分；pointwise/uniform convergence 主 anchor 在 RA10；
- §12 continuous functions constructed by convergent series（交叉 RA10）；
- §12.2 continuous-function ring maximal ideals；
- §16 space-filling curve 作为 continuous-image / topology boundary example；
- §43.1 decimal expansion 中 function-limit / continuity item 按题拆分。

**出口证据**

- 能进行 `ε-δ` functional-limit proof；
- 能使用 sequential criterion；
- 能证明并应用 continuous image of compact / connected sets；
- 能正确使用 EVT / uniform continuity / IVT arguments；
- 能处理典型 discontinuity counterexamples。

---

### RA08 — Differentiation

**Rudin primary — Chapter 5**

全部 sections：

- `The Derivative of a Real Function`
- `Mean Value Theorems`
- `The Continuity of Derivatives`
- `L'Hopital's Rule`
- `Derivatives of Higher Order`
- `Taylor's Theorem`
- `Differentiation of Vector-valued Functions`

**Abbott conceptual layer**

- §5.1 `Discussion: Are Derivatives Continuous?`
- §5.2 `Derivatives and the Intermediate Value Property`
- §5.3 `The Mean Value Theorem`
- §5.4 `A Continuous Nowhere-Differentiable Function`

**Analysis123 tutor push**

- §13 derivative definition / elementary differentiation；
- §14 Leibniz、Faà di Bruno、vector-valued derivative、extrema、Rolle/MVT、nowhere-differentiable construction；
- §15 MVT applications、Darboux、Cauchy MVT、trigonometric ODE viewpoint；matrix exponential cross-anchor RA12；
- §15.1 Takagi function；
- §16 L'Hôpital、Taylor；space-filling curve cross-anchor RA07；
- §17 convex functions / Jensen；
- §17.1 Borel lemma / Peano proof 作为 `FORWARD`：强调 finite Taylor data 与 arbitrary jet 的区别；
- §23 differentiation under parameter integral 只作 forward，正式 anchor RA14 / RA19；
- §58–64 distributional derivative / jump formula / fundamental solutions 作为远期 `FORWARD`：用于说明“导数”概念可继续推广，但不要求当前掌握 distribution theory。

**出口证据**

- 能从 derivative definition 构造证明；
- 能识别 MVT / Rolle hypotheses；
- 能理解 derivative 不必连续但具有 IVP；
- 能使用 Taylor remainder 而不把 function 与 Taylor series 混同；
- 能在 vector-valued / convexity 等新情境中迁移基本 derivative reasoning。

---

### RA09 — Riemann and Riemann–Stieltjes Integration

**Rudin primary — Chapter 6**

全部 sections：

- `Definition and Existence of the Integral`
- `Properties of the Integral`
- `Integration and Differentiation`
- `Rectifiable Curves`

`Rectifiable Curves` 可以晚于前三节，但最终仍属于 Rudin core coverage。

**Abbott conceptual layer**

- §7.1 `Discussion: How Should Integration be Defined?`
- §7.2 `The Definition of the Riemann Integral`
- §7.3 `Integrating Functions with Discontinuities`
- §7.4 `Properties of the Integral`
- §7.5 `The Fundamental Theorem of Calculus`
- §7.6 `Lebesgue's Criterion for Riemann Integrability`
- §8.1 `The Generalized Riemann Integral` 作为 enrichment。

**Analysis123 tutor push**

- §18 simple-function viewpoint / Riemann integrability；
- §19 Riemann sums / Darboux sums；
- §19.1 Sturm–Liouville example；
- §20 integrability characterization、FTC、integration by parts、substitution；
- §21 oscillation / null sets / Lebesgue criterion；
- §22 integral properties、integral-form Taylor remainder、improper integrals、Euler constant、Wallis、Stirling；
- §23 history、parameter integrals；
- §24 ODE / Kepler / first calculus-of-variations application 中与 integral reasoning 相关部分；Picard uniqueness 主 anchor RA13；
- §25 brachistochrone / Huygens / first mean-value theorem for integrals；
- §26–27 Stieltjes integral and mean-value theorems；
- §27.1 oscillatory integrals；
- §28 Liouville theorem on elementary antiderivatives；Baire part cross-anchor RA04；
- §29 oscillation / decay / Riemann–Lebesgue / van der Corput 作为 RA11 forward；
- §29.2 final-exam integral problems；
- §48.2、§51.2、§53.2 三组 Riemann-integral definition exercise classes，按题拆分用于 deep transfer；
- §29.3 寒假作业中的 integration item 按题拆分。

**出口证据**

- 能用 upper/lower sums 或等价 criterion 判断 integrability；
- 能区分 Riemann 与 Riemann–Stieltjes；
- 能证明并使用 integral properties；
- 能准确说明 FTC hypotheses；
- 能处理 rectifiable-curve 基本结构；
- 能在 improper / parameter / oscillatory examples 中识别当前工具的适用边界。

---

### RA10 — Sequences and Series of Functions

**Rudin primary — Chapter 7 到 Stone–Weierstrass 之前**

- `Discussion of the Main Problem`
- `Uniform Convergence`
- `Uniform Convergence and Continuity`
- `Uniform Convergence and Integration`
- `Uniform Convergence and Differentiation`
- `Equicontinuous Families of Functions`

`The Stone-Weierstrass Theorem` 放 RA11。

**Abbott conceptual layer**

- §6.1 `Discussion: Branching Processes`
- §6.2 `Uniform Convergence of a Sequence of Functions`
- §6.3 `Uniform Convergence and Differentiation`
- §6.4 `Series of Functions`

**Analysis123 tutor push**

- §11 pointwise vs uniform convergence、`C([a,b]), ||·||∞`；compactness / uniform continuity 分别 cross-anchor RA04 / RA07；
- §12 series of continuous functions、function-space completeness；metric completion cross-anchor RA03/RA05；
- §20.1 Dini theorem；Stone–Weierstrass 主 anchor RA11；
- §51 convolution / function approximation 作为 `FORWARD`；
- §52 smooth approximation of `L1` 作为 later forward；
- §54 approximate identities / Féjer kernel 作为 RA11 transfer。

**出口证据**

- 能严格区分 pointwise 与 uniform convergence；
- 能判断 continuity / integration / differentiation 何时可与 limit 交换；
- 能使用 uniform Cauchy criteria；
- 能处理基本 equicontinuity；
- 能把 uniform convergence 重新理解为 function-space norm convergence。

---

### RA11 — Approximation, Power Series & Special Functions

**Rudin primary**

Chapter 7:

- `The Stone-Weierstrass Theorem`

Chapter 8：**全部 sections 均属于最终 coverage**

- `Power Series`
- `The Exponential and Logarithmic Functions`
- `The Trigonometric Functions`
- `The Algebraic Completeness of the Complex Field`
- `Fourier Series`
- `The Gamma Function`

其中 algebraic completeness / gamma 可以使用 later block，但不再标为永久 optional。

**Abbott conceptual layer**

- §6.5 `Power Series`
- §6.6 `Taylor Series`
- §8.3 `Fourier Series`

**Analysis123 tutor push**

- §6 exponential / trigonometric construction、double sums；
- §15 trigonometric functions via ODE、`π`；
- §20.1 polynomial approximation / Weierstrass–Stone；
- §22 Stirling；
- §29 oscillation / decay、Riemann–Lebesgue、van der Corput；
- §29.2 Chudnovsky approximation 与相关 final-exam applications；
- §52–53 Fourier `L2` theory / higher-dimensional Fourier series 作为 `FORWARD`；
- §54 Dirichlet / Féjer kernels、localization；
- §55 du Bois-Reymond counterexample、Dirichlet / Dini / Hölder / Jordan convergence theorems；
- §55.1 Fourier computation / spherical-harmonic connection；
- §56 Bernstein theorem / equidistribution；
- §57 Roth three-term AP theorem；
- §57.1 `L1` Fourier-series divergence example；
- §57.2 Maass-wave expansion；
- §65 complex-analysis primer 仅作为需要时的 `FORWARD`；
- §65.1–68 Fourier transform / Schwartz / tempered-distribution material 作为更远期 `FORWARD`，正式 functional anchor 在 RA20。

**核心关系**

```text
uniform convergence
→ power-series regularity
→ Taylor series and its limits
→ polynomial approximation
→ Stone-Weierstrass
→ Fourier approximation / convergence
→ later Fourier-transform viewpoint
```

**出口证据**

- 能证明 power series 在适当区域的 uniform convergence / termwise operations；
- 能区分 smooth、analytic、equal to Taylor series；
- 能理解 polynomial approximation 的数学问题；
- 能使用 Stone–Weierstrass / Fourier material 完成新的综合证明；
- 能说明 Chapter 8 中 complex / gamma / Fourier 各部分在整条分析路线中的角色。

---

### RA12 — Multivariable Linear Structure & Differentiability

**Rudin primary — Chapter 9**

- `Linear Transformations`
- `Differentiation`

**Abbott conceptual layer**

Abbott 没有系统多元微分章节；只复用已经学过的 approximation / derivative-as-local-linearization language，不人为制造不存在的 Abbott 对应章节。

**Analysis123 tutor push**

- §30 directional derivatives、partial derivatives、differentiability、extrema；
- §31 differential of mappings、Jacobian matrix、chain rule、inverse-map differential、matrix exponential differential；
- §31.1 homogeneous functions / Euler identity；
- §32 diffeomorphisms、coordinate changes、Clairaut–Schwarz、multivariable Taylor；submanifold definition cross-anchor RA13；
- §37 Hessian / second derivative test / convexity 的计算部分 cross-anchor RA14。

**出口证据**

- 能把 derivative 理解为最佳线性近似，而不是偏导数组；
- 能从 linear-map viewpoint 写 chain rule；
- 能区分 directional / partial derivative 与 differentiability；
- 能正确使用 Jacobian / operator norm / multivariable estimates。

---

### RA13 — Contraction, Inverse / Implicit / Rank Theorems

**Rudin primary — Chapter 9**

- `The Contraction Principle`
- `The Inverse Function Theorem`
- `The Implicit Function Theorem`
- `The Rank Theorem`

**Analysis123 tutor push**

- §7 Picard contraction principle / complete metric space connection；
- §24 ODE existence-uniqueness 中 contraction-mapping application；
- §33 inverse function theorem、coordinate-change viewpoint；
- §33.2 inverse / implicit function exercises；
- §34 implicit function theorem 的 submanifold statement、regular level sets、parameterization、Möbius band；
- §35 preimage theorem、tangent spaces、normal vectors；
- §35.1 IFT applications、classical groups as submanifolds；
- §36 smooth maps between submanifolds、tangent bundle、submanifold IFT；
- §37.1 stereographic projection；
- §37.2 transversality / Morse lemma 中直接依赖 IFT / rank ideas 的部分作为 `FORWARD`。

**出口证据**

- 能解释 contraction theorem 为什么需要 completeness；
- 能准确陈述 IFT / implicit FT / rank theorem 的非退化条件；
- 能识别 local invertibility / regular level set / coordinate normalization 三种表述之间的关系；
- 能把 theorem 用到新的 geometric / ODE setting。

---

### RA14 — Determinants, Higher Derivatives & Parameter Dependence

**Rudin primary — Chapter 9**

- `Determinants`
- `Derivatives of Higher Order`
- `Differentiation of Integrals`

**Analysis123 tutor push**

- §32 Clairaut–Schwarz / multivariable Taylor；
- §36 Lagrange multipliers on submanifolds；
- §37 Hessian、second derivative test、convexity；
- §37.2 Lagrange multipliers / Morse lemma；
- §43 differentiation under the integral sign（measure-theoretic stronger version 只在 RA19 后回看）；
- §46 determinant 的 geometric meaning；
- §58–64 distributional differentiation、fundamental solutions 作为 `FORWARD`：强调 higher derivatives / differential operators 的后续 extension；
- §69 PDE differential operators 与 Sobolev mapping properties 作为远期 `FORWARD`。

**出口证据**

- 能处理 higher derivative 的 multilinear structure；
- 能正确使用 determinant / Jacobian 在 local geometry 中的作用；
- 能说明 differentiating under the integral sign 需要什么控制条件；
- 能在 Hessian / constrained-extremum 等新问题中正确选择工具。

---

### RA15 — Integration in Euclidean Space & Change of Variables

**Rudin primary — Chapter 10 前半**

- `Integration`
- `Primitive Mappings`
- `Partitions of Unity`
- `Change of Variables`

**Analysis123 tutor push**

- §44 product measure / Fubini 在 `R^n` integration 中的降维思想，measure-theoretic proof 主 anchor RA19；
- §44.1 Archimedes parabola / Gaussian integral；
- §45 abstract change of variables、Borel regularity、diffeomorphism change-of-variables；
- §46 common coordinate substitutions、geometric meaning of determinant、graph integrals；
- §47 cutoff functions / periodic partition of unity；
- §48.2 / §51.2 / §53.2 中 Riemann integration construction 与高维积分相关 item 可作为 retrospective transfer。

**出口证据**

- 能理解 Rudin integration construction 的对象与 partition role；
- 能准确陈述 change-of-variables hypotheses；
- 能把 determinant 解释为 volume distortion；
- 能在 coordinates / partition of unity / nonrectangular domains 中组织证明。

---

### RA16 — Differential Forms, Simplexes & Chains

**Rudin primary — Chapter 10 中段**

- `Differential Forms`
- `Simplexes and Chains`

**Analysis123 tutor push**

- §35–36 tangent spaces / tangent maps 中与 differential forms pairing 所需的 geometry 作为 bridge；
- §46–49 curve / surface integration 中第一类与第二类积分的关系；
- §47 orientation / normal vector / boundary intuition；
- §60 partition-of-unity / Cauchy-formula examples 只作 `FORWARD`；
- §65 complex-analysis forms / residues 在需要时作为 cross-domain application。

**出口证据**

- 能计算 pullback / wedge / exterior derivative 的基本结构；
- 能解释 orientation、simplex、chain 为什么是 Stokes 的语言准备；
- 能把传统 line/surface integral 与 form language 对接。

---

### RA17 — Stokes, Closed / Exact Forms & Vector Analysis

**Rudin primary — Chapter 10 后半**

- `Stokes' Theorem`
- `Closed Forms and Exact Forms`
- `Vector Analysis`

**Analysis123 tutor push**

- §47 Stokes first proof / bounded smooth domains / outward normal；
- §48 Sard-type lemma / differential-topological proof of Stokes；
- §48.1 curve / surface integral exercises；
- §49 first/second-kind submanifold integrals、vector-field operations、divergence theorem、Green、Gauss–Ostrogradsky、physical meaning of divergence；
- §51.1 applications of Stokes；
- §59 distributional Stokes as `FORWARD`；
- §60 Cauchy integral formula / fundamental solution as a cross-domain Stokes application；
- §63–64 PDE fundamental solutions as `FORWARD`，只用来显示 Stokes / integration-by-parts 思想如何继续发展。

**出口证据**

- 能准确追踪 boundary orientation 与 signs；
- 能用 Stokes 统一 FTC / Green / divergence-type formulas；
- 能判断 closed vs exact 的局部/全局区别；
- 能在 vector-analysis setting 中选择 form-based proof strategy。

---

### RA18 — Measurable Structure & Measure Construction

**Rudin primary — Chapter 11 前半**

- `Set Functions`
- `Construction of the Lebesgue Measure`
- `Measure Spaces`
- `Measurable Functions`
- `Simple Functions`

**Analysis123 tutor push**

- §38 σ-algebra、generated σ-algebra、Borel algebra、product σ-algebra、measurable spaces/maps/functions；
- §39 measures、σ-finiteness、Carathéodory extension；
- §40 pushforward measure、Lebesgue measure、translation/scaling、completion、simple/step functions；
- §41.1 Stieltjes measure / Borel–Cantelli / Diophantine approximation；submanifold-null-set item cross-anchor RA17；
- §43.2 coin-space measure theory；
- §46.1 construction of a non-Borel set；
- §58 Radon measures embedded as distributions 作为 `FORWARD`。

**出口证据**

- 能区分 algebra / σ-algebra / Borel / completion；
- 能从 generators 判断 measurability；
- 能解释 outer measure / extension construction 的目的；
- 能处理 null sets、pushforward、σ-finiteness 等基本结构。

---

### RA19 — Lebesgue Integration, Convergence & Product Measures

**Rudin primary — Chapter 11 中段**

- `Integration`
- Rudin Chapter 11 中与 monotone / dominated convergence 和 integrability 直接相关的核心论证。

**Analysis123 tutor push**

- §41 simple-function integral、integral on measure spaces、a.e.、Beppo Levi；
- §42 Riemann/Lebesgue comparison、`L1`、Fatou、DCT、parameter continuity；
- §43 differentiation under integral、product measure construction；
- §43.1 DCT exercises；
- §43.2 coin-space integration / probability examples；
- §44 product measure / Fubini / dimensional reduction；
- §44.1 Gaussian integral；
- §45 regularity / abstract change of variables 中 measure-theoretic部分；
- §51–52 `L1` approximation / convolution 作为 `FORWARD`；
- §57.1 `L1` Fourier-series divergence example 作为 convergence-theorem boundary case。

**出口证据**

- 能构造非负/可积函数积分；
- 能准确选择 MCT / Fatou / DCT；
- 能处理 a.e. equality 与 norm/integral consequences；
- 能说明 Fubini / Tonelli 所需条件及其作用；
- 能把 parameter-limit problems 转化为 convergence-theorem hypotheses。

---

### RA20 — Riemann Comparison, Complex Integration & `L2` / Functional Viewpoint

**Rudin primary — Chapter 11 后半**

- `Comparison with the Riemann Integral`
- `Integration of Complex Functions`
- `Functions of Class L2`

**Analysis123 tutor push — functional / harmonic / PDE bridge**

- §50 Hilbert space、normed-space completeness by series、Fischer–Riesz；Brouwer fixed point cross-anchor RA04/RA13；
- §51 `L2` / `L∞` completeness、continuous linear operators、extension、convolution / approximation；sphere tangent field cross-anchor RA17；
- §52 separable Hilbert space、Hilbert basis、Fourier `L2` theory、smooth approximation of `L1`；
- §53 higher-dimensional Fourier `L2` theory / absolute Fourier convergence；
- §53.1 wave-equation local energy estimate；
- §54–57 deeper Fourier convergence / localization / equidistribution / Roth；这些也可回看 RA11；
- §57.1 `L1` divergence example；§57.2 Maass-wave expansion；
- §58–64 distributions、support、convolution、fundamental solutions：作为从 `L1/L2 + derivatives + Stokes` 出发的 `FORWARD`；
- §65 complex-analysis primer；
- §65.1–68 Fourier transform on `L1/L2`、Plancherel、Schwartz space、tempered distributions、Fourier transform / convolution；
- §69–76 Sobolev spaces、Fourier multipliers、embedding、Riesz representation、orthogonal projection、duality、trace、extension、Dirichlet problem、elliptic regularity；
- §70.1 Fourier / uncertainty / fractional Sobolev / Poisson-summation exercises；
- §72.1 midterm；§75.1 wave / Airy / KdV exercises；§76.1 variational elasticity model；
- §77 compact / self-adjoint operators、weak convergence；
- §78–82 compact spectral theory、Laplacian eigenfunctions、heat kernel、Weyl asymptotics；
- §83–85 wavefront set、microlocal elliptic regularity、bicharacteristics、propagation of singularities；
- §86.1–86.3 distribution-theory final review sets。

这些 advanced topics **都被纳入 coverage ledger，但默认是 `FORWARD` / later enrichment，不把 Rudin Chapter 11 的 readiness 变成一门完整 distribution/PDE qualifying exam**。真正推送时，Project 应选择其中能自然挂在当前已学 Rudin skills 上的 atom，例如：

```text
L2 completeness → Hilbert space
Hilbert space → orthogonal projection / Riesz representation
Fourier series → Fourier transform / Plancherel
weak derivative → distributions / Sobolev
compactness → compact operators / spectral theory
integration + differentiation → PDE fundamental solutions
locality + Fourier decay → wavefront set
```

**出口证据**

- 能说明 Riemann 与 Lebesgue integration 的关系；
- 能处理 complex-valued integrals；
- 能使用 `L2` inner-product / norm viewpoint；
- 能理解 `L2` 为什么是进入 Hilbert / Fourier / PDE 的自然桥梁；
- 至少能对一项 tutor-pushed advanced application 说明它复用了哪些已掌握的 Rudin concepts，而不要求掌握全部后续理论。

---

## 3. Full Abbott Coverage Ledger

下面的 ledger 用于避免 Abbott 只被零散调用。它不改变 Rudin reading order。

| Abbott section | Primary RA anchor | 默认用途 |
|---|---|---|
| §1.1 Irrationality of √2 | RA01 | CONCEPT / proof motivation |
| §1.2 Some Preliminaries | RA00 | CONCEPT / PROOF |
| §1.3 Axiom of Completeness | RA01 | CONCEPT / PROOF |
| §1.4 Consequences of Completeness | RA01 / RA02 | CONCEPT / TRANSFER |
| §1.5 Cantor's Theorem | RA02 | PROOF / BOUNDARY |
| §1.6 Epilogue | RA01–RA02 | synthesis |
| §2.1 Rearrangements | RA06 | CONCEPT / BOUNDARY |
| §2.2–§2.6 sequences / limits / Cauchy | RA05 | CONCEPT / PROOF |
| §2.7–§2.8 series / double sums | RA06 | PROOF / TRANSFER |
| §2.9 Epilogue | RA05–RA06 | synthesis |
| §3.1 Cantor Set | RA04 | CONCEPT / example |
| §3.2 Open and Closed Sets | RA03 | CONCEPT |
| §3.3 Compact Sets | RA04 | CONCEPT / PROOF |
| §3.4 Perfect / Connected | RA04 | BOUNDARY / PROOF |
| §3.5 Baire's Theorem | RA04 | TRANSFER / forward |
| §3.6 Epilogue | RA03–RA04 | synthesis |
| §4.1–§4.6 Functional Limits / Continuity / Discontinuity | RA07 | CONCEPT / BOUNDARY / PROOF |
| §4.7 Epilogue | RA07 | synthesis |
| §5.1–§5.4 Derivative / Darboux / MVT / nowhere differentiable | RA08 | CONCEPT / BOUNDARY / PROOF |
| §5.5 Epilogue | RA08 | synthesis |
| §6.1–§6.4 Uniform convergence / differentiation / series of functions | RA10 | CONCEPT / PROOF / TRANSFER |
| §6.5 Power Series | RA11 | CONCEPT / PROOF |
| §6.6 Taylor Series | RA11 | BOUNDARY / TRANSFER |
| §6.7 Epilogue | RA10–RA11 | synthesis |
| §7.1–§7.6 Riemann integral | RA09 | CONCEPT / PROOF / BOUNDARY |
| §7.7 Epilogue | RA09 | synthesis |
| §8.1 Generalized Riemann Integral | RA09 | FORWARD / comparison |
| §8.2 Metric Spaces and Baire | RA03 / RA04 | FORWARD / TRANSFER |
| §8.3 Fourier Series | RA11 | TRANSFER / application |
| §8.4 Construction of R from Q | RA01 | later-return conceptual support |

Project 不要求把 Abbott 每一节逐段复述给用户；要求的是在相应 RA 中**有意识地使用其独特教学价值**，避免只在出错时临时查一小段。

---

## 4. Analysis123 Coverage Ledger

本 ledger 是“不要遗漏”的静态检查表。每个 numbered section / homework / exam 都至少有一个 anchor；真正运行时仍应按 atom 拆分，不整章灌输。

### 4.1 Sections 1–29.3

| Analysis123 | Primary RA anchor(s) | Timing |
|---|---|---|
| §1 | RA01 | INLINE |
| §2 | RA01 / RA03 | INLINE |
| §3 | RA01 | later return |
| §3.1 | RA02 | TRANSFER |
| §4 | RA05 / RA06 | INLINE |
| §5 | RA05 / RA06 | INLINE / TRANSFER |
| §6 | RA11 / RA06 | TRANSFER |
| §6.1 | RA06 / RA04 | TRANSFER |
| §7 | RA06 / RA05 / RA13 | split by atom |
| §7.1 | RA06 | TRANSFER |
| §8–§9 | RA07 | INLINE |
| §10 | RA03 / RA04 / RA07 | split by atom |
| §10.1 | RA03 / RA04 | TRANSFER |
| §11 | RA04 / RA07 / RA10 | split by atom |
| §12 | RA10 / RA05 / RA03 | split by atom |
| §12.1 | RA03 / RA04 | TRANSFER |
| §12.2 | RA07 / RA04 | FORWARD / TRANSFER |
| §13–§14 | RA08 | INLINE / TRANSFER |
| §15 | RA08 / RA11 / RA12 | split by atom |
| §15.1 | RA08 | TRANSFER |
| §16 | RA08 / RA07 | split by atom |
| §17 | RA08 | TRANSFER |
| §17.1 | RA08 / RA11 | TRANSFER / FORWARD |
| §18–§19 | RA09 | INLINE |
| §19.1 | RA09 | TRANSFER |
| §20 | RA09 | INLINE / TRANSFER |
| §20.1 | RA10 / RA11 | TRANSFER |
| §21–§23 | RA09 | INLINE / TRANSFER |
| §23.1 | RA06 / RA09 | TRANSFER |
| §24 | RA13 / RA09 | split by atom |
| §25 | RA09 / RA08 | split by atom |
| §25.1 | RA06 / RA09 | TRANSFER |
| §26–§27 | RA09 | INLINE / TRANSFER |
| §27.1 | RA09 / RA11 | TRANSFER |
| §28 | RA04 / RA09 | split by atom |
| §29 | RA11 / RA09 | TRANSFER / FORWARD |
| §29.1 | route each omitted topic to its matching RA | locator-only |
| §29.2 | RA09 / RA11 | capstone transfer |
| §29.3 | RA01–RA11 by item; default capstone anchor RA11 | item-level routing before use |

### 4.2 Sections 30–57.2

| Analysis123 | Primary RA anchor(s) | Timing |
|---|---|---|
| §30–§31 | RA12 | INLINE / TRANSFER |
| §31.1 | RA12 | TRANSFER |
| §32 | RA12 / RA13 / RA14 | split by atom |
| §33 | RA13 | INLINE |
| §33.1 | RA03 / RA13 | FORWARD / TRANSFER |
| §33.2 | RA13 | TRANSFER |
| §34–§36 | RA13 / RA17 | geometric transfer; forms connection later |
| §35.1 | RA13 | TRANSFER |
| §37 | RA14 | TRANSFER |
| §37.1 | RA13 | TRANSFER |
| §37.2 | RA13 / RA14 | FORWARD / TRANSFER |
| §38–§40 | RA18 | INLINE / TRANSFER |
| §41 | RA19 | INLINE |
| §41.1 | RA18 / RA19 / RA17 | split by atom |
| §42–§44 | RA19 | INLINE / TRANSFER |
| §43.1–§43.2 | RA19 / RA18 | TRANSFER |
| §44.1 | RA15 / RA19 | TRANSFER |
| §45 | RA15 / RA18 | split by atom |
| §46 | RA15 / RA17 | split by atom |
| §46.1 | RA18 | TRANSFER |
| §47–§49 | RA17 / RA15 / RA16 | split by atom |
| §48.1 | RA17 | TRANSFER |
| §48.2 | RA09 | retrospective transfer |
| §50 | RA20 / RA04 / RA13 | FORWARD / split by atom |
| §51 | RA20 / RA17 / RA10 | split by atom |
| §51.1 | RA17 | TRANSFER |
| §51.2 | RA09 | retrospective transfer |
| §52–§53 | RA20 / RA11 | FORWARD / TRANSFER |
| §53.1 | RA20 / RA17 | FORWARD |
| §53.2 | RA09 | retrospective transfer |
| §54–§55 | RA11 / RA20 | TRANSFER / FORWARD |
| §55.1 | RA11 / RA20 | TRANSFER |
| §56–§57 | RA11 | advanced application |
| §57.1 | RA11 / RA20 | BOUNDARY / advanced transfer |
| §57.2 | RA11 / RA20 | advanced application |

### 4.3 Sections 58–86.3

这些 section 超出 Rudin 的 exposition scope，但不因此遗漏；它们作为 Rudin concepts 的 forward application network 路由。

| Analysis123 | Primary RA anchor(s) | Timing |
|---|---|---|
| §58 | RA20 / RA18 | FORWARD: measures → distributions |
| §59 | RA20 / RA14 / RA17 | FORWARD: derivative / Stokes extension |
| §60 | RA17 / RA20 | FORWARD: Cauchy / fundamental solution / partition unity |
| §61 | RA20 / RA03 | FORWARD: locality / support |
| §61.1 | RA20 | advanced exercise |
| §62 | RA20 / RA10 | FORWARD: convolution |
| §63–§64 | RA20 / RA14 / RA17 | FORWARD: PDE fundamental solutions |
| §63.1 | RA20 | advanced exercise |
| §65 | RA11 / RA20 | FORWARD: complex-analysis toolkit |
| §65.1 | RA20 / RA11 | FORWARD: `L1` Fourier transform |
| §66–§68 | RA20 | FORWARD: Plancherel / Schwartz / tempered distributions |
| §66.1 | RA20 | advanced exercise |
| §69–§70 | RA20 / RA14 | FORWARD: Fourier PDE / Sobolev / multipliers |
| §70.1 | RA20 / RA11 | advanced transfer |
| §71 | RA20 | FORWARD: Riesz / projection / duality / trace |
| §72–§76 | RA20 / RA13 / RA17 | FORWARD: Sobolev on domains / boundary / elliptic problems |
| §72.1 | RA20 | advanced assessment bank |
| §75.1 | RA20 | advanced PDE exercise bank |
| §76.1 | RA20 | variational application |
| §77 | RA20 / RA04 | FORWARD: compact operators / weak convergence |
| §78–§82 | RA20 / RA04 / RA11 | FORWARD: spectral theory / heat kernel / Weyl |
| §83–§85 | RA20 / RA03 / RA11 | FORWARD: locality + Fourier decay → microlocal analysis |
| §86.1–§86.3 | RA20 | advanced review / exercise bank |

### 4.4 Composite homework / exam rule

像 §29.3、§72.1、§86.x 这类综合题组，section-level anchor 只保证“有归宿”；**真正推送前必须逐题重新判断 prerequisite 和诊断目标**。不能因为整套卷子挂在某 RA，就一次性把未学内容塞给用户。

---

## 5. Recommended Reading Order

默认顺序：

```text
RA00 → RA01 → RA02 → RA03 → RA04 → RA05 → RA06
     → RA07 → RA08 → RA09 → RA10 → RA11
     → RA12 → RA13 → RA14
     → RA15 → RA16 → RA17
     → RA18 → RA19 → RA20
```

这是 Rudin Chapters 1–11 的 knowledge dependency map，不是锁定状态机。用户可以回退、跳转、暂停或提前讨论后续内容。

Rudin chapter mapping：

```text
Chapter 1  → RA01（RA00 只负责 proof-language entry）
Chapter 2  → RA02–RA04
Chapter 3  → RA05–RA06
Chapter 4  → RA07
Chapter 5  → RA08
Chapter 6  → RA09
Chapter 7  → RA10–RA11
Chapter 8  → RA11
Chapter 9  → RA12–RA14
Chapter 10 → RA15–RA17
Chapter 11 → RA18–RA20
```

---

## 6. Reading Block Rule

Project 不应把整个 RA 一次全部布置给用户。进入或恢复章节时，先读取 `Review Analysis / RAxx` 的顶部状态和最近 Study Record，再选择一个自然且有限的 **Rudin reading block**。

- 没有历史时才从本 RA 的首个自然 Rudin block 开始；
- 有 `Reading State: ASSIGNED` 时优先恢复；
- Abbott / Analysis123 不单独生成 reading block；
- 一个 Rudin block 读完后，assessment 可以穿插 Abbott conceptual push 与 Analysis123 enrichment push；
- enrichment 不应在 core retrieval 之前把答案讲透；
- 教材习题前先查历史，避免无意重复；Retest 规则见 `01_LEARNING.md` / `03_NOTION.md`。

例如 RA13 可以拆为：

```text
Block A
Contraction Principle

Block B
Inverse Function Theorem

Block C
Implicit Function Theorem + Rank Theorem
```

在 Block B / C assessment 中再适时推送 Analysis123 的 coordinate-change、regular-level-set、submanifold examples。

---

## 7. RA Session Teaching Pattern

默认一次 RA learning loop 可按下面组织，但不要求机械执行每一项：

```text
1. Rudin Reading
   用户只读当前有限 Rudin block

2. Core Retrieval
   定义 / 假设 / 结论 / proof skeleton

3. Abbott Conceptual Push
   why / intuition / proof organization / counterexample

4. Rudin Core Assessment
   检验是否能独立使用

5. Analysis123 Enrichment Push
   application / geometry / technique / later-analysis connection

6. Transfer Question
   若有诊断价值，用自包含的新情境验证迁移

7. Readiness Update
   仍只以 Rudin core coverage + required evidence 为准
```

顺序可以动态调整。例如一个 Rudin 定义特别压缩时，可以在 core assessment 前先进行很短的 Abbott conceptual push；但不要把 enrichment 变成替代用户独立阅读/作答的 scaffold。

---

## 8. Reading Assignment Template

```text
Chapter
RAxx — [name]

Rudin
[具体 chapter / section / theorem range]

Reading Focus
1. [核心定义与量词]
2. [定理假设、结论、使用边界]
3. [需要自己重建的 proof step]

Tutor-side Sources
- Abbott: 已映射，按需要在 chat 中调用，不要求额外阅读
- Analysis123: 已映射，按需要推送例子 / 应用 / 习题，不要求额外阅读

Deferred
[当前 Rudin block 暂不要求、但后续仍要覆盖的 Rudin 内容]

Completion Signal
读完后告诉我“这一段读完了”。
```

---

## 9. Chapter Completion Evidence

“完成 RA”不是读完页数，也不是看过 enrichment。

正式 readiness contract 仍以 `02_REVIEW.md §8` 为准，并遵循：

1. 当前 RA 的 Rudin core reading scope 已由 `COMPLETED` reading blocks 覆盖；
2. chapter-specific 出口证据已有直接 evidence；
3. 核心定义 / theorem conditions 有独立正确证据；
4. 有 boundary / example / counterexample evidence；
5. 有 proof / strategy evidence；
6. 有 transfer/application evidence；
7. 重要 `PARTIAL` / `INCORRECT` weakness 已 remediation + independent verification。

Abbott / Analysis123 的角色：

- 可以提供更高质量的 boundary / transfer / application evidence；
- 可以暴露 Rudin core weakness；
- 不因为某个 advanced enrichment 没有做完就自动阻塞 RA；
- 不把“听懂了 Abbott / 课程讲义解释”当 mastery evidence。

---

## 10. Source Mapping and Reliability

如果实际上传版本与本文件的 section title / 编号不一致：

1. 以当前 Project Source 的目录和正文为准；
2. Rudin 决定 curriculum spine 与正式 theorem reference；
3. Abbott / Analysis123 的映射保留知识关系，不强行使用错误页码；
4. Analysis123 某个高阶 topic 在正式推送前应读取对应正文；目录只用于 routing，不能据此补写 theorem hypotheses；
5. 无法确认时请求相关页或检查 Project Source，不凭记忆补全；
6. Solution Guide 仍只在 substantive attempt 后或用户明确要求 reference/full solution 时使用，普通 hint 不先查 solution。
