---
permalink: /valtree09/
math: true
---
# 赋值树理论简介 09

> 虽然我们这里叫它 thinness, 但未来我们会叫它 log discrepancy. 就像当初叫小甜甜, 现在叫牛夫人.

## Thinness

> **定义 9.1.** 对任意赋值 \(v\in \mathcal{V}\), 定义它的 **thinness** 为
> 
$$
A(v) := 2 + \int_{v_{\mathfrak{m}}}^{v} m(w)\,\mathrm{d}\alpha(w).
$$

> 即若 \((v_{i})_{0}^{g}\) 为 \(v\) 的逼近序列 (approxmating sequence), 其中 \(v_{g+1} = v\), 则
> 
$$
A(v) := 2 + \sum_{i=1}^{g+1} m_{i}(\alpha_{i} - \alpha_{i-1}),
$$

> 其中 \(\alpha_{i}= \alpha(v_{i})\). 

若 \(v\) 为 infinitely singular 赋值, 即 \(g = \infty\), 上述求和为一个无穷求和, \(A(v)\) 同样定义.

> **命题 9.2.** Thinness 定义了赋值树 \(\mathcal{V}\) 上的一个参数化 \(A : \mathcal{V} \to [2, \infty]\). 进一步地: <br> (i) 若 \(v\) 为 divisorial 赋值, 则 \(A(v)\) 为有理数; <br> (ii) 若 \(v\) 为 irrational 赋值, 则 \(A(v)\) 为无理数; <br> (iii) 若 \(v\) 为 curve 赋值, 则 \(A(v) = \infty\);
> (iv) 若 \(v\) 为 infinitely singular 赋值, 则 \(A(v) \in (2, \infty]\).

**证明.** 由 `定理 7.3` 及 `定义 9.1` 立即可得. Q.E.D.

> **命题 9.3.** Thinness \(A : \mathcal{V} \to [2, \infty]\) 关于 \(\mathcal{V}\) 上弱拓扑是下半连续的, 但不是连续的.

**证明.** 类似于 `命题 8.3` 的证明即可得. Q.E.D.

> **命题 9.4.** 对任意 \(v\in \mathcal{V}\), 有 \(A(v) \ge 1 + \alpha(v)\), 且等号当且仅当 \(m(v)=1\) 时 (即 \(v\) 在某个局部坐标下是 monomial 赋值) 成立.

**证明.** 注意到在逼近序列中所有 \(m_{i} \ge 1\), 因此 \(A(v)\ge 2+\sum (\alpha_{i} - \alpha_{i-1}) = 1+\alpha(v)\). 等号成立当且仅当所有 \(m_{i} = 1\), 此时 \(g=0\), \(m(v) = m_{1} = 1\). Q.E.D.

> **命题 9.5.** 若 \(m(v) > 1\), 则 \(A(v) < m(v)\alpha(v)\).

**证明.** 同样取 \(v\) 的逼近序列 \((v_{i})_{0}^{g}\), 则有
$$
\begin{align*}
A(v) - m(v)\alpha(v) &= 2 + \sum m_{i}(\alpha_{i} - \alpha_{i-1}) - m_{g+1}\Big(\sum(\alpha_{i} - \alpha_{i-1})+1\Big)\\
&\le 1 - (m_{g+1} -1)\alpha_{1} < 0.
\end{align*}
$$
Q.E.D.

> **命题 9.6.** 若 \(v\in \mathcal{V}\) 为 infinitely singular 赋值, 则当 \(w \in [v_{\mathfrak{m}} , v)\) 并且 \(w \to v\) 时, 有 \(A(w) - m(w)\alpha(w) \to - \infty\).

**证明.** 取 \(v\) 的逼近序列 \((v_{i})_{0}^{\infty}\), 由上面 `命题 9.5` 的证明, 我们知当 \(m(w) > 1\) 时有 \(A(w) - m(w)\alpha(w) \le 1 - \big(m(w) - 1\big)\alpha(v_{1})\), 其中当 \(w \to v\) 时, 由 `命题 8.6` 有 \(m(w) \to \infty\), 因此 \(A(w) - m(w)\alpha(w) \to - \infty\). Q.E.D.


## 特征区域

假设 \(v\in \mathcal{V}\) 为一个 quasimonomial 赋值, 记 \(v = v_{\phi,t}\), 其中 \(m(\phi) = m(v)\). 设局部坐标 \((x,y)\) 使得 \(v_{x} \wedge v_{\phi} = v_{\mathfrak{m}}\).

> **定义 9.7.** 对于较小的 \(r > 0\), 定义区域
> 
$$
\Omega(r) := \Big\{(x,y) \in \mathbb{C}^{2} : |x| < 2, \ |\phi(x,y)| < |x|^{t m(\phi)}\Big\},
$$

> 称 \(\Omega(r)\) 为赋值 \(v\) 的 **特征区域 (characteristic region)**.

![Characteristic region]({{ site.baseurl }}/assets/mdnotes/valtree/Char_region.png "Characteristic region")

注意到

$$
\mathrm{Vol}(\Omega_{r}) \sim r^{2A(v)}, \qquad \text{当 } \ r \to 0.
$$

这就是 \(A(v)\) 的名字 thinness 的由来. 由特征区域可以定义赋值在 `多次调和函数 (plurisubharmonic function)` 上的作用, 当然实际上也可以反过来利用多次调和函数在特征区域上的广义 `Kiselman 数` 来刻画赋值. 这些内容将在之后的内容中予以介绍.


## 参考文献

Favre, C. and Jonsson, M. (2004). [The Valuative Tree](http://link.springer.com/10.1007/b100262). vol 1853 Springer Berlin Heidelberg, Berlin, Heidelberg.


