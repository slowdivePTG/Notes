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

## 积分因子法

**定义**：
$$
P(x,y)\text dx+Q(x,y)\text dx=0
$$
若非零函数 $\mu(x,y)$ 满足 $\mu P\text dx+\mu Q\text dy=0$ 是恰当的，则称 $\mu$ 为原方程的一个积分因子

**定理**：若 $P,Q$ 为 $C^1$ 的，则 $C^1$ 函数 $\mu$ 为积分因子，当且仅当
$$
\frac{\partial (\mu P)}{\partial y}=\frac{\partial (\mu Q)}{\partial x}\Leftrightarrow P\frac{\partial \mu}{\partial y}-Q\frac{\partial \mu}{\partial x}=\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)\mu
$$
即解一个一般的一阶常微分方程的难度相当于解一个一阶线性偏微分方程，一般而言解不出来

**一些特殊情形**

**例**：可分离变量的方程
$$
P_1(x)P_2(y)\text dx+Q_1(x)Q_2(y)\text dy=0
$$
取 $\mu=Q_1^{-1}(x)P_2^{-1}(y)$

**例**：一阶线性常微分方程
$$
\frac{\text dy}{\text dx}+p(x)y=q(x)\Leftrightarrow \left[p(x)y-q(x)\right]\text dx+\text dy=0
$$
取
$$
\mu=\exp\left[\int p(x)\text dx\right]
$$
**定理**：方程 $P(x,y)\text dx+Q(x,y)\text dy=0$ 有一个只依赖于 $x$ 的 $C^1$ 积分因子，当且仅当
$$
G=\frac1Q\left(\frac{\partial P}{\partial y}-\frac{\partial Q}{\partial x}\right)
$$
只依赖于 $x$；有一个只依赖于 $y$ 的 $C^1$ 积分因子，当且仅当
$$
H=\frac1P\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)
$$
只依赖于 $y$，并且
$$
\mu(x)=\exp{\left[\int G(x)\text dx\right]},\quad\text{or }\mu(y)=\exp{\left[\int H(y)\text dy\right]}
$$
**证明**：$\mu$ 为只依赖于 $x$ 的积分因子等价于
$$
\mu\frac{\partial P}{\partial y}=\mu'Q+\mu\frac{\partial Q}{\partial x}
$$

$$
\Leftrightarrow \frac{\mu'}{\mu}=\frac1Q\left(\frac{\partial P}{\partial y}-\frac{\partial Q}{\partial x}\right)\equiv G=G(x)
$$

$$
\Leftrightarrow\mu(x)=\exp{\left[\int G(x)\text dx\right]}
$$

另一情况的证明完全类似

**例**：回到上例中一阶线性常微分方程的情形
$$
P=p(x)y-q(x),\quad Q=1\\
G=\frac1Q\left(\frac{\partial P}{\partial y}-\frac{\partial Q}{\partial x}\right)=\frac{\partial}{\partial y}[p(x)y-q(x)]=p(x)
$$
积分因子为
$$
\mu=\exp\left[\int p(x)\text dx\right]
$$
**定理**：方程有形如 $\mu=f[\phi(x,y)]$ 的积分因子，当且仅当
$$
\frac{P_y-Q_x}{Q\phi_x-P\phi_y}=g[\phi(x,y)]
$$
**证明**：
$$
\frac{\partial (\mu P)}{\partial y}=\frac{\partial (\mu Q)}{\partial x}\Leftrightarrow f'(\phi)\phi_y P+\mu P_y=f'(\phi)\phi_x Q+\mu Q_x
$$

$$
\Leftrightarrow \frac{f'(\phi)}{f(\phi)}=\frac{P_y-Q_x}{Q\phi_x-P\phi_y}
$$

**例**：
$$
(3x^2y+2xy+y^3)\text dx+(x^2+y^2)\text dy=0
$$

$$
P(x,y)=3x^2y+2xy+y^3,\quad Q(x,y)=x^2+y^2
$$

$$
\frac{P_y-Q_x}{Q}=-\frac{2x-3x^2-2x-3y^2}{x^2+y^2}=3
$$

与 $y$ 无关，则 $\mu=e^{3x}$ 是个积分因子
$$
e^{3x}\left(x^2y+\frac{y^3}{3}\right)=C
$$
**定理**：若 $\mu(x,y)$ 是一个积分因子，使得
$$
\mu P\text dx+\mu Q\text dy=\text d\Phi(x,y)
$$
则 $\mu(x,y)f[\Phi(x,y)]$ 也是积分因子，其中 $f$ 是任意连续函数

**证明**：
$$
\frac{\partial\left[\mu f(\Phi )P\right]}{\partial y}-\frac{\partial\left[\mu f(\Phi )Q\right]}{\partial x}=\mu f'(\Phi)(\Phi_yP-\Phi_xQ)=\mu f'(\Phi)(\mu PQ-\mu PQ)=0
$$
**分组求积分因子法**

假设方程左端可以分成两组，即
$$
\left(P_{1} \mathrm{d} x+Q_{1} \mathrm{d} y\right)+\left(P_{2} \mathrm{d} x+Q_{2} \mathrm{d} y\right)=0
$$
其中第一组和第二组各有积分因子 $\mu_1,\mu_2$
$$
\mu_{1}\left(P_{1} \mathrm{d} x+Q_{1} \mathrm{d} y\right)=\mathrm{d} \Phi_{1}, \quad \mu_{2}\left(P_{2} \mathrm{d} x+Q_{2} \mathrm{d} y\right)=\mathrm{d} \Phi_{2}
$$
从而如果能适当选取 $f_1$ 和 $f_2$，使得 $\mu=\mu_1f_1(\Phi_1)=\mu_1f_1(\Phi_1)$，则 $\mu$ 就是方程的一个积分因子

**例**：
$$
(x^3y-2y^2)\text dx+x^4\text dy
$$

$$
\Leftrightarrow (x^3y\text dx+x^4\text dy)-2y^2\text dx=0
$$

第一部分积分因子 $\mu_1=x^{-3}$，且
$$
y\text dx+x\text dy=\text d\left(xy\right)\Rightarrow \Phi_1=xy=C
$$
第二部分积分因子$\mu_2=y^{-2}$，且 $\Phi_2=x=C$

从而需要寻找可微函数 $g_1$ 和 $g_2$，使得
$$
\frac{1}{x^3}g_1(xy)=\frac{1}{y^2}g_2(x)
$$
只需取 $g_1(xy)=(xy)^{-2},g_2(x)=x^{-5}$，得到原方程的积分因子
$$
\mu=\frac{1}{x^5y^2}
$$
进而得到全微分
$$
\text d\left(\frac1{xy}-\frac{1}{2x^4}\right) =0\Rightarrow y=\frac{2x^3}{2Cx^4+1}
$$


**定理**：设 $\mu_1,\mu_2$ 都为积分因子，若 $\mu_1/\mu_2$ 不为常数，则 $\mu_1/\mu_2$ 是方程的通解

**证明**：设 $\mu_1P\text dx+\mu_2Q\text dy=\text d\phi_1,\ \mu_2P\text dx+\mu_2Q\text dy=\text d\phi_2$

设 $\omega=P\text dx+Q\text dy$
$$
\mu_1\omega=\text d\phi_1,\quad \mu_2\omega=\text d\phi_2
$$

$$
\text d\mu_1\wedge\omega+\mu_1\text d\omega=0,\quad \text d\mu_2\wedge\omega+\mu_2\text d\omega=0
$$

$$
\Rightarrow (\mu_2\text d\mu_1-\mu_1\text d\mu_2)\wedge\omega=0\Rightarrow \mu_2\text d\mu_1-\mu_1\text d\mu_2=f\omega=0
$$

$$
\Rightarrow \text{d}\left(\frac{\mu_1}{\mu_2}\right)=0
$$

**例**：当 $P,Q$ 为 $n$ 次齐次函数的时候，求积分因子

令 $y=ux$，
$$
P\text dx+Q\text dy=x^nP(1,u)\text dx+x^nQ(1,u)(u\text dx+x\text du)
$$
有积分因子
$$
\mu=\frac{1}{x^{n+1}[P(1,u)+u Q(1,u)]}
$$

$$
\Rightarrow \frac{\text dx}{x}+\frac{Q(1,u)}{P(1,u)+uQ(1,u)}=0
$$

从而原方程有积分因子
$$
\frac{1}{xP+yQ}
$$
也可直接证明它为积分因子，由齐次性
$$
xP_x+yP_y=nP,\quad xQ_x+yQ_y=nQ
$$
从而
$$
\frac{\partial (\mu P)}{\partial y}=\frac{\partial (\mu Q)}{\partial x}\Leftrightarrow \mu_yP+\mu P_y=\mu_xQ+\mu Q_x
$$

$$
LHS=-\frac{xPP_y+PQ+yPQ_y}{(xP+yQ)^2}+\frac{P_y}{xP+yQ}=\frac{y(QP_y-PQ_y)-PQ}{(xP+yQ)^2}
$$

同理
$$
RHS=\frac{x(PQ_x-QP_x)-PQ}{(xP+yQ)^2}
$$

$$
LHS-RHS=\frac{Q(yP_y+xP_x)-P(yQ_y+xQ_x)}{(xP+yQ)^2}=0
$$

## 一些例子

### 等角轨线

**定义**：给定一族曲线 $\phi(x,y,c)=0$ ，找一族曲线 $\psi(x,y,k)=0$，使得两组曲线之间夹角为等值；若夹角为**直角**，则称第二族曲线是第一族曲线的**正交轨线族**
$$
\phi(x,y,c)=0\Rightarrow \phi_x\text dx+\phi_y\text dy=0
$$
代入 $c=c(x,y)$
$$
\frac{\text dy}{\text dx}=H(x,y)\equiv-\frac{\phi_x[x, y, c(x,y)]}{\phi_y[x, y, c(x,y)]}
$$
设与上述曲线族夹角为 $\alpha$ 的曲线斜率为 $y'$，则若 $\alpha\neq\pi/2$
$$
\tan \alpha=\frac{y'-H(x,y)}{1+y'H(x,y)}\Rightarrow y'=\frac{H(x,y)+\tan\alpha}{1-H(x,y)\tan\alpha}
$$
若 $\alpha=\pi/2$
$$
y'=-\frac{1}{H(x,y)}
$$
**例**：求与抛物线族 $y=cx^2$ 正交的曲线族
$$
c=\frac{y}{x^2}\Rightarrow\frac{\text dy}{\text dx}=2cx=\frac{2y}{x}
$$
其正交曲线族满足的方程为
$$
\frac{\text dy}{\text dx}=-\frac{x}{2y}\Leftrightarrow 2y\text dy+x\text dx=0\Leftrightarrow y^2+\frac{x^2}{2}=K
$$
**例**：求与曲线 $y=x\ln(cx)$ 夹角为 $-\pi/4$ 的曲线族
$$
\frac{\text dy}{\text dx}=\ln(cx)+1=\frac{y}{x}+1
$$
其正交曲线族满足的方程为
$$
-1=\frac{y'-{y}/{x}-1}{1+y'\left({y}/{x}+1\right)}\Rightarrow y'=\frac{y}{2x+y}
$$
令 $y=ux$，则当 $y\neq-x$ 时
$$
y'=u+u'x=\frac{u}{2+u}\Rightarrow\frac{\text dx}{x}=-\frac{2+u}{u+u^2}\text du=-\frac{2}{u}\text du+\frac{1}{u+1}\text du
$$

$$
\Rightarrow \ln |x|=-2\ln|u|+\ln|u+1|\Rightarrow |x|=\frac{k|u+1|}{u^2}
$$

$$
\Rightarrow y^2=\pm k(x+y),\quad k\ge0
$$

同时 $y=-x$ 也是一个解

### 抛物线的光学性质

见习题 2-3 的第 6 题

### 传染病模型

记 $N(t)$ 为 $t$ 时刻病人数（足够大），有
$$
N(t+\Delta t)=N(t)+rN(t)\Delta t
$$
令 $\Delta t\to 0$，有
$$
\frac{N'(t)}{N(t)}=r\Rightarrow N(t)=N_0e^{r(t-t_0)},\quad N_0=N(t_0)
$$
$r$ 被称为传染率，若数据显示一周之内病人变为原来十倍，则可以估计 $r$
$$
10=e^{7r}\Rightarrow r\sim0.32
$$
然而由于疾病只能传播给健康人，随着健康人数的减少，传染率应该会下降，假设它是线性的
$$
r=r_0-r_1N\Rightarrow \frac{\text dN}{\text dt}=(r_0-r_1N)N\Rightarrow N(t)=\frac{N_0r_0e^{r_0(t-t_0)}}{r_0+N_0r_1[e^{r_0(t-t_0)-1}]}
$$
$$
\lim_{t\to+\infty}N(t)=\frac{r_0}{r_1}
$$

### 生态方程

食肉动物吃食草动物，食草动物吃草，可以用一组方程表现两种动物的种群大小是如何相互制约的

设 $x$ 是捕食者数量，$y$ 是被捕食者数量

最简单的假设：捕食者增长率与被捕食者数目线性正相关，被捕食者增长率与捕食者数目线性负相关
$$
\frac{\dot x}{x} = -a+by\\
\frac{\dot y}{y} = +c-dx
$$
消去时间参量有
$$
\frac{\text dy}{\text dx}=\frac{(c-dx)y}{(-a+by)x}\Rightarrow F(x,y)=by+dx-c\ln x-a\ln y=K
$$

首先 $F$ 是一个凸函数，因为
$$
\frac{\partial^2F}{\partial x^2},\ \frac{\partial^2F}{\partial y^2}>0,\ \frac{\partial^2F}{\partial x\partial y}=0
$$
从而 $\forall K\in(F(x_0,y_0),+\infty)$，$F(x,y)=K$ 是一个闭凸曲线，绕着 $(x_0,y_0)$ 旋转

很难求出 $x(t)$ 和 $y(t)$ 的具体表达式，但是可以求平均值，假设周期为 $T$
$$
\frac{\text dx}{x}=(-a+by)\text dt
$$
两边积分
$$
\ln x(t)\Big|_0^T=0=-aT+b\int_0^Ty(t)\text dt\Rightarrow \bar y=\frac{1}{T}\int_0^Ty(t)\text dt=\frac{a}{b}
$$
同理
$$
\bar x=\frac{c}{d}
$$

若对两种动物都进行捕杀，方程组变为
$$
\frac{\dot x}{x} = -(a+\epsilon)+by\\
\frac{\dot y}{y} = +(c-\epsilon)-dx
$$
平均值变为
$$
\bar x=\frac{a-\epsilon}{b},\quad \bar y=\frac{c+\epsilon}{d}
$$
即捕食者数目减少，被捕食者数目增加

### 最速降线

从 $(0,0)$ 至 $(x,y)$

*历史上，这是约翰·伯努利的证明*

任意一点处满足“光的折射定律”——入射角与出射角的正弦值之比为常数，该常数为两种介质中的光速之比，当物体纵坐标为 $y$ 时，有

$$
v=\sqrt{-2gy}\Rightarrow \frac{\sin{\theta}}{\sqrt{-y}}=C
$$

这里 $\sin\theta$ 满足

$$
\sin\theta=\frac{1}{\sqrt{1+y'^2}}
$$

$$
y(1+y'^2)=C_1\Rightarrow \text dx=\sqrt{\frac{y}{C_1-y}}\text dy
$$
令 $\tan \theta=\sqrt{\frac{y}{C_1-y}}$，则
$$
y=C_1\sin^2\theta
$$

$$
x=\int C_1\tan\theta\cdot2\sin\theta\cos\theta\text d\theta=C_1\int2\sin^2\theta\text d\theta=C_1\left(\theta-\frac12\sin2\theta\right)
$$

令 $C=C_1/2,\ \phi=2\theta$，则

$$
x=C(1-\cos\phi),\quad y=C(\phi-\sin\phi)
$$

这是摆线的方程