# 基本概念

## 微分方程及其解的定义

**定义1.1**——常微分方程

凡是联系自变量 $x$ 与未知函数 $y(x)$ ，和它的导数 $y'=y'(x)$ 以及直到 $n$ 阶导数 $f^{(n)}$ 的方程
$$
F(x,y,y',\cdots,y^{(n)})=0
$$
称为**常微分方程**，其中导数实际出现的最高阶数 $n$ 称为方程的阶

- 线性常微分方程：$F$ 对 $y$ 及其各阶导数是线性的

**定义1.2**——常微分方程的解

设 $y=\phi(x)$ 在区间 $J$ 上连续，且有直到 $n$ 阶的导数。如果其满足恒等式
$$
F(x,\varphi(x),\varphi'(x),\cdots,\varphi^{(n)}(x))=0
$$
对 $\forall x\in J$ 成立，则称 $\phi(x)$ 为方程在区间 $J$ 上的一个解

**定义1.3**——通解&特解

设 $n$ 阶微分方程的阶
$$
y=\varphi(x,C_1,C_2,\cdots,c_n)
$$
包含 $n$ 个独立的任意常数，则称它为**通解**，其中“独立”指 Jacobi 行列式不为零，即
$$
\frac{D\left[\varphi, \varphi^{\prime}, \cdots, \varphi^{(n-1)}\right]}{D\left[C_{1}, C_{2}, \cdots, C_{n}\right]} =\left|\begin{array}{cccc}{\frac{\partial \varphi}{\partial C_{1}}} & {\frac{\partial \varphi}{\partial C_{3}}} & {\cdots} & {\frac{\partial \varphi}{\partial C_{4}}} \\ {\frac{\partial \varphi^{\prime}}{\partial C_{1}}} & {\frac{\partial \varphi^{\prime}}{\partial C_{2}}} & {\cdots} & {\frac{\partial \varphi^{\prime}}{\partial C_{n}}} \\ {\vdots} & {\vdots} & {} & {\vdots} \\ {\frac{\partial \varphi^{(n-1)}}{\partial C_{1}}} & {\frac{\partial \varphi^{(n-1)}}{\partial C_{2}}} & {\cdots} & {\frac{\partial \varphi^{(n-1)}}{\partial C_{n}}}\end{array}\right|\neq0
$$
如果方程的解 $y=\phi(x)$ 不包含任意常数，则称它为**特解**

- 初值问题（柯西问题）：在特定初值条件下，微分方程有唯一确定的解
  $$
  \left\{\begin{array}{l}{y^{(n)}=F\left(x, y, y^{\prime}, \cdots, y^{(n-1)}\right)} \\ {y\left(x_{0}\right)=y_{0}, y^{\prime}\left(x_{0}\right)=y_{0}^{\prime}, \cdots, y^{(n-1)}\left(x_{0}\right)=y_{0}^{(n-1)}}\end{array}\right.
  $$

- 边值问题

- 关于独立性的讨论：一个 $n$ 阶微分方程的通解包含 $n$ 个独立的任意常数，反之，设 $y=g(x,C_1,C_2,\cdots,C_n)$ 是充分光滑的函数族，其中 $x$ 是自变量，而 $C_i$ 是独立参数，则存在一个 $n$ 阶微分方程，使得它的通解恰好是该函数族

  证明：

  可以先后对充分光滑的函数 $y$ 求导 $1,2,\cdots,n-1$ 次，得到由 $n$ 个方程组成的 $n$ 元方程组，$C_1,\cdots,C_n$ 的 Jacobi 行列式非零等价于该方程组关于 $C_1,\cdots,C_n$ 有唯一解 (?)，从而可以利用 $y$ 的各阶导数解出各个 $C_i$，将这些常数带入 $y$ 的第 $n$ 阶导数即可以得到一个以该函数族为通解的常微分方程

- 从通解到特解：设 $y=g(x,C_1,C_2,\cdots,C_n)$ 是方程的通解，利用初值条件可以确定其中的任意常数，得到一个特解

  利用隐函数存在定理在局部范围内讨论，假定在点
  $$
  P: \quad x=\xi, C_{1}=a_{1}, \cdots, C_{n}=a_{n}
  $$
  的某个邻域 $\mathcal{N}(P)$ 内考虑通解 $y$，有
  $$
  \left\{\begin{array}{l}{y=\varphi\left(x, C_{1}, C_{2}, \cdots, C_{\mathrm{n}}\right)} \\ {y^{\prime}=\varphi^{\prime}\left(x, C_{1}, C_{2}, \cdots, C_{n}\right)} \\ {\cdots } \\ {y^{(n-1)}=\varphi^{(n-1)}\left(x, C_{1}, C_{2}, \cdots, C_{n}\right)}\end{array}\right.
  $$
  令
  $$
  \left\{\begin{array}{l}{\eta=\varphi\left(\xi, a_{1}, a_{2}, \cdots, a_{n}\right)} \\ {\eta^{\prime}=\varphi^{\prime}\left(\xi, a_{1}, a_{2}, \cdots, a_{n}\right)} \\ {\cdots } \\ {\eta^{(n-1)}=\varphi^{(n-1)}\left(\xi, a_{1}, a_{2}, \cdots, a_{n}\right)}\end{array}\right.
  $$
  由于在 P 点 Jacobi 行列式非零，由[隐函数存在定理](https://en.wikipedia.org/wiki/Implicit_function_theorem)，可以在 P 点邻域内反解出 $C_1,\cdots, C_n$，且满足
  $$
  \left\{\begin{array}{l}{a_{1}=C_{1}\left(\xi, \eta, \eta^{\prime}, \cdots, \eta^{(n-1)}\right)} \\ { a_{2}=C_{2}\left(\xi, \eta, \eta^{\prime}, \cdots, \eta^{(n-1)}\right)} \\ {\cdots} \\ {a_{n}=C_{n}\left(\xi, \eta, \eta^{\prime}, \cdots, \eta^{(n-1)}\right)}\end{array}\right.
  $$
  如此，对 $(\xi,\eta,\eta',\cdots,\eta^{(n-1)})$ 近旁的初值 $(x_0,y_0,y'_0,\cdots,y^{(n-1)}_0)$，可以确定常数
  $$
  \left\{\begin{array}{l}{C_{1}^{0}=C_{1}\left(x_{0} \cdot y_{0}, y_{0}^{\prime}, \cdots, y_{0}^{(n-1)}\right)} \\ {C_{2}^{0}=C_{2}\left(x_{0}, y_{0}, y_{0}^{\prime} \cdots, y_{0}^{(n-1)}\right)} \\ {\cdots} \\ {C_{n}^{0}=C_{n}\left(x_{0}, y_{0}, y_{0}^{\prime}, \cdots, y_{0}^{(n-1)}\right)}\end{array}\right.
  $$
  使得 $y=\varphi(x,C^0_1,C^0_2,\cdots,C^0_n)$ 是初值问题的解

## 微分方程及其解的几何解释

- 积分曲线：假设 $y=\varphi(x),\ x\in I$ 是方程
  $$
  \frac{\text{d}y}{\text{d}x}=f(x,y)
  $$
  的解（其中 $f(x,y)$ 在平面区域 $G$ 上连续，$I$ 是解的存在区间），则 $y=\varphi(x)$ 在平面上是一条光滑的曲线 $\Gamma$，称为该微分方程的**积分曲线**

  - 积分曲线在 $(x_0,\varphi(x_0))$ 处切线斜率为 $f(x_0,\varphi(x_0))$，切线方程为 $y=y_{0}+f\left(x_{0}, y_{0}\right)\left(x-x_{0}\right)$

- 线素：在区域 $G$ 内每一点 $P(x,y)$，可以作一个以 $f(P)$ 为斜率的（短小）直线段 $l(P)$，以表明积分曲线在该店的切线方向，称为该微分方程在 $P$ 点处的**线素**

  - 线素场：区域 $G$ 连同上述全体线素

- $\forall P\in\Gamma$，$l(P)$ 和 $\Gamma$ 在 $P$ 点的切线吻合

- 反之，若在 $G$ 内有一条光滑曲线
  $$
  \Lambda:\quad y=\psi(x)\quad(x\in J)
  $$
  与微分方程的线素场温和，则其是方程的一条积分曲线

- 等斜线：
  $$
  f(x,y)=k
  $$
  
- 一阶微分方程在许多情况下取如下形式
  $$
  \frac{\mathrm{d} y}{\mathrm{d} x}=-\frac{P(x, y)}{{Q}(x, y)}
  $$

  - 只要 $P(x_0,y_0)$ 和 $Q(x_0,y_0)$ 不全为零，总可以在 $(x_0,y_0)$ 附近确定线素场
  - 如果两者全为 $0$，线素场在 $(x_0,y_0)$ 没有意义——**奇异点**

### 微分方程初值问题的几何说明

- 给定微分方程
  $$
  \frac{\text{d}y}{\text{d}x}=f(x,y)
  $$
  就是在平面区域 $G$ 上给定一个线素场

- 求解初值问题
  $$
  \frac{\mathrm{d} y}{\mathrm{d} x}=f(x, y), \quad y\left(x_{0}\right)=y_{0}
  $$
  就是求经过点 $(x_0,y_0)$ 并与线素场相吻合的一条光滑曲线