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



### 常系数微分方程组

$$
\frac{\text dy}{\text dx}=Ay+f(x)
$$

其中 $A$ 是 $n\times n$ 的常系数矩阵

其对应的齐次方程组为
$$
\frac{\text dy}{\text dx}=Ay
$$
$y=e^{Ax}$ 是一个解，因为
$$
\frac{\text d e^{Ax}}{\text dx}=\sum_{i=0}^\infty A^{i+1}\frac{x^i}{i!}=A\sum_{i=0}^\infty A^{i}\frac{x^i}{i!}=Ae^{Ax}
$$
这里已经定义了
$$
e^{Ax}=I_n+\frac{Ax}{1!}+\frac{A^2x^2}{2!}+\cdots
$$
这个级数逐项收敛，且逐项求导之后依然一致收敛，因此对级数求导的结果相当于逐项求导后的级数

$e^{Ax}$ 当然是一个解矩阵，同时 $x=0$ 时，$e^{Ax}=I_n$，因此 $e^{Ax}$ 是一个基本解矩阵

**定义** (矩阵的模)

$M_n$ 是一切 $n$ 阶实矩阵的集合，实际上构成了一个 $n^2$ 维的完备的线性空间，定义
$$
||A||=\sum_{i,j}|a_{ij}|,\quad A\in M_n
$$
从而
$$
e^{Ax}=I_n+\frac{Ax}{1!}+\frac{A^2x^2}{2!}+\cdots
$$
在 $x$ 的任意有界区间上是绝对一致收敛的，任意阶逐项求导之后也是绝对一致收敛的，因此它是一个 $C^\infty$ 的矩阵函数，可逐项求导任意多次

**矩阵函数的性质**

- $A,B\in M_n$ 且 $AB=BA$，则 $e^{A+B}=e^Ae^B=e^Be^A$
  $$
  e^Ae^B=\sum_{i=0}^\infty\frac{A^i}{i!}\sum_{j=0}^\infty\frac{B^j}{j!}
  $$
  由级数的绝对收敛性，可以合并两个级数，且任意交换求和次序
  $$
  e^Ae^B=\sum_{k=0}^\infty\sum_{i+j=k}\frac{A^iB^j}{i!j!}=\sum_{k=0}^\infty\frac{1}{k!}\sum_{i=0}^kC_k^iA^iB^{k-i}=\sum_{k=0}^\infty\frac{1}{k!}(A+B)^k=e^{A+B}
  $$
  **推论**：对任意 $A\in M_n$，$(e^A)^{-1}=e^{-A}$

- $P\in M_n$ 是可逆的，则
  $$
  e^{PAP^{-1}}=Pe^AP^{-1}
  $$

  $$
  LHS=\sum_{i=0}^\infty\frac{\left(PAP^{-1}\right)^i}{i!}=\sum_{i=0}^\infty\frac{PA^iP^{-1}}{i!}=Pe^AP^{-1}=RHS
  $$

**命题**
$$
\frac{\text dy}{\text dx}=Ay
$$
满足 $\Phi(0)=E_n$ 的基本解矩阵为 $\Phi(x)=e^{Ax}$

**推论**
$$
\frac{\text dy}{\text dx}=Ay+f(x)
$$
的通解为
$$
y=e^{Ax}C+\int_{x_0}^xe^{A(x-s)}f(s)\text ds
$$
$C\in R^n$ 为任意列向量，而满足 $y(x_0)=y_0$ 的初值问题的解为
$$
y=e^{A(x-x_0)}y_0+\int_{x_0}^xe^{A(x-s)}f(s)\text ds
$$
**如何求出 $e^{Ax}$**

**例**

$A=\text{diag}(a_1,a_2,\cdots,a_n)$，则 $A^k=\text{diag}(a_1^k,a_2^k,\cdots,a_n^k)$，从而
$$
e^{Ax}=\text{diag}(a_1^k,a_2^k,\cdots,a_n^k)\sum_{k=0}^\infty\frac{x^k}{k!}=\text{diag}(e^{a_1x},e^{a_2x},\cdots,e^{a_nx})
$$
**例**
$$
A=\left(
\begin{array}{ccc}
1&1&1\\
0&1&1\\
0&0&1
\end{array}
\right)=E_3+Z_3
$$
其中
$$
Z_3=\left(
\begin{array}{ccc}
0&1&1\\
0&0&1\\
0&0&0
\end{array}
\right)
$$
显然有 $E_3Z_3=Z_3E_3$，且
$$
Z_3^2=\left(
\begin{array}{ccc}
0&0&1\\
0&0&0\\
0&0&0
\end{array}
\right),\quad Z_3^3=0
$$
因此
$$
\begin{align*}
e^{Ax}&=e^{E_3x+Z_3x}=e^{E_3x}e^{Z_3x}=e^{x}e^{Z_3x}\\
&=e^{x}\left(E_3+Z_3x+\frac{Z_3^2x^2}{2}\right)\\
&=e^x
\left(
\begin{array}{ccc}
1&x&x+\frac{1}{2}x^2\\
0&1&x\\
0&0&1
\end{array}
\right)\\
&=
\left(
\begin{array}{ccc}
e^x&xe^x&\left(x+\frac{1}{2}x^2\right)e^x\\
0&e^x&xe^x\\
0&0&e^x
\end{array}
\right)
\end{align*}
$$
**利用 Jordan 标准型**

对于每一个 $n$ 阶矩阵 $A$，存在 $n$ 阶非奇异矩阵 $P$，使得
$$
A=PJP^{-1}
$$
其中
$$
J=\text{diag}(J_1,J_2,\cdots,J_m)
$$
被称为 Jordan 标准型，由 Jordan 块
$$
{J}_{i}=\left(\begin{array}{cccc}\lambda_{i} & 1 & & \\ & \lambda_{i} & \ddots & \\ & & \ddots & 1 \\ & & & \lambda_{i}\end{array}\right)=\lambda_iE_{n_i}+Z_{n_i}
$$
构成，因此
$$
\begin{align*}
e^{J_ix}&=e^{\lambda_iE_{n_i}x}e^{Z_{n_i}x}=e^{\lambda_ix}e^{Z_{n_i}x}=e^{x J_{i}}\\
&=e^{\lambda_{i} x}\left(\begin{array}{cccccc}1 & x & \frac{x^{2}}{2 !} & \cdots & \cdots & \frac{x^{n_{i}-1}}{\left(n_{i}-1\right) !} \\ & 1 & x & \cdots & \cdots & \frac{x^{n_{i}-2}}{\left(n_{i}-2\right) !} \\ & & \ddots & \ddots & & \vdots \\ & && \ddots & \ddots & \vdots \\ & & && \ddots & x \\ & & & && 1\end{array}\right)
\end{align*}
$$
从而
$$
e^{x J}=\text{diag}(e^{xJ_1},e^{xJ_2},\cdots,e^{xJ_m})
$$

$$
e^{Ax}=Pe^{Jx}P^{-1}
$$

事实上由 $P$ 的可逆性， $e^{Ax}P=Pe^{Jx}$ 也是方程的一个基本解矩阵

但是一般来说，求 Jordan 标准型和过渡矩阵 $P$ 的计算量非常大，需要寻找替代方法

**待定指数函数法**

矩阵 $A$ 的 Jordan 标准型依赖于它特征根的重数

- 如果 $A$ 只有实的单特征根 $\lambda_1,\cdots,\lambda_n$，则 $A$ 的 Jordan 标准型就是一个对角矩阵
  $$
  \Phi(x)=e^{Ax}P=Pe^{Jx}=P\cdot\text{diag}(e^{\lambda_1x}, e^{\lambda_2x},\cdots,e^{\lambda_nx})
  $$
  且 $\Phi(0)=P$，有 $e^{Ax}=\Phi(x)\Phi^{-1}(0)$

  令 $r_i$ 表示 $P$ 的第 $i$ 列的向量，则基本解矩阵 $\Phi(x)$
  $$
  \Phi(x)=\left(e^{\lambda_1x}r_1,e^{\lambda_nx}r_n,\cdots,e^{\lambda_nx}r_n\right)
  $$
  可是要怎么求 $r_i$ 呢

  **引理**

  微分方程组有非零解 $y=e^{\lambda x} r$，当且仅当 $\lambda$ 是 $A$ 的特征根，而 $r$ 是与 $\lambda$ 相应的特征向量

  **证明**
  $$
  \frac{\text dy}{\text dx}=\lambda e^{\lambda x}r=e^{\lambda x}Ar
  $$

  $$
  \Leftrightarrow (A-\lambda E_n)r=0
  $$

  $r$ 的非零解就是 $A$ 的特征根相应的特征向量

  从而有

  **定理**

  设 $n$ 阶矩阵 $A$ 有 $n$ 个互不相同的特征根 $\lambda_i$，则矩阵函数
  $$
  \Phi(x)=\left(e^{\lambda_1x}r_1,e^{\lambda_nx}r_n,\cdots,e^{\lambda_nx}r_n\right)
  $$
  是一个基本解矩阵，其中 $r_i$ 是与 $\lambda_i$ 相应的特征向量

  **证明**

  由上面的引理，$\Phi(x)$ 当然是一个解矩阵，又由 $r_i$ 之间是线性无关的，即 $\Phi(0)$ 是满秩的，$\Phi(x)$ 也是一个基本解矩阵

  实际上证明过程并没有用到 $\lambda_i$ 互不相同，只要求 $r_i$ 之间线性无关，因此定理的结果可以加强 (但是不一定好用，因为不好判断相同的特征根下的特征向量是否线性无关)

- $A$ 只有单特征根，但是包括复值根，从而 $\Phi(x)$ 可能是复的，虽然最终的 $e^{Ax}$ 一定是实的，但是计算 $\Phi^{-1}(0)$ 的过程计算量较大

  事实上如果微分方程组有一个复值解，则由于方程的系数是实数，对方程两边取共轭之后易知该复值解的共轭也是方程的解；由于复值解的实部和虚部都可以用它与其共轭的线性表出，实部和虚部一定同时为方程的解，可以将两个复值解替换掉

- $A$ 有重特征根

  设 $A$ 互不相同的特征根为 $\lambda_1,\lambda_2,\cdots,\lambda_s$，相应的重数分别为 $n_1,n_2,\cdots,n_s$

  在 $A$ 的 Jordan 标准型中，与 $\lambda_i$ 相对应的 Jordan 块可能不止一个，但这些 Jordan 块的阶数之和为 $n_i$

  在基本解矩阵 $e^{Ax}P$ 的所有列向量中，与 $\lambda_i$ 相关的 $n_i$ 列都具有下列形式
  $$
  y=e^{\lambda_{i} x}\left(r_{0}+\frac{x}{1 !} r_{1}+\frac{x^{2}}{2 !} r_{2}+\cdots+\frac{x^{n_{i}-1}}{\left(n_{i}-1\right) !} r_{n_{i}-1}\right)
  $$
  级数截断在 $n_i-1$

  **引理**

  方程有如上的非零解的充要条件是，$r_0$ 是齐次线性方程组
  $$
  (A-\lambda_i E)^{n_i}r=0
  $$
  的一个非零解，而 $r_k$ 是递推定义的
  $$
  r_{k}=(A-\lambda_iE)r_{k-1},\quad 1\le k\le n_i-1
  $$
  **证明**

  将上述形式代入
  $$
  \frac{\text dy}{\text dx}=\lambda_iy+e^{\lambda_ix}\left(r_1+\frac{x}{1 !} r_{2}+\frac{x^{2}}{2 !} r_{3}+\cdots+\frac{x^{n_{i}-2}}{\left(n_{i}-2\right) !}r_{n_{i}-1}\right)=Ay
  $$

  $$
  \Rightarrow (A-\lambda_i E_n)\left(r_{0}+\frac{x}{1 !} r_{1}+\frac{x^{2}}{2 !} r_{2}+\cdots+\frac{x^{n_{i}-1}}{\left(n_{i}-1\right) !} r_{n_{i}-1}\right)=r_1+\frac{x}{1 !} r_{2}+\frac{x^{2}}{2 !} r_{3}+\cdots+\frac{x^{n_{i}-2}}{\left(n_{i}-2\right) !}r_{n_{i}-1}
  $$

  逐项比较系数即有上述定义

  **命题**

  设矩阵 $A$ 的互不相同的特征根为 $\lambda_1,\lambda_2,\cdots,\lambda_s$，相应的重数分别为 $n_1,n_2,\cdots,n_s$，记 $n$ 维常数列向量组成的线性空间为 $\mathbb{V}$，则

  - $\mathbb V_i=\left\{r\in \mathbb V\left|(A-\lambda_i)^{n_i}r=0\right.\right\}$ 是矩阵 $A$ 的 $n_i$ 维不变子空间

  - $\mathbb V$ 有直和分解
    $$
    \mathbb{V}=\mathbb{V}_{1} \oplus \mathbb{V}_{2} \oplus \cdots \oplus \mathbb{V}_{s}
    $$

  **定理**

  在有重根的情形下，基本解矩阵 $\Phi(x)$ 为
  $$
  \left(e^{\lambda_{1} x} P_{1}^{(1)}(x), \cdots, e^{\lambda_{1} x} P_{n_{1}}^{(1)}(x) ; \cdots ; e^{\lambda_{s} x} P_{1}^{(s)}(x), \cdots, e^{\lambda_s x} P_{n_{s}}^{(s)}(x)\right)
  $$
  其中
  $$
  P_j^{(i)}(x)=r_{j0}^{(i)}+\frac{x}{1!}r_{j1}^{(i)}+\cdots+\frac{x^{n_i-1}}{(n_i-1)!}r_{jn_i-1}^{(i)}
  $$
  是与 $\lambda_i$ 对应的第 $j$ 个向量多项式，而 $r_{jk}^{(i)}$ 是齐次线性方程组的 $n_i$ 个线性无关的解，且 $r_{jk}^{(i)}$ 是用 $r_{j0}^{(i)}$ 代替引理中的 $r_0$ 而依次得出的 $r_k$

  **证明**

  $\Phi(x)$ 显然是解矩阵，只需要证明各列线性无关，而
  $$
  \Phi(0)=
  \left(r_{10}^{(1)}, \cdots, r_{n_{1} 0}^{(1)} ; \cdots ; r_{10}^{(s)}, \cdots, r_{n_s 0}^{(s)}\right)
  $$
  则我们总可以选取解空间 $\mathbb V$ 中满足 $(A-\lambda_iE_n)^{n_i}r=0$ 的 $r$ 张成的 $n_i$ 维子空间 $\mathbb V_i$ 的基底作为 $r_{j0}^{(i)}$，同时由于 $\mathbb V$ 恰为 $s$ 个 $\mathbb V_i$ 的直和，各个子空间的基底与其他子空间的基底也是线性无关的，从而就证明了 $\Phi(x)$ 的各项是线性无关的，它是一个基本解矩阵