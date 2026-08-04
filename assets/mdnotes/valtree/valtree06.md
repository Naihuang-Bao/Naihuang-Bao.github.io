---
permalink: /valtree06/
math: true
---
# 赋值树结构的证明

> 一棵树的本质就是上面的蚂蚁只有唯一一种不走回头路的方法从一根树枝爬到另一根树枝上.

## 赋值空间的树结构

回忆 $R = \mathbb{C}[[x,y]]$, 以及 $\mathcal{V}$ 为 $R$ 上的所有 centered normalized 赋值全体组成的空间.

- 赋值 $v$ 是 `centered normalized` 指 $v(\mathfrak{m}) = 1$, 其中 $\mathfrak{m} = (x,y)$ 为 $R$ 的极大理想;
- 赋值空间 $\mathcal{V}$ 上有自然的偏序: $v \le w$ 当且仅当 $v(\phi) \le w(\phi)$ 对所有 $\phi \in R$ 成立;
- 重数赋值 $v_{\mathfrak{m}} \in \mathcal{V}$, 其中 $v_{\mathfrak{m}}(\phi) = m(\phi) = \max\{k \mid \phi \in \mathfrak{m}^k\}$.

> **定理 6.1.** 赋值空间 $\mathcal{V}$ 为一个 rooted 在 $v_{\mathfrak{m}}$ 处的 complete nonmetric tree.

回顾: 称偏序集 $(\mathcal{T} , \le)$ 为一个 `rooted nonmetric  tree`, 如果其满足:
- (T1) $\mathcal{T}$ 有唯一的最小元 $\tau_0$ (称为 $\mathcal{T}$ 的 `root`);
- (T2) 若 $\tau\in \mathcal{T}$, 则集合 $\{\sigma \in \mathcal{T} \mid \sigma \le \tau\}$ 同构于一个实区间;
- (T3) $\mathcal{T}$ 的任意 full 全序子集均同构于一个实区间.

称 $\mathcal{T}$ 是 `complete`, 如果对任意 $\mathcal{T}$ 中递增的点列 $(\tau_i)_{i\ge 1}$, 存在元素 $\tau_{\infty} \in \mathcal{T}$, 满足 $\tau_{i} \le \tau_{\infty}$ 对任意 $i$ 成立.

那么我们很容易看出来 $(\mathcal{V}, \le)$ 是一个偏序集, 且有唯一最小元 $v_{\mathfrak{m}}$, 即 (T1) 是成立的.

---

### 证明的准备工作

回顾任意 $R$ 上的 centered 赋值 $v$, 存在唯一的 (有限长度或者无限长度的) SKP $[(U_{j}) ; (\tilde{\beta}_j)]$ 使得 $v = \mathrm{val}[(U_{j}) ; (\tilde{\beta}_j)]$. 记 $v$ 对应的 SKP 的长度为 $\mathrm{length}(v)$.

> **引理 6.2.** 令 $v, v' \in \mathcal{V}$ 为赋值且 $v \neq v'$. 取局部坐标 $(x,y)$ 使得 $1 = v(x) = v'(x) \le \min \{ v(y), v'(y)\}$. 设 $v = \mathrm{val}[(U_{j}) ; (\tilde{\beta}_j)]$ 以及 $v' = \mathrm{val}[(U_{j}') ; (\tilde{\beta}_{j}')]$. 则 $v < v'$ 当且仅当以下同时成立: <br> (i) $\mathrm{length}(v') \ge \mathrm{length}(v) =: k < \infty$, <br> (ii) $U_{j} = U_{j}'$ 对所有 $0 \le j \le k$ 成立; <br> (iii) $\tilde{\beta}_{k}' \ge \tilde{\beta}_{k}$.

**证明.** 假设这三个条件成立, 令 $v_{0} = \mathrm{val}[(U_{j})^{k}_{0} ; (\tilde{\beta}{j})_{0}^{k-1}, \tilde{\beta}_{k}']$, 则由 `定理 3.5` 及其证明中的构造过程可知, $v' \ge v_{0} \ge v$.

反过来, 若 $v < v'$, 记 $k = \mathrm{length}(v)$. 我们对 $j \le k$ 归纳证明 $U_{j} = U_{j}'$. 由假设知 $j = 0,1$ 时成立. 如果已有 $U_{i} = U_{i}'$ 当 $0 \le i \le j-1$, 定义 $v_{j-1} = \mathrm{val}[(U_i)_{0}^{j-1}; (\tilde{\beta}_i)_0^{j-1}]$, 则由 $v' \ge v$ 及 `定理 3.5` 知 $v'(U_{j}) \ge v(U_{j}) > v_{j-1}(U_{j})$. 此时 `定理 3.9` 说明 $U_{j}' = U_{j}$. 进一步地, 有 $k < \infty$, 否则 $v' = v$, 以及有 $\mathrm{length}(v') \ge k$. 最后, $\tilde{\beta}'_{k} = v'(U_{k}) \ge v(U_{k}) = \tilde{\beta}_{k}$. Q.E.D.

> **推论 6.3.** 令 $(v^{i})_{i\in I}$ 为 $\mathcal{V}$ 的一族赋值, 并且有局部坐标 $(x,y)$ 使得 $1 = v^{i}(x) \le v^{i}(y)$ 对所有 $i \in I$ 成立. 令 $v^{i} = \mathrm{val}[(U_{j}^{i}); (\tilde{\beta}_j^i)]$. 则存在关于这族赋值的极小元 $$\bigwedge_{i\in I} v^{i} = \mathrm{val}\Big[(U_j)_{0}^{k}; (\tilde{\beta}_j)_{0}^{k-1}, \inf_{i\in I} \tilde{\beta}_{k}^{i}\Big],$$ (即其为集合 $\{v \in \mathcal{V} \mid v \le v^{i}, \forall\, i\in I\}$ 中的最大元), 其中 $1 \le k <\infty$ 为最大的 $k$ 使得: $U_{j}^{i} = U_{j}^{i'} =: U_{j}$ 对所有 $0 \le j \le k$ 以及 $i, i' \in I$ 成立, 并且 $\tilde{\beta}_{j}^{i} = \tilde{\beta}_{j}^{i'} =: \tilde{\beta}_{j}$ 对所有 $0 \le j < k$ 以及 $i, i' \in I$ 成立.

**证明.** 这是 `引理 6.2` 的直接推论. Q.E.D.

---

### (T2) 的证明

令 $v \in \mathcal{V}$ 满足 $v > v_{\mathfrak{m}}$. 我们需要证明 $I := \{w\in \mathcal{V} \mid v_{\mathfrak{m}} \le w \le v\}$ 为一个同构于 $\overline{\mathbb{R}_{+}}$ 中的区间的全序集.

取局部坐标 $(x,y)$ 使得 $1 = v(x) \le v(y)$. 令 $v = \mathrm{val}[(U_{j})_{0}^{k}; (\tilde{\beta}_{j})_{0}^{k}]$. 首先假设 $k < \infty$. 令 $d_{j} = \deg_{y}(U_{j})$ 对任意 $1 \le j \le k$ 并记 $d_{0} = \infty$. 回忆 $(\tilde{\beta}_{j}/d_{j})$ 为一个严格递增的数列 (`引理 3.2`). 我们下面将证明 $I$ 同构于区间 $J = [1 , \tilde{\beta}_{k}/d_{k}]$.  取 $t \in J$. 则存在唯一整数 $l \in [1, k]$ 使得 $$\tilde{\beta}_{l-1}/d_{l-1} < t \le \tilde{\beta}_{l}/d_{l}.$$ 令 $$v_{t} := \mathrm{val}[(U_{j})_{0}^{l} ; (\tilde{\beta}_{j})_{j=0}^{l-1}, t d_{l}].$$ 此时由 `引理 6.2` 知 $t \mapsto v_{t}$ 给出了 $J$ 到 $I$ 的同构. 同理可得 $k = \infty$ 情形. Q.E.D.

---

### (T3) 及完备性的证明

由 (T2) 的成立, 我们会发现实际上要证明 (T3) 只需证 $\mathcal{V}$ 是 `complete`, 即对任意全序子集 $\mathcal{S} \subset \mathcal{V}$, 存在 $v'\in \mathcal{V}$ 使得 $v' \ge v$ 对所有 $v \in \mathcal{S}$ 成立.

取局部坐标 $(x, y)$ 使得 $1 = v(x) \le v(y)$ 对所有 $v \in \mathcal{S}$. 由 $\mathcal{S}$ 为全序集知这是可以办到的, 并且由 `引理 6.2` 知 $v \in \mathcal{S}$ 所对应的 SKP 的长度 $\mathrm{length}(v)$ 定义了一个 $\mathcal{S}$ 上的不减的函数. 当 $\mathrm{length}(v) \to \infty$ 时, 由 `定理 3.7` 知 $v$ 趋向于一个赋值 $v_{\infty} \in \mathcal{V}$ 大于等于所有 $\mathcal{S}$ 中的赋值 ($v_{\infty}$ 为一个 `curve 赋值` 或 `infinitely singular 赋值`). 否则对充分大 $v \in \mathcal{S}$, 有 $\mathrm{length}(v)$ 为常值. 此时记 $$v = \mathrm{val}[\big(U_{j})_{0}^{n} ; (\tilde{\beta}_{j})_{0}^{n-1}, \tilde{\beta}_{n}^{(v)}\big].$$ 由 `引理 6.2`, 数列 $\tilde{\beta}_{n}^{(v)}$ 为一个关于充分大 $v \in \mathcal{S}$ 的递增函数, 因此存在 $\tilde{\beta}_{n} \in \overline{\mathbb{R}_+}$, 大于等于所有的 $\tilde{\beta}_{n}^{(v)}$. 此时赋值 $v = \mathrm{val}[\big(U_{j})_{0}^{n} ; (\tilde{\beta}_{j})_{0}^{n}\big] \in \mathcal{V}$ 即满足 $v' \ge v$ 对所有 $v \in \mathcal{S}$ 成立. Q.E.D.

至此我们完成了 `定理 6.1` 的完整证明.

---

## 不同类型赋值在树中的位置

回忆由 SKP 所定义的 $\mathcal{V}$ 中的赋值的分类:

> **定义 3.8.** 令 $v \in \mathcal{V}$ 满足 $v := \mathrm{val}[(U_j)_0^k ; (\tilde{\beta}_j)_0^k]$, 其中 $1\le k \le \infty$. 称 $v$ 为 <br> <br> (1) `monomial` (在坐标 $(x,y)$ 下) 如果 $k=1$, 且 $\tilde{\beta}_0, \tilde{\beta}_1 < \infty$; <br> (2) `quasimonomial` 如果 $k < \infty$, 且 $\tilde{\beta}_0, \tilde{\beta}_k < \infty$; <br> (3) `divisorial` 如果 $v$ 是 quasimonomial 且 $\tilde{\beta}_k \in \mathbb{Q}$; <br> (4) `irrational` 如果 $v$ 是 quasimonomial 但不是 divisorial; <br> (5) `infinitely singular` 如果 $k = \infty$ 且 $d_j \to \infty$, 其中 $d_j = \deg_{y}(U_j)$; <br> (6) 一个 `curve valuation` 如果 $k = \infty$ 且 $d_j \not\to \infty$, 或者 $k < \infty$ 且 $\max\{\tilde{\beta}_0, \tilde{\beta}_k\} = \infty$.

结合 $\mathcal{V}$ 的树结构, 我们可知不同类型赋值在该赋值树中的位置:

> **命题 6.4.** 对于赋值树 $\mathcal{V}$, 我们有: <br> <br> (i) $\mathcal{V}$ 的 `root` 为 `multiplicity 赋值` $v_{\mathfrak{m}}$; <br> (ii) $\mathcal{V}$ 的 `ends` 为 `curve 赋值` 以及 `infinitely singular 赋值` (反过来非 end 点为所有 `quasimonomial 赋值`); <br> (iii) $\mathcal{V}$ 的任意 `切向量 (tangent vector)` 所代表等价类都包含一个 curve 赋值以及一个 infinitely singular 赋值; <br> (iv) $\mathcal{V}$ 的 `正则点` (即该点处只有两个切向量) 为所有的 `irrational 赋值`; <br> (v) $\mathcal{V}$ 的 `分支点` (即 `奇异点` , 非正则点) 为所有的 `divisorial 赋值`, 并且在每个 divisorial 赋值处的切空间同构于 $\mathbb{P}^{1}$. 

此命题的证明并不困难但很琐碎, 所以在此略去. 下面《The Valuative Tree》中的图表示了赋值树 $\cal{V}$ 中不同赋值所在的位置.


![Nonmetric tree structure]({{ site.baseurl }}/assets/mdnotes/valtree/Nonmetric_tree_structure.png)

---

下次我们介绍如何利用 `skewness 函数` 给出 $\mathcal{V}$ 的 `参数化 (parameterization)`.


## 参考文献

Favre, C. and Jonsson, M. (2004). [The Valuative Tree](http://link.springer.com/10.1007/b100262). vol 1853 Springer Berlin Heidelberg, Berlin, Heidelberg.
