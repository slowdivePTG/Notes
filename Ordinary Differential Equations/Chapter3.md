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
若 $x<x_0$，
$$
h(x)\le-L\int_{x_0}^xh(s)\text ds\le 0
$$
若 $x>x_0$，由于 $h(x)$ 是一维的函数，Gronwall 引理显然成立，即对
$$
f(x)\le C+\int_a^xf(s)g(s)\text ds
$$
其中 $g(x)\ge 0$，有
$$
f(x)\le Ce^{\int_a^xg(s)\text ds}
$$
且这里 $C=0,g(s)=L$，即可直接推出 $h(x)\le 0$

无论如何，都有 $0\ge h(x)\ge 0\Rightarrow h(x)\equiv0$

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
\left|f(x,y_2)-f(x,y_2)\right|\le F(|y_1-y_2|),\forall y_1\neq y_2
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



## 解的延伸

**定理**

$$
\frac{\text dy}{\text dx}=f(x,y),\quad y(x_0)=y_0
$$
其中 $f$ 在区域 $G$ 上连续，$(x_0,y_0)\in G$，则方程任意一条过 $(x_0,y_0)$ 的解曲线都可以延伸到 $G$ 的边界，即对 $G$ 的任意有界闭子区域 $G_1$，解曲线可以延伸到 $G/G_1$ 中

**定义**：(解的存在区间)

称区间 $I$ 为解的存在区间，若存在解 $y(x),y(x_0)=y_0,x\in I$

- 必定是开子区间，否则，设 $I=[x_0,b]$，则 $(b,y(b))\in G$，而 $G$ 为一个区域，则 $(b,y(b))$ 必定有一个邻域属于 $G$；进而由 Peano 定理，$\exist \delta>0$，使得解可以延伸到 $[b,b+\delta)$

**定义**：(最大解区间)

$J=\bigcup I$ (开区间)

- 若 $J^+=J\bigcap [x_0,\infty)=[x_0,\infty)$，由于 $G_1$ 为有界闭区域，则一定存在 $x_1>x_0$，$\{x|x=x_1\}\bigcap G_1=\empty$，设 $y(x)$ 是 $[x_0,x_1]$ 上的解，则
  $$
  (x,y(x))\bigg|_{x\in[x_0,x_1]}\bigcap G/G_1\neq\empty
  $$

- 若 $J^+=[x_0,a)$，设 $(x,y(x))\bigg|_{x\in J^+}$ 是解曲线，且位于 $G_1$ 中，令
  $$
  M=\max_{G_1}|f(x,y)|\Rightarrow |y'(x)|\le M
  $$
  由于 $y$ 为李氏连续，$\lim_{x\to a-} y(x)=b$ 存在
  $$
  y(x)=y_0+\int_{x_0}^xf(s,y(s))\text ds\Rightarrow b=y(a-)=y_0+\int_{x_0}^af(s,y(s))\text ds
  $$
  从而解可以延伸到 $(a,b)$ 处
  
  由 Peano 定理，过 $(a,b)$ 有解，解区间含 $a$ 的邻域，与 $J^+$ 为最大解区间矛盾
  
  

**定义**：(局部李氏）

$G$ 是 $R^2$ 上一个区域，$f\in C(G)$，称 $f$ 关于 $y$ 局部李氏，若 $\forall (x_0,y_0)\in G$，均存在 $a,b>0,L>0$，使得

$$
Q=\left\{(x,y)\bigg | |x-x_0|<a, |y-y_0|<b\right\}<G,\quad |f(x,y_1)-f(x,y_2)|\le L|y_1-y_2|,\quad \forall (x_1, y_2)\in G
$$

**推论**

设 $f\in C(G)$ 关于 $y$ 局部李氏，则方程 $y'=f$ 过 $\forall (x_0,y_0)\in G$ 都存在唯一的解曲线延伸到 $G$ 的边界 ($C^1$ 函数是局部李氏连续的)

**例**

$$
\frac{\text dy}{\text dx}=x^2+y^2,\quad (x,y)\in R^2
$$

由于右端函数是 $C^1(R^2)$ 的，则过平面任意一点 $(x_0,y_0)$ 都有唯一的解曲线，设 $(x,y(x))$ 是解曲线，

$$
y'(x)=x^2+y^2(x)\ge 0\Rightarrow y(x)\uparrow
$$
设 $(a,b)$ 是 $y(x)$ 的最大解区间，则 $(x,y(x))\bigg|_{x\in(a,b)}$ 无界

下面证明 $(a,b)$ 是 $R$ 的一个真子集

$$
y'(x)=x^2+y^2\ge x_0^2+y^2(x), x\ge x_0\Rightarrow \frac{y'(x)}{x_0^2+y^2(x)}\ge 1
$$

$$
\int_{x_0}^x \frac{y'(s)\text ds}{x_0^2+y^2(s)}\ge x-x_0,\quad \forall x\in [x_0,b)
$$

$$
\Rightarrow x-x_0\le\frac{1}{x_0}\arctan\frac{y(s)}{x_0}\Bigg|_{x_0}^x=\frac{1}{x_0}\arctan\frac{y(x)}{x_0}-\frac{\pi}{2x_0}\le\frac{\pi}{2x_0}
$$

从而 $b<+\infty$，同理 $a>-\infty$，这说明解曲线存在垂直渐近线，使得
$$
y(a+)=-\infty,\quad y(b-)=+\infty
$$

**例**

$$
\frac{\text dy}{\text dx}=(x^2+y^2+1)\sin \pi y
$$

由于右端是 $C^1(R)$ 的，则过平面上任意一点存在唯一的解，其中 $y=n\in Z$ 显然是解，那么 $\forall (x_0,y_0)$, 若 $y_0\in Z$，则解为 $y=y_0$，最大解区间为 $R$

若 $y_0\notin Z$，设 $n=[y_0]$，$y(x)$ 是解，由唯一性定理，任意两条解曲线不相交，从而

$$
n<y(x)<n+1,\quad \forall x\in J
$$

此时方程右端是定号的，则 $y(x)$ 单调，$(x,y(x))\bigg|_{x\in J}$ 与 $R^2$ 边界相交，$J=(-\infty,+\infty)$

**定理**：(关于 $y$ 线性增长的函数 $f$)

考虑区间 $D=\left\{(x,y)\bigg|a<x<b, y\in R\right\}$ 上的连续函数 $f(x,y)$，且

$$
|f(x,y)|\le A(x)|y|+B(x),\quad A(x), B(x)\le 0, A(x), B(x)\in C(a,b)
$$

则方程的每一个解的存在区间都为 $(a,b)$  (对于线性微分方程，解的最大存在区间就是定义域)

**证明**

设 $y(x)$ 是过 $(x_0,y_0)$ 的解，其最大解区间是 $(a_0,b_0)$，假设 $b_0<\bar b<b$，设 

$$
A_0=\max_{[x_0,\bar b]}|A(x)|, B_0=\max_{[x_0,\bar b]}|B(x)|,
$$

则 $|f(x,y)|\le A_0|y|+B_0,\quad x\in[x_0,\bar b]$

取 $x_1,x_2$ 满足 $x_0<x_1<b_0<x_2<\bar b$，且 $x_2-x_1<1/4A$，令 $y_1=y(x_1)$，作矩形

$$
R:\quad |x-x_1|\le a_1,\quad |y-y_1|\le b_1
$$

其中 $a_1= x_2-x_1$，$b_1$ 待定，由 Peano 定理，过 $(x_1,y_1)$ 有解 $y(x)$，在 $|x-x_1|\le h_1$ 上存在，其中

$$
M_1=A_0(|y_1|+b_1)+B_0+1,\quad h_1=\min\left\{a_1,\frac{b_1}{M_1}\right\}
$$

取 $b_1$ 充分大，使得 $b_1/M_1>a_1$，则 $h_1=a_1$，解 $y(x)$ 可以延伸到 $x_1+a_1=x_2$ 处，与 $b$ 为最大解区间的右端点矛盾
$$
\Rightarrow b_0=b,\quad a_0=a
$$

**例**

$$
\frac{\text dy}{\text dx}=(y^2-2y-3)e^{(x+y)^2},\quad y(x_0)=y_0
$$

解的最大存在区间为 $(a,b)$，则 $a=-\infty$ 或者 $b=+\infty$

**证明**

$y=-1,3$ 为两个常值解，方程右端是 $C^1$ 的，过任意点的解存在唯一

- 当 $-1<y<3$ 时，$y'$ 恒负，$y$ 单调减，从而 $y=-1,3$ 是方程的两条水平渐近线
- 当 $y>3$ 时，$y$ 单调增，有水平渐近线 $y=3$，$a=-\infty$，可以证明 $y$ 有垂直渐近线，$b<+\infty$
- 当 $y>3$ 时，$y$ 单调增，有水平渐近线 $y=-1$，$b=+\infty$，可以证明 $y$ 有垂直渐近线，$a>-\infty$



## 比较定理

**定理**：(第一比较定理)

设 $f,F\in C(G)$，$G$ 是 $R^2$上区域，$f(x,y)<F(x,y), (x,y)\in G$，而 $y=\phi(x)$ 和 $y=\Phi(x)$ 分别是两个初值问题
$$
y'=f(x,y),\quad y(x_0)=y_0\\
y'=F(x,y),\quad y(x_0)=y_0
$$
在 $(a,b)$ 上的解，则
$$
\left\{
\begin{array}{c}
\phi(x)<\Phi(x),\quad x_0<x<b\\
\phi(x)>\Phi(x),\quad a<x<x_0
\end{array}
\right.
$$
**证明**

只需证明第一个式子，设 $\psi(x)=\Phi(x)-\phi(x)$，则
$$
\psi(x_0)=0,\quad \psi'(x_0)=F(x_0,y_0)-f(x_0,y_0)>0
$$
从而存在 $\sigma>0$，使得当 $x\in(x_0,x_0+\sigma)$时，$\psi(x)>0$；当 $x\in(x_0-\sigma,x_0)$时，$\psi(x)<0$

利用反证法，假设存在 $A=\left\{x\in(x_0,b)|\psi(x)\le 0\right\}$，取其下确界 $x_1>x_0$，有 $\psi(x_1)\le0$，从而
$$
\psi(x)>0,\quad \psi(x_1)\le 0\Rightarrow \psi'(x_1)\le 0
$$
但是 $\psi'(x_1)=F(x_1,y_1)-f(x_1,y_1)>0$，矛盾！

**定义** (最小解和最大解)

由 Peano 定理，当 $f(x,y)$ 在矩形区域 $D$：$|x-x_0|\le a,|y-y_0|\le b$ 上连续时，$y'=f,y(x_0)=y_0$ 在 $|x-x_0|\le h$ 时有解，但不一定唯一，这里
$$
h=\min\left(a,\frac{b}{M}\right),\quad M=\max_{D}|f(x,y)|
$$
若 $y_1(x)$ 满足对任意解 $y(x)$ 都有 $y(x)\ge y(x),x\in[x_0-h,x_0+h]$，则 $y_1$ 为**最小解**，类似可以定义**最大解**

**定理**

初值问题在 $|x-x_0|<\tilde h<h$ 时存在最大最小解

**证明**

考虑初值问题
$$
y'=f_n(x,y)=f(x,y)+\frac1n,\quad y(x_0)=y_0
$$
由 Peano 定理，在 $|x-x_0|\le h_n$ 上该方程有解，其中
$$
h=\min\left(a,\frac{b}{M_n}\right)\to h,\quad M_n=\max_{ D}|f_n(x,y)|\to M
$$
则当 $n$ 充分大时，$h_n>\tilde h$，由比较定理
$$
\phi_n(x)>\phi(x),\quad x\in(x_0,x+\tilde h]\\
\phi_n(x)<\phi(x),\quad x\in[x-\tilde h,x_0)
$$
其中 $\phi(x)$ 是原初值问题的任意一个解

注意到 $|\phi_n(x)-y_0|\le b$，$|\phi'_n(x)|=|f_n(x,\phi(x))|$ 一致有界，从而 $|\phi_n(x)|$ 也一致有界——$\left\{\phi_n(x)\right\}$ 等度连续一致有界，必有一个一致收敛的子列 $\left\{\phi_{n_k}(x)\right\}$ (设其一致收敛到 $\tilde y_2(x)$)，满足
$$
\begin{align*}
\phi_{n_k}(x)&=y_0+\int_{x_0}^xf_{n_k}(s,\phi_{n_k}(s))\text ds\\
&=y_0+\int_{x_0}^xf(s,\phi_{n_k}(s))\text ds+\frac{x-x_0}{n}
\end{align*}
$$
$$
\Rightarrow \tilde y_2=y_0+\int_{x_0}^xf(s,\tilde y_2(s))\text ds,\quad |x-x_0|\le \tilde h
$$
从而 $\tilde y_2$ 是原方程的一个解，且 $\tilde y_2\ge \phi(x),\quad x\in(x_0,x+\tilde h]$，同理，$\tilde y_2\le \phi(x),\quad x\in[x-\tilde h,x_0)$

若考虑
$$
y'=f(x,y)-\frac1n,\quad y(x_0)=y_0
$$
则同样可以得到方程的另一个解 $\tilde y_1$，满足 $\tilde y_1\le \phi(x),\quad x\in(x_0,x+\tilde h]$，$\tilde y_1\ge \phi(x),\quad x\in[x-\tilde h,x_0)$

定义最小解 $y_1$ 和最大解 $y_2$
$$
y_1(x)=
\left\{
\begin{array}{c}
\tilde y_2(x),x\in[x_0-\tilde h, x_0]\\
\tilde y_1(x),x\in[x_0, x_0+\tilde h]
\end{array}
\right.
,\quad 
y_2(x)=
\left\{
\begin{array}{c}
\tilde y_1(x),x\in[x_0-\tilde h, x_0]\\
\tilde y_2(x),x\in[x_0, x_0+\tilde h]
\end{array}
\right.
$$
- 最小解和最大解为局部的概念 (过指定的某一点)
- 如果过某一点，最小解与最大解相等，等价于初值问题的解唯一
- 最大最小解可以延伸到区域 $D$ 的边界

**定理**：(第二比较定理)

设 $f,F\in C(G)$，$G$ 是 $R^2$上区域，$f(x,y)<F(x,y), (x,y)\in G$，而 $y=\phi(x)$ 初值问题
$$
y'=f(x,y),\quad y(x_0)=y_0\\
$$
在 $(a,b)$ 上的**右行最小解**和**左行最大解** (并非任意解)，$y=\Phi(x)$
$$
y'=F(x,y),\quad y(x_0)=y_0
$$
在 $(a,b)$ 上的解，则
$$
\left\{
\begin{array}{c}
\phi(x)\le\Phi(x),\quad x_0<x<b\\
\phi(x)\ge\Phi(x),\quad a<x<x_0
\end{array}
\right.
$$

**证明**

考虑初值问题
$$
y'=f_n(x,y)=f(x,y)-\frac1n<F(x,y),\quad y(x_0)=y_0
$$
设 $\phi_n(x)$ 是其一个解，等同于上面的证明，可以说明 $\left\{\phi_n(x)\right\}$ 有一个子列 $\left\{\phi_{n_k}(x)\right\}$ ，一致收敛到原方程的右行最小解和左行最大解 $\phi(x)$，而由第一比较定理，存在 $\tilde h\in(0,h)$
$$
\phi_{n_k}(x)<\Phi(x),\quad x\in(x_0,x+\tilde h]\\
\phi_{n_k}(x)>\Phi(x),\quad x\in[x-\tilde h,x_0)
$$
取极限之后有
$$
\phi(x)\le \phi(x),\quad x\in(x_0,x+\tilde h]\\
\phi(x)\ge \phi(x),\quad x\in[x-\tilde h,x_0)
$$

**例**
$$
y'=x^2+(y+1)^2,\quad y(0)=0
$$
设 $y(x)$ 右侧最大存在区间为 $(0,\beta)$，求证
$$
\frac{\pi}{4}<\beta<1
$$

**证明**
当 $(x,y)\in G=\left\{(x,y)\in R^2||x|\le 1\right\}$，有
$$
f_1(x,y)=(y+1)^2\le f(x,y)=x^2+(y+1)^2\le 1+(y+1)^2=f_2(x,y)
$$
$$
y'=(y+1)^2,\quad y(0)=0\Rightarrow y_1(x)=\frac1{1-x}-1
$$
$$
y'=1+(y+1)^2,\quad y(0)=0\Rightarrow y_2(x)=\tan\left(x+\frac{\pi}{4}\right)-1
$$

当 $x\in(0,1)\bigcap(0,\beta)$ 时，由第二比较定理，$y(x)\ge y_1(x)$，但是 $y_1(1-)\to+\infty$，一定有 $\beta\le1$

当 $x\in(0,\pi/4)\bigcap(0,\beta)$ 时，由第一比较定理，$y(x)< y_2(x)$，但是 $y_2(\pi/4+)\to+\infty$，一定有 $\beta>\pi/4$

最后证明等号无法取到

显然 $\phi(x)$ 关于 $x$ 递增，考虑其反函数 $x=x(y),y\in(0,+\infty)$ 满足的方程
$$
\frac{\text dx}{\text dy}=\frac{1}{x(y)+(y+1)^2}\Rightarrow \beta=\int_0^{+\infty}  \frac{\text dy}{x(y)+(y+1)^2}
$$
$$
\Rightarrow \frac{\pi}{4}=\int_0^{+\infty} \frac{\text dy}{1+(y+1)^2}<\beta<\int_0^{+\infty}\frac{\text dy}{(y+1)^2}=1
$$