---
permalink: /valtree05/
math: true
---
# 定理 3.7 及 3.9 的证明

> 无限的存在亦是为了有限.

利用上节中的对于 `定理 3.5` 的证明, 我们已经可以通过 `有限长度的 SKP` 构造出大量的赋值, 但所有如此得到的赋值组成的空间并非一个紧空间, 还需要本节所证明的通过 `无限长度的 SKP` 构造出的赋值来完成对前述空间的紧化.

## 定理 3.7 的证明

> **定理 3.7.** 令 \([(U_j) ; (\tilde{\beta}_j)]\) 为一个无限长度的 SKP. 对任意 \(k \ge 1\), 令 \(v_k\) 为 `定理 3.5` 中的关于 \([(U_j)_{0}^k ; (\tilde{\beta}_j)_{0}^k]\) 的赋值. <br> <br> (i) 如果对无穷多个 \(j\) 有 \(n_j \ge 2\), 则对任意 \(\phi \in R\), 存在 \(k_0 = k_0(\phi)\) 使得 \(v_{k}(\phi) = v_{k_0}(\phi)\) 对所有 \(k \ge k_{0}\) 成立, 特别地 \(v_{k}\) 收敛于一个赋值 \(v_{\infty}\). <br> <br> (ii) 如果对 \(j \gg 1\) 有 \(n_j = 1\), 则 \(U_{k}\) 在 \(R\) 中收敛于一个不可约的形式幂级数 \(U_{\infty}\), 且 \(v_{k}\) 收敛于一个赋值 \(v_{\infty}\). 更精确地说, 如果 \(U_{\infty}\) 整除 \(\phi \in R\), 则 \(v_{k}(\phi) \to \infty\), 否则存在 \(k_{0}(\phi)\) 使得 \(v_{k}(\phi)=v_{k_0}(\phi)\) 对所有 \(k \ge k_0 = k_0(\phi)\).

**证明.** (i) 若对于无穷多个 \(j\) 有 \(n_j \ge 2\), 那么 \(\deg_{y}(U_{k+1}) = d_{k+1} = \prod_{j=1}^k n_{j}\) 将随着 \(k\) 的增加趋向于无穷. 取 \(\phi \in R\), 由 `Weierstrass 除法定理`, 我们不妨设 \(\deg_{y}(\phi) < \infty\). 对 \(k \gg 1\), 有 \(\deg_{y}(\phi) < \deg_{y}(U_{k+1})\), 从而由 \(v_{k}\) 的构造过程可知 \(v_{k}(\phi) = v_{k+l}(\phi)\) 对所有 \(l \ge 1\) 成立. 因此 \(v_{k}\) 收敛到一个赋值 \(v_{\infty}\) 并满足所述性质.

(ii) 若当 \(k \ge K\) 时均有 \(n_{k} = 1\), 令 \(d := \max_{j} \deg_{y}(U_j)\). 则当 \(k \ge K\) 时 \(\deg_{y}(U_{k+1} = \deg_{y} (U_k) = d\), 此时由 

$$
U_{k+1} = U_{k} - \theta_{k} \prod_{j=0}^{k-1} U_{j}^{m_{k,j}},
$$

可知对所有 \(j \ge K\) 有 \(m_{k,j} = 0\). 因此数列 \(\{\tilde{\beta}_{k}\}_{k \ge K}\) 时一个属于离散格点集 \(\sum_{j=0}^{K} \mathbb{Z} \tilde{\beta}_{j}\) 中的严格递增列. 因此有 \(\tilde{\beta}_{k} \to \infty\). 记 

$$
U_{k} = y^d + a_{d-1}^k (x) y^{d-1} + \cdots + a_{0}^k(x),
$$

为其 Weierstrass 多项式形式. 注意到由于对所有 \(j \ge K\) 有 \(m_{k,j} = 0\), 因此

$$
a_{n}^{k+1}(x) = a_{n}^k(x) - \tilde{\theta}_{k} \sum a_{i_1}^{j_1}(x) \cdots a_{i_l}^{j_l}(x),
$$

其中 \(i_1 + \cdots +i_{l} = n\), \(\sharp \{j_s = \alpha \}=m_{k,\alpha}\). 因此 

$$
a_{n}^{k+1}(x) - a_{n}^{k}(x) \in \mathfrak{m}^{\sum_{i=0}^{K} m_{k,i}}.
$$

另一方面, 由于 \(\tilde{\beta}_{j}\) 递增趋于无穷, 我们有

$$
\sum_{i=0}^{K} m_{k,i}\ge \tilde{\beta}_{K}^{-1} \sum_{i=0}^{K}\tilde{\beta}_{i} m_{k,i} = \frac{\tilde{\beta}_{k}}{\tilde{\beta}_{K}} \to \infty,
$$

这里用到了 \(n_j = 1\) 对于 \(j \ge K\) 成立, 以及数列 \(\tilde{\beta}_{k}\) 的递推关系式. 从而我们可以得知 \(\{U_{k}\}\) 的每项系数 \(a_{n}^{k}(x)\) 收敛到某个关于 \(x\) 的形式幂级数, 即 \(U_{k}\) 收敛到一个关于 \(y\) 的系数为形式幂级数的 \(d\) 次多项式 \(U_{\infty} \in \mathbb{C}[[x]][y] \subset \mathbb{C}[[x,y]]\). 

回忆

$$
U_{k+1} = U_{k} - \theta_{k} \prod_{j=0}^{k-1} U_{j}^{m_{k,j}}, \qquad k \ge K+1,
$$

其中 \(v_{k-1}(U_{k}) = n_{k-1}\tilde{\beta}_{k-1} =\tilde{\beta}_{k-1}\), 以及 

$$
v_{k-1}(U_{k+1} - U_{k}) = \sum_{j=0}^{k-1} m_{k,j} \tilde{\beta}_{j} = \tilde{\beta}_{k} > \tilde{\beta}_{k-1}.
$$

这意味着 \(v_{k-1}(U_{k+1}) = \tilde{\beta}_{k-1}\), 并因此有 \(v_{k-1}(U_{k+l}) = \tilde{\beta}_{k-1}\) 对所有 \(l \ge 0\) 成立. 即 \(v_{k-1}(U_{\infty}) = \tilde{\beta}_{k-1}\). 故

$$
v_{\infty}(U_{\infty}) := \lim_{k} v_{k}(U_{\infty}) = \lim_{k} \tilde{\beta}_{k} = \infty.
$$

更一般地, 对任意 \(\phi \in R\), 令 \(\phi = \phi_{0} + U_{\infty} \phi_{1}\), 其中 \(\deg_{y}(\phi_{0}) < \deg_{y} (U_{\infty}) = d\). 若 \(\phi_{0} \equiv 0\), 我们令 

$$
v_{\infty}(\phi) := \lim_{k}v_{k}(\phi) = \infty.
$$

否则, 对充分大的 \(k \ge K\), 以及任意 \(l \ge 0\), 有

$$
v_{k+l}(\phi) = v_{k+l}(\phi_{0}) = v_{k}(\phi_{0}).
$$

因此数列 \(v_{k}(\phi)\) 在 \(k\) 充分大后是常值, 即我们同样可以令 \(v_{\infty} := \lim_{k} v_{k}(\phi)\).

容易验证上述构造的 \(v_{\infty}\) 确实是一个赋值. 特别地, 有 \(v_{\infty}(\phi) = \infty\) 当且仅当 \(U_{\infty}\) 整除 \(\phi\). 由此亦可知 \(U_{\infty}\) 在 \(R\) 中是不可约的. Q.E.D.

---

## 定理 3.9 的构造思路

> **定理 3.9.** 对任意 \(R\) 上的 centered 赋值, 存在唯一的 SKP \([(U_j)_{0}^n ; (\tilde{\beta}_j)_0^n]\), \(1 \le n \le \infty\), 使得 \(v = \mathrm{val}[(U_j) ; (\tilde{\beta}_j)]\). 此时我们有 \(v(U_j) = \tilde{\beta}_j\) 对所有 \(j\). <br> <br> 进一步地, 如果 \(k < n\) 且 \(v_k = \mathrm{val}[(U_j)_0^k ; (\tilde{\beta}_j)_0^k]\), 则 \(v(\phi) \ge v_k(\phi)\) 对所有 \(\phi \in R\) 成立, 并且 \(v(\phi) > v_k(\phi)\) 当且仅当在 \(\mathrm{gr}_{v_k} \mathbb{C}(x)[y]\) 中 \(U_{k+1}\) 能整除 \(\phi\).

**证明概要.** 我们对 \(k\) 归纳地构造赋值 \(v_{k}\) 使得 \(v_{k}(U_{j}) = \tilde{\beta}_{j}\) 对 \(j \le k\) 成立.

令 \(U_{0} = x\), \(U_{1} = y\), 以及 \(\tilde{\beta}_{0} = v(x)\), \(\tilde{\beta}_{1} = v(y)\). 假设 \(v_{k} := \mathrm{val}[(U_{j})_{0}^{k}; (\tilde{\beta}_{j})_{0}^{k}]\) 已经构造出. 则由 `定理 3.5`, 我们有 \(v(\phi) \ge v_{k}(\phi)\) 对所有 \(\phi \in R\) 成立. 由于 \(v(x) =v_{k}(x)\), 这个结果对于所有 \(\phi \in \mathbb{C}(x)[y]\) 亦是正确的. 如果完全有 \(v = v_{k}\), 那么所有的工作都结束了. 否则, 令

$$
\mathcal{D}_{k} := \big\{\phi \in \mathbb{C}(x)[y] \mid v(\phi) > v_{k}(\phi) \big\}.
$$


容易验证: **\(\mathcal{D}_{k}\) 定义了 分次环 \(\mathrm{gr}_{v_{k}}\mathbb{C}(x)[y]\) 中的一个素理想.**

回忆: 分次环 \(\mathrm{gr}_{v_{k}}\mathbb{C}(x)[y]\) 是一个欧几里得整环. 因此 \(\mathcal{D}_{k}\) 由某个不可约元素生成.

可以证明: **\(\mathcal{D}_{k}\) 由唯一的形如 \(U_{k+1} = U_{k}^{n_{k}} - \theta_{k} \prod_{j=0}^{k-1} U_{j}^{m_{k,j}}\) 的不可约元素生成, 其中 \(\theta_{k} \in \mathbb{C}^{*}\), \(0 \le m_{k,j} < n_{j}\) 当 \(j \ge 1\), 且 \(m_{k,0} \ge 0\).**

定义 \(\tilde{\beta}_{k+1} := v(U_{k+1})\). 容易验证 \([(U_{j})_{0}^{k+1}; (\tilde{\beta}_{j})_{0}^{k+1}]\) 确实是一个 SKP. 即完成了归纳构造.

最后这个归纳构造过程要么在有限步停止, 要么我们最终会得到一个无限长度的 SKP \([(U_{j}); (\tilde{\beta}_{j})]\). 分别我们均可验证 \(v = \mathrm{val}[(U_{j}); (\tilde{\beta}_{j})]\). 其中前一种情况是显然的, 后一种也可以由上述 `定理 3.7` 的证明过程类似得出. Q.E.D.

---

至此, 我们完成了通过 SKP 来一对一地表示出 \(\mathbb{C}[[x,y]]\) 上 centered 赋值空间 \(\widetilde{\mathcal{V}}\) 中的所有元素的工作. 这将为我们后面讨论赋值空间的树结构提供可计算基础.

下节我们将开始赋值空间上树结构的证明.

### 参考文献

Favre, C. and Jonsson, M. (2004). [The Valuative Tree](http://link.springer.com/10.1007/b100262). vol 1853 Springer Berlin Heidelberg, Berlin, Heidelberg.