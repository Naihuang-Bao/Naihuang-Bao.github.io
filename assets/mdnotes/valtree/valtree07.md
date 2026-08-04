---
permalink: /valtree07/
math: true
---
# Skewness 的引入

> 想象一下一群人入住旅馆, 如果每个人只知道哪些人在自己前面的房间哪些人在自己后面的房间, 相比于给每人发一个准确的房间号, 是否入住效率要低下得多?

回顾二元形式幂级数环 \(R = \mathbb{C}[[x,y]]\) 以及 \(\mathcal{V}\) 表示 \(R\) 上所有 centered normalized 赋值组成的空间. 在前面的章节中我们证明了 \(\mathcal{V}\) 有一个 **完备的树结构**, 然而想要进一步对 \(\mathcal{V}\)  的树结构加以应用, 给 \(\mathcal{V}\) 以 `参数化 (parameterization)` 是必不可缺的. 本节介绍使用 `skewness 函数` 作参数化的方法, 后面的章节还会介绍使用 `thinness 函数` 进行参数化的方法.


## Skewness

> **定义 7.1.** 对 \(v \in \mathcal{V}\), 定义 **skewness** \(\alpha(v) \in [1, \infty]\) 为 
$$
\alpha(v) := \sup \Big\{ \frac{v(\phi)}{m(\phi)} \mid \phi \in \mathfrak{m}\Big\}.
$$


- 例如对于赋值树 \(\mathcal{V}\) 的根 `重数赋值` \(v_{\mathfrak{m}}\), 显然有 \(\alpha(v_{\mathfrak{m}}) = 1\).

首先给出关于 skewness 的一些关键结论, 后面再慢慢详细阐述证明.

- 回顾对任意不可约 \(\phi \in \mathfrak{m}\), 其对应的 `curve 赋值` 为 
$$
v_{\phi}(\psi) := \frac{\{\phi = 0\} \cdot \{\psi = 0\}}{m(\phi)}, \qquad \forall\, \psi \in \mathfrak{m}.
$$


> **命题 7.2.** 对任意 \(v \in \mathcal{V}\) 以及任意不可约元 \(\phi \in \mathfrak{m}\), 我们有 
$$
v(\phi) = \alpha (v \wedge v_{\phi}) m(\phi).
$$
 特别地, \(v(\phi) \le \alpha(v) m(\phi)\) 且等号成立当且仅当 \(v_{\phi} \ge v\). 

由于 \(\mathcal{V}\) 具有树结构, 因此 \(v \wedge v_{\phi}\) 这个赋值的位置如下图所示.
![Infimum]({{ site.baseurl }}/assets/mdnotes/valtree/Infimum.png)
> **定理 7.3.** Skewness 函数定义了赋值树 \(\mathcal{V}\) 的一个参数化 \(\alpha : \mathcal{V} \to [1, \infty]\). 更进一步地, <br> (i) 若 \(v\) 为 `divisorial 赋值`, 则 \(\alpha(v)\) 为有理数; <br> (ii) 若 \(v\) 为 `irrational 赋值`, 则 \(\alpha(v)\) 为无理数; <br> (iii) 若 \(v\) 为 `curve 赋值`, 则 \(\alpha(v) = \infty\); <br> (iv) 若 \(v\) 为 `infinitely singular 赋值`, 则 \(\alpha(v) \in (1, \infty]\).


## 证明前的准备工作

### SKP 与赋值计算

我们给出以下关于如何使用 SKP 来计算一个赋值在某个具体元素上取值的结果.

令 \(v\in \mathcal{V}\) 以及 \(\phi \in \mathfrak{m}\) 不可约. 令 \(v_{\phi}\) 为关于 \(\phi\) 的 curve valuation. 记 \(v = \mathrm{val}[(U_{j}) ; (\tilde{\beta}_{j})]\) 及 \(v_{\phi} = \mathrm{val}[(U_{j}^{\phi}) ; (\tilde{\beta}_{j}^{\phi})]\) 为其与 SKP 的对应. 假设 \(v \neq v_{\phi}\), 定义 \(v\) 与 \(v_{\phi}\) 的 **contact order** 为

$$
\mathrm{con}(v, v_{\phi}) = \max \{ j \mid U_{j} = U_{j}^{\phi}\}.
$$

令整数 \(n_{j}^{\phi}\) 为关于 \(v_{\phi}\) 的 SKP 中对应的常数, 并令 \(\gamma_{k}^{\phi} = \prod_{j \ge k} n_{j}^{\phi}\) 对 \(k \ge 1\). 注意到这个乘积是有限的因为 \(n_{j}^{\phi} = 1\) 对于 \(j \gg 1\).

> **命题 7.4.** 若 \(\phi = x\), 则 \(v(\phi) = \tilde{\beta}_{0}\). 否则 
$$
v(\phi) = \gamma_{k}^{\phi} \min\{\tilde{\beta}_{k} , \tilde{\beta}_{k}^{\phi}\} \min\{1 , \tilde{\beta}_{0}/\tilde{\beta}_{0}^{\phi}\},
$$
 其中 \(k = \mathrm{con}(v , v_{\phi})\).

**证明.** 当 \(\phi = x\) 时这是显然的. 下面假设 \(\phi \neq x\), 此时 \(\tilde{\beta}_{0}^{\phi} < \infty\). 由 `定义 3.8(6) ` 知我们不妨设 \(\phi = U_{l}^{\phi}\), 其中 \(l = \mathrm{length}(v_{\phi}) \in [k, \infty]\) 为 \(v_{\phi}\) 对应的 SKP 的长度. 注意到由于 \(v\) 和 \(v_{\phi}\) 都是 normalized, 我们有 \(\min\{\tilde{\beta}_{0} , \tilde{\beta}_{1}\} = \min\{\tilde{\beta}_{0}^{\phi} , \tilde{\beta}_{1}^{\phi}\} = 1\).

首先假设 \(k \ge 2\), 此时 \(\tilde{\beta}_{j} = \tilde{\beta}_{j}^{\phi}\) 对所有 \(0 < j < k\). 如若 \(l = k\), 那么 \(\phi = U_{k}\), 此时 \(v(\phi) = \tilde{\beta}_{k}\) 且 \(\tilde{\beta}_{k}^{\phi} = \infty\), 此时欲证等式成立. 因此以下可以假设 \(l > k\). 定义

$$
\xi_{j} = \tilde{\beta}^{\phi}_{k+j}, \qquad \eta_{j} = \min\{\tilde{\beta}_{k} , \tilde{\beta}_{k}^{\phi}\}\frac{\gamma_{k}^{\phi}}{\gamma_{k+j}^{\phi}},
$$

其中 \(0 \le j \le l-k\). 从而
$$
\begin{align*}
v_{\phi}(U_{k+j}^{\phi}) & = \xi_{j}, \qquad j \ge 0,\\
v(U_{i}^{\phi}) &= \tilde{\beta}_{i}, \qquad 0 \le i \le k.
\end{align*}
$$
我们将归纳地对 \(j \ge 1\) 证明 \(v(U_{k+j}^{\phi}) = \eta_{j}\). 特别地, 当 \(j = l - k\) 时由于 \(\gamma_{l}^{\phi} = 1\) 这就是欲证等式.

回忆 SKP 的定义将下面多项式记作

$$
U_{k+j+1}^{\phi} = (U_{k+j}^{\phi})^{n_{k+j}^{\phi}} - \theta_{k+j}^{\phi} \prod_{i=0}^{k+j-1} (U_{i}^{\phi})^{m_{k+j,i}^{\phi}} =: A_{j} - B_{j}. \tag{7.1}
$$

首先我们证明 \(v(U_{k+1}^{\phi}) = \eta_{1}\). 有以下三种情形.
1. \(\tilde{\beta}_{k} > \tilde{\beta}_{k}^{\phi}\). 此时 
$$
v(A_{0}) = n_{k}^{\phi}\tilde{\beta}_{k} > n_{k}^{\phi} \tilde{\beta}_{k}^{\phi} = \sum\limits_{i=0}^{k-1} m_{k,i}^{\phi} \tilde{\beta}_{i} = v(B_0),
$$
 即 \(v(U_{k+1}^{\phi}) = v(B_{0}) = \eta_{1}\).
2. \(\tilde{\beta}_{k} < \tilde{\beta}_{k}^{\phi}\). 此时同理有 \(v(A_{0}) < v(B_{0})\), 即 \(v(U_{k+1}^{\phi}) = v(A_{0}) = \eta_{1}\).
3. \(\tilde{\beta}_{k} = \tilde{\beta}_{k}^{\phi}\). 此时令 \(v_{k} := \mathrm{val}[(U_{j})_{0}^{k} ; (\tilde{\beta}_{j})_{0}^{k}]\). 由 `引理 4.8`, \(U_{k+1}^{\phi}\) 在分次环 \(\mathrm{gr}_{v_{k}} \mathbb{C}(x)[y]\) 中不可约, 且 \(v_{k}(U_{k+1}^{\phi}) = \tilde{\beta}_{k} n_{k}^{\phi} = \eta_{1}\). 若 \(\mathrm{length}(v) = k\), 则 \(v=v_{k}\), 即 \(v(U_{k+1}^{\phi}) = \eta_{1}\). 若 \(\mathrm{length}(v) > k\), 则 \(U_{k+1}^{\phi} \neq U_{k+1}\) 由 \(k\) 的定义, 从而 \(U_{k+1}^{\phi}\) 不属于由 \(U_{k+1}\) 在 \(\mathrm{gr}_{v_{k}} \mathbb{C}(x)[y]\) 中生成的理想, 但由 `定理 3.9` (或见第 05 节该定理证明过程) 可知该理想正与 \(\{v > v_{k}\}\) 相同, 因此有 \(v(U_{k+1}^{\phi}) = v_{k}(U_{k+1}^{\phi}) = \eta_{1}\).

现在令 \(0 \le j \le l-k\), 以及假设 \(v(U_{k+i}^{\phi}) = \eta_{i}\) 对所有 \(1 \le i \le j\) 成立. 下面证明 \(v(U_{k+j+1}^{\phi}) = \eta_{j+1}\). 记 (7.1) 式中 \(a_{i} = m_{k+j, k+i}\) 对 \(0 \le i < j\), 以及 \(c = n_{k+j}^{\phi}\). 则 \(v(A_{j}) = c \eta_{j}\), 并且
$$
\begin{align*}
v(B_{j}) &= \sum_{i=1}^{k} m_{k+j,i}^{\phi} \tilde{\beta}_{i} + \sum_{i=1}^{j-1} a_{i}\eta_{i} \\
&= \sum_{i=1}^{k+j-1} m_{k+j,i}^{\phi}\tilde{\beta}_{i}^{\phi} + a_{0} (\tilde{\beta}_{k} - \xi_{0}) + \sum\limits_{i=1}^{j-1} a_{i}(\eta_{i} - \xi_{i})\\
&\ge \sum_{i=1}^{k+j-1} m_{k+j,i}^{\phi} \tilde{\beta}_{i}^{\phi} + \sum_{i=0}^{j-1} a_{i} (\eta_{i} - \xi_{i})\\
&= c\xi_{j} - \sum_{i=0}^{j-1} a_{i} (\xi_{i} - \eta_{i}).
\end{align*}
$$
为了证明 \(v(U_{k+j+1}^{\phi}) = \eta_{j+1}\), 我们只需要证明 \(v(B_{j}) > c\eta_{j}\), 也就是

$$
\sum_{i=0}^{j-1} a_{i} (\xi_{i} - \eta_{i}) > c (\xi_{j} - \eta_{j}).
$$

令

$$
p_i=\frac{a_{i}\xi_{i}}{\sum_{i=0}^{j-1} a_{i} \xi_{i}},
$$

则 \(\sum_{i=0}^{j-1} p_{i} = 1\). 注意到:
- \(\sum_{i=0}^{j-1} a_{i}\xi_{i} < c \xi_{j}\);
- \(\eta_{i}/\xi_{i} \le 1\),  \(\forall\, 0 \le i \le j\);
- 数列 \((\eta_{i}/\xi_{i})_{0}^{j}\) 是严格递增的.
因此
$$
\begin{align*}
\sum_{i=0}^{j-1} a_{i}(\xi_{i} - \eta_{i}) &= \bigg(\sum_{i=0}^{j-1} a_{i}\xi_{i}\bigg)\sum_{i=0}^{j-1} p_{i} \bigg(1-\frac{\eta_{i}}{\xi_{i}}\bigg)\\
&< c \xi_{j} \bigg(1 - \frac{\eta_{j}}{\xi_{j}}\bigg)\\
&= c(\xi_{j}- \eta_{j}).
\end{align*}
$$
综上我们完成了 \(k \ge 2\) 情形的证明.

下面我们假设 \(k = 1\). 此时有以下几类情形:
1. \(\tilde{\beta}_{0} \ge \tilde{\beta}_{1} = 1\) 且 \(1 = \tilde{\beta}_{0}^{\phi} \le \tilde{\beta}_{1}^{\phi}\);
2. \(\tilde{\beta}_{0} \ge \tilde{\beta}_{1} = 1\) 且 \(\tilde{\beta}_{0}^{\phi} > \tilde{\beta}_{1}^{\phi} = 1\);
3. \(1 = \tilde{\beta}_{0} < \tilde{\beta}_{1}\) 且 \(1 = \tilde{\beta}_{0}^{\phi} \le \tilde{\beta}_{1}^{\phi}\);
4. \(1 = \tilde{\beta}_{0} \ge \tilde{\beta}_{1}\) 且 \(\tilde{\beta}_{0}^{\phi} > \tilde{\beta}_{1}^{\phi} = 1\).
可以分别类似于上述方法处理. Q.E.D.


> **推论 7.5.** 若 \(v\in \mathcal{V}\) 以及 \(\phi\in \mathfrak{m}\) 不可约, 则
> 
$$
\frac{v(\phi)}{m(\phi)} = d_{k}^{-1} \min\{\tilde{\beta}_{k} , \tilde{\beta}_{k}^{\phi}\} \min\{\tilde{\beta}_{0} , \tilde{\beta}_{0}^{\phi}\},
$$

> 其中 \(k = \mathrm{con}(v , v_{\phi})\) 以及 \(d_{k} = \deg_{y}(U_{k}) = \prod_{j=1}^{k-1} \eta_{j}\).

**证明.** 在 `命题 6.4` 中令 \(v = v_{\mathfrak{m}}\), 则有 \(m(\phi) = v_{\mathfrak{m}}(\phi) = \gamma_{1}^{\phi}/\tilde{\beta}_{0}^{\phi}\) 若 \(\phi \neq x\). 带入即得. Q.E.D.


### 不同类型赋值的 skewness

> **引理 7.6.** 令 \(v\in \mathcal{V}\). 设在局部坐标 \((x,y)\) 下 \(v = \mathrm{val}[(U_{j})_{0}^{k} ; (\tilde{\beta}_{j})_{0}^{k}]\). 则有
> (i) 若 \(v\) 是 `quasimonomial 赋值`, 则 \(\alpha(v) = d_{k}^{-1} \tilde{\beta}_{k}\tilde{\beta}_{0}\), 其中 \(d_{k} = \deg_{y}(U_{k})\); 特别地, 如果 \(\alpha(v) \in \mathbb{Q}\) 则 \(v\) 是 `divisorial`;
> (ii) 若 \(v\) 是 `curve 赋值`, 则 \(\alpha(v) = \infty\);
> (iii) 若 \(v\) 是 `infinitely singular 赋值`, 则 \(\alpha (v) = \lim\limits_{j \to \infty} d_{j}^{-1} \tilde{\beta}_{j} \tilde{\beta}_{0} \in (1, \infty]\).

**证明.** (i) 首先我们假设 \(\phi \in \mathfrak{m}\) 不可约. 设 \(v_{\phi} = \mathrm{val}[(U^{\phi}_{j}) ; (\tilde{\beta}^{\phi}_{j})]\), 并令 \(l = \mathrm{con}(v, v_{\phi})\). 则 \(l \le k\). 回忆数列 \((d_{j}^{-1} \tilde{\beta}_{j})_{1}^{k}\) 是单调递增的. 此时由 `推论 7.5` 得

$$
\frac{v(\phi)}{m(\phi)} = d_{l}^{-1} \min\{\tilde{\beta}_{l} , \tilde{\beta}_{l}^{\phi}\} \min\{\tilde{\beta}_{0}, \tilde{\beta}_{0}^{\phi}\} \le \sup_{j\le k} d_{j}^{-1} \tilde{\beta_{j}}\tilde{\beta}_{0} = d_{k}^{-1} \tilde{\beta_{k}}\tilde{\beta}_{0}.
$$

若 \(v\) 是 quasimonomial, 则 \(k < \infty\), 此时选取 \(\phi\) 使得 \(l = k\) 及 \(\tilde{\beta}_{k}^{\phi} = \tilde{\beta}_{k}\), 上面不等式即取等号. 如果 \(\phi\) 可约,  令 \(\phi = \prod \phi_{i}\) 其中 \(\phi_{i}\) 均不可约, 则

$$
v(\phi) = \sum v(\phi_{i}) \le C \sum m(\phi_{i}) = C m(\phi),
$$

其中 \(C\) 使得 \(v(\phi) \le C m(\phi)\) 对于所有 \(\phi\) 不可约成立. 因此 \(\alpha(v) = d_{k}^{-1}\tilde{\beta}_{k}\tilde{\beta}_{0}\).

(ii) 若 \(v = v_{\phi}\) 为关于 \(\phi\) 的 curve valuation, 则 \(\alpha(v) \ge v(\phi)/m(\phi) = \infty\).

(iii) 若 \(v\) 为 infinitely singular, 此时 \(k = \infty\), 类似于 (i) 中取 \(\phi\) 使 \(l = j\) 及 \(\tilde{\beta}_{l}^{\phi}=\tilde{\beta}_{l}\),  则有 \(\alpha(v) \ge d_{j}^{-1}\tilde{\beta}_{j}\tilde{\beta}_{0}\). 令 \(j \to \infty\) 即得欲证结论. Q.E.D.


## 定理 7.3 的证明

由 `引理 7.6`, 知 (i)-(iv) 这些结论均是成立的, 因此我们只需证 \(\alpha\) 给出了 \(\mathcal{V}\) 的一个参数化. 对此我们只需证, 如果 \(v \in \mathcal{V}\) 是一个 end (即为 curve 赋值或者 infinitely singular 赋值), 则 \(\alpha\) 给出一个 \([v_{\mathfrak{m}}, v)\) 到 \([1, \alpha(v))\) 上的递增映射.

取局部坐标 \((x,y)\) 使得 \(v(x) = 1 \le v(y)\). 设 \(v = \mathrm{val}[(U_{j})_{0}^{k} ; (\tilde{\beta}_{j})_{0}^{k}]\). 则 \(k = \infty\) 或者 \(\tilde{\beta}_{k} = \infty\). 令 \(d_{l} = \deg_{y}(U_{l})\). 回忆 \((\tilde{\beta}_{l}/d_{l})_{1}^{k}\) 是严格递增数列. 由 `引理 6.2` 知任意赋值 \(w \in (v_{\mathfrak{m}} , v)\) 必为以下形式

$$
w = \mathrm{val}[(U_{j})_{0}^{l} ; (\tilde{\beta}_{j})_{0}^{l-1}, \tilde{\beta}],
$$

其中 \(1 \le l \le \min\{k, \infty\}\), \(\tilde{\beta} < \infty\) 若 \(l = k < \infty\) 且 \(d_{l-1}^{-1} d_{l}\tilde{\beta}_{l-1} < \tilde{\beta} \le \tilde{\beta}_{l}\). 由 `引理 7.6` 我们有 \(\alpha(w) = \tilde{\beta}/d_{l}\). 这表明 \(\alpha\) 确实是一个 \([v_{\mathfrak{m}} , v]\) 到 \([1, \alpha(v))\) 上的递增双射. Q.E.D.


## 命题 7.2 的证明

我们沿用 `引理 7.6` 及其证明中的记号. 若 \(v = v_{\phi}\), 则 \(v \wedge v_{\phi} = v_{\phi}\), 结论成立. 否则 \(l := \mathrm{con}(v_{\phi}, v) < \infty\), 并且由 `推论 6.3` 有 \(v \wedge v_{\phi} = \mathrm{val}[(U_{j})_{0}^{l} ; (\tilde{\beta}_{j})_{0}^{l-1}, \tilde{\beta}]\), 其中 \(\tilde{\beta} = \min\{\tilde{\beta}_{k} , \tilde{\beta}_{l}^{\phi}\}\). 从而

$$
\alpha(v \wedge v_{\phi}) = d_{l}^{-1} \tilde{\beta} \tilde{\beta}_{0} = \frac{v(\phi)}{m(\phi)}.
$$

Q.E.D.

---

下一节我们介绍 skewness 相关的更多结果, 以及引入赋值的重数等概念.


## 参考文献

Favre, C. and Jonsson, M. (2004). [The Valuative Tree](http://link.springer.com/10.1007/b100262). vol 1853 Springer Berlin Heidelberg, Berlin, Heidelberg.
