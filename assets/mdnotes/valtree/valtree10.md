---
permalink: /valtree10/
math: true
---
# 赋值树理论简介 10

本节我们利用 `逼近序列 (approximating sequence)` 来计算一个赋值的值域, 即 `value semigroup`.

## Value semigroup

记 \(R^{*} = R \setminus \{0\}\), 以及 \(\mathbb{N} = \mathbb{Z}_{+}\).

> **命题 10.1.** 令 \(v\in \mathcal{V}\), 以及 \((v_{i})_{0}^{g}\) 为 \(v\) 的逼近序列 (这里 \(g\) 可能为无穷). 则 `value semigroup`, 定义为 \(v(R^{*})\), 由如下给出
> 
$$
v(R^{*}) = \sum_{i=0}^{g+1} m_{i}\alpha_{i} \mathbb{N},
$$

> 其中 \(v_{g+1} = v\) 若 \(g < \infty\), \(\alpha_{i} = \alpha(v_{i})\) 以及 \(m_{i} = m(v_{i})\).

对于某个 \(v \in\mathcal{V}\), 取局部坐标 \((x,y)\) 使得 \(v(y) \ge v(x) = 1\). 我们将 \(v\) 用 SKP 表示出来: 设 \(v = \mathrm{val}[(U_{j})_{0}^{k} ; (\tilde{\beta}_{j})_{0}^{k}]\), 其中 \(\tilde{\beta}_{1} \ge \tilde{\beta}_{0} = 1\). 记 \(d_{j} = \deg_{y}(U_{j})\). 回忆

$$
n_{j} = \min\Big\{ n \in \mathbb{N} \mid n\tilde{\beta}_{j} \in \sum_{i=0}^{j-1} \tilde{\beta}_{i} \mathbb{Z}\Big\},
$$

且 \(d_{k} = \prod_{j=0}^{k} n_{j}\). 定义数列 \((k_{j})_{j=0}^{g+1}\) 满足: \(k_{0} = 0\),  \(n_{k_{i}} \ge 2\), 以及 \(n_{j} = 1\) 当 \(k_{i} < j < k_{i+1}\).

此时根据逼近序列的定义可知其中每个

$$
v_{i} = \mathrm{val}[(U_{j})_{0}^{k_{i}} ; (\tilde{\beta}_{j})_{0}^{k_{i}}]
$$

其中 \(m(v_{i}) = d_{k_{i}}\). 
- 由 `引理 7.6` 得 \(\alpha_{i} = \alpha(v_{i}) = \tilde{\beta}_{k_{i}}/d_{k_{i}}\). 
- 由于 \(m_{i+1}\) 为 \(v_{i}\) 的广义重数, 因此若 \(v\) 是 divisorial 的, 有 \(b(v) = d_{k}n_{k} = \prod_{j=1}^{k} n_{j}\).

**命题 10.1 的证明.** 由 SKP 所对应的赋值的构造过程可以看出

$$
v(R^{*}) = \sum_{j=0}^{k} \tilde{\beta}_{j} \mathbb{N}.
$$

但是当 \(k_{i} < j < k_{i+1}\) 时, 有 \(n_{j}=1\), 即 \(\tilde{\beta}_{j} \in \sum_{j' < j} \tilde{\beta}_{j'}\mathbb{N}\). 从而

$$
v(R^{*}) = \sum_{i=0}^{g+1}\tilde{\beta}_{k_{i}} \mathbb{N} = \sum_{i=0}^{g+1} m_{i}\alpha_{i}\mathbb{N}.
$$

Q.E.D.


### 广义重数

> **命题 10.2.** 假设 \(v\in\mathcal{V}\) 为 divisorial 赋值, 其逼近序列为 \((v_{i})_{0}^{g}\). 记 \(\alpha_{i}=\alpha(v_{i})\). 则 \(v\) 的广义重数由如下给出:
> $$\begin{align*}\\
b(v) &= \inf\Big\{ b \in m\mathbb{N} \mid b \alpha \in \sum_{i=0}^{g} m_{i}\alpha_{i}\mathbb{N}\Big\}\\
 &= \inf\Big\{ b \in m\mathbb{N} \mid b \alpha \in \sum_{i=0}^{g} m_{i}\alpha_{i}\mathbb{Z}\Big\},
\end{align*}
$$
> 其中 \(m = m(v)\), \(\alpha = \alpha(v)\), 以及 \(m_{0} = 1\).

**证明.** 由上述, 有 \(b(v) = n_{k}d_{k}\), 其中 \(n_{k} = \min \{a \in \mathbb{N} \mid a\tilde{\beta}_{j} \in \sum_{j=0}^{k-1} \tilde{\beta}_{j}\mathbb{Z}\}\). 同上, 我们有 \(\sum_{j=0}^{k-1} \tilde{\beta}_{j} \mathbb{Z} = \sum_{i=0}^{g} m_{i}\alpha_{i}\mathbb{Z}\). 此时, 由 \(\tilde{\beta}_{k}=m\alpha\) 以及 \(d_{k}=m\) 即得

$$
b(v) = \min\Big\{ b \in m\mathbb{N} \mid b\alpha \in \sum_{i=0}^{g} m_{i}\alpha_{i} \mathbb{Z}\Big\}.
$$

最后, 由 `引理 3.4` 知其中的 \(\mathbb{Z}\) 也可以替换为 \(\mathbb{N}\). Q.E.D.

> **命题 10.3.** 令 \(v\in\mathcal{V}\) 为一赋值. 则: <br> (i) 若 \(v\) 为 curve 赋值, 其重数 \(m(v) = m\), 则 \(v(R^{*}) \subset m^{-1}\overline{\mathbb{N}}\); 进一步地, 若 \(a\in \mathbb{N}\), 则 \(a\cdot v(R^{*}) \subset \overline{\mathbb{N}}\) 当且仅当 \(m \mid a\); <br> (ii) 若 \(v\) 为 divisorial 赋值, 其广义重数为 \(b(v)=b\), 则 \(v(R^{*}) \subset b^{-1}\mathbb{N}\); 进一步地, 若 \(a\in \mathbb{N}\), 则 \(a\cdot v(R^{*}) \subset \mathbb{N}\) 当且仅当 \(m \mid a\); <br> (iii) 若 \(v\) 为 irrational 赋值, 其重数 \(m(v)=m\) 且 skewness \(\alpha(v)=\alpha\), 则 \(v(R^{*}) \subset \mathbb{Q}+m\alpha\mathbb{N}\) 但 \(v(R^{*}) \not\subset \mathbb{Q}\); 进一步地, 若 \(a\in \mathbb{N}\), 则 \(a\cdot v(R^{*}) \subset \mathbb{N} + \alpha \mathbb{N}\) 当且仅当 \(m \mid a\); <br> (iv) 若 \(v\) 为 infinitely singular 赋值, 则 \(v(R^{*})\) 且非有限生成的.

**证明.** 首先证明 (ii), 假设 \(v\) 为 divisorial 赋值. 此时 \(k < \infty\). 令 \(a = \min\{a \in \mathbb{N} \mid a\cdot v(R^{*}) \subset \mathbb{N}\}\). 我们需要证明 \(a=b(v)\). 由 \(v(R^{*}) = \sum_{j=0}^{k}\tilde{\beta}_{j} \mathbb{N}\), 记 \(\tilde{\beta}_{j} = r_{j}/s_{j}\), 其中整数 \(r_{j}, s_{j}\) 互素, 记 \(S_{j} = \mathrm{lcm} (s_{0}, s_{1}, \ldots, s_{j})\). 则 \(S_{0}=1\), \(a=S_{k}^{-1}\). 显然 \(\sum_{j'=0}^{j} \tilde{\beta}_{j'}\mathbb{Z} = S_{j}^{-1}\mathbb{Z}\). 由于 \(b(v)=\prod_{j=1}^{k}n_{j}\), 因此我们只需证 \(n_{j}=S_{j}/S_{j-1}\), \(1 \le j \le k\). 实际上
$$
\begin{align*}
	n_{j} &= \min\Big\{ n \in \mathbb{N} \mid n\tilde{\beta}_{j} \in \sum_{j'=0}^{j-1}\tilde{\beta}_{j'}\mathbb{Z}\Big\}\\
&= \min \{n\in\mathbb{N} \mid n\tilde{\beta}_{j} \in S_{j-1}^{-1}\mathbb{Z}\}\\
&= \min\{ n\in \mathbb{N} \mid nr_{j}S_{j-1} \in s_{j} \mathbb{Z}\}\\
&= \min\{n \in \mathbb{N} \mid nS_{j-1} \in s_{j}\mathbb{Z}\}\\
&= \mathrm{lcm}(s_{j}, S_{j-1})/S_{j-1}=S_{j}/S_{j-1}.
\end{align*}
$$

接着证明 (i). 假设 \(v\) 为 curve 赋值, 令 \((v_{i})_{0}^{g}\) 为 \(v\) 的逼近序列. 则由 `命题 10.1`, \(v(R^{*}) = v_{g}(R^{*})\cup \{\infty\}\). 由于 \(v_{g}\) 为 divisorial 赋值, 且广义重数 \(b(v_{g})=m(v)\), 由 (ii) 即得 (i).

对于 (iii), 假设 \(v\) 为 irrational 赋值, 令 \((v_{i})_{0}^{g}\) 为 \(v\) 的逼近序列. 则由 `命题 10.1`, \(v(R^{*})=v_{g}(R^{*})+m\alpha \mathbb{N}\). 由于 \(v_{g}\) 为 divisorial 赋值, 因此 \(v(R^{*}) \subset \mathbb{Q} + m\alpha\mathbb{N}\), 且由 \(\alpha \notin \mathbb{Q}\) 知 \(v(R^{*})\not\subset \mathbb{Q}\). 对任意 \(a\in \mathbb{N}\), 有 \(a\cdot v(R^{*}) \subset \mathbb{N}+\alpha\mathbb{N}\) 当且仅当 \(a\cdot v_{g}(R^{*}) \subset \mathbb{N}\), 而由 (ii) 知这当且仅当 \(b(v_{g})=m(v)\) 整除 \(a\).

最后证明 (iv). 假设 \(v\) 为 infinitely singualr 赋值, 令 \((v_{i})_{0}^{\infty}\) 为 \(v\) 的逼近序列. 则由于所有 \(\alpha(v_{i})\in\mathbb{Q}\), 根据 `命题 10.1` 有 \(v(R^{*}) \subset \mathbb{Q}\). 另一方面, 假设 \(v(R^{*})\) 是有限生成的, 则存在 \(b\in\mathbb{N}\) 使得 \(b\cdot v(R^{*}) \subset \mathbb{N}\). 则此时必有 \(b\cdot v_{i}(R^{*}) \subset \mathbb{N}\) 对所有 \(i\) 成立. 但由 (ii) 知这会导致所有 \(b_{i} \mid b\), 这与当 \(i \to \infty\) 时有 \(b_{i} \to \infty\) 矛盾. Q.E.D.


---

本节结束后, 我们对于赋值树的基本理论大体上介绍完毕了. 虽然还有例如 `使用 Puiseux 展开构造赋值` 等理论是必须涉及的, 但是也很有必要在这里先给出一些赋值树理论的应用, 以避免过分空中楼阁和枯燥. 我将选择主要介绍赋值树在 `乘子理想` 等方面的应用.

当然实际上下一节更可能是一个拾遗篇, 包含一些之前所遗漏的但有必要介绍的内容.


## 参考文献

Favre, C. and Jonsson, M. (2004). [The Valuative Tree](http://link.springer.com/10.1007/b100262). vol 1853 Springer Berlin Heidelberg, Berlin, Heidelberg.
