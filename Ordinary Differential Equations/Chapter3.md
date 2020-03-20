# 存在和唯一性定理

## Picard 定理

**引理** (Gronwall 不等式)

设 $f,g\in[a,b], g(x)\ge0$，$C$ 是一个常数，已知
$$
f(x)\le C+\int_a^xf(s)g(s)\text ds, x\in[a,b]
$$
则有
$$
f(x)\le Ce^{\int_a^xg(s)\text ds}
$$
**证明**

设
$$
\phi(x)=\int_a^xf(s)g(s)\text ds\Rightarrow \phi'(x)=f(x)g(x)\le\left[C+\int_a^xf(s)g(s)\text ds\right]g(x)=\left[C+\phi(x)\right]g(x)
$$

$$
\Rightarrow \phi'(x)-g(x)\phi(x)\le Cg(x)\Rightarrow \left(\phi(x)e^{-\int_a^xg(s)\text ds}\right)'\le Cg(x)e^{-\int_a^xg(s)\text ds}
$$

两边对 $x$ 积分，得到
$$
\phi(x)e^{-\int_a^xg(s)\text ds}\le\int_a^xCg(s)e^{-\int_a^sg(t)\text dt}\text ds
$$

$$
\Rightarrow\phi(x)\le \int_a^xCg(s)e^{\int_s^xg(t)\text dt}\text ds=-C\int_a^x\text de^{\int_s^xg(t)\text dt}=Ce^{\int_a^xg(s)\text ds}-C
$$

$$
\Rightarrow f(x)\le Ce^{\int_a^xg(s)\text ds}
$$



**Picard 定理**
$$
\frac{\text dy}{\text dx}=f(x,y),\quad (x,y)\in D
$$

其中
$$
D=\left\{(x,y)\Big||x-x_0|\le a, |y-y_0|\le b\right\}
$$
$f$ 关于 $y$ 李氏连续
$$
\left|f(x_1,y_1)-f(x_2,y_2)\right|\le L|y_1-y_2|,\quad \forall(x_1,y_1),(x_2,y_2)\in D,\quad f\in C(D)
$$
则初值问题
$$
y'=f(x,y)\\
y(x_0)=y_0
$$
在 $x\in I=[x_0-h,x_0+h], h=\min\{a,b/M\}, M=\max_D|f|$ 上存在**唯一**解

**证明**

**存在性**

原问题等价于
$$
y(x)=y_0+\int_{x_0}^x f(s,y(s))\text ds
$$
构造 $I=[x_0-h,x_0+h]$ 上连续函数列
$$
y_0(x)=y_0\\
y_{n+1}(x)=y_0+\int_{x_0}^xf(x,y_n(x))\text dx
$$
显然 $y_1\in C^1(I)$，且
$$
|y_1(x)-y_0|=\left|\int_{x_0}^xf(s,y_0(s))\text ds\right|\le M|x_0-x|\le Mh\le b
$$
从而 $(x,y_1(x))_{x\in I}\in D$，进而可以用归纳法证明，上面构造的 Picard 序列 $y_n(x)$ 在 $I$ 上是连续的，并且满足不等式
$$
|y_n(x)-y_0|\le M|x-x_0|
$$
现在证明，这个函数列一致收敛到该积分方程的解

$y_n$ 的收敛性等价于级数
$$
\sum_{n=1}^{\infty}\left[y_{n+1}(x)-y_{n}(x)\right]
$$
的收敛性，现在用数学归纳法证明
$$
\left|y_{n+1}(x)-y_{n}(x)\right|\le\frac{M}{L}\frac{\left(L\left|x-x_{0}\right|\right)^{n+1}}{(n+1) !}
$$
$n=0$ 时成立，假设 $n=k-1$ 时成立，当 $k+1$ 时
$$
\begin{align*}
\left|y_{k+1}(x)-y_k(x)\right|&=\left|\int_{x_0}^x\left[f(s,y_k(s))-f(s,y_{k-1}(s))\right]\text ds\right|\\
&\le L\left|\int_{x_0}^x\left|y_k(s)-y_{k-1}(s)\right|\text ds\right|\\
&\le L\times \frac{M}{L}\int_{x_0}^x\frac{\left(L\left|s-x_{0}\right|\right)^{k}}{k !}\text ds\\
&= \frac{M}{L}\frac{\left(L\left|x-x_{0}\right|\right)^{k+1}}{(k+1) !}\\
\end{align*}
$$

$$
\Rightarrow y_n(x)\le\frac{M}{L}\sum_{k=0}^n\frac{\left(L\left|x-x_{0}\right|\right)^{k+1}}{(k+1) !}\le \frac{M}{L}\sum_{k=0}^n\frac{(Lh)^{k+1}}{(k+1) !}<+\infty
$$

即 Picard 序列一致收敛，设其极限函数为 $\phi$ ，有
$$
\phi(x)=y_0+\int_{x_0}^x\lim_{n\to\infty}f(s,y_n(s))\text ds=y_0+\int_{x_0}^xf(s,\phi(s))\text ds
$$
$\phi(x)$ 就是原积分方程的解，存在性得证

**唯一性**

设 $\phi(x)$ 和 $y(x)$ 是方程的两个解
$$
\phi(x)-y(x)=\int_{x_0}^x\left[f(s,\phi(s))-f(s,y(s))\right]\text ds
$$
令 $h(x)=|\phi(x)-y(x)|\le 0$，则
$$
\begin{align*}
h(x)&\le\left|\int_{x_0}^x\left[f(s,\phi(s))-f(s,y(s))\right]\text ds\right|\\
&\le L\left|\int_{x_0}^x\left|\phi(s)-y(s)\right|\text ds\right|\\
&=L\left|\int_{x_0}^xh(s)\text ds\right|\\
\end{align*}
$$
由 **Gronwall 引理**

对 $x>x_0\Rightarrow C=0, g(s)=L$；对 $x<x_0\Rightarrow C=0, g(s)=-L$；无论如何
$$
h(x)\le 0\Rightarrow h(x)\equiv 0
$$

### 收敛速度

$$
\left|y_0(x)-\phi(x)\right|=\int_{x_0}^xf(s,\phi(s))\text ds\le M|x-x_0|
$$

用归纳法证明
$$
y_{n}(x)-\phi(x) \le \frac{M L^{n}}{(n+1) !}\left| x-x_{0}\right|^{n+1}
$$
$n=0$ 时已经证明，设 $n=m$ 时成立
$$
\begin{align*}
\left|y_{m+1}(x)-\phi(x)\right|
&=\left|\int_{x_0}^x\left[f(s,y_{m}(s))-f(s,\phi(s))\right]\text ds\right|\\
&=L\left|\int_{x_0}^x\left|y_{m}(s)-\phi(s)\right|\text ds\right|
\end{align*}
$$

### 关于李氏连续的讨论

**例**： 不满足李氏连续时的反例
$$
y'=y^{1/3}\\
y(0)=0
$$
此时
$$
y_1\equiv0,\quad y_2(x)=\left\{\begin{array}{ll}0, & x \leq 0 \\ \left(\frac{2}{3} x\right)^{\frac{3}{2}}, & x \geq 0\end{array}\right.
$$
都是解

**定义**：Osgood 条件

存在 $(0,+\infty)$ 上连续函数 $F(r)>0$ 满足
$$
\left|f(x_1,y_2)-f(x_2,y_2)\right|\le F(|y_1-y_2|),\forall y_1\neq y_2
$$
且
$$
\int_{0}^\delta\frac{\text dr}{F(r)}=\infty
$$
若 $F(r)=Lr$，则 $f$ 关于 $y$ 李氏连续

**定理**：$f\in C(D)$，满足 Osgood 条件，则柯西问题对 $D$ 上每一点有唯一解

**证明**：设有两个不同的解 $\phi_1,\phi_2$，且存在 $x_1\neq x_0$，$\phi_1(x)>\phi_2(x)$，不妨设 $x_1>x_0$，记
$$
\bar{x}=\max_{x\in[x_0,x_1]}\left\{x\Big|\phi_1(x)=\phi_2(x)\right\}
$$
则显然有 $x_0\le \bar x<x_1$
$$
r(x)\equiv \phi_1(x)-\phi_2(x)>0,\ \bar x<x\le x_1\\
r(\bar x)=0
$$
因此
$$
r'(x)=f(x,\phi_1(x))-f(x,\phi_2(x))\le F\left(\left|y_{1}(x)-y_{2}(x)\right|\right)=F(r(x))
$$
从而
$$
\frac{\text dr(x)}{F(r(x))}\le \text dx,\ \bar x<x\le x_1
$$
从 $\bar x$ 到 $x_1$ 积分，得到
$$
\int_0^{r_1}\frac{\text dr}{F(r)}\le x_1-\bar x
$$
与该积分发散矛盾

## Peano 存在定理

### Ascoli 引理

**定义** (一致有界)

$\{f_n\}_{n\in N^*}$ 一致有界，若 $\exists M>0,\left|f_n(x)\right|<M,\forall x, n$

**定义** (等度连续)

$\{f_n\}_{n\in N^*}$ 等度连续，若 $\forall \epsilon>0,\exist \delta>0, \left|f_n(x)-f_n(y)\right|<\epsilon,\forall |x-y|<\delta, \forall n$

**引理**

$\{f_n\}_{n\in N^*}$ 是 $I=[a,b]$ 上一致有界，等度连续的函数列，则 $\{f_n\}$ 有一个一致收敛的子列

- **辅助命题 1**：$E$ 是 $I$ 的一个可数子集，$\{f_n\}$ 是 $I$ 上一个一致有界的函数列，则 $\{f_n\}$ 在 $E$ 上有一个收敛的子列

  **证明**

  设 $E=\{x_1, x_2, \cdots\}$，由于 $\{f_n(x_1)\}$ 是一个有界数列，则它有一个收敛的子列，记为 $\{f_{1,1}(x_1), f_{1,2}(x_1), f_{1,3}(x_1), \cdots\}$

  考虑其在 $x_2$ 处的值 $\{f_{1,1}(x_1), f_{1,2}(x_1), f_{1,3}(x_1), \cdots\}$，当然是有界的，从而同样可以选出一个收敛子列

  $\{f_{2,1}(x_2), f_{2,2}(x_2), f_{2,3}(x_2), \cdots\}$

  以此类推，一般地，我们有函数列 $\{f_{k,1}, f_{k,2}, f_{k,3}, \cdots\}$ 在 $x_1,\cdots, x_k$ 处均收敛，从而函数列 $\left\{f_{n,n}(x)\right\}_{n\in N^*}$ 在任意 $x_k$ 处收敛

- **辅助命题 2**：函数列 $\{f_n\}$ 在 $I=[a,b]$ 上等度连续，一致有界，已知存在 $I$ 的一个稠密子集 $E_0$，满足 $\{f_n\}$ 在 $E_0$ 上收敛，则 $\{f_n\}$ 在 $I$ 上一致收敛

  **证明**

  由 Cauchy 收敛原理，只需证 $\forall \epsilon>0, \exist N$，当 $n,m\ge N$ 时有 $\left|f_n(x)-f_m(x)\right|<\epsilon,\forall x\in I$

  由等度连续性，$\exist \delta>0$，使得只要 $x,x'\in I$ 且 $\left|x-x'\right|<\delta$，就有
  $$
  \left|f_n(x)-f_n(x')\right|<\frac\epsilon9,\ \forall n
  $$
  考虑 $B_\delta(x)=\left\{y\in \mathcal R\Big||y-x|<\delta\right\}$，当 $x\in I$ 时是 $I$ 的一个开覆盖，则由有限子覆盖定理，存在有限的子覆盖 $B_\delta(x_j),1\le j\le k_0, I \subset \bigcup_{j=1}^{k_{0}} B_{\delta}\left(x_{j}\right)$

  由于 $E_0$ 稠密，对于 $\forall j$，$\exist y_j\in E_0\bigcap B_\delta(x_j)$，而 $\{f_n\}$ 在 $E_0$ 上收敛，则数列 $\{f_n(y_j)\}$ 收敛，即可以找到 $N$，当 $m,n\ge N$ 时有
  $$
  \left|f_n(y_j)-f_m(y_j)\right|<\frac{\epsilon}{9},\ \forall j,\ 1\le j\le k_0
  $$

  $$
  \Rightarrow \left|f_n(x_j)-f_m(x_j)\right|\le \left|f_n(x_j)-f_n(y_j)\right|+ \left|f_n(y_j)-f_m(y_j)\right|+\left|f_m(y_j)-f_m(x_j)\right|\le\frac\epsilon3
  $$

  对 $\forall x\in I,\exist j, 1\le j\le k_0, x\in B_\delta(x_j)$
  $$
  \Rightarrow \left|f_n(x)-f_m(x)\right|\le \left|f_n(x)-f_n(x_j)\right|+ \left|f_n(x_j)-f_m(x_j)\right|+\left|f_m(x_j)-f_m(x)\right|<\epsilon
  $$
  最终得到 $\{f_n\}$ 在 $I$ 上一致收敛

**证明**

$E_0=Q\bigcap [a,b]$ 是 $I$ 上的一个可数稠密子集，$\{f_n\}$ 在 $I$ 上一致有界，则它有子列 $\{f_{n_k}\}$ 在 $E_0$ 上收敛；又有 $\{f_n\}$ 等度连续，则必有 $\{f_{n_k}\}$ 在 $I$ 上一致收敛

### Peano 存在定理

$$
D=\left\{(x,y)\big||x-x_0|\le a,|y-y_0|\le b\right\},\quad f(x,y)\in C(D)
$$

则初值问题
$$
y'=f(x,y)\\
y(x_0)=y_0
$$
在 $x\in I=[x_0-h,x_0+h], h=\min\{a,b/M\}, M=\max_D|f|$ 上有解 (不一定唯一)

**证明**

只讨论 $[x_0, x_0+h]$ 上的解，构造 Euler 折线：过 $P_k(x_k,y_k)$ 作以 $f(P_k)$ 为斜率的直线，与 $x=x_{k+1}=(k+1)h/n+x_0$ 交于 $P_{k+1}(x_{k+1},y_{k+1})$，即
$$
x_k=x_0+\frac hnk\\
y_k=y_{k-1}+f(x_{k-1},y_{k-1})\frac hn
$$
折线 $\overline{P_0P_1\cdots P_n}$ 称为 Euler 折线，其对应的函数 $y_n(x)$ 为原方程的近似解

一般来说 $y_n(x)$ 并不收敛到原方程的解，但是可以找到一个收敛的子列

首先折线上任意一段的斜率都不超过 $M$，则必有
$$
|y_n(x)-y_n(x')|\le M|x-x'|\le Mh,\ \forall x,x'\in [x_0,x_0+h]
$$
即 $y_n$ 李氏连续，从而有等度连续且一致有界，从而一定可以找到一个一致收敛的子列 $y_{n_k}(x)$

对 $x\in[x_k,x_k+1]$
$$
y_n(x)=y_0+\sum_{s=0}^{k-1}f(x_s,y_s)\frac hn+f(x_k,y_k)(x-x_k)
$$
令
$$
\delta_n(x)=y_n(x)-y_0-\int_{x_0}^xf(t,y_n(t))\text dt,\ x\in [x_0,x_0+h]
$$

$$
\begin{align*}
\left|\delta_n(x)\right|&=\left|\sum_{s=0}^{k-1}f(x_s,y_s)\frac hn+f(x_k,y_k)(x-x_k)-\int_{x_0}^xf(t,y_n(t))\text dt\right|\\
&=\left|\sum_{s=0}^{k-1}\int_{x_s}^{x_{s+1}}\left[f(x_s,y_s)-f(t,y_n(t))\right]\text dt+\int_{x_k}^x\left[f(x_k,y_k)-f(t,y_n(t))\right]\text dt\right|\\
&\le \sum_{s=0}^{k-1}\int_{x_s}^{x_{s+1}}\left|f(x_s,y_s)-f(t,y_n(t))\right|\text dt+\int_{x_k}^x\left|f(x_k,y_k)-f(t,y_n(t))\right|\text dt\\
\end{align*}
$$

$(x_s,y_s)$ 到 $(t,y_n(t))_{t\in[x_s,x_{s+1}]}$ 的距离不大于 $\sqrt{m^2+1}h/n$，从而当 $n$ 充分大时，对于任意的 $t\in[x_s,x_{s+1}]$
$$
\left|f(x_s,y_s)-f(t, y_n(t))\right|<\epsilon,\ \forall \epsilon>0
$$
从而
$$
RHS\le\epsilon (x-x_0)\le \epsilon h
$$
$\delta_n(x)$ 一致收敛到 $0$，$x\in[x_0,x_0+h]$
$$
y_{n_k}(x)=y_0+\int_{x_0}^xf(s,y_{n_k}(s))\text ds+\delta_{n_k}(x)
$$
令 $k\to\infty$
$$
\phi(x)=\lim_{k\to\infty} y_{n_k}(x)=y_0+\int_{x_0}^xf(s,\phi(s))\text ds,\ x\in[x_0,x_0+h]
$$
**例** (隐函数定理)
$$
D=\left\{(x,y)\big||x-x_0|\le a,|y-y_0|\le b\right\},\quad F(x,y)\in C^1(D)
$$
已知 $F_y(x_0,y_0)\neq0,F(x_0,y_0)=0$，则 $\exist y(x)$，在 $(x_0,y_0)$ 附近
$$
F(x,y)=0\Leftrightarrow y=y(x)
$$
**证明**

**存在性**

考虑如下微分方程
$$
y'=-\frac{F_x(x,y)}{F_y(x,y)},\quad y(x_0)=y_0
$$
由 Peano 定理，一定存在一个解 $y=\phi(x)\in C^1$，使得
$$
\phi'(x)=-\frac{F_x(x,\phi(x))}{F_y(x,\phi(x))},\quad \phi(x_0)=y_0
$$
这等价于
$$
\frac{\text d}{\text dx}F(x,\phi(x))\equiv 0\Rightarrow F(x,\phi(x))=F(x_0,\phi(x_0))=0
$$
从而 $\phi(x)$ 就是满足条件的隐函数

**唯一性**

设 $F(x,\psi(x))\equiv 0$
$$
\begin{align*}
0&=F(x,\phi(x))-F(x,\psi(x))\\
&=\int_{\psi(x)}^{\phi(x)}F_y(x, y)\text dy\\
&=\int_{\psi(x)}^{\phi(x)}F_y[x, t\psi(x)+(1-t)\phi(x)]\text d[t\psi(x)+(1-t)\phi(x)]\\
&=(\phi(x)-\psi(x))\int_0^1F_y[x, t\psi(x)+(1-t)\phi(x)]\text dt\\
\end{align*}
$$
由于偏导数非零，只能有
$$
\phi(x)=\psi(x)
$$


