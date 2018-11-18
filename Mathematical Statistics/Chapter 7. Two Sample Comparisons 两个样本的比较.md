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
  U = \frac { \overline { X } - \overline { Y } - \left( \mu _ { X } - \mu _ { Y } \right) } { \sigma \sqrt { 1 / n + 1 / m } }
  $$

  $$
  V = \sqrt { \left[ \frac { ( n - 1 ) S _ { X } ^ { 2 } } { \sigma ^ { 2 } } + \frac { ( m - 1 ) S _ { Y } ^ { 2 } } { \sigma ^ { 2 } } \right] \frac { 1 } { m + n - 2 } }
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
    \overline { X } - \overline { Y } \approx N \left( \mu _ { x } - \mu _ { Y } , \frac { \sigma _ { X } ^ { 2 } } { n } + \frac { \sigma _ { Y }^2 } { m } \right)
    $$
    进而给出 $\mu _ { X } - \mu _ { Y }$ 的 $1-\alpha$ 置信区间，$S = \sqrt { S _ { X } ^ { 2 } / n + S _ { Y } ^ { 2 } / m }$：
    $$
    \overline { X } - \overline { Y } \pm S Z _ { 1 - \alpha / 2 }
    $$

  - 如果甚至不满足大样本情况：

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

- 这里已经假设了不同观测之间没有联系；如果有少量的关联，相关的观测量的秩全部取为平均值，对 $\alpha​$ 不会有显著影响

- 定义 $T_Y$ 为 $Y _ { 1 } , \ldots , Y _ { m }$ 的秩和

- 零假设下：
  $$
  E \left( T _ { Y } \right) = \frac { m ( m + n + 1 ) } { 2 } , \operatorname { Var } \left( T _ { Y } \right) = \frac { m n ( m + n + 1 ) } { 12 }
  $$

