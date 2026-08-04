---
permalink: /valtree13/
math: true
---
# 赋值树理论简介 13

本文中依然记 \(R = \mathbb{C}[[x,y]]\), 其极大理想 \(\mathfrak{m}=(x,y)R\).

## ACC 定理

对任意 \(\psi\in R\), 简记 \(c(\psi) = \mathrm{lct}(\psi)\). 回忆 \(c(\psi) = \inf_{v\in\mathcal{V}_{\mathrm{qm}}} A(v)/v(\psi)\). 本文介绍下面的结果在 \[[1](#参考文献)\] 文中对下面的结果利用赋值树理论给出的另证.

> **定理 13.1.** 集合 \(\mathbf{c} = \{c(\psi) \mid \psi \in \mathfrak{m}\}\) 满足 ACC (ascending chain condition), 即任意 \(\mathbf{c}\) 中的递减序列均最终稳定.

实际上, 上面的 ACC 定理在任意维数都是成立的.

> **命题 13.2.** 上述集合 \(\mathbf{c}\) 的极限点集为 \(\{0\}\cup \{1/a \mid a\in\mathbb{N}\}\).


## 赋值树理论的结果

对任意 \(\psi\in \mathfrak{m}\), 令 \(\lambda(\psi) := c(\psi)^{-1}\) 为 \(\psi\) 的 **Arnold 重数 (Arnold multiplicity)**, 等价于我们需要证 \(\boldsymbol{\lambda} := \{\lambda(\psi) \mid \psi \in \mathfrak{m}\}\) 满足 DCC (descending chain condition), 且极限点集为 \(\mathbb{N}\cup \{\infty\}\). 对任意 \(v\in \mathcal{V}\), 令 \(\chi_{\psi}(v) = v(\psi)/A(v)\), 则 \(\lambda(\psi)= \sup_{v\in \mathcal{V}_{\mathrm{qm}}} \chi_{\psi}(v)\).

对于 \(\psi\), 令 \(\psi=\prod \phi_{k}^{a_{k}}\) 为将其分解为不可约因子的乘积. 对每个 \(k\), 定义赋值

$$
v_{k} := \max\{v \in \mathcal{V} \mid m(v) = 1, \ v \le v_{\phi_{k}}\}.
$$

则 \(v_{k}\) 为 \(v_{\phi_{k}}\) 或者某个 divisorial 赋值. 记 \(\alpha_{k}=\alpha(v_{k})\), \(b_{k} = b(v_{k})\), \(v_{kl} = v_{k} \wedge v_{l}\) 以及 \(\alpha_{kl} = \alpha(v_{kl})\).

> **引理 13.3.** 对所有 \(k,l\), 有 \(\alpha_{kl} m_{k}\) 与 \(\alpha_{kl}m_{l}\) 二者至少有一个为整数, 其中 \(m_{k}=m(\phi_{k})\).

**证明.** 由 `命题 10.2`, 知 \(b_{k}\alpha_{k}\in\mathbb{N}\) ( 若 \(\alpha_{k} < \infty\)), 且 \(m_{k}\) 被 \(b_{k}\) 整除, 因此 \(m_{k}\alpha_{k}\in\mathbb{N}\). 由此知若 \(v_{kl}=v_{k}\) 或 \(v_{l}\), 则该引理成立. 否则我们有 \(v_{kl} < v_{k}\) 且 \(v_{kl} < v_{l}\). 那么我们由 \(m(v_{k}) = m(v_{l}) = 1\) 即可知 \(b(v_{kl}) = 1\), 此时再根据 \(b_{kl}\alpha_{kl} \in \mathbb{N}\) 知也有 \(\alpha_{kl}\in\mathbb{N}\) 成立. Q.E.D.

> **引理 13.4.** 函数 \(\chi_{\psi}\) 的上确界在某个 \(v_{kl}\) 处取得.

**证明.** 由于

$$
\chi_{\psi}(v) = \frac{v(\psi)}{A(v)} = \frac{\sum a_{k}v(\phi_{k})}{A(v)},
$$

类似于 `引理 12.6` 的证明, 我们可以得到 \(\chi_{\psi}\) 的上确界必在 \(v_{\mathfrak{m}}\) 或者某个 \(v_{kl}\) 处取得 (具体细节不再赘述). 如果某个 \(v_{kl} = v_{\mathfrak{m}}\), 那么引理成立. 否则我们设 \(v_{kl} > v_{\mathfrak{m}}\) 对所有 \(k,l\) 成立. 这意味着 \(w := \wedge_{k,l}v_{kl} > v_{\mathfrak{m}}\). 此时类似于 `引理 12.6` 的证明会发现在 \([v_{\mathfrak{m}}, w)\) 上有 \(\mathrm{d}\chi_{\psi}/\mathrm{d}\alpha > 0\), 即 \(\chi_{\psi}\) 不会在 \(v_{\mathfrak{m}}\) 处达到上确界. Q.E.D.

> **引理 13.5.** 对任意 \(k,l\), 我们有 \(v_{kl}(\psi) \in \frac{1}{m_{k}}\mathbb{N}^{*} \cup \frac{1}{m_{l}}\mathbb{N}^{*}\).

**证明.** 固定某个 \(i\). 
- 若 \(v_{\phi_{i}} \ge v_{kl}\), 则 \(v_{kl}(\phi_{i}) = \alpha_{kl}m_{i}\), 由 `引理 13.3`, 它属于 \(\frac{1}{m_{k}}\mathbb{N}^{*} \cup \frac{1}{m_{l}}\mathbb{N}^{*}\). 
- 若 \(v_{\phi_{i}} \not \ge v_{kl}\), 则 \(v_{kl}(\phi_{i})=v_{ik}(\phi_{i})\). 此时根据 `引理 13.3` 及其证明过程: 要么 \(v_{ik}=v_{i}\) 且 \(v_{kl}\in \mathbb{N}^{*}\); 要么 \(v_{ik} < v_{i}\), \(v_{ik} < v_{kl}\) 且 \(\alpha_{ik} \in \mathbb{N}^{*}\), 由此亦有 \(v_{kl}(\phi_{i}) \in \mathbb{N}^{*}\).
综上, \(v_{kl}(\psi)=\sum a_{i}v_{kl}(\phi_{i})\in \frac{1}{m_{k}}\mathbb{N}^{*} \cup \frac{1}{m_{l}}\mathbb{N}^{*}\). Q.E.D.

> **引理 13.6.** 由 `引理 13.4` 假设 \(\lambda(\psi) = \chi_{\psi}(v_{kl})\). 令 \(I = \{i : v_{\phi_{i}} \ge v_{kl}\}\) 并令 \(J\) 为 \(I\) 的补集. 则
> 
$$
\sum_{j\in J} a_{j}v_{kl}(\phi_{j}) \le \sum_{i\in I} a_{i}m_{i}.
$$


**证明.** 对任意 \(t\in (\alpha_{kl}-\eta, \alpha_{kl})\), 其中 \(\eta\) 为很小的正实数, 我们有

$$
\chi_{\psi}(v_{\phi_{i}, t}) = \frac{t\big(\sum_{i\in I} a_{i}m_{i}\big)+ \sum_{j\in J}a_{j}v_{kl}(\phi_{j})}{1+t},
$$

并且由于 \(\chi_{\psi}\) 的上确界在 \(v_{kl}\) 处取到, 即 \(\chi'(t) \ge 0\) 在该区间上成立, 从而得到欲证不等式. Q.E.D.


## ACC 定理的证明

首先我们证明 `定理 13.1`, 为此我们只需证明对任意 \(C > 0\), 集合 \(\boldsymbol{\lambda} \cap (0, C)\) 满足 DCC.

任取一列 \(\psi_{n}\in\mathfrak{m}\) 满足 \(\lambda(\psi_{n})\) 递减并且均小于 \(C\). 由

$$
\lambda(\psi) = \sup_{v}\frac{v(\psi)}{A(v)} \ge \frac{m(\psi)}{2},
$$

得 \(m(\psi_{n}) \le 2C\). 对任意 \(n\), 我们如上引入记号 \(\phi_{k}^{n}\), \(\alpha_{kl}^{n}\), \(I^{n}\) 以及 \(J^{n}\). 后面为了简便也可能不带角标 \(n\). 再令

$$
\mathcal{N} = \left\{\frac{p}{q} : p,q\in \mathbb{N}^{*}, \ q\le 2C\right\}.
$$


另一方面, 由 `引理 13.4`,
$$
\begin{align*}
\lambda(\psi_{n}) &= \frac{\Big(\sum\limits_{i\in I}a_{i}m_{i}\Big)\alpha_{kl}+\sum\limits_{j\in J}a_{j}v_{kl}(\phi_{j})}{1+\alpha_{kl}}\\
&= \Big(\sum_{i\in I}a_{i}m_{i}\Big)-\frac{1}{1+\alpha_{kl}}\Big(\sum_{i\in J} a_{i}m_{i}- \sum_{j\in J} a_{j}v_{kl}(\phi_{j})\Big).
\end{align*}
$$

注意到 \(\sum_{i\in I}a_{i}m_{i}\le m(\psi_{n}) \le 2C\), 因此对于充分大的 \(n\), 我们可以不妨假设 \(\sum_{i\in I}a_{i}m_{i}\) 是常数, 记为 \(D\). 另一方面, 由 `引理 13.5`, \(\sum_{j\in J} a_{j}v_{kl}(\phi_{j})\) 总是属于离散集 \(\mathcal{N}\) 中. 而由 `引理 13.6` 知它又是被 \(D\) 作为上界所控制的, 因此我们也可以不妨假设它是常数. 因此,

$$
\lambda(\psi_{n})=D-\frac{E}{1+\alpha_{kl}},
$$

其中 \(E\) 是某个常数. 从而当 \(\lambda(\psi_{n})\) 递增的时候, 相应地有 \(\alpha_{kl}\) 是递减的. 最后, 结合 `引理 13.3` 知 \(\alpha_{kl} \in \mathcal{N}\) 得到对于充分大的 \(n\), 有 \(\alpha_{kl}\) 是常数. 综上, 得证 \(\boldsymbol{\lambda}\) 满足 DCC.
Q.E.D.

下面计算 \(\boldsymbol{\lambda}\) 的所有极限点. 假设 \(\lambda(\psi_{n}) \to \lambda \in \boldsymbol{\lambda}\), \(\lambda\neq \infty\). 由 DCC 我们不妨假设 \(\lambda(\psi_{n})\) 是单调递增的. 同样由上, 我们可以得到 \(\lambda(\psi_{n})=D-E(1+\alpha_{kl})^{-1}\) 对某两个常数 \(D,E > 0\), 其中 \(D\) 是一个整数. 因此若使 \(\lambda(\psi_{n})\) 不最终稳定, 必须有 \(\alpha_{kl} \to \infty\), 即 \(\lambda = D\in \mathbb{N}\). 因此 \(\boldsymbol{\lambda}\) 的极限点包含在 \(\mathbb{N}\cup\{\infty\}\) 中. 

另一方面, 对任意 \(m,n\in \mathbb{N}\), 计算可得 \(\lambda(y^{m}+x^{n})=\dfrac{mn}{m+n}\), 这个集合的极限点包含了 \(\mathbb{N}\cup\{\infty\}\) 中所有的元素. 综上, `命题 13.2` 得证.
Q.E.D.

> **引理 13.7.** 对任意 \(m,n\in\mathbb{N}\), 有 \(\lambda(y^{m}+x^{n})=\dfrac{mn}{m+n}\).

实际上对于这类多项式的 log canonical threshold 的计算有专门的 (Howald's) Newton polyhedron 的算法, 参见 \[[2](#参考文献), 9.3.C 节\].


## 参考文献

\[1\]. Favre, C. and Jonsson, M. (2005). Valuations and multiplier ideals. _J. Amer. Math. Soc._ **18** 655–84.

\[2\]. Lazarsfeld, R. (2004). _Positivity in Algebraic Geometry II_. Springer Berlin Heidelberg, Berlin, Heidelberg.
