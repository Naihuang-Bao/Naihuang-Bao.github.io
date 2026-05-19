# 赋值树理论简介 01

以下均假设:

- $R=\mathbb{C}[[x,y]]$ 为二元形式幂级数环, $\mathfrak{m} = (x,y)$ 为 $R$ 的唯一极大理想.

- $K$ 为 $R$ 的分式域. $K^* = K \setminus \{0\}$, $R^* = R \setminus \{0\}$.


实际上这里的 $\mathbb{C}$ 也可以换成任意其他特征 $0$ 的代数闭域, 形式幂级数环上的结果基本上也都可以直接搬到多项式环与收敛幂级数环上.

## 赋值

记 $\overline{\mathbb{R}_+} = \mathbb{R}_+ \cup \{\infty\}$.

> 称非常值映射 $v : R \to \overline{\mathbb{R}_+}$ 为一个**赋值**, 如果其满足: <br>
(1) $v(\phi \psi)=v(\phi)+v(\psi)$ 对所有 $\phi, \psi\in R$; <br>
(2) $v(\phi+\psi)\ge \min \{ v(\phi), v(\psi) \}$ 对所有 $\phi,\psi\in R$; <br>
(3) $v(1)=0$.

- $R$ 上的赋值可以唯一地延拓到其分式域 $K$ 上, 并保持满足这三条公理: 定义 $v(\phi/\psi)=v(\phi)-v(\psi)$, 其中 $\psi\neq 0$.

- 易知若 $v(\phi) \neq v(\psi)$, 则 $v(\phi+\psi) = \min \{v(\phi), v(\psi) \}$.

- 集合 $\mathfrak{p} = \{\phi\in R \mid v(\phi)=\infty\}$ 为 $R$ 的一个素理想.

- 称 $v$ 是 `proper` 的, 如果 $\mathfrak{p}\subsetneq \mathfrak{m}$.

- 称 $v$ 是 `centered`, 如果 $v$ 是 proper 的, 并且 $v(\mathfrak{m}):=\min \{v(\phi) \mid \phi\in\mathfrak{m}\}>0$.

- 称 $v$ 是 `normalized` 的, 如果 $v(\mathfrak{m})=1$.

记 $\mathcal{V}$ 为 $R$ 上所有 centered normalized 赋值全体. 注意到:

- $\mathcal{V}$ 上有自然的`(弱)拓扑结构`: 称一列赋值 $v_k \to v$, 如果对于任意 $\phi \in R$, 有 $v_k(\phi) \to v(\phi)$.

- $\mathcal{V}$ 上有自然的`偏序结构`: 称赋值 $v_1\le v_2$, 如果对于任意的 $\phi\in R$, 有 $v_1(\phi) \le v_2(\phi)$.

**我们要介绍的结果是:**

> 赋值空间 $\mathcal{V}$ 具备一个 ***完备的树结构***.

### Abhyankar 不等式

若 $v$ 在 $R^{*}$ 上不取 $\infty$, 则称 $v$ 为 `Krull 赋值`. 此时其赋值环 $R_v := \{0\}\cup\{\phi\in K^* \mid v(\phi) \ge 0\}$ 具有唯一的极大理想 $\mathfrak{m}_v := \{0\} \cup \{\phi \mid v(\phi) > 0\}$. 称 $v(K^*)$ 为 $v$ 的 `赋值群`, 以及 $v(R^*)$ 为 $v$ 的`赋值半群`.

定义:

- $v$ 的`秩 (rank)` $\mathrm{rk}(v)$ 为 $R_v$ 的 Krull 维数;

- $v$ 的 `有理秩 (rational rank)` $\mathrm{rat.rk} (v) := \dim_{\mathbb{Q}} \big( v(K^*) \otimes_{\mathbb{Z}} \mathbb{Q}\big)$.

- $v$ 的 `超越次数 (transcendence degree)` $\mathrm{tr.deg} (v)$ 为剩余域 $\mathbb{C} \hookrightarrow k_v := R_v/\mathfrak{m}_v$ 之间的超越扩张次数.

> **Abhyankar 不等式** $$ \mathrm{rat.rk}(v) + \mathrm{tr.deg}(v) \le \dim R =2.$$

称一个赋值为 `Abhyankar 赋值`, 如果它使上面不等式中的等号成立.

## 例子

最基本的例子是所谓的`重数赋值`:
$$v_{\mathfrak{m}}(\phi) := \max \{k \mid \phi \in \mathfrak{m}^k \}.$$

即 $v_{\mathfrak{m}}(\phi) = m(\phi)$ 为曲线 $\{\phi=0\}$ 在原点处的重数. 或者说 $v_{\mathfrak{m}}(\phi)$ 等于多次调和函数 $\log |\phi|$ 在原点处的 `Lelong 数`. 

### Monomial 赋值

固定局部坐标 $(x,y)$ 以及 $\alpha \ge 1$. 定义赋值 $v_{y,\alpha}$ 满足: $v_{y,\alpha} (x) = 1$, $v_{y,\alpha} (y) = \alpha$, 以及对任意 $\phi = \sum a_{ij} x^i y^j$, 
$$v_{y,\alpha} (\phi) := \min \{ i+\alpha j \mid a_{ij} \neq 0 \}.$$
称这样的赋值 $v_{y,\alpha}$ 为 `monomial 赋值` (在坐标 $(x,y)$ 下).

Monomial 赋值均为 Abhyankar 赋值:

- 若 $\alpha \in \mathbb{Q}$, 则 $\mathrm{rat.rk}(v) = \mathrm{tr.deg}(v) = 1$;

- 若 $\alpha \notin \mathbb{Q}$, 则 $\mathrm{rat.rk}(v) = 2$, $\mathrm{tr.deg}(v) = 0$.

Monomial 赋值可以对应到多次调和函数的 `Kiselman number`:
$$v_{y,\alpha}(\phi) = \lim_{r \to 0^+} \frac{\sup\limits_{|x| < r, \, |y| < r^{\alpha}} \log |\phi|}{\log r}.$$

### Curve 赋值

令 $C$ 为一条通过原点的不可约曲线, 在原点处的重数为 $m(C)$, 定义:
$$v_C (\psi) := \frac{C \cdot \{\psi = 0\}}{m(C)}.$$
这里的相交数为两条曲线在原点处的`局部相交数`: 若 $C$ 由 $\{\phi = 0\}$ 所定义, 则 $C \cdot \{\psi = 0\}= \dim_{\mathbb{C}} R \big/ (\phi, \psi)$. 称赋值 $v_C$ 为 `curve 赋值`. 注意到 $v_C(\phi) = \infty$.

### Divisorial 赋值

考虑一个双有理态射 $\pi : X \to (\mathbb{C}^2 , 0)$. 令 $E$ 为例外除子的某个不可约分支. 则存在一个唯一的正整数 $b = b_E$ 使得
$$v_E(\phi) := b_E^{-1} \mathrm{ord}_E (\pi^{*} \phi)$$
为一个 $R$ 上的 normalized 的 (Krull) 赋值. 这样的赋值称为一个 `divisorial 赋值`.

- 重数赋值 $v_{\mathfrak{m}}$ 是一个特殊的 divisorial 赋值: 考虑 $\pi : X \to (\mathbb{C}^2 , 0)$ 为原点单点的 blow-up, 并取 $E = \pi^{-1}(0)$ 及 $b_E = 1$.

- 对 divisorial 赋值 $v_E$, 有 $\mathrm{rat.rk}(v_E) = \mathrm{tr.deg}(v_E) = 1$.

- 一个 monomial 赋值 $v_{y,\alpha}$ 为 divisorial 赋值当且仅当 $\alpha \in \mathbb{Q}$. 

### Quasimonomial 赋值

考虑一个双有理态射 $\pi : X \to (\mathbb{C}^2 , 0)$, 并令 $E \subset \pi^{-1}(0)$ 为例外除子的某个不可约分支. 选取点 $p \in E$, 以及一个位于 $p$ 的 monomial 赋值 $\mu$. 则
$$v(\phi) := \pi_{*} \mu (\phi)$$
称为一个 `quasimonomial 赋值`.

- Monomial 赋值都是 quasimonomial 赋值.

- 一个 quasimonomial 赋值为 divisorial 赋值当且仅当 $\alpha \in \mathbb{Q}$.

- 若 $\alpha \in \mathbb{Q}$ (此时称该 quasimonomial 赋值为 `rational`), 则 $\mathrm{rat.rk}(v) = \mathrm{tr.deg}(v) = 1$. 若 $\alpha \notin \mathbb{Q}$ (此时称该赋值为 `irrational`), 则 $\mathrm{rat.rk}(v) = 2$, $\mathrm{tr.deg}(v) = 0$.

下面这个结果实际上对任意维数均成立:

> 一个 $R$ 上的 Krull 赋值为 Abhyankar 赋值当且仅当其为一个 quasimonomial 赋值.

### Infinitely singular 赋值

实际上存在不为 Abhyankar 赋值的 $R$ 上的 centered 赋值, 这些赋值被称为 `infinitely singular 赋值`. 我们将在以后给出具体构造.


## 参考文献

Favre, C. and Jonsson, M. (2004). [The Valuative Tree](http://link.springer.com/10.1007/b100262). vol 1853 Springer Berlin Heidelberg, Berlin, Heidelberg.