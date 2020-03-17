# 存在和唯一性定理

## Picard 定理

$$
\frac{\text dy}{\text dx}=f(x,y),\quad (x,y)\in D
$$

其中
$$
D=\left\{(x,y)\Big||x-x_0|\le a, |y-y_0|\le b\right\}
$$
$f$ 满足
$$
\left|f(x_1,y_1)-f(x_2,y_2)\right|\le L|y_1-y_2|\\
\forall(x_1,y_1),(x_2,y_2)\in D,\quad f\in C(D)
$$
**Picard 定理**

$f$ 关于 $y$ 李氏连续，则柯西问题
$$
y'=f(x,y)\\
y(x_0)=y_0
$$
在 $x\in I=[x_0-h,x_0+h], h=\min\{a,b/M\}, M=\max_D|f|$ 上存在唯一解

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
&\le\left|\int_{x_0}^x\left|f(s,y_k(s))-f(s,y_{k-1}(s))\right|\text ds\right|\\
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
令 $h(x)=|\phi(x)-y(x)|$，则
$$
\begin{align*}
h(x)&\le\left|\int_{x_0}^x\left[f(s,\phi(s))-f(s,y(s))\right]\text ds\right|\\
&\le L\left|\int_{x_0}^x\left|\phi(s)-y(s)\right|\text ds\right|\\
&=L\left|\int_{x_0}^xh(s)\text ds\right|\\
\end{align*}
$$
由**格朗沃尔引理**，

对 $x>x_0$
$$
h(x)\le L\int_{x_0}^xh(s)\text ds\Rightarrow h(x)\equiv 0
$$
对 $x<x_0$
$$
h(x)\le L\int_{x}^{x_0}h(s)\text ds\Rightarrow h(x)\equiv 0
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