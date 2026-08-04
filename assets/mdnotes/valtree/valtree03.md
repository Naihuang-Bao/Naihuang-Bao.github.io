---
permalink: /valtree03/
math: true
---
# 赋值与 SKP

> SKP 可以是商场, 可以是某种文件格式, 也可以是 `Sequences of Key Polynomials`.

本节介绍 MacLane 的利用 SKP 构造赋值的方法.

## Sequence of Key Polynomials

固定局部坐标 $(x,y)$.

> **定义 3.1.** 称一列 $\mathbb{C}[x,y]$ 中的多项式 $(U_j)_{j=0}^{k}$, $1 \le k \le \infty$ 为一个 ***sequence of key polynomials (SKP)*** 如果其满足: <br> <br>
> (P0) $U_0 = x$, $U_1 = y$; <br> <br>
> (P1) 任意多项式 $U_j$ 相关于一个数 $\tilde{\beta}_{j} \in \overline{\mathbb{R}_+}$ (要求不全是 $\infty$) 且满足 
> $$\tilde{\beta}_{j} > n_{j} \tilde{\beta}_{j} = \sum_{l=0}^{j-1} m_{j,l}\tilde{\beta}_l, \quad 1 \le j < k, \tag{1}$$ 
> 其中 $n_{j} \in \mathbb{N}_{+}$ 与 $m_{j,l} \in \mathbb{N}$ 满足对任意 $j > 1$ 以及 $1 \le l < j$, 有
> $$n_{j} = \min \{ l \in \mathbb{Z} \mid l \tilde{\beta}_{j} \in \mathbb{Z} \tilde{\beta}_{0} + \cdots + \mathbb{Z} \tilde{\beta}_{j-1} \}, \tag{2}$$
> 以及 $0 \le m_{j,l} < n_{l}$; <br> <br>
> (P2) 对 $1 \le j < k$, 存在 $\theta_{j} \in \mathbb{C}^{*}$ 使得
> $$U_{j+1} = U_{j}^{n_j} - \theta_{j} \cdot U_{0}^{m_{j,0}} \cdots U_{j-1}^{m_{j,j-1}}.  \tag{3}$$
> 最后, 我们称 $k$ 为这个 SKP 的 `长度 (length)`.

- 注意到如果 $(U_j)_0^k$ 是一个长度 $k \ge 2$ 的 SKP, 那么实际上数列 $(\tilde{\beta}_{j})_{1}^{k-1}$ 就完全由 $\tilde{\beta}_{0}$ 以及 $(U_j)_0^k$ 所决定了.

- 反过来, 给定一个满足 (P2) 的数列 $(\tilde{\beta}_{j})_{1}^{k+1}$ 以及任意 $\mathbb{C}^{*}$ 中的数列 $(\theta_j)_{1}^k$, 那么存在一个唯一对应的 SKP.

我们将一个 SKP 记为 $[(U_j) ; (\tilde{\beta}_j)]$. 

### SKP 的基本性质

设 $[(U_j) ; (\tilde{\beta}_j)]_{j=0}^{k}$ 为一个 SKP.

> **引理 3.2.** 对 $1 \le j \le k$, 多项式 $U_j$ 均不可约, 且为如下的 Weierstrass 多项式:
> $$U_j = y^{d_j} + a_1(x) y^{d_{j} - 1} + \cdots +a_{d_j}(x)$$
> 其中 $a_{l}(0) = 0$ 对所有 $l$. 并且 $d_{j+1} = n_j d_j$ 当 $1 \le j < k$. 

> **引理 3.3.** 若 $\tilde{\beta}_{1} \ge \tilde{\beta}_0$, 则 $m(U_j) = d_j$ 对任意 $j > 0$.

> **引理 3.4.** 假设 $\tilde{\beta}_{0}, \ldots, \tilde{\beta}_{k+1}$ 已给定并满足对所有 $j = 1, \ldots, k$ 有 $\tilde{\beta}_{j+1} > n_{j} \tilde{\beta}_{j}$, 其中 <br>
> $$n_{j} := \min \Big\{ n \in \mathbb{N}_+ \mid n \tilde{\beta}_{j} \in \sum_{0}^{j-1} \mathbb{Z} \tilde{\beta}_{j} \Big\}.$$
> 则对任意 $j = 1, \ldots, k$, 存在唯一一个分解:
> $$n_{j} \tilde{\beta}_{j} = \sum_{0}^{j-1} m_{j,l} \tilde{\beta}_{l}$$
> 其中 $0 \le m_{j,l} < n_{l}$ 对所有 $l = 1, \ldots, j - 1$.

除了 *$U_j$ 不可约* 这点, 上述引理基本上都可以利用数学归纳法很容易地证明. 相信未来写教材的人就可能把这都留作习题了. 具体证明还是参照原书 [《The Valuative Tree》](http://link.springer.com/10.1007/b100262) 的第二章.

## SKP 与赋值

### 从有限 SKP 到赋值

下面介绍如何从一个 `有限 SKP` 典范地对应到一个赋值.

记 $\widetilde{\mathcal{V}}$ 为 $R = \mathbb{C}[[x,y]]$ 上的 centered 赋值全体.

> **定理 3.5.** 令 $[(U_j)_{0}^{k} ; (\tilde{\beta}_{j})_{0}^{k}]$ 为一个长度 $1 \le k < \infty$ 的 SKP. 那么存在唯一的赋值 $v_k \in \widetilde{\mathcal{V}}$ 满足 <br> (Q1) $v_{k}(U_j) = \tilde{\beta}_{j}$ 当 $0 \le j \le k$; <br> (Q2) 对任意满足 (Q1) 的赋值 $v \in \widetilde{\mathcal{V}}$ 有 $v_k \le v$. <br> <br>进一步地, 如果 $k > 1$, 并且 $v_{k-1}$ 为类似于上述的对应于 $[(U_j)_{0}^{k-1} ; (\tilde{\beta}_{j})_{0}^{k-1}]$ 的赋值. 那么 <br> (Q3) $v_{k-1} \le v_{k}$; <br> (Q4) 对任意 $\phi \in R$, 有 $v_{k-1}(\phi) < v_{k}(\phi)$ 当且仅当在分次环 $\mathrm{gr}_{v_{k}}\mathbb{C}(x)[y]$ 中 $U_{k}$ 整除 $\phi$.

这里若 $v$ 为 $R$ 上的一个赋值, `分次环`
$$\mathrm{gr}_{v} R := \bigoplus_{\lambda} \{v \ge \lambda\} \Big/ \{ v > \lambda\}.$$

注意到上述 $v_{k}$ 为 normalized, 即 $v_{k}(\mathfrak{m}) = 1$, 当且仅当 $\min \{ \tilde{\beta}_{0} , \tilde{\beta}_{1} \} = 1$.

此定理的证明比较复杂, 我们首先介绍 $v_{k}$ 的具体构造过程.

1. 首先 $v_{1}$ 直接选取为满足 $v_{1}(x) = \tilde{\beta}_{0}$ 及 $v_{1}(y) = \tilde{\beta}_{1}$ 的 monomial 赋值, 即:
$$v_{1}\Big( \sum a_{ij} x^{i} y^{j} \Big) = \min \big\{ i \tilde{\beta}_{0} + j \tilde{\beta}_{1} \mid a_{ij} \neq 0 \big\}.$$

2. 若 $k > 1$, 归纳构造 $v_{k}$. 假设 $v_{1}, \ldots, v_{k-1}$ 已如要求构造出. 考虑任意多项式 $\phi \in \mathbb{C}[x,y]$. 由于 $U_{k}$ 关于 $y$ 首一, 我们可以在 $\mathbb{C}[x][y]$ 中用 $U_{k}$ 除 $\phi$ 得到 $\phi = \phi_{0} + U_{k} \psi$, 其中 $\deg_{y}(\phi_{0}) < d_{k} = \deg_{y} (U_{k})$ 且 $\psi \in \mathbb{C}[x,y]$. 重复这个步骤, 我们最终会得到唯一的一个分解 $$\phi = \sum_{j} \phi_{j} U_{k}^{j},$$ 其中 $\phi_{j} \in \mathbb{C}[x,y]$ 且 $\deg_{y}(\phi_{j}) < d_{k}$. 定义: 
$$v_{k}(\phi) := \min_{j} v_{k}(\phi_{j} U_{k}^j) := \min_{j} \big\{ v_{k-1}(\phi_{j}) + j \tilde{\beta}_{k} \big\}.$$

实际上如上构造容易看出 $v_k$ 满足赋值定义中的 (V2) 和 (V3), 但 (V1) 即 $v_k(\phi\psi) = v_k(\phi) + v_k(\psi)$ 并不直接. 假定如此的话, $v_k$ 将是 $\mathbb{C}[x,y]$ 上的赋值, 并由如下结果唯一地延拓为 $\mathbb{C}[[x,y]]$ 上的 centered 赋值.

> **命题 3.6.** 任意满足 $v(x), v(y) > 0$ 的赋值 $v : \mathbb{C}[x,y] \to \overline{\mathbb{R}_+}$ 唯一地延拓为 $R = \mathbb{C}[[x,y]]$ 上的 centered 赋值.

**证明.** 对任意 $R$ 的理想 $\mathfrak{a}$, 定义 $v(\mathfrak{a}) = \lim_{n \to \infty} v(\mathfrak{a} + \mathfrak{m}^n)$. Q.E.D.

我们将在之后的章节证明定理 3.5 (画个饼在这).

### 从无限 SKP 到赋值

令 $[(U_j) ; (\tilde{\beta}_j)]$ 为一个无限长度的 SKP.

> **定理 3.7.** 对任意 $k \ge 1$, 令 $v_k$ 为 `定理 3.5` 中的关于 $[(U_j)_{0}^k ; (\tilde{\beta}_j)_{0}^k]$ 的赋值. <br> <br> (i) 如果对无穷多个 $j$ 有 $n_j \ge 2$, 则对任意 $\phi \in R$, 存在 $k_0 = k_0(\phi)$ 使得 $v_{k}(\phi) = v_{k_0}(\phi)$ 对所有 $k \ge k_{0}$ 成立, 特别地 $v_{k}$ 收敛于一个赋值 $v_{\infty}$. <br> <br> (ii) 如果对 $j \gg 1$ 有 $n_j = 1$, 则 $U_{k}$ 在 $R$ 中收敛于一个不可约的形式幂级数 $U_{\infty}$, 且 $v_{k}$ 收敛于一个赋值 $v_{\infty}$. 更精确地说, 如果 $U_{\infty}$ 整除 $\phi \in R$, 则 $v_{k}(\phi) \to \infty$, 否则存在 $k_{0}(\phi)$ 使得 $v_{k}(\phi)=v_{k_0}(\phi)$ 对所有 $k \ge k_0 = k_0(\phi)$.

这个结果的证明也留到后面的章节 (继续画饼).

### 赋值的分类

最后给出由 SKP 构造出的赋值的分类. 注意到下面的部分名称沿用的之前出现过的, 实际上可以证明与之前的定义是等价的, 但在这里只当是一个新的称呼.

> **定义 3.8.** 令 $v$ 是一个由前述的方式通过一个 SKP 构造处的赋值 $v := \mathrm{val}[(U_j)_0^k ; (\tilde{\beta}_j)_0^k]$, 其中 $1\le k \le \infty$. 假设 $v$ 是 normalized. 称 $v$ 为 <br> <br> (1) `monomial` (在坐标 $(x,y)$ 下) 如果 $k=1$, 且 $\tilde{\beta}_0, \tilde{\beta}_1 < \infty$; <br> (2) `quasimonomial` 如果 $k < \infty$, 且 $\tilde{\beta}_0, \tilde{\beta}_k < \infty$; <br> (3) `divisorial` 如果 $v$ 是 quasimonomial 且 $\tilde{\beta}_k \in \mathbb{Q}$; <br> (4) `irrational` 如果 $v$ 是 quasimonomial 但不是 divisorial; <br> (5) `infinitely singular` 如果 $k = \infty$ 且 $d_j \to \infty$, 其中 $d_j = \deg_{y}(U_j)$; <br> (6) 一个 `curve valuation` 如果 $k = \infty$ 且 $d_j \not\to \infty$, 或者 $k < \infty$ 且 $\max\{\tilde{\beta}_0, \tilde{\beta}_k\} = \infty$. <br> <br> 如果 $v$ 不是 normalized, 则 $v$ 的分类由 $v/v(\mathfrak{m})$ 所决定. 

对于 infinitely singular 这种类型的赋值 $v$, 我们实际上可以证明 $\mathrm{rat.rk}(v) = 1$ 及 $\mathrm{tr.deg}(v) = 0$. 也就是说它不是一个 Abhyankar 赋值.

### 从赋值到 SKP

反过来, 对于任意 $R = \mathbb{C}[[x,y]]$ 上的 centered 赋值, 可以构造对应的 SKP.

> **定理 3.9.** 对任意 $R$ 上的 centered 赋值, 存在唯一的 SKP $[(U_j)_{0}^n ; (\tilde{\beta}_j)_0^n]$, $1 \le n \le \infty$, 使得 $v = \mathrm{val}[(U_j) ; (\tilde{\beta}_j)]$. 此时我们有 $v(U_j) = \tilde{\beta}_j$ 对所有 $j$. <br> <br> 进一步地, 如果 $k < n$ 且 $v_k = \mathrm{val}[(U_j)_0^k ; (\tilde{\beta}_j)_0^k]$, 则 $v(\phi) \ge v_k(\phi)$ 对所有 $\phi \in R$ 成立, 并且 $v(\phi) > v_k(\phi)$ 当且仅当在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中 $U_{k+1}$ 能整除 $\phi$.

证明需要大量铺垫过于繁琐, 再见. 但总之最终的结果就是, $\mathbb{C}[[x,y]]$ 上的 centered 赋值在某种意义上和 SKP 是有一一对应关系的, 由此给出未来对所有赋值形成的空间进行完整的刻画所需要的可计算的基础.

### 参考文献

Favre, C. and Jonsson, M. (2004). [The Valuative Tree](http://link.springer.com/10.1007/b100262). vol 1853 Springer Berlin Heidelberg, Berlin, Heidelberg.