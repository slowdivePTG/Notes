# 初等积分法

## 恰当方程

从形式上，对于**一阶常微分方程**，我们希望找到连续函数 $P$ 和 $Q$
$$
\frac{\text{d}y}{\text{d}x}=f(x,y)\Leftrightarrow P\text{d}x+Q\text{d}y=0
$$
**定义**——恰当方程

若存在连续函数 $\phi(x,y)$ 满足
$$
\text{d}\phi=P\text{d}x+Q\text{d}y
$$
则称 $P\text{d}x+Q\text{d}y$ 为恰当的，此时
$$
\text{d}\phi=0\Leftrightarrow \phi=C
$$

- **定理**：由 $\phi=C$ 确定的函数 $y=u(x)$ 或 $x=u(y)$ 满足原方程

- **证明**：设 $\phi=C$ 确定 $y=u(x)$
  $$
  \Leftrightarrow \forall x,\ \phi(x,u(x))=C\\
  \Leftrightarrow\phi'_x(x,u(x))+\phi'_y(x,u(x))\cdot u'(x)=0\\
  \Leftrightarrow u'(x)=-\frac{\phi'_x(x,u(x))}{\phi'_y(x,u(x))}=-\frac{P(x,u(x))}{Q(x,u(x))}\\
  $$
  从而 $y=u(x)$ 是方程 $P\text{d}x+Q\text{d}y=0$ 的解

  反之，若 $y=u(x)$ 是原方程的解，也一定有 $\phi(x,u(x))=C$

- **例**：
  $$
  y\text{d}x+x\text{d}y=0=\text{d}(xy)\Rightarrow xy=C
  $$

进而有一系列问题

1. **如何判断 $P\text{d}x+Q\text{d}y=0$ 为恰当的**

   $P\text{d}x+Q\text{d}y=0$ 恰当 $\Leftrightarrow$ $\exists$ 连续函数 $\phi$，$\phi'_x=P,\ \phi'_y=Q$

   一般情况很难判断，但如果我们有更强的条件，我们就可以有以下定理

   **定理**：$P,Q\in C^1(D)$，$D\subset R^2$ 是单连通区域，则 $P\text{d}x+Q\text{d}y=0$ 恰当等价于
   $$
   \frac{\partial P}{\partial y}=\frac{\partial Q}{\partial x},\ (x,y)\in D
   $$
   **证明**：

   - 充分性：设 $P\text{d}x+Q\text{d}y=0$ 恰当，则 $\exists$ 连续函数 $\phi$，$\phi'_x=P,\ \phi'_y=Q,\ (x,y)\in D$，由于 $\phi\in C^2(D)$
     $$
     \Rightarrow \frac{\partial P}{\partial y)}=\frac{\partial^2\phi}{\partial y\partial x}=\frac{\partial^2\phi}{\partial x\partial y}=\frac{\partial Q}{\partial x)}
     $$

   - 必要性：设我们已经有 ${\partial P}/{\partial y}={\partial Q}/{\partial x},\ (x,y)\in D$，取定 $p_0(x_0,y_0)\in D$，则 $\forall p(x,y)\in D$，可以定义与路径无关的积分
     $$
     \phi(x,y)=\int_{p_0}^p P\text{d}x+Q\text{d}y
     $$
     它显然满足 $\text{d}\phi=P\text{d}x+Q\text{d}y$

     具体地，该积分可以构造在一个与坐标轴平行的矩形区域上，即
     $$
     \phi(x, y)=\int_{x_{0}}^{x} P(x, y) \mathrm{d} x+\int_{y_{0}}^{y} Q\left(x_{0}, y\right) \mathrm{d} y
     $$
     或
     $$
     \tilde{\Phi}(x, y)=\int_{x_{0}}^{x} P\left(x, y_{0}\right) \mathrm{d} x+\int_{y_{0}}^{y} Q(x, y) \mathrm{d} y
     $$
     取决于先对 $x$ 或 $y$ 积分

2. 如果是恰当的，如何求 $\phi$

   **例**：
   $$
   (ye^x+2e^x+y^2)\text{d}x+(e^x+2xy)\text{d}y
   $$
   $\partial P/\partial y=e^x+2y=\partial Q/\partial x$，从而原方程是恰当的

   构造 $\phi(x,y)=ye^x+2e^x+y^2x+f(y)$
   $$
   e^x+2xy=Q=\frac{\partial \phi}{\partial y}=e^x+2xy+f'(y)\Rightarrow f(y)=C
   $$
   则不妨直接另 $f(y)\equiv0$

3. 如果不是恰当的，如何求 $\phi$ 

## 分离变量法

**定义**：称 $P\text{d}x+Q\text{d}y=0$ 为分离变量型，若
$$
P=P_1(x)P_2(y),\quad Q=Q_1(x)Q_2(y)
$$
一般这样的方程不是恰当的，但是若 $Q_1(x)P_2(y)\neq0$，我们有
$$
\frac{P_1(x)}{Q_1(x)}\text{d}x+\frac{Q_2(y)}{P_2(y)}\text{d}y=0
$$
显然是恰当的，因 $\phi$ 的二阶偏导数为零，通积分为
$$
\int\frac{P_1(x)}{Q_1(x)}\text{d}x+\int\frac{Q_2(y)}{P_2(y)}\text{d}y=C
$$
若 $Q_1(x_i)=P_2(y_j)=0$，则 $x\equiv x_i,\ y\equiv y_j$ 都是解

**例**：
$$
x\frac{\text{d}y}{\text{d}x}=\sqrt{1-y^2}\Rightarrow\frac{\text{d}x}{x}-\frac{{\text{d}y}}{\sqrt{1-y^2}}=0, x\neq0,\ y\neq\pm1
$$
此时的解为
$$
\ln|x|-\arcsin y=C\Rightarrow x=Ce^{\arcsin y}
$$
$x\equiv0$ 和 $y\equiv\pm1$ 也是解

**例**：
$$
y'=\frac{3}{2}y^{1/3}
$$
若 $y\neq0$，极易解得
$$
y^{2/3}=x+C\quad (x+C\ge0)
$$
为此得到通积分
$$
y^2=(x+C)^3,\ x\ge-C
$$
外加特解 $y=0$

此时在平面上几乎所有点 $P_0$，在局部有且仅有一条积分曲线（**局部唯一**），而例外是 $y=0$，在其上每一点的局部范围内都有无穷多条积分曲线（**局部不唯一**）

**例**——跟踪问题：设某 $A$ 从原点出发，沿 $x$ 轴正向前进，同时 $B$ 从 $(0,b)$ 开始跟踪，且与 $A$ 保持等距 $b$，求 $B$ 的光滑运动轨迹
$$
\frac{\text{d}y}{\text{d}x}=\frac{y}{x-x_A}
$$
其中
$$
(x_A-x)^2+y^2=b^2
$$
因此
$$
\frac{\text{d}y}{\text{d}x}=\frac{y}{x-x_A}=-\frac{y}{\sqrt{b^2-y^2}}
$$
因为
$$
\int\frac{\sqrt{b^2-y^2}}{y}\text{d}y=-b\ln\left|\frac{b-\sqrt{b^2-y^2}}{y}\right|+\sqrt{b^2-y^2}+C
$$
最终得到
$$
x-b\ln\left|\frac{b-\sqrt{b^2-y^2}}{y}\right|+\sqrt{b^2-y^2}=C
$$
**例**：
$$
\frac{\text{d}y}{\text{d}x}=\frac{x+y}{x-y}
$$
令 $y=ux$，则
$$
\frac{\text{d}y}{\text{d}x}=u+x\frac{\text{d}u}{\text{d}x}=\frac{1+u}{1-u}\Rightarrow \frac{1-u}{1+u^2}\text{d}u=\frac{\text dx}{x}
$$

$$
\arctan u-\ln\sqrt{1+u^2}=\ln|x|-C\Rightarrow\arctan\left(\frac{y}{x}\right)=\ln\sqrt{x^2+y^2}-C
$$

若采用极坐标，解即为 $r=Ce^\theta$，事实上方程化为
$$
\frac{\text{d}(r\sin\theta)}{\text{d}(r\cos\theta)}=\frac{\cos\theta+\sin\theta}{\cos\theta-\sin\theta}\Rightarrow r\text{d}\theta=\text{d}r
$$

## 一阶线性微分方程

$$
\frac{\text dy}{\text dx}+p(x)y=q(x),\quad p(x),q(x)\in C(a,b)
$$

- $q(x)\equiv0,y\neq0$ 时
  $$
  \frac{\text dy}{\text dx}+p(x)y=0\Rightarrow\frac{\text dy}{y}+p(x)\text dx=0\Rightarrow|y|=Ce^{-\int_{x_0}^xp(s)\text ds},\quad C>0
  $$
  $y=0$ 显然也是一个解，则最终
  $$
  y=Ce^{-\int_{x_0}^xp(s)\text ds}
  $$

- $q(x)\neq0$
  $$
  e^{\int_{x_0}^xp(s)\text ds}\frac{\text dy}{\text dx}+e^{\int_{x_0}^xp(s)\text ds}p(x)y=e^{\int_{x_0}^xp(s)\text ds}q(x)\\
  \Rightarrow
  \frac{\text d}{\text dx}\left(e^{\int_{x_0}^xp(s)\text ds}y\right)=e^{\int_{x_0}^xp(s)\text ds}q(x)\\
  \Rightarrow 
  e^{\int_{x_0}^xp(s)\text ds}y-y_0=\int_{x_0}^xe^{\int_{x_0}^tp(s)\text ds} q(t)\text{d}t
  $$
  从而
  $$
  y(x)=e^{-\int_{x_0}^xp(s)\text ds}\left[y_0+\int_{x_0}^xe^{\int_{x_0}^tp(s)\text ds} q(t)\text{d}t\right]
  $$
  通解
  $$
  y(x)=e^{-\int p(x)\text dx}\left[C+\int e^{\int p(x)\text dx} q(x)\text{d}x\right]
  $$

**线性方程解的性质**

1. $q(x)\equiv0$ 时（齐次线性方程），解恒为零或恒不为零
2. 所有解都为整体的（大范围的），即 $p(x)$ 和 $q(x)$ 的定义域上该解恒有意义
3. 齐次方程任两个解的和还是解，任意解乘以常数后还是解
4. 方程的任意一个解与对应的齐次方程的通解的和构成方程的通解
5. 方程的初值问题的解存在且唯一

**例**：
$$
\frac{\text dy}{\text dx}+\frac{y}{x}=x^2
$$

$$
\Rightarrow xy'+y=x^3\Rightarrow (xy)'=x^3\Rightarrow y=\frac{x^3}{4}+\frac{C}{x}
$$

**例**：设 $f\in C^1[0,+\infty),a(x)\in C[0,\infty),a(x)\ge c_0>0$，已知
$$
\lim_{x\to+\infty}\left[f'(x)+a(x)f(x)\right]=0
$$
求证 $\lim_{x\to+\infty}f(x)=0$

设 $g(x)=f'(x)+a(x)f(x)\in C[0,+\infty)$，则
$$
f(x)=\frac{f(0)+\int_0^x\exp\left(\int_0^sa(t)\text dt\right)g(s)\text ds}{\exp\left(\int_0^xa(s)\text ds\right)}
$$
则
$$
\lim_{x\to+\infty}f(x)=\lim_{x\to+\infty}\frac{\int_0^x\exp\left(\int_0^sa(t)\text dt\right)g(s)\text ds}{\exp\left(\int_0^xa(s)\text ds\right)}=\lim_{x\to+\infty}\frac{\exp\left(\int_0^xa(t)\text dt\right)g(x)}{\exp\left(\int_0^xa(s)\text ds\right)a(x)}=\lim_{x\to+\infty}\frac{g(x)}{a(x)}=0
$$
**例**：若 $p(x)$ 和 $q(x)$ 均为 $2\pi$ 周期的，且
$$
\frac{\text dy}{\text dx}+p(x)y=q(x)
$$
有唯一的有界解，求证这个有界解为 $2\pi$ 周期的

设 $y(x)$ 是这个有界解，则 $y(x+2\pi)$ 仍然为有界解，由有界解的唯一性，$y(x)=y(x+2\pi)$

## 可以转化为变量可分离方程的形式

### 齐次方程

$$
\frac{\text dy}{\text dx}=f\left(\frac{y}{x}\right)
$$

令 $y=u(x)$，则
$$
\frac{\text dy}{\text dx}=x\frac{\text{d} u}{\text dx}+u\Rightarrow f(u)-u=x\frac{\text{d} u}{\text dx}\Rightarrow\int\frac{\text du}{f(u)-u}=\ln|x|+C
$$

**例**：
$$
\frac{\text dy}{\text dx}=\frac{a_1x+b_1y+c_1}{a_2x+b_2y+c_2}
$$

1. $c_1=c_2=0$，则有
   $$
   \frac{\text dy}{\text dx}=\frac{a_1+b_1y/x}{a_2+b_2y/x}
   $$

2. $a_1b_2-a_2b_1=0$，则有
   $$
   \frac{\text dy}{\text dx}=f(ax+by)\equiv f(u)\Rightarrow \frac{\text du}{\text dx}=af(u)
   $$

3. $a_1b_2-a_2b_1\neq0$，设 $\alpha,\beta$ 是
   $$
   \left\{
   \begin{array}{cc}
   a_1x+b_1y+c_1=0\\
   a_2x+b_2y+c_2=0
   \end{array}
   \right.
   $$
   的解，则有
   $$
   \frac{\text dy}{\text dx}=\frac{a_1(x-\alpha)+b_1(y-\beta)}{a_2(x-\alpha)+b_2(y-\beta)}
   $$
   令 $X=x-\alpha,Y=y-\beta$，有
   $$
   \frac{\text dY}{\text dX}=\frac{a_1X+b_1Y}{a_2X+b_2Y}=\frac{a_1+b_1Y/X}{a_2+b_2Y/X}
   $$
   化为了齐次方程

事实上，用类似的方法，形如
$$
\frac{\text dy}{\text dx}=f\left(\frac{a_1x+b_1y+c_1}{a_2x+b_2y+c_2}\right)
$$
的方程我们也可以解

### Bernoulli 方程

$$
\frac{\text dy}{\text dx}=P(x)y+Q(x)y^n,\quad n\neq0,1
$$

若 $n>0$，则 $y\equiv0$ 是解，下设 $y\neq0$
$$
y^{-n}\frac{\text dy}{\text dx}=\frac{1}{1-n}\frac{\text d}{\text dx}y^{1-n}=P(x)y^{1-n}+Q(x)
$$
令 $z=y^{1-n}$，则
$$
\frac{\text dz}{\text dx}=(1-n)zP(x)+(1-n)Q(x)
$$
是一阶线性微分方程

### Riccati 方程

$$
\frac{\text dy}{\text dx}=P(x)y^2+Q(x)y+r(x)
$$

若 $r\equiv0$，转为 Bernoulli 方程，否则一般难以直接解出

**定理**：若已知一个解 $y=\varphi(x)$，则可以求通解

**证明**：令 $y=u(x)+\varphi(x)$，有
$$
u'+\varphi'=P(x)(u^2+2u\varphi+\varphi^2)+Q(x)(u+\varphi)+r(x)\Rightarrow u'=\left[2\varphi P(x)+Q(x)\right]u+P(x)u^2
$$
化为 Bernoulli 方程

**定理**：$P(x)\equiv a,Q(x)\equiv0,r(x)=bx^m$ 时能化为可积分求解的方程，其中 $a,b,m$ 是常数，$m=0,-2,-4k/(2k\pm1)$，$k=1,2,\cdots$ 

**证明**：不妨设 $a=1$，将方程记为 $T_m$，$T_0$ 显然是分离变量的，对于 $T_{-2}$，作变换 $z=xy$
$$
\frac{\text dz}{\text dx}=y+xy'=\frac{z}{x}+x\left(\frac{b}{x^2}-\frac{z^2}{x^2}\right)=\frac{b+z-z^2}{x}
$$
同样是变量分离的

一般情形下，记 $X_k^\pm$ 对应 $m=-4k/(2k\pm1)$ 的方程，对 $X_k^+$ 作变换
$$
x=\xi^{1/(m+1)},\quad y=-\frac{b}{m+1}\eta^{-1}\Rightarrow\frac{\text d\eta}{\text d\xi}=\eta^2+\frac{b}{(m+1)^2}\xi^n,\quad n=-\frac{4k}{2k-1}
$$
再作变换
$$
\xi=\frac1t,\eta=t-zt^2\Rightarrow \frac{\text dz}{\text dt}+z^2=\frac{b}{(m+1)^2}t^l,\quad l=\frac{-4(k-1)}{2(k-1)+l}
$$
即将方程化为了一个 $X^+_{k-1}$ 的方程；如此重复 $k$ 次即可化为 $m=0$ 的方程并求解

对于 $X^-_{k}$，情况完全类似