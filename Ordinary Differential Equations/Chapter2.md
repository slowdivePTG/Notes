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


