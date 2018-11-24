# Chapter 7. Two Sample Comparisons 两个样本的比较



## 两个样本的比较

在许多实验中，两个样本都被认为是独立的



### 引理

- 令 $X _ { 1 } , \ldots , X _ { n }$ 是来自正态分布的随机样本，则：
  1. 均值和方差是独立随机样本
  2. $\overline { X } \sim N \left( \mu , \sigma ^ { 2 } / n \right)$
  3. $( n - 1 ) S ^ { 2 } / \sigma ^ { 2 }\sim\chi^2_{n-1}$



## 参数方法



### t 检验

- 可以利用 t 检验比较两个样本的均值（$H_0: \mu_X=\mu_Y$），但必须假设两个样本方差相同

- 对于两个样本，$\overline { X } \sim N \left( \mu , \sigma ^ { 2 } / n \right)$ ，$\overline { Y } \sim N \left( \mu , \sigma ^ { 2 } / m \right)$ ，$( n - 1 ) S _ { X } ^ { 2 } / \sigma ^ { 2 }\sim\chi^2_{n-1}$，$( m - 1 ) S _ { Y } ^ { 2 } / \sigma ^ { 2 }\sim\chi^2_{m-1}$ ，且互相独立

- 定义：
  $$
  U = \frac { \overline { X } - \overline { Y } - \left( \mu _ { X } - \mu _ { Y } \right) } { \sigma \sqrt { 1 / n + 1 / m } }\sim N(0,1)
  $$

  $$
  V = \sqrt { \left[ \frac { ( n - 1 ) S _ { X } ^ { 2 } } { \sigma ^ { 2 } } + \frac { ( m - 1 ) S _ { Y } ^ { 2 } } { \sigma ^ { 2 } } \right] \frac { 1 } { m + n - 2 } },\\\text{ where } \frac { ( n - 1 ) S _ { X } ^ { 2 } } { \sigma ^ { 2 } } + \frac { ( m - 1 ) S _ { Y } ^ { 2 } } { \sigma ^ { 2 } }\sim\chi^2(m+n-2)
  $$

  构造统计量为：$T=U/V\sim t_{n+m-2}$

- 置信区间：

  $\mu_X - \mu_Y$ 的一个 $1-\alpha$ 置信区间为：
  $$
  \overline { X } - \overline { Y } \pm S \sqrt { 1 / n + 1 / m } t _ { n + m - 2 } ( 1 - \alpha / 2 )
  $$
  这里的 $S$ 相当于总体的标准差：
  $$
  S = \sqrt { \left[  { ( n - 1 ) S _ { X } ^ { 2 } }  + { ( m - 1 ) S _ { Y } ^ { 2 } }  \right] \frac { 1 } { m + n - 2 } }
  $$

- 如果方差相同的假设不成立——Behrens Fisher problem：

  - 大样本情况下，依然可以由中心极限定理和正态分布的性质得到：
    $$
    \overline { X } - \overline { Y } \approx N \left( \mu _ { X } - \mu _ { Y } , \frac { \sigma _ { X } ^ { 2 } } { n } + \frac { \sigma _ { Y }^2 } { m } \right)
    $$
    进而给出 $\mu _ { X } - \mu _ { Y }$ 的 $1-\alpha$ 置信区间，$S = \sqrt { S _ { X } ^ { 2 } / n + S _ { Y } ^ { 2 } / m }$：
    $$
    \overline { X } - \overline { Y } \pm S Z _ { 1 - \alpha / 2 }
    $$

  - 如果甚至不满足大样本情况：
    $$
    U = \frac { \overline { X } - \overline { Y } } {  \sqrt { S_X^2 / n + S_Y^2 / m } }\sim t(v)
    $$
    其中 $v$ 为离 $v^*$ 最近的整数：
    $$
    v = \frac { \left( S _ { X } ^ { 2 } / n + S _ { Y } ^ { 2 } / m \right) ^ { 2 } } { \left( S _ { X } ^ { 2 } / n \right) ^ { 2 } / \left( n  + 1 \right) + \left( S _ { Y } ^ { 2 } / m \right) ^ { 2 } / \left( m + 1 \right) } - 2
    $$


    - Fisher’s Fiducial approach
    - Bayesian approach



### F 检验

- 可以用 F 检验比较两个样本的方差（$H_0: \sigma_X^2=\sigma_Y^2$）

- F 统计量表示为样本方差的比，满足 F 分布（两个独立卡方分布之比）：
  $$
  F = \frac { S _ { X } ^ { 2 } } { S _ { Y } ^ { 2 } } \sim F _ { n  - 1 , m - 1 }
  $$

- $1-\alpha$ 置信区间

  - 双侧（$H_1: \sigma_X^2\neq\sigma_Y^2$）：$F_{n-1,m-1;\alpha/2}<F<F_{n-1,m-1;1-\alpha/2}$

    其中 $F_{n-1,m-1;\alpha/2}\cdot F_{n-1,m-1;1-\alpha/2}=1$

  - 单侧

    - 若 $H_1: \sigma_X^2>\sigma_Y^2$：$F<F_{n-1,m-1;1-\alpha}$
    - 若 $H_1: \sigma_X^2<\sigma_Y^2$：$F>F_{n-1,m-1;\alpha}$



### 配对的 t 检验

- $Z _ { i } = \left( X _ { i } , Y _ { i } \right)$ 是独立同分布的，检验 $H _ { 0 } : \mu _ { X } = \mu _ { Y }$

- 等价于对于 $D_i=X_i-Y_i$ ，检验 $H _ { 0 } : \mu _ { X } - \mu _ { Y }=\mu_D=0$

- t 统计量：
  $$
  t = \frac { \overline { D } _ { n } - \mu _ { D } } { S _ { \overline { D } _ { n } } } \sim t _ { n - 1 }
  $$






## 非参方法

- 非参方法不假设数据服从特定的分布，很多都基于对数据顺序的改变
- 仅仅涉及各数据之间相对大小，对原数据作任何单调变换之后，比较的结果保持不变
- 减小了离群值的影响



### Mann-Whitney 检验

- $X _ { 1 } , \ldots , X _ { n }\sim F$，$Y _ { 1 } , \ldots , Y _ { m }\sim G$，$H _ { 0 } : F = G$ 
- 零假设下，这 $m+n$ 个观测量的任何一种排列都是等可能的
- 这里已经假设了不同观测之间两两不等；如果有少量的观测值相等，它们的秩全部取为平均值，对 $\alpha$ 不会有显著影响



#### 第一种视角

- 定义 $T_Y$ 为 $Y _ { 1 } , \ldots , Y _ { m }$ 的秩和

- 零假设下：
  $$
  E \left( T _ { Y } \right) = \frac { m ( m + n + 1 ) } { 2 } , \operatorname { Var } \left( T _ { Y } \right) = \frac { m n ( m + n + 1 ) } { 12 }
  $$






- 证明：根据抽样调查理论：
  $$
  E \left( T _ { Y } \right) = m \mu , \operatorname { Var } \left( T _ { Y } \right) = m \sigma ^ { 2 } \frac { N - m } { N - 1 }
  $$
  $N=m+n$ ，$\mu，\sigma^2$ 是总体中某一个元素的均值和方差：
  $$
  \mu=\frac{1}{N}\sum_{k=1}^N k=\frac{N+1}{2}
  $$

  $$
  \begin{align*}
  \sigma^2&=\frac{1}{N}\sum_{k=1}^N (k-\mu)^2=\frac{1}{N}\sum_{k=1}^N k^2-\mu^2\\
  &=\frac{(N+1)(2N+1)}{6}-\frac{(N+1)^2}{4}\\&
  =\frac{(N+1)(N-1)}{12}
  \end{align*}
  $$

  直接代入就证明了上述结果

- $n$ 足够大时：
  $$
  \frac { T _ { Y } - E \left( T _ { Y } \right) } { \sqrt { \operatorname { Var } \left( T _ { Y } \right) } } \sim N ( 0,1 )
  $$
  可以据此构造检验



#### 第二种视角

- 考虑 $\pi=P(X<Y)$， $H_0：\pi=1/2$

- 定义统计量：
  $$
  \widehat { \pi } = \frac { 1 } { m n } \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } Z _ { i j }\equiv\frac { 1 } { m n } \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } I(X_i<X_j)
  $$






- 容易证明：
  $$
  \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m } Z _ { i j } = \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m } V _ { i j }\equiv \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m } I(X_{(1)}<X_{(j)})
  $$

  $$
  \sum _ { j = 1 } ^ { m } V _ { i j } = T _ { Y } - \frac { m ( m + 1 ) } { 2 }
  $$

  $$
  \Rightarrow \widehat { \pi }=\frac{1}{mn}\left(T _ { Y } - \frac { m ( m + 1 ) } { 2 }\right)
  $$






### 符号秩检验

- 可以对**成对**的样本构造符号秩检验

  - 计算 $D_i=Y_i-X_i$ 和 $|D_i|$ 的秩，其中如果有多个 $|D_i|$ 相等，将其秩取为平均——这样的情况不太多的时候，$\alpha$ 受的影响不大，否则要作修正
  - 若 $D_i>0$ ，记秩的符号为正；若 $D_i<0$ ，记秩的符号为为负；若恰好为零，一般把这组数据点丢弃
  - 记符号秩的和为 $W_+$

- 零假设下 $D_i$ 对称分布在零点两侧，可以证明：
  $$
  E \left( W _ { + } \right) = \frac { n ( n + 1 ) } { 4 } , \operatorname { Var } \left( W _ { + } \right) = \frac { n ( n + 1 ) ( 2 n + 1 ) } { 24 }
  $$

- 证明：

  - 将 $W_+$ 写成：
    $$
    W _ { + } = \sum _ { k = 1 } ^ { n } k I _ { k }\equiv\sum _ { k = 1 } ^ { n } k I(D_k>0)
    $$
    $k$ 是第 $k$ 大的 $|D_i|$ 的下标

  - 零假设下，$I_k\sim Bernoulli(1/2)​$ ，有：

     $$
     E \left( l _ { k } \right) = 1 / 2 , \operatorname { Var } \left( I _ { k } \right) = 1 / 4
     $$

     推出：
     $$
     { E \left( W _ { + } \right) = \frac { 1 } { 2 } \sum _ { k = 1 } ^ { n } k = \frac { n ( n + 1 ) } { 4 } } \\ { \operatorname { Var } \left( W _ { + } \right) = \frac { 1 } { 4 } \sum _ { k = 1 } ^ { n } k ^ { 2 } = \frac { n ( n + 1 ) ( 2 n + 1 ) } { 24 } }
     $$



