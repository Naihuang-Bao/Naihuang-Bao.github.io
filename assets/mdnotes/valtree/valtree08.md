---
permalink: /valtree08/
math: true
---
# 赋值的重数与逼近序列

> 赋值重数 (multiplicity of valuation), 重数赋值 (multiplicity valuation), 傻傻分不清楚~ 

## Skewness 续

回顾对任意赋值 $v \in \mathcal{V}$, 其 skewness 定义为 $\alpha(v) := \sup_{\phi \in \mathfrak{m}} v(\phi)/m(\phi)$. Skewness 函数 $\alpha : \mathcal{V} \to [1, \infty]$ 给出了 $\mathcal{V}$ 的一个参数化. 若 $v$ 为 quasimonomial 赋值, 则 $\alpha(v) < \infty$; 若 $v$ 为 curve 赋值, 则 $\alpha(v) = \infty$; 若 $v$ 为 inifinitely singular 赋值, 则 $\alpha(v) \in (1, \infty]$.

> **定义 8.1.** 令 $C$ 为过原点的一条不可约曲线, $t \in [1, \infty]$ 以及 $v_{C} \in \mathcal{V}$ 为曲线 $C$ 对应的 curve 赋值. 定义 $v_{C,t}$ 为 segement $[v_{\mathfrak{m}} , v_{C}]$ 上唯一具有 skewness $\alpha(v) = t$ 的赋值. 若 $C = \{\phi = 0\}$ 其中 $\phi \in \mathfrak{m}$ 不可约, 亦记 $v_{\phi,t} = v_{C,t}$.

回忆对于 curve 赋值 $v_{C}$ 与 $v_{D}$, 与其相关的极小赋值 $v_{C} \wedge v_{D}$ 满足: segements $[v_{\mathfrak{m}}, v_{C}]$ 与 $[v_{\mathfrak{m}}, v_{D}]$ 在 $[v_{\mathfrak{m}}, v_{C}\wedge v_{D}]$ 段重合, 而在 $v_{C}\wedge v_{D}$ 后分为两支. 也就是说, 我们有:
$$v_{C,s} = v_{D, t} \Leftrightarrow s = t \le \alpha(v_{C}\wedge v_{D}).$$
假设 $C=\{\phi=0\}$, $D=\{\psi=0\}$ 其中 $\phi,\psi \in \mathfrak{m}$ 不可约, 即 $v_{C}=v_{\phi}$, $v_{D}=v_{\psi}$. 则此时由 `命题 7.2` 可得 
$$\alpha(v_{\phi}\wedge v_{\psi})=\frac{v_{\phi}(\psi)}{m(\psi)}=\frac{\{\phi = 0\}\cdot \{\psi =0 \}}{m(\phi) m(\psi)}=\frac{C\cdot D}{m(C)m(D)}.$$
容易验证这对于一般情形也是对的. 因此综合前述我们有
$$v_{C,s} = v_{D,t} \Leftrightarrow s=t \le \frac{C\cdot D}{m(C)m(D)}.$$

> **推论 8.2.** 设 $v \in \mathcal{V}$, $\phi \in \mathfrak{m}$ 不可约. 若 $v(\phi)$ 为无理数, 则 $v=v_{\phi,t}$ 其中 $t=v(\phi)/m(\phi)$.

**证明.** 由 `命题 7.2`, $\alpha(v \wedge v_{\phi}) = v(\phi)/m(\phi) = t$, 即 $v \ge v \wedge v_{\phi} = v_{\phi,t}$. 注意到 $\alpha(v_{\phi,t}) = t$ 为无理数, 由 `定理 7.3` 知 $v_{\phi,t}$ 为 irrational 赋值, 此时 `命题 6.4` 告诉我们 $v_{\phi,t}$ 为赋值树 $\mathcal{V}$ 中正则点(切向量只有两个), 即如果 $v > v_{\phi, t}$, 则存在 $s > t$ 使得 $v \ge v_{\phi, s}$. 但此时 $v(\phi) \ge s m(\phi) > t m(\phi)$, 矛盾. 因此只能有 $v = v_{\phi,t}$. Q.E.D.

> **命题 8.3.** Skewness 函数 $\alpha : \mathcal{V} \to [1, \infty]$ 为下半连续函数, 但不连续, 关于 $\mathcal{V}$ 作为一个树对应的弱拓扑.

**证明.** 实际上对于任意的 rooted nonmetric tree, 可以直接验证其上的参数化都是弱下半连续的. 另一方面, 考虑 $\mathcal{V}$ 中赋值列 $v_{n} = v_{y-nx , 2}$. 我们断言 $v_{n} \to v_{\mathfrak{m}}$, 其中 $v_{\mathfrak{m}}$ 为重数赋值. 实际上由树的弱拓扑定义, 这等价于: 对任意 $v\in \mathcal{V}\setminus \{v_{\mathfrak{m}}\}$, 以及充分大 $n$, 有 $v \le v_{n}$ 不成立. 注意到 $v_{n_{i}} \wedge v_{n_{j}} = v_{\mathfrak{m}}$ 当 $n_{i} \neq n_{j}$, 即可知断言成立.  此时对任意 $n$ 有 $\alpha(v_{n}) = 2$, 但 $\alpha(v_{\mathfrak{m}}) = 1$, 即得 $\alpha$ 并非 $\mathcal{V}$ 上的(弱)连续函数. Q.E.D.


## 赋值的重数

### 重数

> **定义 8.4.** 对任意赋值 $v \in \mathcal{V}$, 定义 $v$ 的 **重数 (multiplicity)** 为 
> $$m(v) := \min\{m(C) \mid \text{曲线 } C \text{ 不可约, 且 } v_{C} \ge v\}.$$
> 若这样的曲线 $C$ 不存在, 则定义 $m(v) = \infty$.

1. $m(v_{C}) = m(C)$, 其中(形式)曲线 $C$ 不可约;
2. 这个赋值重数的定义实际上为满足上述 $m(v_{C}) = m(C)$ 的最大的递增函数 $m : \mathcal{V} \to \overline{\mathbb{Z}_{+}}$.
3. 显然 $m(v_{\mathfrak{m}}) = 1$.

> **引理 8.5.** 设 $v \in \mathcal{V}$, 取局部坐标 $(x,y)$ 使 $1= v(x) \le v(y)$. 若 $v = \mathrm{val}[(U_{j})_{0}^{k} ; (\tilde{\beta}_{j})_{0}^{k}]$, $1 \le k \le \infty$, 则 $m(v) = \sup_{j} \deg_{y}(U_{j})$.

**证明.** 注意到 $U_j$ 关于 $y$ 不可约, 即 $m(U_{j})= d_{j} = \deg_{y}(U_{j})$, 从而由 `引理 6.2` 可知此结论成立. Q.E.D.

> **命题 8.6.** 若 $w \le v$, 则 $m(w)$ 整除 $m(v)$. 进一步地, <br> (i) $m(v) = \infty$ 当且仅当 $v$ 是 infinitely singular 赋值; <br> (ii) $m(v) = 1$ 当且仅当在某个局部坐标 $(x,y)$ 下 $v$ 是 monomial 赋值.

**证明.** 设 $w \le v$. 利用 SKP 将这两个赋值分别写作: $v = \mathrm{val}[(U_{j})_{0}^{k} ; (\tilde{\beta}_{j})_{0}^{k}]$, $w = \mathrm{val}[(U'_{j})_{0}^{k'} ; (\tilde{\beta}'_{j})_{0}^{k'}]$. 则由 `引理 6.2` 知 $k' \le k$, $U_{j} = U'_{j}$ 当 $0 \le j \le k'$, 且 $\tilde{\beta}'_{k'} \le \tilde{\beta}_{k'}$. 从而由 `引理 8.5` 我们有 $m(w) = \prod_{j=0}^{k'-1} n_{j}$ 以及 $m(v) = \prod_{j=0}^{k-1} n_{j}$, 即得 $m(w)$ 整除 $m(v)$.

由 `定义 3.8` 及 `引理 8.5` 立即得 $m(v) = \infty$ 当且仅当 $v$ 为 infinitely singular 赋值.

若 $v$ 为 monomial, 则 $v \le v_{x}$ 或 $v \le v_{y}$, 即 $m(v) = 1$. 反过来, 若 $m(v) = 1$, 则由定义, 存在不可约形式曲线 $C$ 满足 $m(C) = 1$ 使得 $v_{C} \ge v$. 取局部坐标 $(x,y)$ 使得 $C=\{y=0\}$, 即 $v_{C}=v_{y}$. 令 $v_{t}$ 为坐标 $(x,y)$ 下的 monomial 赋值, 满足 $v_{t}(x) = 1$, $v_{t}(y) = t$. 则 $v_{t} \le v_{y}$ 且 $\alpha(v_{t}) = t$, 即 $v_{t} = v_{y,t}$. 由此可知 segment $[v_{\mathfrak{m}}, v_{y}]$ 上的所有赋值都是 monomial 赋值. 特别地 $v$ 是 monomial 赋值. Q.E.D.

> **命题 8.7.** 重数函数 $m : \mathcal{V} \to \overline{\mathbb{Z}_+}$ 下半连续, 但不是连续的.

**证明.** 关于不连续部分, 可以取 $v_{n} := v_{(y+nx)^2+x^3}$ 作为反例. 此时有 $v_{n} \to v_{\mathfrak{m}}$, 但 $m(v_{n}) = 2$, $m(v_{\mathfrak{m}})= 1$. Q.E.D.

### 广义重数

对于赋值 $w\in\mathcal{V}$ 处的切向量 $\vec{v}$, 定义**重数 $m(\vec{v})$** 如下: 若 $\vec{v}$ 所对应等价类中包含 $v_{\mathfrak{m}}$, 则 $m(\vec{v}):=m(w)$; 否则 $m(\vec{v})$ 定义为等价类中所有 curve 赋值 $v_{C}$ 的重数的最小值. 

> **命题 8.8.** 令 $w \in \mathcal{V}$ 为一个 divisorial 赋值. 则存在一个可被 $m(w)$ 整除的正整数 $b(w)$ 使得下述其中之一成立: <br> (i) 所有 $w$ 处的切向量拥有同样的重数 $m(w)$; 此时令 $b(w)= m(w)$; <br> (ii) 在所有 $w$ 处的切向量中, 恰有两个的重数为 $m(w)$, 其中一个为由 $v_{\mathfrak{m}}$ 所代表的切向量; 而所有其他的切向量拥有一个共同的重数 $b(w) > m(w)$.

证明可以参照上面的方法, 利用 `引理 8.5` 及 `引理 6.2` 来计算, 这里不再赘述. 特别地, 对于第 (ii) 种情形, 可以发现 $b(w) = n_{k}\deg_{y}(U_{k})$.

> **定义 8.9.** 称如上的 $b(w)$ 为赋值 $w$ 的 **广义重数 (generic multiplicity)**.


## 逼近序列

由 `命题 8.6, 8.7, 8.8` 立即得:

> **命题 8.10.** 对任意 $v \in \mathcal{V}$, 若 $m(v) < \infty$, 则存在一个 divisorial 赋值的有限序列 $v_{i}$, 以及一个严格递增的整数列 $m_{i}$, 使得
> $$v_{\mathfrak{m}} = v_{0} < v_{1} < \cdots < v_{g} < v_{g+1} = v$$
> 以及 $m(w) = m_{i}$ 对所有 $w \in (v_{i-1}, v_{i}]$, $1\le j \le g+1$. 更进一步地, $m_{1} = 1$, $m_{i}$ 整除 $m_{i+1}$, 且 $v_{i}$ 的广义重数 $b(v_{i}) = m_{i+1}$.

![Approximating sequence]({{ site.baseurl }}/assets/mdnotes/valtree/Approximating_sequence.png)

> **定义 8.11.** 称如上的序列 $(v_{i})_{i=0}^{g}$ 为赋值 $v$ 的 **逼近序列 (approximating sequence)**. 逼近序列的概念可自然地延拓至 infinitely singular 赋值, 此时序列会是个无限序列.


---

下一节, 我们将用赋值重数及逼近序列的概念来定义 Thinness 函数, 此函数将会给出 $\mathcal{V}$ 的令一个参数化.


## 参考文献

Favre, C. and Jonsson, M. (2004). [The Valuative Tree](http://link.springer.com/10.1007/b100262). vol 1853 Springer Berlin Heidelberg, Berlin, Heidelberg.

