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
- Abbott 和 Analysis123 不创建额外 reading block；
- Abbott / Analysis123 中需要的定义、解释、例子、背景或题目，由 Project 在 chat 中直接提供足以完成当前任务的自包含内容；
- 用户不需要为了 enrichment 离开 Rudin 去顺读第二本或第三本教材。

### 1.2 Rudin full-coverage and ownership rule

Rudin Chapters 1–11 **全部 exposition 内容都必须覆盖**，包括 Chapter 1 Appendix、Chapter 6 `Rectifiable Curves`、Chapter 8 `The Algebraic Completeness of the Complex Field` 与 `The Gamma Function` 等容易被课程裁掉的内容。

每个 Rudin exposition section 必须有且只有一个 **owning RA**：

- owning RA 的 Rudin reading scope 未完成时，该 RA 默认不能被判为 ready；
- reading assignment 中的 `Deferred` 只表示“当前 block 暂不读”，必须在离开同一 owning RA 之前由后续 Rudin block 回收；
- 不允许形成“以后整条课程结束前再补”的悬空 Rudin backlog；
- Rudin exercises 不要求机械全做，按诊断和 evidence 价值动态选择。

RA00–RA11 保留已有主结构；Rudin Chapters 9–11 自然继续为 RA12–RA20。不再区分 Analysis 1 / Analysis 2。

### 1.3 Abbott coverage principle

Abbott 不决定课程顺序，但应尽量完整利用其独特教学价值。

- 与 Rudin curriculum 有实质联系的 discussion、core exposition、counterexample、proof discussion、project material 和高价值 exercise，都应映射到一个或多个 RA；
- 默认用途：`CONCEPT`（动机/直觉）、`PROOF`（证明结构）、`BOUNDARY`（边界/反例）、`TRANSFER`（另一表述或迁移）；
- Abbott 可以主动推送，不需要等到用户答错；
- Abbott 永远不是第二套必读教材，且“听懂 Abbott”不能替代 Rudin core 的独立 mastery evidence。

### 1.4 Analysis123 coverage principle

Analysis123 不按原讲义顺序成为第二条课程，而要拆成 **knowledge / skill / application atoms**，再路由到最合适的 Rudin RA。

Coverage 分两层：

1. **Section locator**：每个正式 section、作业、习题课、考试至少有一个 locator，保证没有整节失踪；
2. **Significant atom routing**：复合 section 中的重要概念、技能、经典例子、应用和题组必须分别有 concept anchor 与 activation gate。

一节只有 section-level locator **不算完成 routing**，如果它实际包含多个显著不同的教学单元。综合 homework / exam 在真正使用前还必须逐题判断 prerequisite 与诊断目标。

“尽量不遗漏”默认覆盖：正式讲授主题、named theorem / method、显著 worked example、重要 historical/application thread、以及有独立教学价值的 homework/exam problem cluster；行政说明和纯重复文本不构成必须路由的 atom。

### 1.5 Concept anchor, activation gate, and timing

对 Analysis123 的较深内容，区分两个概念：

- **Concept Anchor**：它最自然地连接到哪个已经存在的 Rudin 知识节点；
- **Activation Gate**：完整推送该 atom 所需的最晚 prerequisite RA。

这避免把所有 Fourier / distribution / Sobolev / PDE / spectral / microlocal 内容都堆进 RA20。

Tutor push 的默认时机：

```text
INLINE
= 当前 Rudin 概念刚出现时，短解释 / 短应用

TRANSFER
= Rudin core 已初步掌握后，用新情境检验迁移

FORWARD
= 在 concept anchor 处建立后续位置感，不要求当前掌握完整理论

DEEPEN
= activation gate 已满足后，对此前 forward atom 做更完整的回访
```

`FORWARD` / `DEEPEN` enrichment 本身不构成 chapter readiness requirement；但如果其中的独立题暴露出 Rudin core 的真实弱点，该 evidence 可以阻塞 readiness。

### 1.6 Chapter naming

`RAxx` 是本 Project 的 knowledge chapter；`Rudin Chapter n / Rudin 第 n 章` 是教材章节。一个 Rudin chapter 可以拆成多个 RA。

---

## 2. Knowledge Chapters and Source Mapping

### RA00 — Proof Language

**目标**：建立后续分析立即需要的定义展开、量词、否定、反例和基本证明策略，不扩展成独立逻辑课程。

**Rudin anchor**

- Chapter 1 `Introduction` 中实际出现的集合/数系论证语言；
- Chapter 2 Definition 2.1–2.2 的 function、image、inverse image，在需要时补充。

**Abbott**：§1.2 `Some Preliminaries`。

**Analysis123**：从后续题目中抽取自包含 proof-language drills，不产生额外 reading。

**出口证据**：量词与否定准确；会构造反例；能区分 direct / contradiction / contrapositive；能独立完成短集合/函数证明。

---

### RA01 — Real Numbers & Completeness

**Rudin owned — Chapter 1**

- `Introduction`
- `Ordered Sets`
- `Fields`
- `The Real Field`
- `The Extended Real Number System`
- `The Complex Field`
- `Euclidean Spaces`
- `Appendix` — Dedekind construction of the real field

Appendix 可以作为 RA01 的最后一个独立 reading block，但 **RA01 readiness 前必须完成**。

**Abbott**：§1.1、§1.3、§1.4；§8.4 用于 Dedekind construction 的第二解释。

**Analysis123 major atoms**：§1 实数公理；§2 区间套/确界原理；§3 Dedekind 分割；§6 中“由完备性构造具体对象”的思想；§29.3 中对应题目按 item 路由。

**出口证据**：能严格使用 supremum/infimum；区分 maximum 与 supremum；指出证明中 completeness 的真正使用点；处理 Archimedean/density arguments；能说明 Dedekind construction 的目标和闭合结构。

---

### RA02 — Countability and the Infinite

**Rudin owned — Chapter 2**

- `Finite, Countable, and Uncountable Sets`

**Abbott**：§1.4 cardinality 部分、§1.5 Cantor's Theorem。

**Analysis123 major atoms**：§3.1 可数/不可数与 Schröder–Bernstein；§43.1 十进制表示中与 representation/cardinality 有关的 atom；其他 number-theoretic density 题仅在 prerequisite 满足时 transfer。

**出口证据**：injection/surjection/bijection；enumeration；countable union；diagonal argument；表示问题中的 cardinality transfer。

---

### RA03 — Metric Spaces and Topological Structure

**Rudin owned — Chapter 2**

- `Metric Spaces`

**Abbott**：§3.2；§8.2 中 metric-space language。

**Analysis123 major atoms**：§2 distance-space language；§4–5 metric convergence；§7 equivalent metrics/norms；§10 open/closed/closure/limit point/topological continuity；§12 completion 的 construction idea；§12.1 topology transfer；§33.1 一般拓扑只作受控 forward。

**出口证据**：metric/neighborhood/open/closed；limit point/closure/interior/dense；relative topology；能从 `R` 直觉迁移到一般 metric space。

---

### RA04 — Compactness, Perfectness & Connectedness

**Rudin owned — Chapter 2**

- `Compact Sets`
- `Perfect Sets`
- `Connected Sets`

**Abbott**：§3.1、§3.3、§3.4、§3.5。

**Analysis123 major atoms**：§10 compactness；§11 open cover/Heine–Borel/Lebesgue number；§16 space-filling curve 的 compact/connected image；§28 Baire category；§50 Brouwer fixed point 作为 forward；§77–79 “compactness → compact operators/spectral theory”作为远期 concept anchor。

**出口证据**：open-cover compactness；sequential behavior；perfect/Cantor sets；connected interval structure；识别“局部信息经 compactness 统一为有限/全局控制”的证明模式。

---

### RA05 — Sequences and Completeness

**Rudin owned — Chapter 3 前半**

- `Convergent Sequences`
- `Subsequences`
- `Cauchy Sequences`
- `Upper and Lower Limits`
- `Some Special Sequences`

**Abbott**：§2.2–§2.6。

**Analysis123 major atoms**：§4–5 sequence/Cauchy/vector convergence/Bolzano–Weierstrass；§7 complete metric/normed spaces；§12 metric completion；§29.3 对应题目。

**出口证据**：`ε-N`；subsequence/BW；Cauchy vs completeness；`lim sup/lim inf`；能识别 completion argument。

---

### RA06 — Numerical Series

**Rudin owned — Chapter 3 后半**

- `Series`
- `Series of Nonnegative Terms`
- `The Number e`
- `The Root and Ratio Tests`
- `Power Series`
- `Summation by Parts`
- `Absolute Convergence`
- `Addition and Multiplication of Series`
- `Rearrangements`

**Abbott**：§2.1、§2.4 series 部分、§2.7–§2.8。

**Analysis123 major atoms**：§4–5 series Cauchy/absolute convergence；§6 double-index sums；§6.1 rearrangement/Cesàro；§7 product series/ζ/Dirichlet-Abel；§7.1 primes reciprocal/Basel；§23 Leibniz series；§23.1 ζ(2)；§25.1 与 summation 有关的 atom。

**出口证据**：absolute/conditional；test selection；summation by parts；Cauchy products/rearrangements；power-series convergence as a series problem。

---

### RA07 — Limits and Continuity

**Rudin owned — Chapter 4：全部 sections**

- `Limits of Functions`
- `Continuous Functions`
- `Continuity and Compactness`
- `Continuity and Connectedness`
- `Discontinuities`
- `Monotonic Functions`
- `Infinite Limits and Limits at Infinity`

**Abbott**：§4.1–§4.6。

**Analysis123 major atoms**：§8–9 continuity/metric continuity/IVT；§10 topological characterization；§11 uniform continuity；§12 continuous functions from series（cross RA10）；§12.2 continuous-function ring as forward；§16 space-filling curve boundary example；§43.1 decimal-function atoms when relevant。

**出口证据**：`ε-δ`；sequential criterion；compact/connected image；EVT/uniform continuity/IVT；discontinuity examples and boundary cases。

---

### RA08 — Differentiation

**Rudin owned — Chapter 5：全部 sections**

- `The Derivative of a Real Function`
- `Mean Value Theorems`
- `The Continuity of Derivatives`
- `L'Hopital's Rule`
- `Derivatives of Higher Order`
- `Taylor's Theorem`
- `Differentiation of Vector-valued Functions`

**Abbott**：§5.1–§5.4。

**Analysis123 major atoms**：§13–14 derivative/Leibniz/Faà di Bruno/vector-valued/extrema/MVT；§15 Darboux/Cauchy MVT/trigonometric ODE；§15.1 Takagi；§16 L'Hôpital/Taylor；§17 convexity/Jensen；§17.1 Borel lemma/Peano as forward；§58–59 generalized derivative 只做 bounded forward，完整 activation later。

**出口证据**：definition-based derivative proof；MVT/Rolle hypotheses；Darboux boundary；finite Taylor remainder；vector-valued/convexity transfer。

---

### RA09 — Riemann and Riemann–Stieltjes Integration

**Rudin owned — Chapter 6：全部 sections**

- `Definition and Existence of the Integral`
- `Properties of the Integral`
- `Integration and Differentiation`
- `Rectifiable Curves`

`Rectifiable Curves` 可以放在后一个 reading block，但 **RA09 readiness 前必须完成**。

**Abbott**：§7.1–§7.6；§8.1 generalized Riemann integral 作为 enrichment。

**Analysis123 major atoms**：§18–21 Riemann/Darboux/integrability/Lebesgue criterion；§19.1 Sturm–Liouville；§22 improper integral/Wallis/Stirling；§23 parameter integrals；§24–25 integral/ODE/variational examples 中积分部分；§26–27 Stieltjes；§27.1 oscillatory integrals；§28 Liouville antiderivative；§29 Riemann–Lebesgue/vdC 的 integration side；§29.2、§48.2、§51.2、§53.2 与 Riemann definition 相关题按 item 使用。

**出口证据**：integrability criteria；Riemann vs Riemann–Stieltjes；FTC hypotheses；rectifiable curves；improper/parameter/oscillatory boundary recognition。

---

### RA10 — Sequences and Series of Functions

**Rudin owned — Chapter 7 前半**

- `Discussion of the Main Problem`
- `Uniform Convergence`
- `Uniform Convergence and Continuity`
- `Uniform Convergence and Integration`
- `Uniform Convergence and Differentiation`
- `Equicontinuous Families of Functions`

**Abbott**：§6.1–§6.4。

**Analysis123 major atoms**：§11 pointwise/uniform + `C([a,b]), ||·||∞`；§12 function series/function-space completeness；§20.1 Dini；§51 convolution/function approximation concept anchor；§52 smooth `L1` approximation as forward；§54 approximate identities cross RA11。

**出口证据**：pointwise vs uniform；interchange limit/continuity/integration/differentiation；uniform Cauchy; equicontinuity；function-space norm viewpoint。

---

### RA11 — Approximation, Power Series & Special Functions

**Rudin owned**

Chapter 7:

- `The Stone-Weierstrass Theorem`

Chapter 8：**全部 sections**

- `Power Series`
- `The Exponential and Logarithmic Functions`
- `The Trigonometric Functions`
- `The Algebraic Completeness of the Complex Field`
- `Fourier Series`
- `The Gamma Function`

Algebraic completeness 与 Gamma 可以作为后置 reading blocks，但 **RA11 readiness 前必须完成**。

**Abbott**：§6.5、§6.6、§8.3。

**Analysis123 major atoms**：§6 exp/trig construction；§15 trig ODE/π；§20.1 Weierstrass–Stone；§22 Stirling；§29 oscillation/RL/vdC；§52–57 Fourier approximation/convergence/kernels/counterexamples/equidistribution/Roth；§65 complex toolkit concept anchor；§65.1–68 Fourier transform/distributional Fourier 先做 forward，完整深挖受 activation gate 控制。

**出口证据**：power-series uniform/termwise operations；smooth vs analytic vs Taylor equality；polynomial approximation；Stone–Weierstrass；Fourier transfer；能说明 algebraic completeness、Fourier、Gamma 在本章中的角色。

---

### RA12 — Multivariable Linear Structure & Differentiability

**Rudin owned — Chapter 9**

- `Linear Transformations`
- `Differentiation`

**Abbott**：没有系统多元章节；复用 derivative-as-local-linearization、metric/compactness 等已学 conceptual language，不虚构对应 reading。

**Analysis123 major atoms**：§30 directional/partial/differentiability/extrema；§31 differential/Jacobian/chain rule/inverse differential/matrix exponential；§31.1 homogeneous/Euler；§32 coordinate/diffeomorphism/Clairaut/Taylor 中属于 local linearization 的部分。

**出口证据**：derivative as best linear approximation；partial/directional ≠ differentiability；chain rule in linear-map form；Jacobian/operator norm estimates。

---

### RA13 — Contraction, Inverse / Implicit / Rank Theorems

**Rudin owned — Chapter 9**

- `The Contraction Principle`
- `The Inverse Function Theorem`
- `The Implicit Function Theorem`
- `The Rank Theorem`

**Analysis123 major atoms**：§7 Picard/completeness；§24 ODE existence-uniqueness；§33 inverse function/coordinates；§33.2 exercises；§34 regular level sets/submanifold local form/Möbius band；§35 preimage/tangent/normal；§35.1 classical groups；§36 submanifold maps/tangent bundle/local theorem；§37.1 stereographic projection；§37.2 transversality/Morse 的 IFT/rank-dependent部分。

**出口证据**：contraction needs completeness；IFT/implicit/rank hypotheses；local invertibility/regular level/coordinate normalization；ODE/geometric transfer。

---

### RA14 — Determinants, Higher Derivatives & Parameter Dependence

**Rudin owned — Chapter 9**

- `Determinants`
- `Derivatives of Higher Order`
- `Differentiation of Integrals`

**Analysis123 major atoms**：§32 Clairaut/Taylor；§36–37 Lagrange/Hessian/second derivative/convexity；§37.2 Morse/Lagrange；§43 differentiation under integral（measure version activation RA19）；§46 determinant geometry；§58–64 differential operators/generalized derivatives/fundamental solutions concept anchors；§69 differential operators/Sobolev mapping as deep forward。

**出口证据**：higher derivative/multilinear structure；determinant/Jacobian geometry；parameter differentiation hypotheses；Hessian/constrained-extremum strategy。

---

### RA15 — Integration in Euclidean Space & Change of Variables

**Rudin owned — Chapter 10 前半**

- `Integration`
- `Primitive Mappings`
- `Partitions of Unity`
- `Change of Variables`

**Analysis123 major atoms**：§44 Fubini dimensional reduction（measure proof activation RA19）；§44.1 Gaussian/Archimedes；§45 abstract change of variables/Borel regularity split；§46 coordinate substitutions/determinant/graph integration；§47 cutoff/partition of unity；高维 Riemann definition exercise atoms retrospective transfer。

**出口证据**：Rudin integration construction；primitive mapping/partition role；change-of-variables hypotheses；determinant as volume distortion；coordinate proof organization。

---

### RA16 — Differential Forms, Simplexes & Chains

**Rudin owned — Chapter 10 中段**

- `Differential Forms`
- `Simplexes and Chains`

**Analysis123 major atoms**：§35–36 tangent/tangent maps as bridge；§46–49 curve/surface/submanifold integrals 中 form language；§47 orientation/normal/boundary；§60 partition-unity/Cauchy-formula connection forward；§65 complex forms/residues cross-domain forward。

**出口证据**：pullback/wedge/exterior derivative；orientation/simplex/chain；传统 line/surface integral 与 forms 对接。

---

### RA17 — Stokes, Closed / Exact Forms & Vector Analysis

**Rudin owned — Chapter 10 后半**

- `Stokes' Theorem`
- `Closed Forms and Exact Forms`
- `Vector Analysis`

**Analysis123 major atoms**：§47 first Stokes proof/boundary normal；§48 Sard-type/differential-topological proof；§48.1 exercises；§49 first/second-kind submanifold integrals/divergence/Green/Gauss-Ostrogradsky/physical divergence；§51.1 Stokes applications；§59 distributional Stokes forward；§60 Cauchy/fundamental-solution cross-domain；§63–64 integration-by-parts/PDE connection forward。

**出口证据**：boundary orientation/signs；Stokes unifies FTC/Green/divergence；closed vs exact local/global；form-based vector-analysis strategy。

---

### RA18 — Measurable Structure & Measure Construction

**Rudin owned — Chapter 11 前半**

- `Set Functions`
- `Construction of the Lebesgue Measure`
- `Measure Spaces`
- `Measurable Functions`
- `Simple Functions`

**Analysis123 major atoms**：§38 σ-algebra/Borel/product/measurable maps；§39 measures/σ-finite/Carathéodory；§40 pushforward/Lebesgue/translation/scaling/completion/simple functions；§41.1 Stieltjes measure/Borel–Cantelli/null-set atoms；§43.1 decimal intervals/measure atoms；§43.2 probability-space structure；§46.1 non-Borel set；§58 Radon measures → distributions as forward。

**出口证据**：σ-algebra/Borel/completion；generators/measurability；outer-measure/extension purpose；null sets/pushforward/σ-finiteness。

---

### RA19 — Lebesgue Integration, Convergence & Product Measures

**Rudin owned — Chapter 11**

- `Integration`

并覆盖该 section 内的 monotone convergence、Fatou、dominated convergence 等完整 exposition。

**Analysis123 major atoms**：§41 simple-function integration/a.e./Beppo Levi；§42 Riemann-Lebesgue comparison/`L1`/Fatou/DCT/parameter continuity；§43 differentiation under integral/product measure；§43.1 DCT exercises；§43.2 probability integration；§44 product measure/Fubini；§44.1 Gaussian；§45 measure-theoretic regularity/change of variables；§51–52 `L1` convolution/approximation concept anchor；§57.1 `L1` Fourier divergence boundary。

**出口证据**：integral construction；MCT/Fatou/DCT selection；a.e. consequences；Fubini/Tonelli conditions；parameter-limit problems。

---

### RA20 — Riemann Comparison, Complex Integration & `L2` / Functional Viewpoint

**Rudin owned — Chapter 11 后半**

- `Comparison with the Riemann Integral`
- `Integration of Complex Functions`
- `Functions of Class L2`

**Analysis123 major atoms**：§50 Hilbert/Fischer–Riesz；§51 `L2/L∞` completeness/continuous operators；§52 Hilbert basis/Fourier `L2`；§53 higher-dimensional Fourier `L2`；§66 Plancherel/Schwartz；§67–71 tempered Fourier/Sobolev/Riesz/projection/duality 的完整 deepening 以 RA20 为主要 activation gate；§72–85 的 domain Sobolev/spectral/heat/Weyl/microlocal内容作为 **post-core deepening network**，不作为 RA20 readiness burden。

**出口证据**：Riemann vs Lebesgue；complex integral；`L2` inner product/norm；Hilbert/Fourier bridge；能对至少一个 advanced push 指出其依赖的 Rudin concepts。

---

## 3. Rudin Ownership Audit

下面是 **exposition completeness ledger**。每一项都必须由 owning RA 的 `COMPLETED` reading blocks 覆盖；Exercises 不在此表中机械计数。

| Rudin | Owning RA |
|---|---|
| Ch1 Introduction; Ordered Sets; Fields; The Real Field; Extended Reals; Complex Field; Euclidean Spaces; Appendix | RA01 |
| Ch2 Finite/Countable/Uncountable | RA02 |
| Ch2 Metric Spaces | RA03 |
| Ch2 Compact Sets; Perfect Sets; Connected Sets | RA04 |
| Ch3 Convergent Sequences; Subsequences; Cauchy Sequences; Upper/Lower Limits; Special Sequences | RA05 |
| Ch3 Series; Nonnegative Series; e; Root/Ratio Tests; Power Series; Summation by Parts; Absolute Convergence; Addition/Multiplication; Rearrangements | RA06 |
| Ch4 all exposition sections | RA07 |
| Ch5 all exposition sections | RA08 |
| Ch6 all exposition sections, including Rectifiable Curves | RA09 |
| Ch7 Discussion through Equicontinuous Families | RA10 |
| Ch7 Stone–Weierstrass | RA11 |
| Ch8 all exposition sections, including Algebraic Completeness and Gamma | RA11 |
| Ch9 Linear Transformations; Differentiation | RA12 |
| Ch9 Contraction; Inverse Function; Implicit Function; Rank | RA13 |
| Ch9 Determinants; Higher Derivatives; Differentiation of Integrals | RA14 |
| Ch10 Integration; Primitive Mappings; Partitions of Unity; Change of Variables | RA15 |
| Ch10 Differential Forms; Simplexes and Chains | RA16 |
| Ch10 Stokes; Closed/Exact Forms; Vector Analysis | RA17 |
| Ch11 Set Functions; Lebesgue Measure Construction; Measure Spaces; Measurable Functions; Simple Functions | RA18 |
| Ch11 Integration | RA19 |
| Ch11 Riemann Comparison; Complex Integration; L2 | RA20 |

如果上传版本的目录标题有轻微排版差异，以实际 Rudin PDF 正文/目录为准，但不得把任何 exposition section 因标题差异而漏掉。

---

## 4. Full Abbott Coverage Ledger

Abbott ledger 用于保证其教学价值被主动考虑；它不是第二套 reading checklist。

| Abbott | RA anchor | Default use |
|---|---|---|
| §1.1 | RA01 | CONCEPT / proof motivation |
| §1.2 | RA00 | CONCEPT / PROOF |
| §1.3 | RA01 | CONCEPT / PROOF |
| §1.4 | RA01 / RA02 | CONCEPT / TRANSFER |
| §1.5 | RA02 | PROOF / BOUNDARY |
| §1.6 | RA01–RA02 | synthesis |
| §2.1 | RA06 | CONCEPT / BOUNDARY |
| §2.2–§2.6 | RA05 | CONCEPT / PROOF |
| §2.7–§2.8 | RA06 | PROOF / TRANSFER |
| §2.9 | RA05–RA06 | synthesis |
| §3.1 | RA04 | CONCEPT / example |
| §3.2 | RA03 | CONCEPT |
| §3.3 | RA04 | CONCEPT / PROOF |
| §3.4 | RA04 | BOUNDARY / PROOF |
| §3.5 | RA04 | TRANSFER / FORWARD |
| §3.6 | RA03–RA04 | synthesis |
| §4.1–§4.6 | RA07 | CONCEPT / BOUNDARY / PROOF |
| §4.7 | RA07 | synthesis |
| §5.1–§5.4 | RA08 | CONCEPT / BOUNDARY / PROOF |
| §5.5 | RA08 | synthesis |
| §6.1–§6.4 | RA10 | CONCEPT / PROOF / TRANSFER |
| §6.5–§6.6 | RA11 | CONCEPT / BOUNDARY / TRANSFER |
| §6.7 | RA10–RA11 | synthesis |
| §7.1–§7.6 | RA09 | CONCEPT / PROOF / BOUNDARY |
| §7.7 | RA09 | synthesis |
| §8.1 | RA09 | FORWARD / comparison |
| §8.2 | RA03 / RA04 | FORWARD / TRANSFER |
| §8.3 | RA11 | TRANSFER / application |
| §8.4 | RA01 | conceptual return |

---

## 5. Analysis123 Section Locator

Section locator 只回答“这节不会丢在哪里”；标记 `SPLIT` 的条目必须再看 §6 atom routing。

### 5.1 §§1–29.3

| Section | Locator | Use |
|---|---|---|
| §1 | RA01 | INLINE |
| §2 | RA01 / RA03 | SPLIT |
| §3 | RA01 | INLINE |
| §3.1 | RA02 | TRANSFER |
| §4 | RA05 / RA06 | SPLIT |
| §5 | RA05 / RA06 | SPLIT |
| §6 | RA11 / RA06 | SPLIT |
| §6.1 | RA06 / RA04 | SPLIT |
| §7 | RA05 / RA06 / RA12 / RA13 | SPLIT |
| §7.1 | RA06 | TRANSFER |
| §8–§9 | RA07 | INLINE |
| §10 | RA03 / RA04 / RA07 | SPLIT |
| §10.1 | RA03 / RA04 | item routing |
| §11 | RA04 / RA07 / RA10 | SPLIT |
| §12 | RA03 / RA05 / RA10 | SPLIT |
| §12.1 | RA03 / RA04 | TRANSFER |
| §12.2 | RA07 / RA04 | FORWARD / TRANSFER |
| §13–§14 | RA08 | INLINE / TRANSFER |
| §15 | RA08 / RA11 | SPLIT |
| §15.1 | RA08 | TRANSFER |
| §16 | RA08 / RA07 | SPLIT |
| §17 | RA08 | TRANSFER |
| §17.1 | RA08 / RA11 | FORWARD |
| §18–§19 | RA09 | INLINE |
| §19.1 | RA09 | TRANSFER |
| §20 | RA09 | INLINE / TRANSFER |
| §20.1 | RA10 / RA11 | SPLIT |
| §21–§23 | RA09 | SPLIT |
| §23.1 | RA06 / RA09 / RA10 | item routing |
| §24 | RA09 / RA13 | SPLIT |
| §25 | RA09 / RA08 | SPLIT |
| §25.1 | RA06 / RA09 | item routing |
| §26–§27 | RA09 | INLINE / TRANSFER |
| §27.1 | RA09 / RA11 | item routing |
| §28 | RA04 / RA09 | SPLIT |
| §29 | RA09 / RA11 | SPLIT |
| §29.1 | matching RA by omitted-topic item | locator only |
| §29.2 | RA09 / RA11 | item routing |
| §29.3 | RA01–RA11 by item | item routing required |

### 5.2 §§30–57.2

| Section | Locator | Use |
|---|---|---|
| §30–§31 | RA12 | INLINE / TRANSFER |
| §31.1 | RA12 | item routing |
| §32 | RA12 / RA13 / RA14 | SPLIT |
| §33 | RA13 | INLINE |
| §33.1 | RA03 / RA13 | SPLIT |
| §33.2 | RA13 | item routing |
| §34–§36 | RA13 / RA14 / RA16 / RA17 | SPLIT |
| §35.1 | RA13 | item routing |
| §37 | RA13 / RA14 | SPLIT |
| §37.1 | RA13 | TRANSFER |
| §37.2 | RA13 / RA14 | SPLIT |
| §38–§40 | RA18 | INLINE / TRANSFER |
| §41 | RA19 | INLINE |
| §41.1 | RA02 / RA18 / RA19 | SPLIT / item routing |
| §42–§44 | RA19 | SPLIT |
| §43.1–§43.2 | RA02 / RA07 / RA18 / RA19 | SPLIT / item routing |
| §44.1 | RA15 / RA19 | TRANSFER |
| §45 | RA15 / RA18 / RA19 | SPLIT |
| §46 | RA15 / RA16 / RA17 | SPLIT |
| §46.1 | RA18 | TRANSFER |
| §47–§49 | RA15 / RA16 / RA17 / RA19 | SPLIT |
| §48.1 | RA17 / RA19 | item routing |
| §48.2 | RA09 / RA15 | retrospective transfer |
| §50 | RA04 / RA13 / RA20 | SPLIT |
| §51 | RA10 / RA17 / RA19 / RA20 | SPLIT |
| §51.1 | RA17 | item routing |
| §51.2 | RA09 / RA15 | retrospective transfer |
| §52–§53 | RA10 / RA11 / RA19 / RA20 | SPLIT |
| §53.1 | RA17 / RA20 | FORWARD |
| §53.2 | RA09 / RA15 | retrospective transfer |
| §54–§55 | RA11 / RA20 | SPLIT |
| §55.1 | RA11 / RA20 | item routing |
| §56–§57 | RA11 / RA20 | advanced application |
| §57.1 | RA11 / RA19 / RA20 | BOUNDARY |
| §57.2 | RA11 / RA20 | advanced application |

### 5.3 §§58–86.3

这里的“Concept anchor”不等于“该 RA 必须完整学这节”。较深内容可在 anchor 处短 preview，再在 gate 满足后 deepening。

| Section | Concept anchor(s) | Activation gate |
|---|---|---|
| §58 distributions: Radon/local integrable/PV | RA18 measures; RA08/RA14 derivative extension | RA18 COMPLETE |
| §59 distribution operations / distributional Stokes | RA08/RA14 derivatives; RA17 Stokes | RA17 COMPLETE |
| §60 partition unity / Cauchy / fundamental-solution bridge | RA15 partitions; RA17 Stokes | RA17 COMPLETE |
| §61 support / locality | RA03 topology; RA14 local differential operators | RA18 COMPLETE |
| §61.1 | same as §61 | matching prerequisites |
| §62 convolution | RA10 approximation; RA19 `L1` integration | RA19 COMPLETE |
| §63–§64 PDE fundamental solutions | RA14 differential operators; RA17 integration by parts; RA19 integration | RA19 COMPLETE |
| §63.1 | same network | RA19 COMPLETE |
| §65 complex-analysis toolkit | RA11 special functions/Fourier; RA17 forms | RA17 COMPLETE |
| §65.1 `L1` Fourier transform | RA11 Fourier; RA19 `L1` | RA19 COMPLETE |
| §66 Plancherel / Schwartz | RA11 Fourier; RA20 `L2` | RA20 core reached |
| §66.1 | same as §66 | RA20 core reached |
| §67–§68 tempered distributions / Fourier / convolution | RA11 Fourier; RA14 derivative; RA19 convolution/integration; RA20 `L2` | RA20 core reached |
| §69 PDE operators / Sobolev | RA14 differential operators; RA20 `L2`/Fourier | RA20 core reached |
| §70 Sobolev/multipliers/embedding | RA20 functional/Fourier; RA04 compactness as concept link | RA20 core reached |
| §70.1 | RA11 Fourier; RA20 Sobolev | RA20 core reached |
| §71 Riesz/projection/duality/trace | RA20 Hilbert | RA20 core reached |
| §72–§76 domain Sobolev/trace/extension/Dirichlet/elliptic/variational | RA13 local coordinates; RA17 boundary/Stokes; RA20 functional analysis | RA20 COMPLETE |
| §72.1 / §75.1 / §76.1 | same network | item-level prerequisites |
| §77 compact/self-adjoint operators/weak convergence | RA04 compactness; RA20 Hilbert | RA20 COMPLETE |
| §78–§79 compact spectral/Laplacian eigenfunctions/variational spectrum | RA04 compactness; RA11 Fourier; RA20 Hilbert | RA20 COMPLETE |
| §80–§82 Sobolev regularity/heat kernel/Weyl | RA14 differential operators; RA19 integration; RA20 spectral/Fourier | RA20 COMPLETE |
| §83 wavefront set / nonstationary phase / diffeomorphism | RA03 locality; RA11 Fourier; RA13 diffeomorphism | RA20 COMPLETE + distribution/Fourier deepening |
| §84–§85 microlocal ellipticity / bicharacteristics / propagation | RA13 local geometry; RA14 differential operators; RA11 Fourier | RA20 COMPLETE + §83 deepening |
| §86.1–§86.3 | all relevant anchors | item-level routing before use |

---

## 6. Significant Atom Routing Audit

以下是复合 section 中最容易因“整节挂一次”而丢失的 atoms。运行时发现新的显著 atom 时，应在后续 curriculum maintenance 中补到此表，而不是默认为已覆盖。

| Source atom | Concept anchor | Activation / use |
|---|---|---|
| §2 nested intervals / supremum equivalence | RA01 | INLINE/TRANSFER |
| §2 metric-space introduction | RA03 | INLINE |
| §6 exp/trig construction | RA11 | TRANSFER |
| §6 double-index summation | RA06 | TRANSFER |
| §6.1 rearrangement / Cesàro | RA06 | TRANSFER |
| §6.1 Banach–Mazur game | RA04 | FORWARD |
| §7 product series / ζ / Dirichlet-Abel | RA06 | TRANSFER |
| §7 complete metric/normed spaces | RA05 | TRANSFER |
| §7 contraction/Picard | RA13 | DEEPEN |
| §7 matrix exponential | RA12 / RA11 | TRANSFER |
| §11 compactness / Lebesgue number | RA04 | TRANSFER |
| §11 uniform continuity | RA07 | TRANSFER |
| §11 pointwise vs uniform convergence | RA10 | INLINE |
| §11 `C([a,b]), ||·||∞` | RA10 | TRANSFER |
| §12 continuous functions from convergent series | RA10 | TRANSFER |
| §12 metric completion | RA05 / RA03 | TRANSFER |
| §15 MVT / Darboux / Cauchy MVT | RA08 | TRANSFER |
| §15 trig functions via ODE | RA11 / RA08 | TRANSFER |
| §20.1 Dini theorem | RA10 | TRANSFER |
| §20.1 Weierstrass–Stone | RA11 | TRANSFER |
| §23 parameter differentiation examples | RA09 / RA14 | preview then deepen |
| §24 ODE existence/uniqueness via contraction | RA13 | TRANSFER |
| §24 Kepler / variational / integration atoms | RA09 | APPLICATION |
| §28 Baire category | RA04 | TRANSFER |
| §28 Liouville elementary-antiderivative theorem | RA09 | APPLICATION |
| §29 Riemann–Lebesgue | RA09 / RA11 | TRANSFER |
| §29 van der Corput oscillatory estimate | RA09 / RA11 | APPLICATION |
| §32 diffeomorphism / pullback coordinates | RA12 / RA13 | TRANSFER |
| §32 Clairaut / multivariable Taylor | RA14 | TRANSFER |
| §34 regular level sets / local graph | RA13 | TRANSFER |
| §35 tangent/normal/preimage theorem | RA13 / RA16 | geometric bridge |
| §36 tangent bundle / maps between submanifolds | RA13 / RA16 | FORWARD/TRANSFER |
| §36–§37 Lagrange multipliers | RA14 | TRANSFER |
| §37 Hessian / second derivative / convexity | RA14 | TRANSFER |
| §38–§40 σ-algebra/Borel/measure/Carathéodory/Lebesgue/pushforward/completion | RA18 | INLINE/TRANSFER |
| §41.1 Stieltjes measure / Borel–Cantelli | RA18 | TRANSFER |
| §41.1 Diophantine/null-set applications | RA02 / RA18 | APPLICATION |
| §42 MCT/Fatou/DCT/`L1` | RA19 | INLINE/TRANSFER |
| §43 differentiation under integral | RA14 concept; RA19 gate | DEEPEN |
| §43 product measure | RA19 | INLINE |
| §43.1 DCT problems | RA19 | assessment bank |
| §43.1 decimal representation/cardinality | RA02 | TRANSFER |
| §43.1 decimal cylinder intervals/Borel/measure | RA18 | TRANSFER |
| §43.2 coin-space measurable/probability structure | RA18 | TRANSFER |
| §43.2 coin-space integration | RA19 | TRANSFER |
| §44 Fubini/product measure | RA19 | INLINE/TRANSFER |
| §45 Borel regularity | RA18 | TRANSFER |
| §45 abstract/diffeomorphic change of variables | RA15 / RA19 | DEEPEN |
| §46 coordinate substitutions / determinant geometry | RA15 | APPLICATION |
| §46 graph/submanifold integration | RA16 / RA17 | geometric bridge |
| §47 cutoff/partition of unity | RA15 | TRANSFER |
| §47–§49 submanifold measure/integration/orientation | RA16 / RA17 | TRANSFER |
| §47–§49 Stokes/divergence/Green/physical divergence | RA17 | TRANSFER/APPLICATION |
| §50 Brouwer fixed point | RA04 / RA13 | FORWARD |
| §50 Hilbert/Fischer–Riesz | RA20 | DEEPEN |
| §51 tangent vector fields | RA17 / RA13 | FORWARD |
| §51 `L2/L∞` completeness/operators/extension | RA20 | DEEPEN |
| §51 convolution/function approximation | RA10 / RA19 | FORWARD then deepen |
| §52 Hilbert basis/Fourier `L2` | RA20 | DEEPEN |
| §52 smooth `L1` approximation | RA19 / RA10 | TRANSFER |
| §53 higher-dimensional Fourier series | RA11 / RA20 | FORWARD then deepen |
| §54 Dirichlet/Féjer kernels / approximate identity | RA11 / RA10 | TRANSFER |
| §55 convergence theorems / du Bois-Reymond | RA11 | BOUNDARY/TRANSFER |
| §56 equidistribution | RA11 / RA06 | APPLICATION |
| §57 Roth 3-AP | RA11 | advanced application |
| §57.1 `L1` Fourier divergence | RA11 / RA19 | BOUNDARY |
| §§58–59 generalized function / derivative / Stokes | RA18 / RA14 / RA17 | preview at anchors, deepen after gates |
| §62 convolution of distributions | RA10 / RA19 | deepen after distribution gate |
| §§63–64 fundamental solutions | RA14 / RA17 / RA19 | advanced application |
| §§65.1–68 Fourier transform / Plancherel / Schwartz / tempered distributions | RA11 / RA19 / RA20 | staged FORWARD → DEEPEN |
| §§69–76 Sobolev / trace / elliptic / variational | RA14 / RA17 / RA20 | staged DEEPEN after RA20 core |
| §§77–82 compact spectral / heat / Weyl | RA04 / RA11 / RA20 | post-core deepening network |
| §§83–85 wavefront / microlocal ellipticity / propagation | RA03 / RA11 / RA13 / RA14 | post-core deepening after distribution/Fourier prerequisites |

---

## 7. Reading and Session Rules

默认顺序：

```text
RA00 → RA01 → RA02 → RA03 → RA04 → RA05 → RA06
     → RA07 → RA08 → RA09 → RA10 → RA11
     → RA12 → RA13 → RA14
     → RA15 → RA16 → RA17
     → RA18 → RA19 → RA20
```

Rudin chapter mapping：

```text
Chapter 1  → RA01
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

Project 不应把整个 RA 一次布置。进入/恢复 RA 时先读取 `Review Analysis / RAxx`，然后选择有限 Rudin block。

- `Reading State: ASSIGNED` 优先恢复；
- Abbott / Analysis123 永不单独产生 reading block；
- `Deferred` Rudin 内容只能留到同一 owning RA 的后续 block；
- owning RA 的 Rudin scope 未全部 `COMPLETED` 时，默认不允许以“Rudin core coverage 已完成”为由推进；
- assessment 中可以穿插 Abbott conceptual push 与 Analysis123 enrichment push，但不能在独立 retrieval 前把答案讲透。

默认 RA learning loop：

```text
Rudin finite reading block
→ core retrieval / assessment
→ Abbott conceptual or proof push（需要时也可提前到 assessment 前）
→ Analysis123 application / example / skill push
→ transfer / verification
→ readiness check
```

不是每个 loop 都必须机械包含两个 tutor-side push；`04` 的 coverage ledgers 用于长期保证材料被有意识地调用，而不是要求一次聊天塞满所有素材。

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

Deferred within this RA
[当前 block 暂不要求、但 owning RA readiness 前必须覆盖的 Rudin 内容]

Tutor-side plan
- Abbott: [CONCEPT / PROOF / BOUNDARY / TRANSFER]
- Analysis123: [INLINE / TRANSFER / FORWARD / DEEPEN]

Completion Signal
读完后告诉我“这一段读完了”。
```

---

## 9. Chapter Completion Evidence

正式 readiness contract 以 `02_REVIEW.md` 为准。Curriculum 层面至少要求：

1. owning RA 的 **全部 Rudin exposition scope** 已由 `COMPLETED` reading blocks 覆盖；
2. chapter-specific 出口证据已有直接 evidence；
3. 核心定义 / theorem conditions 有独立正确 evidence；
4. boundary / example / counterexample 有 evidence；
5. proof / strategy 有 evidence；
6. transfer/application 有 evidence；
7. 重要 core weakness 已 remediation + independent verification。

Abbott / Analysis123 enrichment 不因为“还没全部推送”而自动阻塞当前 RA；其完整利用属于整个 curriculum 的 tutor-side coverage obligation。反之，只要 enrichment 题真实暴露了 Rudin core weakness，该 weakness 就必须按正常 readiness 规则处理。

---

## 10. Source Mapping and Reliability

1. 以当前 Project Source 的目录和正文为准；
2. Rudin 决定 curriculum spine、正式 theorem reference 与 user-facing reading；
3. Abbott / Analysis123 的目录只用于 locator；正式推送高阶 theorem / exercise 前必须读取对应正文和 prerequisite；
4. Analysis123 自身明确提醒存在笔误，后半部分尤其如此；与 Rudin overlapping core 的定义/条件冲突时，以 Rudin 为课程标准来源；
5. 对 Analysis123 独有的高阶内容，若存在疑点，应核对上下文而不是凭目录标题补全；
6. Solution Guide 只在 substantive attempt 后，或用户明确要求 reference/full solution 时使用；普通 hint 不先查 solution。