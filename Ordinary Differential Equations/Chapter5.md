# 高阶微分方程

$$
F(x,y,y',\cdots,y^{(n)})=0
$$

**例**：(简谐运动)
$$
\frac{\text d^2x}{\text dt^2}+f(x)=0
$$
方程里没有自变量 $t$ 的函数，被称为**自治**的

- 若 $x(t)$ 是一个解，则 $x(t+C)$ 也是解
- 若 $x_0$ 是 $f$ 的零点，则 $x\equiv x_0$ 也是方程的解

$$
x''x'+f(x)x'=0\Rightarrow\frac{\text d}{\text dt}\left(\frac12x'^2+F(x)\right)=0
$$

其中 $F(x)=\int^x_0f(s)\text ds$
$$
\Rightarrow \frac12x'^2+F(x)=C\Rightarrow x'=\pm\sqrt{2C-2F(x)}
$$

$$
\Rightarrow \frac{\text dx}{\sqrt{2C-2F(x)}}=\pm\text dt
$$

$$
\int \frac{\text dx}{\sqrt{C_1-2F(x)}}=\pm (t+C_2)
$$

一般来说，当 $f(x)$ 是一个二次多项式的时候，方程就已经无法显式解出了，此时，$F(x)$ 为三次多项式，等式左侧是一个椭圆函数

**例**
$$
f(x)=a^2x\Rightarrow F(x)=\frac12a^2x^2
$$
方程的解为
$$
\int\frac{\text dx}{\sqrt{C_1-a^2x^2}}=\pm(t+C_2)=-\frac{1}{a}\arccos\frac{ax}{\sqrt{C_1}}
$$

$$
\Rightarrow x=\frac{\sqrt{C_1}}{a}\cos[a(t+C_2)]
$$

可以重新写为
$$
x=C_1\cos at+C_2\sin at
$$
$C_1,C_2$ 为任意常数，任何非零解都有一个 $2\pi/a$ 的周期

**例**：(单摆方程)
$$
f(x)=a^2\sin x\Rightarrow F(x)=-a^2\cos x
$$
方程的解为
$$
\int\frac{\text dx}{\sqrt{C_1+a^2\cos x}}=\pm(t+C_2)
$$
显然 $x\equiv0$ 是一个解，对于非零解，在 $x=0$ 附近有 $\sin x\approx x$，类似于简谐运动

一般地，我们证明解在 $f(x_0)$ 的零点附近是周期的，令 $y=x'$，设
$$
 H(x,y)=\frac12y^2+F(x)
$$
方程的解为 $H(x(t),x'(t))\equiv C$，这样的 $(x(t),x'(t))$ 是 $H$ 的等高线

若 $f(x_0)=0$，$f'(x_0)>0$，则 $F(x)$ 在 $x_0$ 附近是凸的，进而 $H(x,y)$ 在 $(x_0,0)$ 附近也是凸的，在 $(x_0,0)$ 取到极小值

从而，$H(x,y)=C$ 在 $(x_0,0)$ 附近为一族围绕 $(x,0)$ 的闭曲线

周期为多少呢？考虑 $f'(x_0)=1$，$f(x)=x-x_0+\mathcal{o}(x-x_0)$
$$
\Rightarrow x''+a^2((x-x_0)+\mathcal{o}(1))=0
$$
回到简谐运动方程，周期约为 $2\pi/a$

一般地，设 $x(0)=x_0,x'(0)=x_0'$，当 $|x_0|\ll1$，$x(t)$ 为周期解，设其振幅为 $A$，则存在 $t-1>0$，$x(t_1)=A,x'(t_1)=0$，周期 $T_A$ 满足
$$
\frac{T_A}{4}=\frac{1}{\sqrt{2}a}\int_0^A\frac{\text dx}{\sqrt{\cos x-\cos A}}
$$
因为
$$
H(x,y)=\frac12y^2+a^2(1-\cos x)=a^2(1-\cos A)\Rightarrow y=\sqrt2a\sqrt{\cos x-\cos A}
$$

$$
\Rightarrow\frac{\text dx}{\sqrt2a\sqrt{\cos x-\cos A}}=\text dt
$$

从而
$$
{T_A}=\frac{2\sqrt{2}}{a}\int_0^A\frac{\text dx}{\sqrt{\cos x-\cos A}}=\frac{2\sqrt{2}}{a}\int_0^1\frac{A\text ds}{\sqrt{\cos As-\cos A}}
$$
在 $A\ll1$ 时，
$$
\cos As=1-\frac{A^2s^2}{2}+\mathcal{o}(A^2),\quad \cos As=1-\frac{A^2}{2}+\mathcal{o}(A^2)
$$

$$
T_A\sim\frac{4}{a}\int_0^1\frac{\text ds}{\sqrt{1-s^2}}=\frac{2\pi}{a}
$$

当 $A\to\pi$ 时
$$
T_A\ge\frac{2}{a}\int_0^A\sqrt{\frac{2}{\cos x-1}}\text dx=\frac{2}{a}\int_0^A\frac{\text dx}{\cos {x/2}}\to+\infty
$$
所以当 $A$ 很小时周期近似为常数，当 $A$ 较大时周期与 $A$ 相关，且最终发散

**定理**

对于方程
$$
x''+f(x)=0
$$

$$
f(0)=0,\ xf(x)>0,\ x\neq0\\ y=x',\ F(x)=\int_0^xf(s)\text ds
$$

考虑原点附近围绕原点的一条闭曲线
$$
\Gamma_h:\quad \frac12y^2+F(x)=h
$$
显然 $(x(t),x'(t))\in\Gamma_h$，且
$$
\Gamma_h\bigcap\left\{(x,y)\big|y=0\right\} = \left\{(x_+(h),0),\ (x_-(h),0)\right\}\\
\Gamma_h\bigcap\left\{(x,y)\big|x=0\right\} = \left\{(0,-\sqrt{2h}),\ (0,\sqrt{2h})\right\}
$$
周期 $T_h$ 不依赖于 $h$ 的充要条件是存在 $C_0>0$，使得 $x_+(h)-x_-(h)=C_0\sqrt{h}$

**证明**

1. 证明一个恒等式
   $$
   \frac1{\sqrt{2}}\int_0^H\frac{T_h}{\sqrt{H-h}}\text dh=\pi[x_+(H)-x_-(H)]
   $$
   令 $y=\text dx/\text dt$，则
   $$
   \frac{1}2y^2+F(x)=h\Rightarrow \text dt=\frac{\text dx}{\pm\sqrt{2(h-F(x))}}
   $$

   $$
   \frac{T_h}{2}=\int_{x_-(h)}^{x_+(h)}\frac{\text dx}{\sqrt{2(h-F(x))}}
   $$

   令 $F(x)=s$，则 $f(x)\text dx=\text ds$
   $$
   \int_0^{x_+(h)}\frac{\text dx}{\sqrt{2(h-F(x))}}=\int_0^h\frac{1}{\sqrt{2(h-s)}}\frac{\text ds}{f(x_+(s))}
   $$
   $x_+(s)>0$ 满足 $F(x_+(s))=s,\forall s>0$

   同理
   $$
   \int_{x_-(h)}^0\frac{\text dx}{\sqrt{2(h-F(x))}}=\int_0^h\frac{1}{\sqrt{2(h-s)}}\frac{-\text ds}{f(x_-(s))}
   $$

   $$
   \Rightarrow \frac{T_h}2=\int_0^h\frac1{\sqrt{2(h-s)}}\left(\frac1{f(x_+(s))}-\frac1{f(x_-(s))}\right)\text ds
   $$

   $$
   \begin{align*}
   \Rightarrow\frac12\int_0^H\frac{T_h}{\sqrt{H-h}}\text dh &=\frac1{\sqrt2}\int_0^H\frac{\text dh}{\sqrt{H-h}}\int_0^h\frac1{\sqrt{h-s}}\left(\frac1{f(x_+(s))}-\frac1{f(x_-(s))}\right)\text ds\\
   &=\frac1{\sqrt2}\int_0^H\left(\frac1{f(x_+(s))}-\frac1{f(x_-(s))}\right)\text ds\int_s^h\frac1{\sqrt{(H-h)(h-s)}}\text dh
   \end{align*}
   $$

   

   由于
   $$
   \int_a^b\frac{\text dx}{\sqrt{(b-x)(x-a)}}=\pi
   $$
   有
   $$
   \begin{align*}
   \frac12\int_0^H\frac{T_h}{\sqrt{H-h}}\text dh &=\frac{\pi}{\sqrt2}\int_0^H\left(\frac1{f(x_+(s))}-\frac1{f(x_-(s))}\right)\text ds\\
   &=\frac{\pi}{\sqrt2}\left[\int_0^{x_+(H)}\frac{f(x_+(s))}{f(x_+(s))}\text ds+\int_{x_-(H)}^0\frac{f(x_-(s))}{f(x_-(s))}\text ds\right]\\
   &=\frac{\pi}{\sqrt2}[x_+(H)-x_-(H)]
   \end{align*}
   $$

2. 若 $T_h=T_0$ 与 $h$ 无关，则
   $$
   x_+(H)-x_-(H)=\frac{\sqrt2}{\pi}\cdot T_0\sqrt{H}
   $$

3. 反之，若 $x_+(H)-x_-(H)=C_0H$，则
   $$
   \int_0^H\frac{T_h}{\sqrt{H-h}}\text dh=\sqrt2\pi C_0\sqrt{H},\quad\forall H>0
   $$

   $$
   \int_0^\beta\frac{\text dH}{\sqrt{\beta-H}}\int_0^H\frac{T_h}{\sqrt{H-h}}\text dh=\sqrt2\pi C_0\int_0^\beta\frac{\sqrt{H}}{\sqrt{\beta-H}}\text dH
   $$

   $$
   LHS=\int_0^\beta T_h\text dh\int_h^\beta\frac{\text dH}{\sqrt{(\beta-H)(H-h)}}=\pi\int_0^\beta T_h\text dh
   $$

   $$
   RHS=C_1\beta
   $$

   两边对 $\beta$ 求导
   $$
   \pi T_\beta=C_1
   $$
   说明 $T_\beta$ 为常数

**定义**：(等时系统)

周期与振幅无关的系统称为**等时系统**

**例**
$$
f(x)=a\max\{x,0\}+b\min\{0,x\},\quad a>0,b>0
$$

$$
x_+(h)-x_-(h)=\left(\sqrt{\frac2a}+\sqrt{\frac2b}\right)\sqrt h
$$

**例**
$$
f(x)=\frac{x+1}{4}-\frac{1}{4(1+x)^3}
$$
$f(0)=0,\ xf(x)>0,\ x\neq 0,\ |x|\ll1$
$$
F(x)=\frac{(x+1)^2}{8}+\frac1{8(1+x)^2}-\frac14
$$
由 $F(x)=h$ 可以解出
$$
x_{\pm}(h)=-1+\sqrt{4h+1\pm\sqrt{(4h+1)^2-1}}
$$

$$
\begin{align*}
(x_+(h)-x_-(h))^2&=\left(\sqrt{4h+1+\sqrt{(4h+1)^2-1}}-\sqrt{4h+1-\sqrt{(4h+1)^2-1}}\right)^2\\
&=8h+2-2=8h
\end{align*}
$$

$$
x_+(h)-x_-(h)=2\sqrt2\sqrt h
$$



## $n$ 维线性空间中的微分方程

$n$ 阶线性方程
$$
\frac{\text d^ny}{\text dx^n}=F\left(x,y,y'',\cdots,y^{(n-1)}\right)
$$
令 $y_1=y,\cdots, y_n=y_{n-1}'$，则微分方程可以拆成 $n$ 阶微分方程组；对于多个未知函数的情形，也可以类似地拆成微分方程组；一般地，考虑
$$
y_1'=f_1(x,y_1,y_2,\cdots,y_n)\\
y_2'=f_2(x,y_1,y_2,\cdots,y_n)\\
\cdots\\
y_n'=f_n(x,y_1,y_2,\cdots,y_n)\\
$$
一些定义

- $y$ 是未知函数的向量函数 $y=(y_1\ y_2\ \cdots\ y_n)^T$

  - 求导
    $$
    \frac{\text dy}{\text dx}=\left(\frac{\text dy_1}{\text dx}\ \frac{\text dy_2}{\text dx}\ \cdots \frac{\text dy_n}{\text dx}\right)^T
    $$
    (类似地定义积分)

  - $$
    f(x,y)=\left(f_1(x,y_1,y_2,\cdots,y_n)\quad f_2(x,y_1,y_2,\cdots,y_n)\quad \cdots\quad f_n(x,y_1,y_2,\cdots,y_n)\right)^T
    $$

  - 形式上可以有柯西问题
    $$
    \frac{\text dy}{\text dx}=f(x,y),\quad y(x_0)=y_0
    $$

  - $R_n$ 中的模

    1. 欧式模：$|y|_2=\sqrt{y_1^2+y^2+\cdots+y_n^2}$
    2. $L_1$ 模：$|y|_1=\sum_{i=1}^n|y_i|$
    3. $L_\infty$ 模：$|y|_\infty=\max_{1\le i\le n}\left\{|y_i|\right\}$

    三种模是等价的，可以利用任意一种证明存在唯一性定理，形式与一维的情形完全相同

**从一维到高维**

- **Peano 定理**

  $D:\left\{(x,y)\Big||x-x_0|\le a,|y-y_0|\le b\right\}\subset R\times R^n$，$f(x,y)\subset C(D)$，$M=\max_D|f|$，$h=\min\{a,b/M\}$，则初值问题的解在 $|x-x_0|\le h$ 上存在

- **Picard 定理**

  设 $f$ 满足上述定理的条件，若 $f(x,y)$ 关于 $y$ 是局部李氏的，则上述定理中的解是唯一的

- **解的最大存在区间**

  - 若  $|f(x,y)|\le a(x)|y|+b(x),\ x\in(\alpha,\beta),\ y\in R^n$，其中 $f,a,b$ 均为连续函数，则
    $$
    \frac{\text dy}{\text dx}=f(x,y)
    $$
    解的最大存在区间均为 $(\alpha,\beta)$

    特别地，对线性微分方程组
    $$
    f(x,y)=A(x)y+B(x)\\
    A(x):(\alpha,\beta)\to M_{n\times n},\ B(x):(\alpha,\beta)\to R^n
    $$
    $A(x),B(x)$ 连续，则其解自然可以延伸到 $(\alpha,\beta)$ 上，存在唯一性也可以保证

  

## 解对初值和参数的连续依赖性

以谐振子方程为例，其初值问题的解为
$$
x=x_0\cos a(t-t_0)+\frac{v_0}{a}\sin a(t-t_0)
$$
显然它对参数 $a$ 和初值 $t_0,x_0,v_0$ 是连续可微的

一般的 $n$ 阶微分方程
$$
y'=f(x,y,\lambda),\quad y(x_0)=y_0
$$
其解为 $y=y(x,x_0,y_0,\lambda)$，下面研究其关于 $x_0,y_0,\lambda$ 的依赖性

令 $t=x-x_0,u=y-y_0$，则
$$
u'=f(t+x_0,u+y_0,\lambda)=\tilde f(t,u,x_0,y_0,\lambda),\quad u(0)=0
$$
从而初值可以转换为参数，只需考虑方程的解关于方程参数的依赖性，不妨考虑初值问题
$$
y'=f(x,y,\lambda),\quad y(0)=0
$$

$$
f\in C(G),\ G:|x|\le a,|y|\le b,|\lambda-\lambda_0|\le c
$$

**定理**

$f$ 关于 $y$ 李氏连续，即存在 $L>0$，使得
$$
|f(x,y_1,\lambda)-f(x,y_2,\lambda)|\le L|y_1-y_2|,\quad \forall (x,y_1,\lambda),(x,y_2,\lambda)\in G
$$

$$
M=\max_G|f|,\ h=\min\left\{a,\frac{b}{M}\right\}
$$

则解 $y=\phi(x,\lambda)$ 在 $|x|\le h,|\lambda-\lambda_0|\le c$ 上连续

**证明**

原问题等价于
$$
y(x,\lambda)=\int_0^xf(s,y(s,\lambda),\lambda)\text ds
$$
引入 Picard 序列
$$
\phi_0\equiv0,\quad \phi_k(x,\lambda)=\int_0^xf(s,\phi_{k-1}(s,\lambda),\lambda)\text ds
$$
由定义知 $\phi_k$ 关于 $(x,\lambda)$ 连续，类似于一维的情形，可以归纳证明
$$
|\phi_{k+1}-\phi_k|\le\frac{M(L|x|)^{k+1}}{L(k+1)!}
$$
因此 $\phi_k(x,\lambda)$ 一致收敛，取 $\phi(x,\lambda)=\lim_{k\to\infty}\phi_k(x,\lambda)$，关于 $(x,\lambda)$ 连续，容易证明 $\phi(x,\lambda)$ 就是初值问题的唯一解

**推论**

设 $f$ 在区域 $R: |x-x_0|\le a,\ |y-y_0|\le b$ 上连续，初值问题
$$
y'=f(x,y),\quad y(x_0)=\eta
$$
的解 $y=\phi(x,x_0,y_0)$ 在区域 $Q$ 上是连续的，其中
$$
Q:|x-x_0|\le\frac h2,\quad |\eta-y_0|\le \frac b2
$$
$h$ 的定义与上面的类似

**定理** (放宽李氏连续的条件)
$$
y'=f(x,y,\lambda),\quad y(x_0)=y_0\\
f\in C(G),\ G\subset R\times R^n\times R^k
$$
设对任意的 $(x_0,y_0,\lambda)\in G$，初值问题的解 $y=\phi(x,x_0,y_0,\lambda)$ 存在唯一，则 $\phi$ 关于 $x_0,y_0,\lambda$ 连续

**证明**

令 $z=\lambda$，则 $z'=0$，方程扩充为
$$
y'=f(x,y,z)\\
z'=0\\
y(x_0)=y_0,\quad z(x_0)=\lambda
$$
即参数也可以转化为初值，下面只考虑解对初值的依赖性，假设存在 $\epsilon_0>0$，任取 $\delta_i>0$，都存在 $\xi_i,\eta_i$，当 $x_i$ 属于有界闭区间 $I$ 时，满足
$$
|(\xi_i,\eta_i)-(x_0,y_0)|<\delta_i,\quad |\phi(x_i,\xi_i,\eta_i)-\phi(x_i,x_0,y_0)|\ge\epsilon_0
$$
由于 $I$ 为有界闭区间，$\{x_i\}$ 有收敛子列，不妨设其自身收敛到 $\bar x$，则
$$
\phi(x,\xi,\eta)=\eta+\int_\xi^xf(s,\phi(s,\xi,\eta))\text ds
$$
$f$ 是一致有界的，因此由中值定理，$\phi$ 是李氏连续的，关于 $x$ 一致有界，等度连续，必有一个一致收敛的子列 $\phi(x_{i_j},\xi_{i_j},\eta_{i_j})$，则当 $j\to\infty$ 时，收敛到
$$
\phi(\bar x)=y_0+\int_{x_0}^{\bar x}f(s,\phi(s))\text ds
$$
恰好是方程的解，但是
$$
|\phi(x_{i_j},\xi_{i_j},\eta_{i_j})-\phi(x_{i_j},x_0,y_0)|\ge\epsilon_0
$$
令 $y\to\infty$，任取 $\epsilon>0$，都有
$$
|\phi(\bar x)-\phi(\bar x,x_0,y_0)|<\epsilon
$$
矛盾！

据此，积分曲线可以局部拉直

**定理**：(局部拉直定理)

初值问题在 $(x_0,y_0)$ 邻域内的解可以局部拉直，即积分曲线族可以与一系列平行直线段一一对应

