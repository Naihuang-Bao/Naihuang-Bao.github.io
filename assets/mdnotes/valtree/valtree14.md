---
permalink: /valtree14/
math: true
---
# 赋值树理论简介 14

我们介绍利用 Puiseux 级数建立赋值树相关理论的方法, 但我们不会再仔细地给出所有中间结果的证明.

以下继续令 \(R = \mathbb{C}[[x,y]]\), \(\mathfrak{m}=(x,y)R\) 为 \(R\) 的一个极大理想. 

---

## Puiseux 级数

令 \(k=\mathbb{C}((x))\) 为 \(\mathbb{C}[[x]]\) 的分式域, 即关于变元 \(x\) 的 形式 Laurent 级数 \(\sum\limits_{n \ge -N} c_{n}x^{n}\) 组成的域. 令 \(\widehat{k}\) 为 \(k\) 的代数闭包.

> **定理 14.1.** (Newton-Puiseux 定理) \(\widehat{k}\) 中的元素由 (有限或无限的) **Puiseux 级数**:
> 
$$
\widehat{\phi} = \sum_{j \ge 1} a_{j} x^{\widehat{\beta}_{j}}, \qquad a_{j}\in\mathbb{C}^{*}, \quad \widehat{\beta}_{j+1} > \widehat{\beta}_{j} \in \mathbb{Q} \tag{14.1}
$$

> 构成, 其中有理数 \(\widehat{\beta}_{j}\) 具有有界分母 (denominator), 即存在某个整数 \(m\) 使得 \(m \widehat{\beta}_{j}\in \mathbb{Z}\) 对所有 \(j\) 成立.

**证明.** 记 \(\mathbb{C}((x^{*}))\) 为所有 Puiseux 级数构成的域. 容易验证 \(\mathbb{C}((x^{*})) \subseteq \widehat{k}\), 因此我们只需证明 \(\mathbb{C}((x^{*}))\) 是代数闭的. 下面的证明参考的是 \[1\].

只需证明任意次数 \(n > 1\) 的系数均位于 \(\mathbb{C}((x^{*}))\) 中的首一多项式

$$
P(x,T) = T^{n} + a_{1}(x) T^{n-1} + \cdots + a_{n}(x)
$$

是可约的. 通过做变换 \(T' = T + a_{1}(x)/n\), 我们不妨假设 \(a_{1}(x) \equiv 0\). 对定理叙述中的 \(\widehat{\phi}\) 我们记 \(\mathrm{ord}(\widehat{\phi}) = \widehat{\beta}_{1} \in \mathbb{Q}\). 令 \(r_{l} = \mathrm{ord}\, a_{l}(x)\) 并记 \(r = \min \{r_{l}/l\}\). 由定义, 我们可以取充分大正整数 \(q\) 使得所有的 Puiseux 级数 \(a_{l}(x)\) 可写作形式 \(f_{l}(x^{1/q})\), 其中 \(f_{l}(x) \in k = \mathbb{C}((x))\). 令 \(r=p/q\), 其中 \(p\in\mathbb{Z}\). 

通过坐标变换 \(x=w^{q}\), \(T=U \cdot w^{p}\), 我们得到

$$
P(x,T) = w^{np} \cdot Q(w, U),
$$

其中

$$
Q(w,U)= U^{n} + b_{2}(w) U^{n-2} + \cdots + b_{n}(w)
$$

以及 \(b_{l}(w) = a_{l}(w^{q})w^{-lp}\). 由于 \(\mathrm{ord}\, b_{l} \in \mathbb{Z}\) 以及

$$
\mathrm{ord}\, b_{l} = q \cdot r_{l} - p \cdot l = ql (r_{l}/l - r) \ge 0,
$$

知 \(Q(w,U)\) 为系数在 \(\mathbb{C}[[x]]\) 中的多项式. 进一步地, 对至少某一个 \(l\) 有 \(\mathrm{ord}\, b_{l} = 0\), 即对这样的 \(l\) 有 \(b_{l}(0) \neq 0\). 因此复多项式

$$
Q(0,U)= U^{n}+b_{2}(0)U^{n-2}+\cdots+b_{n}(0) \not\equiv (U-c)^{n}
$$

对任意 \(c\in\mathbb{C}\), 从而 \(Q(0,U)\) 可以写作两个互素复多项式的乘积. 此时利用 `Hensel 引理`, 我们可以将 \(Q(w,U)\) 写作系数在 \(k=\mathbb{C}[[x]]\) 中的多项式的乘积 \(Q_{1}(w,U)\cdot Q_{2}(w,U)\). 综上

$$
P(x,T) = x^{nr} \cdot Q_{1}(x^{1/q}, x^{-r}T) \cdot Q_{2}(x^{1/q}, x^{-r}T),
$$

即得证. Q.E.D.

实际上, `定理 14.1` 有如下著名的推论, 其证明我们不再赘述.

> **定理 14.2.** (Puiseux 定理) 若 \(P(x,T)\in \mathbb{C}((x))[T]\) 为一个关于 \(T\) 的次数为 \(n\) 的首一不可约多项式, 则存在形式幂级数 \(g(x)\in \mathbb{C}((x))\) 使得
> 
$$
P(x^{n}, T) = \prod_{i=0}^{n-1} \big(T - g(\xi_{n}^{i}x)\big),
$$

> 这里 \(\xi_{n}\) 是一个 \(n\) 次本原单位根.

---

## Puiseux 级数与赋值的延拓

现在我们给 \(k=\mathbb{C}((x))\) 及其代数闭包 \(\widehat{k}\) (Puiseux 级数域) 上装备赋值 \(v_{\star}\), 满足 \(v_{\star}|_{\mathbb{C}^{*}}=0\) 以及 \(v_{\star}(x)=1\). 令 \(\overline{k}\) 为 \(\widehat{k}\) 关于赋值 \(v_{\star}\) 的完备化. 事实上, \(\overline{k}\) 中的元素为满足 (14.1) 式的有限或无限级数, 并满足当级数为无限情形时有 \(\widehat{\beta}_{j} \to \infty\), 但是没有 denominator 上的限制.

赋值 \(v_{\star}\) 自然地延拓到如上形式的级数上去: 我们有 \(v(\widehat{\phi})=\widehat{\beta}_{1}\).

定义 

$$
\widehat{k}_{+}=\{\widehat{\phi} \in \widehat{k} \mid v_{\star}(\widehat{\phi}) > 0\},
$$

即满足 \(\widehat{\beta}_{1} > 0\) 的元素. 类似地, 我们定义 \(k_{+}\) 和 \(\overline{k}_{+}\).

固定 \(y\in\mathfrak{m}\) 使得 \((x,y)\) 是 \(\mathbb{C}^{2}\) 中的局部形式坐标, 即 \(v_{x}\wedge v_{y}=v_{\mathfrak{m}}\). 将 \(y\) 视为一个变量, 考虑环 \(\overline{k}[[y]]\): 由具有 Puiseux 级数系数的形式幂级数组成.

我们将考虑那些赋值 \(\widehat{v} : \overline{k}[[y]] \to \overline{\mathbb{R}_{+}}\), 为 \(\overline{k}\) 上的赋值 \(v_{\star}\) 的延拓, 并满足 \(\widehat{v}(y) > 0\). 由于 \(\overline{k}\) 是代数闭域, 实际上这样的赋值完全由其在线性多项式 \(y-\widehat{\psi}\), \(\widehat{\psi}\in\overline{k}\) 上的取值所决定.

> **命题 14.3.** 任意如上的赋值 \(\widehat{v}\) 可以被一个数 \(\widehat{\beta}\in \overline{\mathbb{R}_{+}}\), 以及一个有限或无限的如 (4.1) 式的级数 \(\widehat{\phi}\) (没有 \(\lim \widehat{\beta}_{j}\) 的限制) 并满足 \(\widehat{\beta} > \widehat{\beta}_{j} > 0\) 对所有 \(j\) 且 \(\widehat{\beta}=\lim \widehat{\beta}_{j}\) 如果级数是无限的, 所唯一表示. 精确地说, 我们有
> 
$$
\widehat{v}(y-\widehat{\psi})=\min \{\widehat{\beta} , v_{\star}(\widehat{\psi}-\widehat{\phi})\}, \qquad \forall\, \widehat{\psi}\in \overline{k}. \tag{14.2}
$$

> 反过来, 如果 \(\widehat{\phi}\) 及 \(\widehat{\beta}\) 满足如上这些条件, 则存在唯一的 \(\overline{k}[[y]]\) 上的一个赋值 \(\widehat{v}\), 满足 (14.2) 式且是 \(v_{\star}\) 的延拓.

我们不再证明这个结论. 实际上可以用 SKP 与 \(\mathbb{C}[[x,y]]\) 上的一一对应来给出证明. 由 Puiseux 级数和赋值的对应也可以给出赋值的分类.

> **定义 14.4.** 我们记 \(\mathrm{val}[\widehat{\phi}; \widehat{\beta}]\) 为命题 14.3 中由 \((\widehat{\phi}, \widehat{\beta})\) 所唯一决定的赋值 \(\widehat{v}: \overline{k}[[y]] \to \overline{\mathbb{R}_{+}}\). 进一步地, 我们称 \(\widehat{v}\) 是 <br> (i) **点型 (point type)** 如果 \(\widehat{\phi}\in\overline{k}\) 且 \(\widehat{\beta}=\infty\); 此时我们记 \(\widehat{v}=\widehat{v}_{\widehat{\phi}}\); <br> (ii) **有限型 (finite type)** 如果 \(\widehat{\phi}\in\widehat{k}\) 且 \(\widehat{\beta} < \infty\); <br> (iii) **有理的 (rational)** 如果 \(\widehat{v}\) 是有限型并且 \(\widehat{\beta}\) 是有理数; <br> (iv) **无理的 (irrational)** 如果 \(\widehat{v}\) 是有限型并且 \(\widehat{\beta}\) 是无理数; <br> (v) **特殊型 (special type)** 如果 \(\widehat{\phi}\notin \overline{k}\).

- 如果 \(\widehat{v}=\mathrm{val}[\widehat{\phi};\widehat{\beta}]\) 是 point type 或者 special type, 可以证明

$$
\widehat{v}(y-\widehat{\psi})=v_{\star}(\widehat{\psi}-\widehat{\phi}), \qquad \forall\,\widehat{\psi}\in\overline{k}.
$$


---

## 树结构与 Puiseux 参数化

令 \(\widehat{\mathcal{V}}_{x}\) 为那些在 \(\overline{k}\) 上是 \(v_{\star}\) 的延拓并满足 \(\widehat{v}(y) > 0\) 的赋值 \(\widehat{v} : \overline{k}[[y]] \to \overline{\mathbb{R}_{+}}\) 全体组成的集合. 我们在 \(\widehat{\mathcal{V}}_{x}\) 中加入赋值 \(\widehat{v}_{\star}\), 它由如下条件所定义: \(\widehat{v}_{\star}(y-\widehat{\phi})=0\) 对所有满足 \(v_{\star}(\widehat{\phi}) \ge 0\) 的 \(\widehat{\phi}\in \overline{k}\) 成立.

\(\widehat{\mathcal{V}}_{x}\) 上有自然的偏序结构: \(\widehat{v} \le \widehat{w}\) 当且仅当其作为 \(\overline{k}[y]\) 上的函数逐点有相应大小关系. 实际上, \(\widehat{v} \le \widehat{w}\) 当且仅当

$$
\widehat{v}(y-\widehat{\psi}) \le \widehat{w}(y-\widehat{\psi}), \qquad \forall\, \widehat{\psi}\in \overline{k}_{+}.
$$


> **命题 14.5.** 如上偏序 \(\le\) 给出 \(\widehat{\mathcal{V}}_{x}\) 上的一个完备 nonmetric tree structure, 其中 root 为 \(\widehat{v}_{\star}\). 其 ends 是 point type 和 special type 的赋值, 分支点是 rational 赋值, 正则点是 irrational 赋值.

若 \(\widehat{v}\in\widehat{\mathcal{V}}_{x}\), 定义 \(\widehat{v}\) 的 **Puiseux 参数 (Puiseux parameter)** 为

$$
\widehat{\beta}(\widehat{v}) := \sup \big\{\widehat{v}(y-\widehat{\psi}) \mid \widehat{\psi}\in \overline{k}\big\}.
$$


> **命题 14.6.** 上述 Puiseux 参数定义了树 \(\widehat{\mathcal{V}}_{x}\) 的一个参数化 \(\widehat{\beta} : \widehat{\mathcal{V}}_{x} \to [0, +\infty]\). 进一步地, <br> (i) 若 \(\widehat{v}\) 为 rational, 则 \(\widehat{\beta}(\widehat{v})\) 为有理数; <br> (ii) 若 \(\widehat{v}\) 为 irrational, 则 \(\widehat{\beta}(\widehat{v})\) 为无理数; <br> (iii) 若 \(\widehat{v}\) 为 point type, 则 \(\widehat{\beta}(\widehat{v})=\infty\); <br> (iv) 若 \(\widehat{v}\) 为 special type, 则 \(\widehat{\beta}(\widehat{v})\in (0,\infty]\).

- 若 \(\widehat{v}=\mathrm{val}[\widehat{\phi};\widehat{\beta}]\), 则实际上 \(\widehat{v}\) 正是 segment \([\widehat{v}_{\star}, \widehat{v}_{\widehat{\phi}}]\) 上满足 \(\widehat{\beta}(\widehat{v})=\widehat{\beta}\) 的那个点对应的赋值.

---

## Galois 作用

令 \(G := \mathrm{Gal}(\widehat{k}/k)\). 群 \(G\) 作用在 \(\widehat{k}\) 上, 对偶地可作用在 \(\widehat{\mathcal{V}}_{x}\) 中的赋值上.

### Galois 群

实际上, \(\mathrm{Gal}(\widehat{k}/k)\) 是一个投射极限 (即逆向极限): 

- 对任意 \(m\ge 1\), 令 \(k_{m}=\mathbb{C}((x^{1/m}))\). 映射 \(x^{1/m} \mapsto (x^{1/mn})^{n}\in k_{mn}\) 定义了一个域扩张 \(k_{m} \to k_{mn}\), 由此 \(k_{m}\) 形成一个内射系统, 其内射极限 (正向极限) 为 \(\widehat{k}\); 

- 每个 Galois 群 \(G_{m}=\mathrm{Gal}(k_{m}/k)\) 同构于 \(\{\omega\in\mathbb{C} : \omega^{m} = 1\}\); 

- 元素 \(\omega\in G_{m}\) 在 \(k_{m}=\mathbb{C}((x^{1/m}))\) 上的作用记为 \(\omega^{*}\), 满足 \(\omega^{*}(x^{1/m})=\omega x^{1/m}\);

- 相应地, \(\omega \mapsto \omega^{n}\) 给出从 \(G_{mn}\) 到 \(G_{m}\) 的群同态;

- 由此, 群 \(G_{m}\) 形成一个投射系统, 其投射极限为 Galois 群 \(G=\mathrm{Gal}(\widehat{k}/k)\).

若 \(\omega\in G\), 记 \(\omega_{m}\) 为其在 \(G_{m}\) 中的像. 则对任意单项式 \(x^{\beta}\in \widehat{k}\), 我们有 \(\omega\) 在 \(x^{\beta}\) 上的作用为: 记 \(\beta=p/q\), 其中 \(\mathrm{gcd}(p,q)=1\), 再取 \(m\) 使得 \(q \mid m\), 记 \(m=qr\). 则

$$
\omega^{*}(x^{\beta}) = \omega_{m}^{pr}x^{\beta}.
$$

可以验证其与 \(m\) 的选取无关. 进一步地, 由此可以给出 \(G\) 在 \(\overline{k}\) 上的自然作用.

显然有:

- \(v_{\star}(\omega^{*}\widehat{\phi})=v_{\star}(\widehat{\phi})\) 以及 \(m(\omega^{*}\widehat{\phi})=m(\widehat{\phi})\) 对任意 \(\widehat{\phi}\in \overline{k}\) 成立;

- 若 \(m(\widehat{\phi})=1\), 即 \(\widehat{\phi}\in k\), 则 \(\omega^{*}\widehat{\phi}=\widehat{\phi}\).

将上述 Galois 群作用延拓到 \(\overline{k}[y]\) 上: 令 \(\omega^{*}y=y\), 对任意 \(\omega\in G\).

则 对任意 \(\omega\), 有 \(\omega^{*}\) 在 \(k[[y]]\supset R\) 上的限制是恒等作用.

### 在 \(\widehat{\mathcal{V}}_{x}\) 上的作用












## 参考文献

[1] Nowak, K. J. (2000). Some elementary proofs of Puiseux’s theorems. _Univ. Iagel. Acta Math._ 279–82.

[2] Favre, C. and Jonsson, M. (2004). [The Valuative Tree](http://link.springer.com/10.1007/b100262). vol 1853 Springer Berlin Heidelberg, Berlin, Heidelberg.