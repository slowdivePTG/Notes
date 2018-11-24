# Chapter 1. Data Reduction 数据压缩



## 统计模型

一个统计模型是一系列概率分布（或概率密度）的集合

- 参数模型
  $$
  \mathcal { P } = \{ p ( x ; \theta ) : \theta \in \Theta \}
  $$
  比如正态分布：
  $$
  p ( x ; \theta ) = \frac { 1 } { \sigma \sqrt { 2 \pi } } e ^ { - \frac { 1 } { 2 \sigma ^ { 2 } } ( x - \mu ) ^ { 2 } }
  $$
  参数 $\theta = ( \mu , \sigma )$ 

- 非参模型

  比如所有平方可积的分布的集合：
  $$
  \mathcal { P } = \left\{ p : \int \left( p ^ { \prime \prime } ( x ) \right) ^ { 2 } d x < \infty \right\}
  $$




## 统计量

统计量 $T$ 是随机向量$X _ { 1 } , \ldots , X _ { n } \sim p ( x ; \theta )$ 的函数，自身是一个随机变量

- 顺序统计量：$X _ { ( 1 ) } \leq X _ { ( 2 ) } \leq \ldots \leq X _ { ( n ) }$
- 样本平均：$\overline { X } = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } X _ { i }$
- 样本方差（无偏估计）：$S ^ { 2 } = \frac { 1 } { n - 1 } \left( X _ { i } - \overline { X } \right) ^ { 2 }$
- 样本最大值：$X _ { ( n ) }$



## 数据压缩

- 一个实验者使用样本里的信息来推断统计总体的未知参数 $\theta$ 
- 当样本容量 $n$ 很大的时候，样本的信息不好转译——在保留样本的一些**关键特征**的前提下对信息进行压缩
- 任何一个统计量 $T ( X )$ 都定义了一种形式的数据压缩
- 选择一个特定的统计量进行数据压缩，相当于对样本空间 $\chi$ 进行了一次分割：
  - 令 $T = \{ t : t = T ( x ) \text { for some } x \in \chi \}$
  - $T(X)$ 把样本空间分成一个个子集 $A_t，t\in T$ ，满足 $A _ { t } = \{ x : T ( x ) = t \}$ 



### 数据压缩的三种原则

- 充分性原则：不丢失 $\theta$ 的任何信息
- 似然性原则：给出参数的一个函数，这个函数由样本决定，包含了样本可以提供的 $\theta$ 的全部信息
- 等价性原则



### 充分性原则

#### 充分统计量

- 令 $X ^ { n } = \left( X _ { 1 } , \ldots , X _ { n } \right) , x ^ { n } = \left( x _ { 1 } , \ldots , x _ { n } \right)$

- 如果 $T(X^n)$ 是 $\theta$ 的充分统计量，那么任何关于参数 $\theta$ 的推断都仅仅依赖于 $T(X^n)$

  对于 $T(x^n)=T(y^n)$ ，不管样本 $x^n$ 和 $y^n$ 是否相等，推断出的 $\theta$ 都是一样的

- 数学表述：

  - $X _ { 1 } , \ldots , X _ { n } \sim p ( x ; \theta )$

  - $T$ 是 $\theta$ 的充分统计量，如果 $T=t$ 下的条件分布与 $\theta$ 无关
    $$
    p \left( x _ { 1 } , \ldots , x _ { n } | T ( x ) = t ; \theta \right) = p \left( x _ { 1 } , \ldots , x _ { n } | T ( x ) = t \right)
    $$




#### 充分统计量的判断

##### 一个定理

如果 $P(x^n|\theta)$ 是 $X^n$ 的联合pdf/pmf，$q ( t | \theta )$ 是 $T \left( X ^ { n } \right)$ 的pdf/pmf，则 $T \left( X ^ { n } \right)$ 是 $\theta$ 的充分统计量当且仅当，任取样本空间中的 $x^n$ ，比例
$$
\frac{p \left( x ^ { n } | \theta \right)}{ q \left( T \left( x ^ { n } \right) | \theta \right)}
$$
与 $\theta$ 无关，只是样本的函数

这个定理非常显然，只需要把 $T=t$ 下的条件分布代入，并注意到 $X^n=x^n$ 时必有 $T(X^n)=T(x^n)$ 即可：
$$
\begin{aligned} &p \left( X ^ { n } = x ^ { n } | T \left( X ^ { n } \right) = T \left( x ^ { n } \right) \right)\\  = &\frac { p \left( X ^ { n } = x ^ { n },T \left( X ^ { n } \right) = T \left( x ^ { n } \right) \right) } { p \left( T \left( X ^ { n } \right) = T \left( x ^ { n } \right) \right) }\\  = &\frac { p \left( X ^ { n } = x ^ { n } \right) } { p \left( T \left( X ^ { n } \right) = T \left( x ^ { n } \right) \right) } \\  =& \frac { p \left( x ^ { n } ; \theta \right) } { q \left( T \left( x ^ { n } \right) ; \theta \right) } \end{aligned}
$$


- 例：泊松分布：$P \left( X _ { i } = x \right) = e ^ { - \theta } ( \theta ) ^ { x } / x !$

  - $p(x^n;\theta)=e ^ { - n\theta } ( \theta ) ^ { \sum x_i } / \prod x_i !$

  - $n$ 个iid的泊松分布之和 $\sim Poisson(n\theta)$
    $$
    q(\sum x_i|\theta)=\frac{e ^ { - n\theta } ( n\theta ) ^ { \sum x_i }} {\left(\sum x_i\right) !}
    $$

  - 比例
    $$
    \frac{p \left( x ^ { n } | \theta \right)}{ q \left( T \left( x ^ { n } \right) | \theta \right)}=\frac{e ^ { - n\theta } ( \theta ) ^ { \sum x_i } / \prod x_i !}{e ^ { - n\theta } ( n\theta ) ^ { \sum x_i } / \left(\sum x_i\right) !}=\frac{\left(\sum x_i\right) !}{\prod x_i !( n) ^ { \sum x_i }}
    $$

    与 $\theta$ 无关

  - $\sum X_i$ 是一个充分统计量

- 例：任取一个分布 $f$ ，对于iid的样本，顺序统计量都是充分统计量——没有对数据进行压缩！



##### 充分划分

- $T(X)$ 把样本空间分成 $B_{t_1},\cdots,B_{t_k}$ 。一个划分是充分的，如果 $f ( x | X \in B )$ 不依赖于 $\theta$ ；而 $T$ 的充分性和分割的充分性是等价的
- 不同的统计量可能产生同样的划分（最简单的例子是一个统计量是另外一个的倍数）
- 进一步划分 $B_i$ 得到的依然是充分的划分

- 例：比如我们可以证明，对于 $X _ { 1 } , X _ { 2 } , X _ { 3 } \sim \text { Bernoulli } ( \theta )​$ ，$T = \sum X _ { i }​$ 是充分的，因为只要给定了 $T​$ ，$x_i​$ 每一种可能的取值都是等概率的；但 $T=X_1​$ 不是充分的，给定 $X_1​$ 之后，不同情况的概率仍和 $\theta​$ 有关



##### 因子化定理

$T(X^n)$ 是 $\theta$ 的充分统计量，如果联合pdf/pmf可以被因子化为：
$$
p \left( x ^ { n } ; \theta \right) = h \left( x ^ { n } \right) \times g ( t ; \theta )
$$


#### 最小充分统计量(MSS)

- $T$ 是最小充分统计量，如果：

  - $T​$ 是充分的
  - 对于任意一个充分统计量 $U$ ，$T$ 是 $U$ 的函数（若 $T(U=U_1)\neq T(U=U_2)$ ，$U_1\neq U_2$
- MSS不是唯一的（考虑任何一一对应的函数）



#### 最小充分统计量的判断

##### 一个定理

- 定义 $R$

$$
R ( x , y ; \theta ) = \frac { p ( y ; \theta ) } { p ( x ; \theta ) }
$$

- 如果 $R(x,y;\theta)$ 不依赖于 $\theta$ 当且仅当 $T ( y ) = T ( x )$ ，则 $T$ 是MSS

- 例：泊松分布
  $$
  p \left( y ^ { n } ; \theta \right) = \frac { e ^ { - n \theta } \theta ^{\sum  y _ { i }} } { \prod _ { i } y _ { i } ! } , \frac { p \left( y ^ { n } ; \theta \right) } { p \left( x ^ { n } ; \theta \right) } = \frac { \theta ^{\sum y _ { i } - \sum  x _ { i } }} { \prod _ { i } y _ { i } ! /\prod _ { i } x _ { i } ! }
  $$
  比例与 $\theta$ 无关当且仅当 $\sum x_i=\sum y_i$ ，所以 $T(X^n)=\sum X_i$ 是MSS

- 例：$(\theta,\theta+1)$ 上的均匀分布
  $$
  p ( x ; \theta ) = \left\{ \begin{array} { l l } { 1 } & { \theta < x _ { i } < \theta + 1 , i = 1 , \ldots , n } \\ { 0 } & { \text { otherwise } } \end{array} \right.
  $$
  也就是：
  $$
  p ( x ; \theta ) = \left\{ \begin{array} { l l } { 1 } & { x _ { (n) } - 1 < \theta < x _ { (1) } } \\ { 0 } & { \text { otherwise } } \end{array} \right.
  $$
  令 $T(X)=\left( X _ { ( 1 ) } , X _ { ( n ) } \right)$ ，显然当且仅当 $T(x)=T(y)$ 时，$p ( x ; \theta )$ 和 $p ( y ; \theta )$在共同区间上恒为1，$T(X)$ 为MSS




#### 充分统计量的意义

充分统计量包含了数据中可以用来计算似然函数的所有信息



#### 辅助统计量

分布与 $\theta$ 无关的统计量——恰与充分统计量相对

- MSS在仍能提取 $\theta$ 信息的前提下把数据量压缩到了最小
- 但它和辅助统计量并不一定是独立的



#### 完备统计量

- 充分性：该保留的信息都保留；完备性：该丢掉的信息都丢掉
- 考虑 $T(X)$ 的一个分布族 $f(t|\theta)$ 
  - 如果对于任意 $\theta$ 都有 $E _ { \theta } g ( T ) = 0$ 可以推出对于任意 $\theta$ 都有 $P _ { \theta } ( g ( T ) = 0 ) = 1$ ，那么这个分布族就是完备的
  - 这个统计量也被称为完备统计量
- Basu定理：如果 $T(X)$ 是完备的最小充分统计量，那么它和辅助统计量独立
- 如果最小充分统计量存在，那么任何完备统计量都是最小充分统计量



#### 指数分布族

- 指数分布族（ $k$ 为参数个数）：
  $$
  f ( x | \theta ) = h ( x ) c ( \theta ) \exp \left( \sum _ { j = 1 } ^ { k } w _ { j } \left( \theta \right) t _ { j } ( x ) \right)
  $$

- $X_1,\cdots,X_n$ 是iid的观测结果，得到联合分布：
  $$
  \begin{align*}
  f ( x | \theta ) &= \prod h ( x_i ) c^n ( \theta ) \exp \left( \sum _ { j = 1 } ^ { k } w _ { j } \left( \theta \right)\sum_{i=1}^n t _ { j } ( x_i ) \right)\\
  &\equiv\prod h ( x_i ) c^n ( \theta ) \exp \left( \sum _ { j = 1 } ^ { k } w _ { j } \left( \theta \right)T_j(x^n) \right)
  \end{align*}
  $$

- 统计量：
  $$
  T ( X ) = \left( \sum _ { i = 1 } ^ { n } t _ { 1 } \left( X _ { i } \right) , \ldots , \sum _ { i = 1 } ^ { n } t _ { k } \left( X _ { i } \right) \right)\equiv\left(  T_1(X^n), \ldots , T_k(X^n)\right)
  $$
  是充分统计量（因子化定理）；只要参数空间包含 $\mathbb{R}^k$ 中的一个开集（有内点，正常模型几乎都满足），则它也是完备统计量

- 例：正态分布
  $$
  \begin{align*}
  f(x^n;\theta)&=(2\pi\sigma^2)^{-n/2}\exp\left[-\frac{\sum(x_i-\mu)^2}{2\sigma^2}\right]\\
  &=(2\pi\sigma^2)^{-n/2}\exp\left(-\frac{n\mu^2}{2\sigma^2}\right)\exp\left[-\frac{n}{2\sigma^2}\frac{\sum x_i^2}{n}+\frac{n\mu}{2\sigma^2}\overline x\right]
  \end{align*}
  $$
  得到 $\frac{1}{n}\sum X_i^2$ 和 $\overline X ​$ 是完备的充分统计量



### 似然性原则

在对 $\theta$ 进行推断和决策时，所有相关的信息都包含在样本的似然函数中

- 如果两个似然函数成比例（$\theta$ 的函数），则它们含有 $\theta$ 的信息相同——两个似然函数是对同一个参数而言的
- 所有有关 $\theta$ 的**实验**结论或证据都来自实际观测到的样本，其他信息还包括先验信息和损失等



### 等价性原则

如果 $Y=g(X)$ 仅仅是一种测量尺度的变换，$X$ 和 $Y$ 的模型的内在结构是一样的，那么推断过程应该是等价的

- $X$ 满足二项分布，为了估计 $p$ ，可以用成功的次数 $X$ ，也可以用失败的次数 $Y=n-X$ ，它们满足一样的分布，因而是等价的