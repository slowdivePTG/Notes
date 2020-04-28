# 线性微分方程组

$$
\frac{\text dy_i}{\text dt}=\sum_{j=1}^na_{ij}(t)y_j+f_i(t),\quad 1\le i\le n
$$

一般假设 $a_ij(t)$ 和 $f_i(t)$ 都是 $(a,b)$ 上的连续函数

若 $f_i(t)\equiv0$，则成为齐次方程组

若令
$$
y(t)=\left(
\begin{array}{c}
y_1(t)\\
\cdots\\
y_n(t)
\end{array}
\right)
$$
是 $(a,b)$ 到 $R^n$ 上的映射，$A(t)=(a_{ij}(t))_{n\times n}$
$$
f(t)=\left(
\begin{array}{c}
f_1(t)\\
\cdots\\
f_n(t)
\end{array}
\right)
$$
则方程组可以重写为
$$
\frac{\text dy}{\text dt}=A(t)y+f(t)=F(t,y)
$$


在 $t\in(a,b),\ y\in R$ 上，$F$ 连续，关于 $y$ 局部李氏连续，且
$$
|F(t,y)|\le A(t)|y|+B(t)
$$
**定理** (解的存在唯一性)：此类微分方程对初值问题的解存在唯一，且解可以延拓到 $(a,b)$ 上



## 齐次线性方程组

**定理**

如果 $y_1,y_2$ 是齐次线性方程组的解，则对任何常数 $C_1,C_2$，$C_1y_1+C_2y_2$ 也是解

**证明**

直接验证
$$
\frac{\text d}{\text dt}(C_1y_1+C_2y_2)=A(t)(C_1y_1+C_2y_2)
$$
**推论**

齐次方程组全体解构成一个线性空间，称为**解空间**

**定义**

向量函数 $\phi_i(x): (a,b)\to R^n,\ 1\le i\le m$ 称为线性相关的，如果存在不全为零的常数 $C_1,C_2,\cdots,C_m$ 满足
$$
\sum_{i=1}^mC_i\phi_i(x)\equiv0,\quad \forall x\in(a,b)
$$
**命题**

假设齐次方程组有 $m$ 个解 $y_i(x)$，则 $y_i(x)$ 线性相关的充要条件是，存在 $x_0\in(a,b)$，$y_i(x_0)$ 线性相关

必要性显然，充分性：由线性相关性，存在不全为零的常数 $C_1,\cdots,C_m$，满足
$$
\sum_{i=1}^mC_iy_i(x_0)=0
$$
令
$$
y(x)=\sum_{i=1}^mC_iy_i(x)
$$
则 $y(x)$ 是齐次方程组的解，$y(x_0)=0$，由解的唯一性，$y(x)\equiv0$，也就是 $y_i(x)$ 线性相关

**定理**

齐次方程组的解空间是 $n$ 维线性空间：存在 $n$ 个线性无关的解 $y_i(x)$，使得
$$
y(x)=\sum_{i=1}^mC_iy_i(x),\quad C_i\in R
$$
构成全体解

**证明**

设
$$
\epsilon_i=\left(
\begin{array}{c}
0\\
\cdots\\
1\\
\cdots\\
0
\end{array}
\right)
$$
是 $n$ 个标准基，$y_i(x)$ 是满足
$$
y'=A(x)y,\quad y(x_0)=\epsilon_i
$$
的解，则 $y_i(x_0)$ 线性无关，必有 $n$ 个 $y_i(x)$ 线性无关

设 $y(x)$ 是方程的任意一个解，设
$$
y(x_0)=\left(
\begin{array}{c}
C_1\\
\cdots\\
C_n
\end{array}
\right)
$$
考虑解
$$
\tilde y(x)=\sum_{i=1}^mC_iy_i(x)
$$
则有 $\tilde y(x_0)=y(x_0)$，由解的唯一性，$\tilde y(x)\equiv y(x),\ \forall x\in(a,b)$

设
$$
y_i(x)=\left(
\begin{array}{c}
y_{1i}(x)\\
\cdots\\
y_{ni}(x)
\end{array}
\right)
$$

$$
Y(x)=(y_1(x)\ \cdots\ y_n(x))=(y_{ij}(x))_{n\times n}
$$

则
$$
\frac{\text dY}{\text dx}=A(x)Y(x)
$$
**命题**

$Y(x)$ 是**解矩阵**等价于 $Y(x)$ 的每一列都是齐次方程组的解

若 $\det Y(x)\neq0$，则 $Y(x)$ 称为**基本解矩阵**

**命题**

$Y(x)$ 是解矩阵，则对于任意向量
$$
C=\left(
\begin{array}{c}
C_1\\
\cdots\\
C_n
\end{array}
\right)\in R^n
$$
有 $Y(x)C$ 一定是解

**命题**

$Y(x)$ 是解矩阵，$B$ 是一个 $n\times n$ 的常数矩阵，则 $Y(x)B$ 仍是解矩阵，特别地，如果 $Y(x)$ 为基本解矩阵，$B$ 是可逆矩阵，则 $Y(x)B$ 仍是基本解矩阵，同时所有的基本解矩阵可以在 $B$ 取遍所有的可逆矩阵时给出

**证明**

取定 $x_0\in(a,b)$，设 $X(x)$ 为任意一个基本解矩阵，$B=Y(x_0)^{-1}X(x_0)$，并设
$$
\tilde X(x)=Y(x)B
$$
则 $\tilde X(x)$ 是基本解矩阵且 $\tilde X(x_0)=X(x_0)$，由唯一性
$$
X(x)\equiv\tilde X(x)=Y(x)B
$$
**命题**

设 $Y(x)$ 是一个基本解矩阵，则 $Y(x)C, C\in R^n$ 是方程的通解

**证明**

取定 $x_0\in(a,b)$，设 $y(x)$ 是任意一个解，取 $C=Y(x_0)^{-1}y(x_0)$，则解 $\tilde y(x)=Y(x)C$ 满足 $\tilde y(x_0)=y(x_0)$，由唯一性 $\tilde y(x)=y(x)$，从而 $y(x)=Y(x)C$

**定理** (刘维尔公式)：

设 $Y(x)$ 是一个解矩阵，$W(x)=\det Y(x)$，则
$$
W(x)=W(x_0)\exp{\int_{x_0}^x}\text{tr} A(s)\text ds 
$$

$$
\text{tr} A(s)=\sum_{i=1}^na_{ii}(s)
$$

**证明**
$$
W(x)=\left|\begin{array}{cccc}y_{11}(x) & y_{12}(x) & \cdots & y_{1 n}(x) \\ y_{21}(x) & y_{22}(x) & \cdots & y_{2 n}(x) \\ \vdots & \vdots & & \vdots \\ y_{n 1}(x) & y_{n 2}(x) & \cdots & y_{n n}(x)\end{array}\right|
$$

$$
\begin{align*}
W'&=\sum_{i=1}^{n}\left|\begin{array}{cccc}y_{11} & y_{12} & \cdots & y_{1 n} \\ \vdots & \vdots & & \vdots \\ \frac{d y_{i 1}}{d x} & \frac{d y_{i 2}}{d x} & \cdots & \frac{d y_{n n}}{d x} \\ \vdots & \vdots & & \vdots \\ y_{n 1} & y_{n 2} & \cdots & y_{n n}\end{array}\right|\\
&=\sum_{i=1}^{n}\left|\begin{array}{cccc}y_{11} & y_{12} & \cdots & y_{1 n} \\ \vdots & \vdots & & \vdots \\ \sum_{j=1}^{n} a_{i j} y_{j 1} & \sum_{j=1}^{n} a_{i j} y_{j 2} & \cdots & \sum_{j=1}^{n} a_{i j} y_{j n} \\ \vdots & \vdots & & \vdots \\ y_{n 1} & y_{n 2} & \cdots & y_{n n}\end{array}\right|\\
&=\sum_{i=1}^na_{ii}W=\text{tr} A(x)W
\end{align*}
$$

即证





## 非齐次方程组

$$
y'=A(x)y+f(x)
$$

**命题**

设 $\Phi(x)$ 是对应齐次方程组的基本解矩阵，$y_*(x)$ 是原方程的一个解，则
$$
y(x)=\Phi(x)C+y_*(x),\quad C\in R^n
$$
**证明**

显然 $y-y_*$ 是齐次方程组的解，因此存在 $C\in R^n$，使得 $y-y_*=\Phi C$

**寻找特解**

设原方程有一个解有形式
$$
y(x)=\Phi(x)C(x)
$$
那么
$$
y'(x)=A(x)\Phi(x)C(x)+f(x)=\Phi'(x)C(x)+\Phi(x)C'(x)
$$

$$
\Rightarrow C'(x)=\Phi'(x)^{-1}f(x)
$$

得到原方程一个解
$$
y_*(x)=\Phi(x)\int_{x_0}^x\Phi(s)^{-1}f(s)\text ds
$$
**求通解**
$$
y_*(x)=\Phi(x)\left(C+\int_{x_0}^x\Phi(s)^{-1}f(s)\text ds\right)
$$
