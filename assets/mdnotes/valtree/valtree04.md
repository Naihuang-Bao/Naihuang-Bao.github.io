---
permalink: /valtree04/
math: true
---
# 定理 3.5 的证明

> 数学归纳法可以是一个直的长条多米诺骨牌, 也可以是曲折来回的螺旋状多米诺骨牌.

本节证明第 03 节的 `定理 3.5`.

回顾记号: $\widetilde{\mathcal{V}}$ 为 $R = \mathbb{C}[[x,y]]$ 上的 centered 赋值全体.

> **定理 3.5.** 令 $[(U_j)_{0}^{k} ; (\tilde{\beta}_{j})_{0}^{k}]$ 为一个长度 $1 \le k < \infty$ 的 SKP. 那么存在唯一的赋值 $v_k \in \widetilde{\mathcal{V}}$ 满足 <br> (Q1) $v_{k}(U_j) = \tilde{\beta}_{j}$ 当 $0 \le j \le k$; <br> (Q2) 对任意满足 (Q1) 的赋值 $v \in \widetilde{\mathcal{V}}$ 有 $v_k \le v$. <br> <br> 进一步地, 如果 $k > 1$, 并且 $v_{k-1}$ 为类似于上述的对应于 $[(U_j)_{0}^{k-1} ; (\tilde{\beta}_{j})_{0}^{k-1}]$ 的赋值. 那么 <br> (Q3) $v_{k-1} \le v_{k}$; <br> (Q4) 对任意 $\phi \in R$, 有 $v_{k-1}(\phi) < v_{k}(\phi)$ 当且仅当在分次环 $\mathrm{gr}_{v_{k}}\mathbb{C}(x)[y]$ 中 $U_{k}$ 整除 $\phi$.

## 赋值的构造

回顾 $v_{k}$ 的具体构造过程.

1. 首先 $v_{1}$ 直接选取为满足 $v_{1}(x) = \tilde{\beta}_{0}$ 及 $v_{1}(y) = \tilde{\beta}_{1}$ 的 monomial 赋值, 即:
$$v_{1}\Big( \sum a_{ij} x^{i} y^{j} \Big) = \min \big\{ i \tilde{\beta}_{0} + j \tilde{\beta}_{1} \mid a_{ij} \neq 0 \big\}.$$

2. 若 $k > 1$, 归纳构造 $v_{k}$. 假设 $v_{1}, \ldots, v_{k-1}$ 已如要求构造出. 考虑任意多项式 $\phi \in \mathbb{C}[x,y]$. 由于 $U_{k}$ 关于 $y$ 首一, 我们可以在 $\mathbb{C}[x][y]$ 中用 $U_{k}$ 除 $\phi$ 得到 $\phi = \phi_{0} + U_{k} \psi$, 其中 $\deg_{y}(\phi_{0}) < d_{k} = \deg_{y} (U_{k})$ 且 $\psi \in \mathbb{C}[x,y]$. 重复这个步骤, 我们最终会得到唯一的一个分解 $$\phi = \sum_{j} \phi_{j} U_{k}^{j},$$ 其中 $\phi_{j} \in \mathbb{C}[x,y]$ 且 $\deg_{y}(\phi_{j}) < d_{k}$. 定义: 
$$v_{k}(\phi) := \min_{j} v_{k}(\phi_{j} U_{k}^j) := \min_{j} \big\{ v_{k-1}(\phi_{j}) + j \tilde{\beta}_{k} \big\}.$$

注意很容易得到有以下基本结果:

- 若 $\deg_{y}(\phi) < d_k$, 则 $v_{k}(\phi) = v_{k-1} (\phi)$;
- $v_k(U_k) = \tilde{\beta}_k$, 且由 SKP 定义可知 $v_k(U_k) = \tilde{\beta}_{k} > n_{k-1} \tilde{\beta}_{k-1} = v_{k-1}(U_k)$;
- $v_k(K^{*}) \subset \sum_{j=0}^{k} \mathbb{Z} \tilde{\beta}_j$.

## 证明思路

对任意 $k \ge 1$, 记以下命题分别为

- $(H_k)$: 如上构造的 $v_k$ 为满足 (Q1)-(Q4) 的赋值.
- $(E_k)$: 分次环 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 为 `欧几里得整环 (Euclidean domain)`.
- $(I_k)$: 多项式 $U_k$ 与 $U_{k+1}$ 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中不可约.
- $(J_k)$: 多项式 $U_j$ 在 $\mathbb{C}[x,y]$ 与 $\mathbb{C}(x)[y]$ 中均不可约对所有 $1 \le j \le k$ 成立.

显然 $H_1$ 与 $J_1$ 是成立的. 定理 3.5 证明的策略是:

1. $J_k \ \& \ H_k \implies E_k$;
2. $J_k \ \& \ H_k \implies I_k$;
3. $E_k \ \& \ I_k \ \& \ H_k \implies H_{k+1}$;
4. $I_k \ \& \ J_k \ \& \ H_{k+1} \implies J_{k+1}$.

## 定理 3.5 的证明

### 1. $J_k \ \& \ H_k \implies E_k$ 

令 $\phi\in R$, 并按照前述考虑展开式 $\phi = \sum_{j} \phi_{j} U_{k}^{j}$. 定义
$$\delta_k(\phi) := \max \Big\{ j \mid v_k(\phi_j U_k^j) = v_k(\phi) \Big\}.$$
并记 $\delta_k(0) = -\infty$.

> **引理 4.1.** $\phi \equiv \phi' \mod v_k \implies \delta_k(\phi) = \delta_k(\phi')$. 即 $\delta_k$ 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 上是良好定义的. <br>

**证明.** 假设 $\delta_k(\phi) = l < l' = \delta_k(\phi')$. 令 $$\psi = \sum_{i > l} \phi_{i} U_k^i, \qquad \psi' = \sum_{i > l'} \phi'_{i} U_k^{i}.$$ 则 $v_k(\psi) > v_k(\phi) = v_k(\phi') < v_k(\psi')$, 但 $\psi \neq \psi'$ (两边关于 $U_k$ 的次数不相等), 这与 $\phi \equiv \phi' \mod v_k$ 矛盾. Q.E.D.

> **引理 4.2.** 对任意 $\phi , \psi \in \mathbb{C}(x)[y]$, 有 $\delta_k(\phi\psi) = \delta_k(\phi) + \delta_k(\psi)$.

**证明.** 首先假设 $\delta_k(\phi) = \delta_k(\psi) = 0$. 即在 $\mathrm{gr}_{v_k}\mathbb{C}(x)[y]$ 中 $\phi = \phi_0, \psi = \psi_0$. 由此不妨假设 $\deg_y(\phi), \deg_y(\psi) < d_k$. 从而 $\deg_y(\phi \psi) < 2 d_k$. 故我们有分解 $$\phi\psi = \alpha_0 + \alpha_1 U_k, \qquad \deg_u(\alpha_0), \deg_y(\alpha_1) < d_k.$$ 假设 $v_k(\alpha_1 U_k) = v_k(\phi \psi)$, 则 $$v_{k-1}(\alpha_1 U_k) < v_{k}(\alpha_1 U_k) \le v_k(\alpha_0) = v_{k-1}(\alpha_0).$$ 从而 $v_{k-1}(\alpha_1 U_k) = v_{k-1} (\phi \psi)$. 但由归纳假设 ($H_k$) 有 $$v_{k-1} (\phi \psi) = v_{k-1}(\phi) + v_{k-1} (\psi) = v_{k}(\phi) + v_{k}(\psi) = v_{k}(\phi \psi),$$ 即 $v_{k-1}(\alpha_1 U_k) = v_k(\alpha_1 U_k)$, 与 (Q4) 矛盾! 从而在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中 $\phi \psi = \alpha_0$, 且 $\delta_k(\phi \psi) = 0$.

对于一般情形, 有 $\phi = \sum \phi_j U_k^j$, $\psi = \sum \psi_j U_k^j$, 从而 $\phi \psi = \sum (\phi_i \psi_j) U_{k}^{i+j}$. 由前述 $\delta_k (\phi_i \psi_j) = 0$ 对所有 $i, j$ 成立可知 $\delta_k(\phi \psi) \le \delta_k(\phi) + \delta_k(\psi)$, 而反向不等式是直接的. Q.E.D.

> **引理 4.3.** 对任意 $\phi \in \mathbb{C}(x)[y]$, 有 $\delta_k(\phi) = 0$ 当且仅当 $\phi$ 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中是单位.

**证明.** 若 $\delta_k(\phi) = 0$, 则在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中 $\phi = \phi_0$. 由归纳假设 ($J_k$), 多项式 $U_k$ 在 $\mathbb{C}(x)[y]$ 中不可约, 因此由 $\deg_{y}(U_k) > \deg_{y} (\phi_0)$ 知 $\phi_0$ 与 $U_k$ 互素. 从而我们可以找到 $A, B \in \mathbb{C}(x)[y]$ 满足 $$A \phi_0 = 1 - B U_k, \qquad \deg_y(A), \deg_y(B) < d_k.$$ 此时根据定义 $v_k(A\phi_0) = v_k(1) < v_k(BU_k)$. 从而在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中 $A \psi_0 = 1$, 即 $\phi_0$ 以及因此 $\phi$ 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中是单位.

反过来, 如果 $\phi$ 为单位, 即在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中 $A \psi_0 = 1$ 对某个 $A \in \mathbb{C}(x)[y]$ 成立, 则由 `引理 4.2` 知 $\delta_k(\phi) + \delta_k(A) = \delta_k(1) = 0$, 从而 $\delta_k(\phi) = 0$. Q.E.D.

> **引理 4.4.** 若 $\phi , \psi \in \mathbb{C}(x)[y]$, 则存在 $Q, R \in \mathbb{C}(x)[y]$ 使得在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中 $\phi = Q \psi + R$ 且 $\delta_k(R) < \delta_k(\psi)$.

**证明.** 记 $\psi = \sum \psi_j U_k^j$. 只需对此引理在如下情形证明: 对所有 $j > M := \delta_k(\psi)$ 有 $\psi_j = 0$. 另外由 `引理 4.3` 可进一步不妨设 $\psi_M = 1$. 此时 $\deg_{y}(\psi) = M d_k$. 在 $\mathbb{C}(x)[y]$ 中关于 $y$ 用除法, 可知存在 $Q, R' \in \mathbb{C}(x)[y]$ 满足 $\deg_{y} (R') < \deg_{y} (\psi)$ 使得 $\phi = Q \psi + R'$. 记 $R' = \sum_{i} R_i U_k^i$, 并令 $N := \delta_k (R')$, 以及 $$R = \sum_{i \le N} R_i U_k^i.$$ 则在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中 $\phi = Q \psi + R$, 且 $$\deg_y (R_N) + N d_k = \deg_{y}(R) < \deg_{y} (\psi) = M d_k.$$ 因此 $N < M$. Q.E.D.

由 `引理 4.4`, 函数 $\delta_k$ 满足所需条件, 使得 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 成为一个欧几里得整环, 这完成了第一步的证明. 特别地, 它是一个 `主理想整环` 以及 `唯一因子分解整环`, 且我们可以在其上使用 `高斯引理 (Gauss' lemma)`.

---

### 2. $J_k \ \& \ H_k \implies I_k$

> **引理 4.5.** 多项式 $U_k$ 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中不可约.

**证明.** 显然 $\delta_k(U_k) = 1$. 因此若 $\phi\psi = U_k$ 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中成立, 则 $\delta_k(\phi) = 0$ 或 $\delta_k(\psi) = 0$, 此时由 `引理 4.3` 知 $\phi$ 或 $\psi$ 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中是单位. Q.E.D.

> **引理 4.6.** 若 $j < k$, 则 $U_j$ 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中为单位.

**证明.** 由 `引理 4.3` 只需证 $\delta_{k}(U_j) = 0$. 若 $d_j < d_k$, 显然. 若 $d_j = d_k$, 则 $U_j = (U_j - U_k) + U_k$, 其中 $\deg_{y}(U_j - U_k) < d_k$. 此时 $v_k(U_j) = \tilde{\beta}_j < \tilde{\beta}_k = v_k(U_k)$ $\implies$ $v_k (U_j - U_k) < v_k(U_k)$, 即 $\delta_k(U_j) = 0$. Q.E.D.

> **引理 4.7.** 若 $\delta_k(\phi) < n_k$, 则在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中 $\phi = \phi_i U_k^i$ 对某个 $i < n_k$ 成立.

**证明.** 反设 $v_k(\phi_i U_k^i) = v_k(\phi_j U_k^i) = v_k(\phi)$ 其中 $i \le j < n_k$. 则 
$$(j-i) \tilde{\beta}_k = v_{k-1}(\phi_i) - v_{k-1} (\phi_j) \in \sum_{j=0}^{k-1} \mathbb{Z} \tilde{\beta}_j.$$
此时由 SKP 定义知 $n_k \mid (j-i)$. 因此 $j = i$. Q.E.D.

> **引理 4.8.** 多项式 $U_{k+1}$ 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中不可约.

**证明.** 我们有 $U_{k+1} = U_k^{n_k} - \tilde{U}_{k+1}$, 其中 $\tilde{U}_{k+1} = \theta_{k} \prod_{j=0}^{k-1} U_{j}^{m_{k,j}}$. 假设在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中有 $U_{k+1} = \phi \psi$, 且 $0< \delta_{k}(\phi), \delta_{k}(\psi) < n_{k}$. 由 `引理 4.7` 可知 $\phi = \phi_i U_{k}^i$, $\psi = \psi_j U_{k}^j$. 则 $U_{k+1} = \phi_i \psi_j U_k^{n_k}$ 从而 $$(1 - \phi_i \psi_j) U_{k}^{n_k} = \tilde{U}_{k+1}.$$ 由于 $U_{k}$ 不可约, 且 $\tilde{U}_{k+1}$ 为单位 (`引理 4.6`), 我们有在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中 $\phi_i \psi_j = 1$. 但由此在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中将有 $\tilde{U}_{k+1} = 0$, 矛盾! 因此我们可以假设 $\delta_{k}(\phi) = n_k$ 且 $\delta_k(\psi) = 0$. 此时 $\psi$ 为单位. Q.E.D.

至此我们完成了第二步的证明.

---

### 3. $E_k \ \& \ I_k \ \& \ H_k \implies H_{k+1}$

我们只需证 $v_{k+1} (\phi \psi) = v_{k+1} (\phi) + v_{k+1} (\psi)$ 对所有 $\phi , \psi \in \mathbb{C}[x,y]$ 成立即可. 回顾:

- 当 $\deg_{y}(\phi) < d_{k+1}$ 时 $v_{k+1}(\phi) = v_{k}(\phi)$;
- $v_{k}(U_{k+1}) < v_{k+1}(U_{k+1})$;
- $v_{k+1}(U_{k+1}\phi) = v_{k+1}(U_{k+1}) + v_{k+1}(\phi)$ 对所有 $\phi \in \mathbb{C}[x,y]$ 成立.

我们下面证明:

> **引理 4.9.** 对所有 $\phi \in \mathbb{C}[x,y]$, 有 $v_{k+1}(\phi) \ge v_{k}(\phi)$.

**证明.** 对 $\deg_{y}(\phi)$ 进行归纳. 若 $\deg_{y}(\phi) < d_{k+1}$, 此时结论成立. 若 $\deg_{y}(\phi) \ge d_{k+1}$, 做分解 $\phi = \sum_{i} \phi_i U_{k+1}^i$. 由归纳假设以及上述性质, 不妨假设 $\phi_0 \not\equiv 0$. 记 $\phi = \phi_0 + \psi$, 其中 $\psi = \sum_{i \ge 1} \phi_i U_{k+1}^i$. 若 $v_{k}(\phi) = \min \{ v_{k}(\phi_0), v_{k}(\psi) \}$, 则由归纳假设
$$v_{k+1} (\phi) = \min \{ v_{k+1}(\phi_0), v_{k+1}(\psi) \} \ge v_{k}(\phi),$$
此时欲证结论成立. 否则, 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中有 $\phi_0 + \psi = 0$, 即在此环中 $U_{k+1}$ 整除 $\phi_0$. 但由于 $\deg_{y}(\phi_0) < d_{k+1}$, 因此 $\delta_{k}(\phi_0) < n_k$. 从而由 `引理 4.7` 有 $\phi_0$ 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中等于不可约多项式 $U_{k}$ 的某个幂次乘以一个单位. 但由 `引理 4.8` 知 $U_{k+1}$ 亦不可约, 矛盾! Q.E.D.

**第三步的证明.** 记
$$\mathfrak{p} := \{v_{k+1} > v_{k} \} \subset \mathrm{gr}_{v_k} \mathbb{C}(x)[y].$$
这是一个真理想: $U_{k+1} \in \mathfrak{p}$. 回忆 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 是一个欧几里得整环且 $U_{k+1}$ 不可约, 知 $\mathfrak{p}$ 由 $U_{k+1}$ 所生成.

对任意 $\phi, \psi \in \mathbb{C}[x,y]$, 我们证明 $v_{k+1} (\phi \psi) = v_{k+1} (\phi) + v_{k+1} (\psi)$. 首先假设 $\phi, \psi \notin \mathfrak{p}$, 则 $\phi \psi \notin \mathfrak{p}$. 由 ($H_k$), $$v_{k+1}(\phi \psi) = v_{k}(\phi \psi) =v_{k}(\phi) + v_{k}(\psi) = v_{k+1}(\phi) + v_{k+1}(\psi).$$
对于一般情形, 我们记: 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中, $\phi = \hat{\phi} U_{k+1}^n$, $\psi = \hat{\psi} U_{k+1}^m$, 其中 $\hat{\phi}, \hat{\psi}$ 与 $U_{k+1}$ 互素, 即 $\hat{\phi}, \hat{\psi} \notin \mathfrak{p}$. 此时
$$\begin{align*}
  v_{k+1}(\phi \psi) & = v_{k+1} (\hat{\phi} \hat{\psi} U_{k+1}^{m+n}) \\
  & = v_{k+1}(\hat{\phi} \hat{\psi}) + (m+n) v_{k+1}(U_{k+1}) \\
  & = v_{k+1}(\phi) + v_{k+1}(\psi).
\end{align*}$$
Q.E.D.

---

### 4. $I_k \ \& \ J_k \ \& \ H_{k+1} \implies J_{k+1}$

> **引理 4.10.** 多项式 $U_{k+1}$ 在 $\mathbb{C}[x,y]$ 及 $\mathbb{C}(x)[y]$ 中不可约.

**证明.** 由于 $U_{k+1}$ 关于 $y$ 首一, 其在 $\mathbb{C}[x,y]$ 中的不可约性可以推出其在 $\mathbb{C}(x)[y]$ 中的不可约性. 下面我们假设 $\phi\phi' = U_{k+1}$ 对 $\phi,\phi' \in \mathbb{C}[x,y]$ 成立. 由于 $U_{k+1}$ 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中不可约, 我们不妨假设 $\phi$ 在 $\mathrm{gr}_{v_k} \mathbb{C}(x)[y]$ 中的像是一个单位, 即 $\delta_{k}(\phi) = 0$ 及 $\delta(\phi') = n_k$. 另一方面, 对任意 $\psi \in \mathbb{C}[x,y]$, 根据定义有 $\delta_{k}(\psi) d_{k} \le \deg_{y}(\psi)$. 由 `引理 3.2` (除了我们需要证明的不可约性部分), 我们得到
$$\begin{align*}
d_k \delta_k (\phi') & = d_k n_k = d_{k+1} = \deg_y(U_{k+1}) \\
& = \deg_y(\phi) + \deg_y(\phi') \ge \deg_y(\phi') \ge d_k \delta_k(\phi'),
\end{align*}$$
因此 $\deg_y(\phi) = 0$ 且 $\deg_y(\phi') = \deg_y (U_{k+1})$. 由 $U_{k+1}$ 关于 $y$ 的首一性, 知 $\phi$ 为 $R$ 中单位. Q.E.D.

实际上此时由 `Weierstrass 分解定理` 我们还可以得出所有 $U_{k}$ 均在 $R = \mathbb{C}[[x,y]]$ 中也是不可约的.

---

至此我们完成了对 `定理 3.5` 的完整证明.

下一次我们考虑给出 `定理 3.7` 的证明, 以及 `定理 3.9` 中的构造思路.


## 参考文献

Favre, C. and Jonsson, M. (2004). [The Valuative Tree](http://link.springer.com/10.1007/b100262). vol 1853 Springer Berlin Heidelberg, Berlin, Heidelberg.
