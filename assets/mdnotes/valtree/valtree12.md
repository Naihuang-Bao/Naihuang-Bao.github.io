---
permalink: /valtree12/
math: true
---
# 赋值树理论简介 12

> "乘子理想" 这个名字是多复变在代数几何里留下的印记之一.

本节中, 我们继续令 \(R = \mathbb{C}[[x,y]]\), 以及记 \(\mathcal{V}\) 为 \(R\) 上所有 normalized centered 赋值全体. 

同时, 我们记 \(\mathcal{V}_{\mathrm{qm}}\) 为 \(\mathcal{V}\) 中所有 quasimonomial 赋值全体. 注意到对任意 \(v\in \mathcal{V}\), 有 \(v\in \mathcal{V}_{\mathrm{qm}}\) 等价于 \(m(v) < \infty\) 且 \(A(v) < \infty\) (后一条件也可换成 \(\alpha(v) < \infty\)).

## 乘子理想

> **定义 12.1.** 对 \(R\) 中理想 \(I\) 以及实数 \(c > 0\), 定义 \(I\) 的关于指数 \(c\) 的 **乘子理想 (multiplier ideal)** \(\mathcal{J}(I^c)\) 为包含满足下述条件的所有 \(\psi \in R\) 全体组成的理想:
> 
$$
\sup_{v\in \mathcal{V}_{\mathrm{qm}}} \frac{v(I)}{A(v) + v(\psi)} < \frac{1}{c}.
$$


回忆对任意 \(R\) 中理想 \(I\) , 其上任意赋值 \(v\) 在 \(I\) 上的取值定义为: \(v(I) := \min\limits_{\phi \in I} v(\phi)\).

我们有时候也将 \(J(I^c)\) 记为 \(\mathcal{J}(c\cdot I)\).

> **定义 12.2.** 对 \(R\) 中理想 \(I\), 定义 \(I\) 的 **对数典范阈值 (lct, log canonical threshold)** 为
> 
$$
\mathrm{lct}(I) := \sup \{ c \ge 0 \mid \mathcal{J}(I^{c}) = R\}.
$$

> 更一般地, 对任意 \(\phi \in R\), 定义理想 \(I\) 关于 \(\phi\) 的 **跳跃数 (jumping number)** 为
> 
$$
\mathrm{lct}^{\phi}(I) := \sup \{c \ge 0 \mid \phi \in \mathcal{J}(I^c)\}.
$$


- 注意到, 若 \(c = \mathrm{lct}^{\phi}(I) > 0\), 则由定义可知 \(\phi \notin \mathcal{J}(I^c)\). 特别地, 我们有 \(\mathcal{J}(\mathrm{lct}(I) \cdot I) \subsetneq R\).

- 由定义可知 
$$
\mathrm{lct}^{\phi}(I) = \inf_{v\in \mathcal{V}_{\mathrm{qm}}} \frac{A(v) + v(\phi)}{v(I)},
$$
 特别地, 
$$
\mathrm{lct}(I) = \inf_{v \in \mathcal{V}_{\mathrm{qm}}} \frac{A(v)}{v(I)}.
$$


- 由于 \(\mathcal{V}_{\mathrm{div}}\)  (全体 divisorial 赋值组成的集合) 在 \(\mathcal{V}_{\mathrm{qm}}\) 中的稠密性, 以及所涉及函数 (在 segment 上的) 的连续性, 可知上述定义和等式中的 \(\mathcal{V}_{\mathrm{qm}}\) 均可替换为 \(\mathcal{V}_{\mathrm{div}}\).

- 由于对任意赋值 \(v\), 有 \(v(I) = v(\overline{I})\), 其中 \(\overline{I}\) 为 \(I\) 的 `整闭包`, 可知乘子理想 \(\mathcal{J}(I^c)\) 均为 `整闭理想`.

- 显然 \(I \subset \overline{I} \subset \mathcal{J}(I)\).


### 分次理想列与次可加理想列

> **定义 12.3.** 称 \(R\) 中的非零理想列 \(I_{\bullet} = (I_{k})_{k \ge 1}\) 为一个 **分次理想列 (graded sequence of ideals)**, 如果
> 
$$
I_{k} I_{l}\subset I_{k+l}, \qquad \forall\, k,l \ge 1.
$$

> 约定 \(I_{0} = R\).

- ***例.*** 设 \(v\) 为 \(R\) 上赋值, 对任意 \(k \in \mathbb{N}\), 令 \(\mathfrak{a}_{k}(v) := \{v \ge k\}\), 则 \(\mathfrak{a}_{\bullet}(v)\) 为 \(R\) 中的一个 graded sequence.

> **命题·定义 12.4.** 若 \(I_{\bullet}\) 为一个 graded sequence of ideals, 则理想列 \(\big( \mathcal{J}(I_{k}^{c/k})\big)_{k \ge 1}\) 中有唯一的一个最大元, 称为 \(I_{\bullet}\) 的关于指数 \(c\) 的 **渐近乘子理想 (asymptotic multiplier ideal)**.

**证明.** 参见 \[[3](#参考文献),  Lemma 11.1.14\]. 注意到对任意 \(k,p \ge 1\) 以及 \(v\in \mathcal{V}\), 有 \(v(I_{pk}) \le v(I_{p})\cdot k\), 因此

$$
\frac{v(I_{p})}{A(v) + v(\psi)} < \frac{p}{c} \implies \frac{v(I_{pk})}{A(v) + v(\psi)} < \frac{pk}{c},
$$

即

$$
\mathcal{J}\left(\frac{c}{p}\cdot I_{p}\right) \subset \mathcal{J}\left(\frac{c}{pk}\cdot I_{pk}\right).
$$

此时由 \(R\) 的诺特性即得最大元的存在唯一性. Q.E.D.

> **定义 12.5.** 定义一个 graded sequence of ideals \(I_{\bullet}\) 的 **log canonical threshold** 为 \(\mathrm{lct}(I_{\bullet}) := \sup\{c \ge 0 \mid \mathcal{J}(I^{c}_{\bullet})= R\}\), 同样定义某个元素 \(\phi \in R\) 关于 \(I_{\bullet}\) 的 **jumping number** 为 \(\mathrm{lct}^{\phi}(I_{\bullet}) := \sup\{c \ge 0 \mid \phi \in \mathcal{J}(I_{\bullet}^c)\}\).

- 注意到, 若 \(I_{\bullet}\) 满足 \(I_{k} := I^{k+k_{0}}\) 对某个理想 \(I\subset R\) 以及 \(k_{0} \in \mathbb{N}\), 则 \(\mathcal{J}(I_{\bullet}^{c}) = \mathcal{J}(I^c)\), 同时 \(\mathrm{lct}(I_{\bullet}) = \mathrm{lct}(I)\), \(\mathrm{lct}^{\phi}(I_{\bullet}) = \mathrm{lct}^{\phi}(I)\).

- 同样我们有

$$
\mathrm{lct}^{\phi}(I_{\bullet}) = \inf_{v\in\mathcal{V}_{\mathrm{qm}}} \frac{A(v) + v(\phi)}{v(I_{\bullet})}, \tag{12.1}
$$
 <br> 其中 \(v(I_{\bullet}) := \lim_{k \to \infty} v(I_{k})/k = \sup_{k} v(I_{k})/k\) (这里是良定的由于 \(v(I_{k+l}) \le v(I_{k}) + v(I_{l})\) 对任意 \(k, l\) 成立).

如果熟知多复变的话, 这里所定义的乘子理想相比于关于某个多次调和函数 \(\Phi\) 的乘子理想 \(\mathcal{J}(\Phi)\), 更类似于关于这个多次调和函数的渐近乘子理想 \(\mathcal{J}_{+}(\Phi) := \bigcup_{p > 1} \mathcal{J}(p \Phi)\), 虽然实际上相当不平凡的 `乘子理想层的强开性定理` (关-周) 告诉我们这两者是一样的.


## 计算跳跃数的赋值

我们将证明在跳跃数的计算公式, 即 (12.1) 式, 中的下确界实际上等价于在整个 \(\mathcal{V}\) 中考虑对应的下确界, 且此时该下确界会被某个 quasimonomial 赋值或者 curve 赋值取到. 我们将会称取到该下确界的赋值为计算该跳跃数的赋值.

> **引理 12.6.** 令 \(\psi \in R\), 以及 \(w\in \mathcal{V}\). 考虑 \(\mathcal{V}_{\mathrm{qm}}\) 上的函数
> 
$$
\chi(v) = \frac{\alpha(w\wedge v)}{A(v) + v(\psi)},
$$

> 则 \(\chi\) 在 \(\mathcal{V}\) 中的每个 segment 上是连续的, 且 \(\chi\) 在 \(\mathcal{V}\) 上 (沿每个 segment) 连续延拓后的上确界在某个 quasimonomial 赋值或者 curve 赋值 \(v_{*}\) 处取到. 特别地, <br> (i) 若 \(\psi\notin \mathfrak{m}\), 则 \(v_{*}\) 可取为具有重数 \(1\) 的赋值; <br> (ii) 若 \(w=v_{\phi}\) 其中 \(\phi\in \mathfrak{m}\) 不可约, 则 \(v_{*}\) 可取为 \(v_{\phi}\) 的逼近序列中的赋值.

**证明.** 参见 \[[1](#参考文献), Lemma 2.11\]. 设 \(v_{\infty}\) 为 \(\mathcal{V}\) 的某个 end, 即 \(v_{0}\) 为一个 curve 赋值或者 infinitely singular 赋值. 考虑 \(\chi\) 在 segment \([v_{\mathfrak{m}}, v_{\infty}]\) 上的取值, 这等价于考虑一个一元实变量函数. 由于 \(\alpha(w\wedge v), v(\psi)\) 以及 \(A(v)\) 在这个 segment 上都是连续的, 因此 \(\chi\) 在其上也是连续的. 由此我们可以将 \(\chi\) 延拓为整个 \(\mathcal{V}\) 上的函数.

注意到, 由 \(\alpha(w \wedge v), v(\psi)\) 关于 \(v\) 的连续性以及 \(A(v)\) 关于 \(v\) 的下半连续性, 知 \(\chi(v)\) 在 \(\mathcal{V}\) 上是上半连续的, 因此 \(\chi\) 在 \(\mathcal{V}\) 上的上确界必定在某个赋值 \(v_{*}\in\mathcal{V}\) 处取到. 我们证明 \(v_{*}\) 必定不为一个 infinitely singular 赋值.

考虑 \(\chi\) 在 segment \([v_{\mathfrak{m}}, v_{\infty}]\) 上的取值, 其中 \(v_{\infty}\) 为某个 infinitely singular 赋值. 令 \(v_{t} \in (v_{\mathfrak{m}} , v_{\infty})\) 满足 \(t = \alpha(v_{t}) \in \big(1, \alpha(v_{\infty})\big)\). 记 \(m(t) := m(v_{t})\), \(A(t) := A(v_{t})\) 以及 \(\chi(t) := \chi(v_{t})\). 则由 thinness 定义可知左导数 \(A'_{-}(t) = m(t)\cdot t\).

(a). 若 \(w \neq v_{\infty}\), 则对于充分接近 \(\alpha(v_{\infty})\) 的 \(t\), 有 \(\alpha(w \wedge v_{t})\) 与 \(v_{t}(\psi)\) 均为常数, 即

$$
\chi'_{-}(t) = - \frac{\alpha(w \wedge v_{\infty})\cdot m(t) \cdot t}{\big(A(t) + v_{t}(\psi)\big)^{2}} < 0.
$$


(b). 若 \(w = v_{\infty}\), 则对于充分接近 \(\alpha(v_{\infty})\) 的 \(t\), 有 \(\alpha (w \wedge v_{t}) = t\) 以及 \(v_{t} = C\) 为某个常数, 从而
	
$$
\chi'_{-}(t) = \frac{A(t) + C - m(t)\cdot t}{\big(A(t) + v_{t}(\psi)\big)^{2}},
$$

回忆当 \(v_{t} \to v_{\infty}\) 时有 \(A(v_{t}) - m(v_{t}) \alpha(v_{t}) \to -\infty\) (`命题 9.6`), 因此当 \(t\) 充分接近 \(\alpha(v_{\infty})\), 总有 \(\chi'_{-}(t) < 0\). 

综上 \(\chi(v)\) 在 \(v\in [v_{\mathfrak{m}}, v_{\infty})\) 充分接近 \(v_{\infty}\) 时总是严格单调递减的, 从而 \(\chi(v)\) 不可能在 \(v_{\infty}\) 处取得其上确界. 故前述 \(v_{*}\) 不可能是一个 infinitely singular 赋值. 因此 \(v_{*}\) 必定为某个 quasimonomial 赋值或者 curve 赋值.

假设 \(\psi \notin \mathfrak{m}\), 即 \(v(\psi) = 0\) 对任意 \(v\in \mathcal{V}\). 考虑任意 \(\widetilde{v}\in \mathcal{V}\) 满足 \(1< m(\widetilde{v}) <\infty\). 取 \(\widetilde{v}\) 的逼近序列中的 \(v_{1}\), 即 \(m(v_{1}) = 1\), 且 \(m(v) > 1\) 对所有 \(v\in (v_{1}, \widetilde{v})\). 类似于上考虑函数 \(\chi(t)\), 此时 \(\chi(t) = \alpha(w\wedge v_{t})/A(t)\), 有
$$
\begin{align*}
\chi'_{-}(t) &= \frac{\alpha'(w\wedge v_{t}) A(t) - \alpha(w\wedge v_{t})m(t)t}{A(t)^{2}}\\
 & \le \frac{A(t) - m(t)t}{A(t)^{2}}< 0,
\end{align*}
$$
其中最后一个不等式是因为当 \(m(v) > 1\) 时有 \(A(v) < m(v)\alpha(v)\) (`命题 9.5`). 因此 \(v_{*} \neq \widetilde{v}\), 即 \(\psi \notin \mathfrak{m}\) 时 \(v_{*}\) 必定位于子树 \(\{v\in\mathcal{V} \mid m(v) = 1\}\) 中.

假设 \(w = v_{\phi}\), 其中 \(\phi \in \mathfrak{m}\) 不可约. 首先证明 \(v_{*}\) 位于 segment \([v_{\mathfrak{m}} , v_{\phi}]\) 中, 否则取 \(v = v_{*} \wedge v_{\phi}\), 有 \(\alpha (v_{\phi} \wedge v_{*}) = \alpha(v_{\phi} \wedge v)\), 以及 \(A(v_{*}) > A(v)\) 和 \(v_{*}(\psi) \ge v(\psi)\), 因此 \(\chi(v_{*}) < \chi(v)\), 矛盾. 其次, 考虑类似于上的函数 \(\chi(t)\), 有

$$
\chi(t) = \frac{t}{A(t) + \min\{C, Mt\}},
$$

其中 \(M= m(\psi)\), \(C=v_{\phi}(\psi)\).  设 \((v_{i})_{0}^{g}\) 为 \(v_{\phi}\) 的逼近序列. 在 \([v_{i}, v_{i+1}]\) 中分别讨论可知 \(\chi(t)\) 的最大值必定可以在每个区间端点处取到. 综上 \(w=v_{\phi}\) 时, \(v_{*}\) 可以取为 \(v_{\phi}\) 的逼近序列中的赋值. Q.E.D.

- ***例.*** 设 \(w = v_{\phi}\) 为关于某个不可约 \(\phi \in \mathfrak{m}\) 的 curve 赋值, 以及 \(\psi = 1\). 则 \(\chi(v) = \alpha(v \wedge v_{\phi})/A(v)\) 的上确界在 \(v_{\phi}\) 的逼近序列 \((v_{i})_{0}^{g}\) 中的 \(v_{1}\) 项取到, 其中 \(m(v_{1}) = 1\). 由此得 
$$
\mathrm{lct}(\phi) = (\sup_{v} \chi(v))^{-1} \cdot m(\phi) = \frac{A(v_{1})}{\alpha(v_{1})}m(\phi) = \left(1 + \frac{1}{\alpha(v_{1})}\right)m(\phi).
$$
 特别地, 下面的不等式成立: 
$$
m(\phi) \le \mathrm{lct}(\phi) \le 2 m(\phi).
$$
 并且, 左边的不等式的等号成立当且仅当 \(v_{1} = v_{\phi}\), 即 \(m(\phi) = 1\); 右边的不等式的等号成立当且仅当 \(v_{1} = v_{\mathfrak{m}}\), 即 \(\alpha(v_{\phi} \wedge v_{\psi}) = 1\) 对任意 \(m(\psi) = 1\), 这等价于 \(\dim_{\mathbb{C}} R/(\phi, \psi) = m(\phi)\) 对所有不可约 \(\psi \in \mathfrak{m} \setminus \mathfrak{m}^2\) 成立. 此外, 容易验证上面的不等式在 \(\phi\) 不必是不可约时也是保持成立的.

> **引理 12.7.** 令 \(v, w \in \mathcal{V}\). 则
> 
$$
\frac{\alpha(v\wedge w)}{\alpha(w)}=\inf_{\phi \in \mathfrak{m} \text{ 不可约}} \frac{v(\phi)}{w(\phi)} = v\big(\mathfrak{a}_{\bullet}(w)\big).
$$


**证明.** 先证第一个等式. 我们需要证明, 对任意 \(\phi \in \mathfrak{m}\) 不可约, 下述不等式成立:

$$
\frac{\alpha( v \wedge w)}{\alpha(w)} \le \frac{v(\phi)}{w(\phi)}=\frac{\alpha(v\wedge v_{\phi})m(\phi)}{\alpha(w\wedge v_{\phi})m(\phi)}=\frac{\alpha(v\wedge v_{\phi})}{\alpha(w\wedge v_{\phi})},
$$

且存在 \(\phi\) 使得两者充分接近. 由于 \(v(\mathfrak{m})=w(\mathfrak{m}) =1\), 我们只需考虑那些 \(\phi\) 满足 \(\alpha(v \wedge v_{\phi}) < \alpha(w \wedge v_{\phi})\), 即 \(w \wedge v_{\phi} > v \wedge w\) 时. 此时均有 \(v \wedge v_{\phi} = v \wedge w\). 若 \(v_{\phi} \ge w\), 则 \(w \wedge v_{\phi} = w\), 欲证不等式取等号; 否则 \(\alpha(w \wedge v_{\phi}) < \alpha(w)\), 此时欲证不等式亦成立, 且当 \(w \wedge v_{\phi}\) 逼近 \(w\) 时, 两者也会充分接近. 综上实际上可以看出该不等式不仅成立, 且欲证的下确界性质也是成立的.

关于第二个等式, 实际上同 \[[2](#参考文献), Lemma 2.4\], 通过基本的带入定义验证可知

$$
v(\mathfrak{a}_{\bullet}(w)) = \inf_{\mathfrak{b} \subset R \text{ 理想}} \frac{v(\mathfrak{b})}{w(\mathfrak{b})}.
$$

而实际上在上面的证明中我们也可以看出下面的等式成立:

$$
\frac{\alpha(v \wedge w)}{\alpha(w)} = \inf_{\psi \in \mathfrak{m}} \frac{v(\psi)}{w(\psi)} = \inf_{\mathfrak{b} \text{ 理想}} \frac{v(\mathfrak{b})}{w(\mathfrak{b})}.
$$

Q.E.D.

> **推论 12.8.** 令 \(\psi \in R\), 以及 \(w \in \mathcal{V}\). 则存在某个 quasimonomial 赋值或者 curve 赋值 \(v\in \mathcal{V}\) 使得 
$$
\mathrm{lct}^{\psi}\big(\mathfrak{a}_{\bullet}(w)\big) = \frac{A(v) + v(\psi)}{v\big(\mathfrak{a}_{\bullet}(w)\big)}.
$$

> 进一步地, 若 \(\psi \notin \mathfrak{m}\), 则 \(v\) 可取为在某个局部坐标下为 monomial 赋值; 若 \(w\) 为 curve 赋值, 则 \(v\) 可取为 \(w\) 的逼近序列中的某个元素.

**证明.** 结合 `引理 12.6, 12.7` 即可得. Q.E.D.

- 如上我们称赋值 \(v\) **计算 (compute)** 跳跃数 \(\mathrm{lct}^{\psi}(\mathfrak{a}_{\bullet}(w))\).

> **引理 12.9.** 令 \(\psi \in R\), 以及 \(I_{\bullet}\) 为 \(R\) 中的一个 graded sequence of ideals. 则存在某个赋值 \(v \in \mathcal{V}\) 计算跳跃数 \(\mathrm{lct}^{\psi}(I_{\bullet})\), 即
$$
\mathrm{lct}^{\psi}(I_{\bullet}) = \frac{A(v) + v(\psi)}{v(I_{\bullet})},
$$
 且此时 \(v\) 亦计算 \(\mathrm{lct}^{\psi}(\mathfrak{a}_{\bullet}(v))\).

**证明.** 参见 \[[2](#参考文献), Theorem 7.3, 7.8\]. 实际上利用 \(\mathcal{V}\) 紧性直接证明应该也并不困难.

> **定理 12.10.** 令 \(\psi \in R\), 以及 \(I_{\bullet}\) 为 \(R\) 中的一个 graded sequence of ideals. 则存在某个 quasimonomial 赋值或 curve 赋值 \(v\in \mathcal{V}\) 计算 \(\mathrm{lct}^{\psi}(I_{\bullet})\).

**证明.** 结合 `推论 12.8, 引理 12.9` 即可. Q.E.D.

进一步地:
- 存在 monomial 赋值计算 \(\mathrm{lct}(I_{\bullet})\);
- 对于任意 \(\phi \in \mathfrak{m}\), 存在 divisorial 赋值或者 curve 赋值计算 \(\mathrm{lct}^{\psi}(\phi)\). 当 \(\phi\) 不可约时可以直接利用 `引理 12.6` 得到, 可约时也可类似于其证明来得到.
 
`定理 12.10` 的高维推广即为著名的 `Jonsson-Mustata 猜想`, 目前只在 \(\psi\notin \mathfrak{m}\) 时由许晨阳所证明. `定理 12.10` 的成立实际上可以推出二维情形的 `乘子理想强开性` 的成立, 这也是 \[[1](#参考文献)\] 中证明类似结果的核心目的之一.

> **练习 12.11.** 对任意 \(v\in \mathcal{V}_{\mathrm{qm}}\) 为 quasimonomial 赋值, 证明存在理想 \(\mathfrak{q}\) 以及 graded sequence \(I_{\bullet}\), 使得 \(v\) 计算 \(\mathrm{lct}^{\mathfrak{q}}(I_{\bullet})\). 进一步地, 证明存在正整数 \(N\), 使得 \(\Big\{w \in \mathcal{V} \mid w\) 计算 \(\mathrm{lct}^{\mathfrak{m}^{N}}\big(\mathfrak{a}_{\bullet}(v)\big) \Big\} = \{v\}\).

---

下一节我们介绍 \[[1](#参考文献)\] 中利用赋值树理论给出 `lct 的 ACC 性质` 的二维情形的另证. 之后或许我们有可能介绍 \[[1](#参考文献)\] 中利用赋值树理论给出任意 \(R\) 中的整闭理想均可实现为某个乘子理想 \(\mathcal{J}(I^{c})\) 的另证 (注意此结论在更高维不再成立).


## 参考文献

[1] Favre, C. and Jonsson, M. (2005). Valuations and multiplier ideals. _J. Amer. Math. Soc._ **18** 655–84.

[2] Jonsson, M. and Mustaţă, M. (2012). Valuations and asymptotic invariants for sequences of ideals. _Ann. inst. Fourier_ **62** 2145–209.

[3] Lazarsfeld, R. (2004). _Positivity in Algebraic Geometry II_. Springer Berlin Heidelberg, Berlin, Heidelberg.