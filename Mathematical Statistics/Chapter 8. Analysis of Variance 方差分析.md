# Chapter 8. Analysis of Variance 方差分析



## ANOVA

- 用于两个及两个以上样本均数差别的显著性检验，假定每个总体服从正态分布
- 如何从更少的观测中得到更多总体的更多信息？
- 不假设任何参数上的联系



### One-way ANOVA

- 假设样本中的数据 $Y_{ij}=\beta _ { i } + \epsilon _ { i j }$ ，其中 $i=1,\cdots,I$ 为组号，$j=1,\cdots,n_i$ 为第 $i$ 组的样本数，$\theta_i=\beta_i$ 是我们未知的参数，而 $\epsilon_i$ 是误差随机变量

- 也可以假设 $Y_{ij}=\mu+\tau_i + \epsilon _ { i j }$，$\mu$ 是可以认为是整体的均值，而 $\tau_i$ 是第 $i$ 组处理后的独有效果，实际上我们只能估计 $\mu+\tau_i$ 的值，除非我们规定 $\sum\tau_i=0$ 

- 进一步，我们作两个假设：
  1. $E \left( \epsilon _ { i j } \right) = 0$ （从而有 $E \left( Y _ { i j } \right) = \theta _ { i }$），$\operatorname { Var } \left( \epsilon _ { i j } \right) = \sigma _ { i } ^ { 2 } < \infty$，$\operatorname { Cov } \left( \epsilon _ { i j } , \epsilon _ { i ^ { \prime } j } ^ { \prime } \right) = 0$ 若 $(i,j)\neq(i',j')$
  2. $\epsilon_{ij}$ 独立且正态分布，$\sigma_i\equiv\sigma$

- 不假设 $\epsilon_{ij}$ 的分布我们只能作点估计；如果我们假设除了正态分布之外的其他分布，区间估计和检验会非常困难，当然在样本很大的时候可以用中心极限定理；方差相等也很重要

- 如果数据不满足这两条假设，可以使用一些变换，比如Box-Cox变换

  > Box-Cox 变换
  > $$
  > y _ { i } ^ { ( \lambda ) } = \left\{ \begin{array} { l l } { \frac { y _ { i } ^ { \lambda } - 1 } { \lambda } } & { \text { if } \lambda \neq 0 } \\ { \ln y _ { i } } & { \text { if } \lambda = 0 } \end{array} \right.
  > $$
  >

- 经典的ANOVA假设：
  $$
  H _ { 0 } : \theta _ { 1 } = \cdots = \theta _ { l } \text { versus } H _ { 1 } : \theta _ { i } \neq \theta _ { j } \text { for some } i \neq j
  $$

- 总离差平方和、组间离差平方和、组内离差平方和
  $$
  \begin{align*}
  \sum _ { i = 1 } ^ { I } \sum _ { j = 1 } ^ { n _ { i } } S S _ { T O T } &= \sum _ { i = 1 } ^ { 1 } \sum _ { j = 1 } ^ { n _ { n } } \left( Y _ { i j } - \overline { Y } _ {\cdot\cdot } \right) ^ { 2 }\\
  &= \sum _ { i = 1 } ^ { I } \sum _ { j = 1 } ^ { n _ { i } } \left( Y _ { i j } - \overline { Y } _ { i \cdot } \right) ^ { 2 } + \sum _ { i = 1 } ^ { 1 } n _ { i } \left( \overline { Y } _ { i } - \overline { Y }_{\cdot\cdot} \right) ^ { 2 }\\
  &\equiv S S _ { W } + S S _ { B }
  \end{align*}
  $$
  $SS_W$ 反应组内数据的方差，$SS_B$ 反应不同组均值之间的方差

- 定理 A
  $$
  E \left( S S _ { W } \right) = \sum _ { i = 1 } ^ { I } \left( n _ { i } - 1 \right) \sigma ^ { 2 }\\
  \begin{aligned} E \left( S S _ { B } \right) & = \sum _ { i = 1 } ^ { I } n _ { i } E \left( \overline { Y } _ { i \cdot } - \overline { Y } _ { \cdot\cdot } \right) ^ { 2 } \\ & = \sum _ { i = 1 } ^ { I } n _ { i } \tau _ { i } ^ { 2 } + ( I - 1 ) \sigma ^ { 2 } \end{aligned}
  $$
  据此可以估计方差 $\sigma^2$：

  - 利用 $SS_W$：
    $$
    {\widehat\sigma^2}  = \frac { S S _ { W } } { \sum _ { i = 1 } ^ { l } \left( n _ { i } - 1 \right) }
    $$

  - 利用 $SS_B$ ，并假设 $\tau_i=0$：
    $$
    {\widehat\sigma^2}  =\frac{SS_B}{I-1}
    $$
    如果有些 $\tau_i$ 不为 $0$ ，则 $SS_B$ 会偏大，偏离零假设

  接下来就可以构造检验统计量，检验零假设 $\tau_i$ 全部相同（为 $0$ ）

- 定理 B

  不失一般性，假设 $n_i\equiv J$ ，则有：

  - $S S _ { W } / \sigma ^ { 2 } \sim \chi _ { I( J - 1 ) } ^ { 2 }$
  - 如果 $\theta_i$ 均相等，也即 $\tau_i$ 均相等，$S S _ { B } / \sigma ^ { 2 } \sim \chi _ { I - 1 } ^ { 2 }$ ，且与 $SS_W$ 独立

- 定理 C

  统计量
  $$
  F = \frac { S S _ { B } / ( I - 1 ) } { S S _ { W } / [ I ( J - 1 )] }\sim F(I-1,N-I)
  $$
  可以用来检验零假设

  - p 值：$P ( X > F )$ 
  - 在正态分布假设下，F 检验等价于似然比检验

- One-way ANOVA 表：

  | 方差的来源 | 自由度 | 离差平方和       | 均值的平方     | F 统计量     |
  | ---------- | ------ | ---------------- | ---- | ---- |
  | 组内       | $k-1$  | $SS_B$           | $MSB=SS_B/(k-1)$ | $MSB/MSW$ |
  | 组间       | $N-k$  | $SS_W$           | $MSW=SS_W/(N-k)$ |      |
  | 总和       | $N-1$  | $SS_T=SS_B+SS_W$ |      |  |

- ANOVA 的不足：
  - F 检验能够提供的信息太少，只能判断多组样本的均值是否相同，不能给出差别的具体表现
  - 一种naive的处理方式是对任意两组进行 level-$\alpha$ t 检验，困难在于当组别很多时，至少得到一组显著结果的概率会变得很大，即总体的 $\alpha$ 会很大，容易犯 Type I 错误
- Bonferroni Correction：把每一次 t 检验的显著性水平取为 $\alpha/n$ ，$n$ 为 t 检验的个数（即零假设的个数）——太保守，假设了各检验彼此独立



### Tukey’s method

- 用于为各对数据均值的区别构造置信区间，使各个区间同时拥有一个区间概率——定出有显著区别的数据对

- 如果各组样本容量相同，误差服从正态分布，则 $\overline { Y } _ {{ i }\cdot} - \mu _ { i }\sim N(0,\sigma ^ { 2 } / J)$ ，可以用 $s_p^2/J$ 估计

- Student-Range 统计量
  $$
  \max _ { i _ { 1 } , i _ { 2 } } \frac { \left| \left( \overline { Y } _ { i _ { 1 } \cdot} - \mu _ { i _ { 1 } } \right) - \left( \overline { Y } _ { i _ { 2 }\cdot } , - \mu _ { i _ { 2 } } \right) \right| } { s _ { p } / \sqrt { J } }
  $$
  这里的最大值是在所有可能的样本对中取得的，这个分布被称为 Studentized Range Distribution，参数为 $I,I(J-1)$

- $\mu _ { i _ { 1 } } - \mu _ { i _ { 2 } }$ 的 $1-\alpha$ 置信区间：
  $$
  \left( \overline { Y } _ { i _ { 1 } \cdot} - \overline { Y } _ { i _ { 2 }\cdot }  \right) \pm q _ { I : I( J - 1 ) } ( \alpha ) \frac { s _ { p } } { \sqrt { J } }
  $$

- level-$\alpha$ 测试：

  $H_0:\mu _ { i _ { 1 } } - \mu _ { i _ { 2 } }=0$ 的拒绝域 $\mathcal{R}$：
  $$
  \mathcal{R}=\left\{(i_1,i_2)\bigg |\left| \overline { Y } _ { i _ { 1}\cdot  } - \overline { Y } _ { i _ { 2}  \cdot } \right| > q _ { I : I( J - 1 ) } ( \alpha ) \frac { s _ { p } } { \sqrt { J } }\right\}
  $$





## 非参方法——Kruskal-Wallis检验

- 继承自 Mann-Whitney 检验

- 令 $R_{ij}$ 表示 $Y_{ij}$ 的秩，$\overline { R } _ { i \cdot } = \frac { 1 } { J _ { i } } \sum _ { j = 1 } ^ { J _ { i } } R _ { i j }$ 为第 $i$ 组秩的均值，$\overline R_{\cdot\cdot}$ 为总的均值，是定值 $(N+1)/2$

- 令：
  $$
  S S _ { B } = \sum _ { i = 1 } ^ { 1 } J _ { i} \left( \overline { R } _ { i\cdot  } - \overline { R } _{\cdot\cdot} \right) ^ { 2 }
  $$
  它可以衡量 $\overline { R } _ { i \cdot } $ 的离散程度，进而检验零假设；$SS_B$ 越大，越不支持零假设

- 在零假设下，各个组的分布相同，有：
  $$
  K = \frac { 12 } { N ( N + 1 ) } S S _ { B }=\frac { 12 } { N ( N + 1 ) } \sum _ { i = 1 } ^ { I } J _ { i } \overline { R } _ { i \cdot } ^ { 2 } - 3 ( N + 1 )
  $$
  近似是自由度为 $I-1$ 的卡方分布