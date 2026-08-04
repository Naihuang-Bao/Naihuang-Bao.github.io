---
permalink: /valtree11/
math: true
---
# 赋值树理论简介 11 (拾遗)

> 拾遗篇之于系列读书笔记, 就如同总集篇之于番剧, 不可或缺.

为了避免与切向量符号混淆, 本节部分地方我们用 $\nu$ 来表示一个赋值, 而不是和以前一样都是用 $v$.

## 赋值树弱拓扑之等价性

回忆赋值空间 $\mathcal{V}$ 上我们其实定义过两种 `弱拓扑`:

1. 其一是利用 `序列收敛`, 即 $\mathcal{V}$ 中 $\nu_{k} \to \nu$ 等价于说 $\nu_{k}(\phi) \to \nu(\phi)$ 对任意 $\phi \in \mathfrak{m}$ 成立;

2. 其二是来自于 $\mathcal{V}$ 的 `树结构`, 即其上开集由 $U(\vec{v})$ 所生成, 这里 $\vec{v}$ 遍历所有 $\mathcal{V}$ 上的切向量.

> **定理 11.1.** 上述两种 $\mathcal{V}$ 上的弱拓扑是完全等价的.

**证明.** 设 $\nu \in \mathcal{V}$, 以及 $\vec{v} \in T\nu$ 为切向量. 我们考虑利用 `命题 7.2` 来刻画对应邻域 $U(\vec{v})$. 
- 若 $\vec{v}$ 不由 root $\nu_{\mathfrak{m}}$ 所表示 (即所对应 $U(\vec{v})$ 中不包含 $\nu_{\mathfrak{m}}$): 设 $\nu_{\phi}$ 为表示 $\vec{v}$ 的一个 curve 赋值 (这样的 curve 赋值总是存在的, 由 `命题 6.4`), 则由树结构及定义可知, 任意赋值 $\mu \in U(\vec{v})$ 等价于 $\alpha(\mu \wedge \nu_{\phi}) > \alpha(\nu)$, 此式由 `命题 7.2` 知等价于 $\mu(\phi) > \alpha m(\phi)$, 其中 $\alpha = \alpha(\nu)$. 即 $$U(\vec{v}) = \{\mu \mid \mu(\phi) > \alpha m(\phi)\}.$$
- 若 $\vec{v}$ 由 $\nu_{\mathfrak{m}}$ 所表示: 这时我们设 $\nu_{\psi}$ 为满足 $\nu_{\psi} \ge \nu$ 的任一 curve 赋值, 则赋值 $\mu\in U(\vec{v})$ 等价于 $\alpha(\mu \wedge \nu_{\psi}) < \alpha (\nu)$, 即 $$U(\vec{v}) = \{\mu \mid \mu(\psi) < \alpha m(\psi)\}.$$
对于这两种情形, 我们均可以验证 $U(\vec{v})$ 在序列收敛对应弱拓扑下是开集. 例如第一种情形中, 我们需要说明若 $\mu_{k} \in \mathcal{V} \setminus U(\vec{v})$, 且 $\mu_{k} \to \mu \in \mathcal{V}$, 则 $\mu \notin U(\vec{v})$. 此时对任意 $k$ 我们有 $\mu_{k}(\phi) \le \alpha m(\phi)$, 而 $\mu_{k} \to \mu$, 因此 $\mu(\phi) \le \alpha m(\phi)$, 即 $\mu \notin U(\vec{v})$. 同理可说明第二种情况该结论也是成立的.

反过来我们需要说明序列收敛对应弱拓扑下的开集也在树结构对应弱拓扑下是开集. 注意到实际上序列收敛弱拓扑对应开集的一组基为 $\{\nu \in \mathcal{V} \mid t < \nu(\phi) < t'\}$, 其中 $\phi \in \mathfrak{m}$ 不可约, $t' > t \ge 1$. 根据我们对集合 $U(\vec{v})$ 的上述两种情形的讨论中可以看出, 如 $\{\nu(\phi) > t\}$ 及 $\{\nu(\phi) < t'\}$ 形式的集合 ($\phi$ 不可约, $t , t' \ge 1$) 均可以对应为某个 $U(\vec{v})$. 因此它们都是树结构拓扑下的开集. Q.E.D.

> **命题 11.2.** $\mathcal{V}$ 中包含所有 divisorial 赋值, irrational 赋值, infinitely singular 赋值及 curve 赋值的这四个子集均分别在 $\mathcal{V}$ 中关于弱拓扑稠密.

**证明.** 前两者可由 `定理 7.3` 得出. 而对于后两个集合, 注意到由 `命题 6.4` 我们可知对于每一个切向量 $\vec{v}$, 其对应开集 $U(\vec{v})$ 中总是包含某个 infinitely singular 赋值以及某个 curve 赋值, 由此可知后两个集合也均分别在 $\mathcal{V}$ 中稠密. Q.E.D.


## 赋值的点积

> **定义 11.3.** 对任意 $\nu, \mu \in\mathcal{V}$, 定义 $\nu \cdot \mu := \alpha(\nu \wedge \mu)$. 实际上对于任意带参数化 $\alpha$ 的 rooted nonmetric tree, 都可以类似定义.

回忆第二节关于 `可参数化 rooted nonmetric tree 都是弱紧的` 定理的证明 (或者直接验证: 若 $\nu_{n} \to \nu$, 则 $\nu_{n}\wedge \mu \to \nu \wedge \mu$ 对于任意固定的 $\mu$), 我们可知:

> **命题 11.4.** 对于固定的 $\nu$ 或者 $\mu$, 点积 $\nu \cdot \mu$ 关于另一个变元在 $\mathcal{V}$ 上是连续的.

另一方面,

> **命题 11.5.** 关于双变元 $(\nu, \mu) \in \mathcal{V}\times \mathcal{V}$, 点积 $\nu \cdot \mu$ 是下半连续的, 但并不是连续的.

**证明.** 我们先证下半连续性. 设 $\nu_{n}\in\mathcal{V}$, $\mu_{n}\in\mathcal{V}$, 并且 $\nu_{n}\to \nu$, $\mu_{n} \to \mu$, 则存在一个 $\nu_{n}\wedge \mu_{n}$ 的子序列使得其取到 $\nu_{n}\cdot \mu_{n}$ 的下极限, 不妨设为该序列自身; 再由于 $\mathcal{V}\times\mathcal{V}$ 为紧空间, 可以找到 $\nu_{n}\wedge \mu_{n}$ 的子序列使得其收敛到某个赋值 $w$, 不妨再设这个子序列为这个序列本身. 此时我们有 $\nu_{n} \to \nu$, $\mu_{n}\to \mu$, 以及 $\nu_{n}\wedge \mu_{n} \to w$. 由 $\alpha$ 在 $\mathcal{V}$ 上的下半连续性只需证 $\alpha(w) \ge \alpha(\nu \wedge \mu)$. 事实上, 对于任意 $\phi\in\mathfrak{m}$ 不可约, 我们有
$$\nu_{n}\wedge \mu_{n} \wedge \nu_{\phi} = (\nu_{n}\wedge \nu_{\phi}) \wedge (\mu_{n}\wedge \nu_{\phi}) = \nu_{\phi, s_{n}} \wedge \nu_{\phi, t_{n}}=\nu_{\phi, \min\{s_{n}, t_{n}\}},$$
其中 $s_{n}=\alpha(\nu_{n}\wedge \nu_{\phi}) \to \alpha(\nu \wedge \nu_{\phi})$, 以及 $t_{n}\to \alpha(\mu\wedge \nu_{\phi})$, 从而
$$\min\{s_n,t_{n}\} \to \min\{\alpha(\nu\wedge \nu_{\phi}), \alpha(\mu\wedge \nu_{\phi})\} \ge \alpha(\nu \wedge \mu\wedge \nu_{\phi}),$$
即 $\alpha(w \wedge \nu_{\phi}) \ge \alpha(\nu \wedge \mu \wedge \nu_{\phi})$. 由 skewness 定义即得 $\alpha(w) \ge \alpha(\nu \wedge \mu)$.

注意到 $\nu\cdot \nu=\alpha(\nu)$, 则点积不连续性可从 $\alpha$ 不连续性直接得到, 例如取 $\nu_{n}=\nu_{y-nx,2}$, 则 $\nu_{n}\to \nu_{\mathfrak{m}}$, 但 $\nu_{n}\cdot \nu_{n} = 2$ 以及 $\nu_{\mathfrak{m}} \cdot \nu_{\mathfrak{m}} = 1$. Q.E.D.


## 具有特定数值的 infinitely singular 赋值

> **命题 11.6.** 对任意 quasimonomial 赋值 $v \in \mathcal{V}$, 以及任意实数 $\alpha > \alpha(v)$, 存在一个 infinitely singular 赋值 $w$ 满足 $w > v$ 且 $\alpha(w) = \alpha$.

**证明.** 不妨设 $v$ 为 divisorial 赋值, 否则将 $v$ 替换为一个满足 $\alpha(v') < \alpha$ 的 divisorial 赋值 $v'$.

令 $(v_{i})_{0}^{g}$ 为 $v$ 的逼近序列, $v_{g+1} = v$. 取 curve 赋值 $w_{g+2} > v$ 使得 $m(w_{g+2}) = b(v)$. 考虑 segment $(v, w_{g+2})$ 上的 divisorial 赋值, 由 `命题 10.2` 知, 在这个 segment 上满足广义重数等于 $b(v)$ 的赋值是个离散点集, 即我们必可以找到某个赋值 $v_{g+2}$ 在这个 segment 上, 且满足
$$b(v_{g+2}) > m(v_{g+2}) = b(v), \quad \alpha - \frac{1}{2} > \alpha(v_{g+2}) > \alpha(v).$$
重复这个过程, 我们可以找到一列严格递增的赋值 $(v_{i})_{1}^{g+k}$, 满足
$$b(v_{g+k+1}) > m(v_{g+k+1}) = b(v_{g+k}), \quad \alpha - \frac{1}{2^{k}} > \alpha(v_{g+k+1}) > \alpha(v_{g+k}).$$
因此 $(v_{i})_{0}^{\infty}$ 定义了一个 infinitely singular 赋值 $w$ 的逼近序列, 且有 $w > v$ 以及 $\alpha(w) = \alpha$. Q.E.D.

> **命题 11.7.** 对任意 quasimonomial 赋值 $v \in \mathcal{V}$, 以及任意实数 $A > A(v)$, 存在一个 infinitely singular 赋值 $w$ 满足 $w > v$ 且 $A(w) = A$.

**证明.** 由 thinness 在每个 segment 上的单调性和连续性, 用几乎和上面完全相同方法即可证明这样的赋值的存在性. Q.E.D.

- 从证明我们可以注意到, 对任意 $t\in (1, \infty)$, 我们可以构造出某个 infinitely singular 赋值 $v\in\mathcal{V}$ 同时满足 $\alpha(v) = t$ 以及 $A(v) = \infty$. 事实上在构造过程中, 我们每次取 $v_{i}$ 时只需将 $b(v_{i})$ 取得非常高即可.

- 记 $\widetilde{\mathcal{V}}$ 为 $R = \mathbb{C}[[x,y]]$ 上的 centered 赋值全体. 利用 $A(tv) := t A(v)$ 可以将 thinness 函数 $A$ 延拓到整个 $\widetilde{\mathcal{V}}$ 上. 注意此时对于 $v,w \in \widetilde{\mathcal{V}}$, 我们无法从 $w \ge v$ 中推出 $A(w) \ge A(v)$. 事实上我们可以取 $w = 3 v_{\mathfrak{m}}$, 而 $v\in\mathcal{V}$ 为 infinitely singular 赋值, normalized, 且满足 $\alpha(v) = 2$ 以及 $A(v) = \infty$. 则 $v(\phi) \le \alpha(v) m(\phi) = 2v_{\mathfrak{m}}(\phi)$ 对任意 $\phi\in \mathfrak{m}$ 成立, 即 $w \ge v$, 但 $A(w) = 3 A(v_{\mathfrak{m}}) = 6 < A(v)$.


---

下一节我们介绍如何利用赋值理论构造 $R = \mathbb{C}[[x,y]]$ 中的理想或者 `次可加理想列 (graded sequence of ideals)` 的 `乘子理想`, 以及其 `对数典范阈值 (log canonical threshold)` 与 `跳跃数 (jumping number)`, 并证明这些数值总会被某个 quasimonomial 赋值所取到 (此结论曾被 Favre-Jonsson 用于证明由 Demailly-Kollar 所提出的 `开性猜想` 的 2 维情形).


## 参考文献

Favre, C. and Jonsson, M. (2004). [The Valuative Tree](http://link.springer.com/10.1007/b100262). vol 1853 Springer Berlin Heidelberg, Berlin, Heidelberg.
