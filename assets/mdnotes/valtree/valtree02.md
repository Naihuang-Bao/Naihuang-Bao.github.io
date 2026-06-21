---
permalink: /valtree02/
---

# 赋值树理论简介 02: 树理论

本节我们介绍 `树 (tree)` 的一些基本概念.

## 树 (Tree)

### 带根无度量树 (Rooted nonmetric  tree)

考虑偏序集 $(\mathcal{T} , \le)$, 称一个全序子集 $\mathcal{S} \subset \mathcal{T}$ 为 `full`, 如果对任意 $\sigma, \sigma' \in \mathcal{S}$, $\tau \in \mathcal{T}$ 且满足 $\sigma \le \tau \le \sigma'$, 必有 $\tau \in \mathcal{S}$.

> 称偏序集 $(\mathcal{T} , \le)$ 为一个 **带根无度量树 (rooted nonmetric  tree)**, 如果其满足: <br> (T1) $\mathcal{T}$ 有唯一的最小元 $\tau_0$ (称为 $\mathcal{T}$ 的 `根 (root)`); <br> (T2) 若 $\tau\in \mathcal{T}$, 则集合 $\{\sigma \in \mathcal{T} \mid \sigma \le \tau\}$ 同构于一个实区间; <br> (T3) $\mathcal{T}$ 的任意 full 全序子集均同构于一个实区间.

若 $\mathcal{T}$ 是一个 rooted nonmetric tree, 则:

(1) 对任意子集 $S \subset \mathcal{T}$, 存在一个极小元 $\wedge_{\tau \in S} \tau$, 实际上它是全序集合 $\{\sigma \in \mathcal{T} \mid \sigma \le \tau, \forall \, \tau \in S\}$ (同构于一些有公共左端点的实闭区间的交) 中的最大元;

(2) 对任意 $\tau_1 , \tau_2 \in \mathcal{T}$, 集合
$$[ \tau_1 , \tau_2 ] := \{\tau \in \mathcal{T} \mid \tau_1 \wedge \tau_2 \le \tau \le \tau_1 \ \text{或} \ \tau_1 \wedge \tau_2 \le \tau \le \tau_2 \}$$
称为一个 `segment`. 类似定义 $(\tau_1 , \tau_2)$, $[\tau_1 , \tau_2)$ 和 $(\tau_1 , \tau_2]$;

(3) $(\mathcal{T} , \le)$ 的子集 $\mathcal{S}$ 称为一个 `子树 (subtree)`, 如果对任意 $\sigma \in \mathcal{S}$, $\tau \in \mathcal{T}$ 且 $\tau \le \sigma$, 均有 $\tau \in \mathcal{S}$. 显然 subtree $\mathcal{S}$ 亦为一个以 $\tau_0$ 为根的 rooted nonmetric tree;

(4) 称 $\mathcal{T}$ 是 `完备的 (complete)`, 如果对任意 $\mathcal{T}$ 中递增的点列 $(\tau_i)_{i\ge 1}$, 存在元素 $\tau_{\infty} \in \mathcal{T}$, 满足 $\tau_{i} \le \tau_{\infty}$ 对任意 $i$ 成立. 任意 rooted nonmetric tree $\mathcal{T}$ 存在一个 `完备化 (completion)` $\overline{\mathcal{T}}$, 只需要对任意无界递增列 $\tau_i$ 增加对应的`终点 (end)`, 即 $\overline{\mathcal{T}}$ 中的极大元.

### 参数化 (Parameterization)

> 令 $\mathcal{T}$ 为一个 rooted nonmetric tree. 定义 $\mathcal{T}$ 的一个 **参数化 (parameterization)**, 为递增映射 $\alpha : \mathcal{T} \to [-\infty , +\infty]$, 如果它限制在任意 full 全序子集上为到一个实区间的双射.

- $\mathcal{T}$ 上存在参数化当且仅当 $\overline{\mathcal{T}}$ 上存在参数化.

### 弱拓扑 (Weak topology)

任意 rooted nonmetric tree $\mathcal{T}$ 上具有一个自然的弱拓扑.

对任意 $\tau \in \mathcal{T}$, 定义 $\tau$ 点处的一个 `切向量 (tangent vector)`, 为下面等价关系下的一个等价类: 任意 $\sigma, \sigma \in \mathcal{T} \setminus \{\tau\}$, 称 $\sigma \sim \sigma'$ 若 segments $(\tau , \sigma]$ 与 $(\tau , \sigma']$ 相交.

若 $\vec{v}$ 为 $\tau \in \mathcal{T}$ 处的一个切向量, 定义 $U(\vec{v})$ 为所有在 $U(\vec{v})$ 等价类中的点全体组成的集合. 那么 $\mathcal{T}$ 上的 `弱拓扑 (weak topology)` 是指由所有集合 $U(\vec{v})$ 为拓扑基所生成的拓扑.

此弱拓扑是 Hausdorff 的.

> **定理.** 任意可参数化的完备 rooted nonmetric tree 都是弱紧的.

**证明概要:** 设 $\alpha : \mathcal{T} \to [0 , 1]$ 为一个参数化. 记 $E$ 为所有函数 $\chi : \mathcal{T} \to [0 , 1]$ 全体. 因此 $E \simeq \prod_{\sigma \in \mathcal{T}} \{\sigma\} \times [0 , 1]$ 上有自然的乘积拓扑, 即函数收敛为逐点收敛. 这使得 $E$ 为一个紧空间 (Tychonov 定理). 定义映射 $\iota : \mathcal{T} \to E$ 为
$$\iota(\tau)(\sigma) := \alpha (\sigma \wedge \tau).$$
易验证 $\iota$ 是单射. 下面说明 $\iota(\mathcal{T})$. 事实上, 若 $\tau \in \mathcal{T}$, 则 $\chi := \iota(\tau) : \mathcal{T} \to [0 , 1]$ 满足:

- 对任意终点 $\sigma \in \mathcal{T}$, 有
$$\chi(\sigma') = \max \{\alpha(\sigma') , \alpha(\sigma \wedge \tau)\}, \quad \forall\,\sigma' \in [\tau_0 , \sigma];$$

- 对任意 $\sigma, \sigma' \in \mathcal{T}$, 有
$$\chi(\sigma \wedge \sigma') = \inf \{\chi(\sigma) , \chi(\sigma')\}.$$

实际上, 可以任意满足上述两个条件的函数 $\chi : \mathcal{T} \to [0 , 1]$ 一定形如 $\chi = \iota(\tau)$, 对某个 $\tau \in \mathcal{T}$.

注意到这两个条件定义了 $E$ 的在乘积拓扑下的一个闭子集. 因此 $\iota(\mathcal{T})$ 是闭的, 且 $\iota$ 给出了 $\mathcal{T}$ 到 $\iota(\mathcal{T})$ 上的双射. 最后只需要说明 $\iota$ 是这两者之间的同胚即可. Q.E.D.

### 度量树 (Metric tree)

称一个度量空间为 `度量树 (metric tree)`, 如果其上任意两点被唯一的一条 segment (等距同构于一个实区间的路径) 所连接.

令 $(\mathcal{T} , \le)$ 为一个 rooted nonmetric tree, $\alpha : \mathcal{T} \to [0 , 1]$ 为其参数化. 定义函数 $d : \mathcal{T} \times \mathcal{T} \to [0 , 2]$ 为:
$$d(\sigma , \tau) = \big( \alpha(\sigma) - \alpha (\sigma \wedge \tau) \big) + \big( \alpha(\tau) - \alpha(\sigma \wedge \tau) \big).$$

> **命题.** $(\mathcal{T} , d)$ 为一个 metric tree.

若 $\mathcal{T}$ 作为 nonmetric tree 是完备的, 那么 $(\mathcal{T} , d)$ 是完备度量空间.

## 赋值树 (Valuative tree)

令 $\mathcal{V}$ 为 $R = \mathbb{C} [[x , y]]$ 上的 centered normalized 赋值全体.

> **定理.** 赋值空间 $\mathcal{V}$ 为一个可参数化完备度量树, 其根为重数赋值 $v_{\mathfrak{m}}$, 参数化可由 `skewness` 函数 $\alpha : \mathcal{V} \to [1 , \infty]$ 或 `thinness` 函数 $A : \mathcal{V} \to [2 , \infty]$ 给出.

这里 skewness 定义稍微简单, 我们提前给出:
$$\alpha(v) := \sup \Big\{ \frac{v(\phi)}{m(\phi)} \mid \phi \in \mathfrak{m} \Big\}.$$
回忆这里的 $m(\phi) = v_{\mathfrak{m}}(\phi)$ 指 $\phi$ 在原点处的重数.

> **推论.** 任意 $\mathcal{V}$ 中子集均可诱导一个极小元. <br> 若 $(v_i)$ 为 $\mathcal{V}$ 中的赋值, 极小元 $v := \wedge v_i \in \mathcal{V}$ 满足: <br> (1) 对所有不可约元 $\phi \in \mathfrak{m}$, 令 $v(\phi) := \inf_{i} v_i(\phi)$; <br> (2) 再对所有 $\phi , \psi \in \mathfrak{m}$, 令 $v(\phi \psi) = v(\phi) + v(\psi)$.

注意到上述结论对于二维以上情形将不再成立. 例如令 $v_i$, $i = 1, 2, 3$ 为 $\mathbb{C}[[x_1, x_2, x_3]]$ 上的 monomial 赋值, 分别满足 $v_i(x_j) = 3$ 若 $i \neq j$, 以及 $v_i(x_i) = 1$. 若同样如上构造定义 $v = \min_{i} v_i$, 则对于 $\phi = x_{1}x_{2} - x_{2}x_{3} - x_{3}x_{1}$, $\psi = x_{1}x_{2} + x_{2}x_{3} - x_{3}x_{1}$, 有 $v(\phi) = v(\psi) = 4$ 以及 $v(\phi + \psi) = 2$, 因此 $v$ 不再是个赋值.

类似计算可知三维形式幂级数环 $\mathbb{C}[[x_1, x_2, x_3]]$ 上的 centered normalized 赋值组成的集合及其上自然的偏序关系 *不再* 定义一个树结构.

下一节开始我们介绍如何具体构造 $\mathcal{V}$ 中的赋值.

![[Valuative_Tree.png]]



## 参考文献

Favre, C. and Jonsson, M. (2004). [The Valuative Tree](http://link.springer.com/10.1007/b100262). vol 1853 Springer Berlin Heidelberg, Berlin, Heidelberg.


