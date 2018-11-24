# Chapter 5. Hypothesis Testing 假设检验



## 假设检验

- 假设检验是一个明确的规则，给出：
  - 对于怎样的样本接受 $H_0$
  - 对于怎样的样本拒绝 $H_0$ 或者接受 $H_1$ ——拒绝前者不代表接收后者
- 拒绝域：对应着拒绝 $H_0$ 的样本空间的子集

- Type I & Type II 错误：

  - 在假设检验中考虑的不是零假设是否正确，而是我们有没有足够的证据**拒绝**零假设

    |            | 接受 $H_0$   | 拒绝 $H_0$  |
    | ---------- | ------------ | ----------- |
    | $H_0$ 为真 |              | Type I 错误 |
    | $H_1$ 为真 | Type II 错误 |             |

- 步骤：

  - 选择测试统计量 $T_n= T _ { n } \left( X _ { 1 } , \ldots , X _ { n } \right)$
  - 选择拒绝域 $\mathcal{R}$
  - 如果 $T _ { n } \in \mathcal { R }$ ，拒绝零假设，否则接受零假设



### 统计功效

- 功效函数：

$$
\beta ( \theta ) = P _ { \theta } \left( T _ { n } \left( X _ { 1 } , \ldots , X _ { n } \right) \in \mathcal { R } \right)
$$

- 含义：当 $\theta\in\Theta_0$ 的时候，犯 Type I 错误的概率为 $\beta(\theta)$ ；当 $\theta\in\Theta_1$ 的时候，犯 Type II 错误的概率为 $1-\beta(\theta)$

- 我们希望构建一个拒绝域，当 $\theta\in\Theta_0$ 的时候 $\beta(\theta)$ 很小（不容易拒绝 $H_0$ ），当 $\theta\in\Theta_1$ 的时候 $\beta(\theta)$ 很大（不容易接受 $H_0$ ）

- 做法：

  - 固定一个 $\alpha$ （比如等于 $0.05$ ）
  - 在 $\beta(\theta)\le\alpha$ 对于 $\theta\in\Theta_0$ 恒成立时，使 $\beta(\theta)$ 在 $\theta\in\Theta_1$ 上取最大

- size $\alpha$ ：相当于犯 Type I 错误的概率的上界
  $$
  \sup _ { \theta \in \Theta _ { 0 } } \beta ( \theta ) = \alpha
  $$

- level $\alpha$
  $$
  \sup _ { \theta \in \Theta _ { 0 } } \beta ( \theta ) \leq \alpha
  $$

- 无偏测试：
  $$
  \beta \left( \theta ^ { \prime } \right) \geq \beta \left( \theta ^ { \prime \prime } \right) \text { for every } \theta ^ { \prime } \in \Theta _ { 1 } \text { and } \theta ^ { \prime \prime } \in \Theta _ { 0 }
  $$

- 例：正态分布，方差已知

  - 零假设和备假设：
    $$
    H _ { 0 } : \theta = \theta _ { 0 } \text { v.s. } H _ { 1 } : \theta > \theta _ { 0 }
    $$

  - 拒绝域：
    $$
    \mathcal{R}=\left\{T_n>c\Bigg|T _ { n } = \frac { \overline { X } _ { n } - \theta _ { 0 } } { \sigma / \sqrt { n } }\right\}
    $$

  - 功效函数：
    $$
    \beta ( \theta ) = P _ { \theta } \left( \frac { \overline { X } _ { n } - \theta _ { 0 } } { \sigma / \sqrt { n } } > c \right) = P _ { \theta } \left( \frac { \overline { X } _ { n } - \theta } { \sigma / \sqrt { n } } > c + \frac { \theta _ { 0 } - \theta } { \sigma / \sqrt { n } } \right)= 1 - \Phi \left( c + \frac { \theta _ { 0 } - \theta } { \sigma / \sqrt { n } } \right)
    $$





  - 为了得到一个 size-$\alpha$ 的检验
    $$
    \alpha=\sup _ { \theta \in \Theta _ { 0 } } \beta ( \theta ) = \beta \left( \theta _ { 0 } \right) = 1 - \Phi ( c )
    $$
    可以解出 $c$



## 检验方法



### 似然比检验 (LRTs)

- 零假设和备假设：
  $$
  H _ { 0 } : \theta \in \Theta _ { 0 }\text { versus } H _ { 1 } : \theta \in \Theta _ { 1 }
  $$

- LRT 统计量：
  $$
  \lambda ( x ) = \frac { \sup _ { \theta \in \Theta _ { 0 } } L ( \theta | x ) } { \sup _ { \theta \in \Theta } L ( \theta | x ) }
  $$

- 当 $\lambda(x)\le c$ 时拒绝零假设——在零分布下，出现观测到的样本的最大概率太小了

- 对于 size-$\alpha$ 的检验，$c$ 由下式给出：
  $$
  \sup _ { \theta \in \Theta _ { 0 } } P _ { \theta } ( \lambda ( \mathbf { X } ) \leq c ) = \alpha
  $$
  


#### LRTs 和充分性

- 考虑用充分统计量 $T(X)$ 和它的似然函数 $L ^ { * } ( \theta | t )$ （而非样本的似然函数 $L  ( \theta | x )$ ）来构造似然比
- 可以证明 $\lambda ^ { * } ( T ( x ) ) = \lambda ( x )$ （用因子化定理）



#### 冗余参数

- LRTs 可以帮助处理含有不感兴趣参数的情况

- 例：正态分布，我们对 $\mu$ 感兴趣但不关心 $\sigma^2$

  - $H _ { 0 } : \mu = \mu _ { 0 } \text { versus } H _ { 1 } : \mu \neq\mu _ { 0 }$

  - 可以这样写似然比：
    $$
    \lambda \left( x _ { 1 } , \ldots , x _ { n } \right) = \frac { L \left( \mu _ { 0 } , \widehat { \sigma } _ { 0 } \right) } { L ( \widehat { \mu } , \widehat { \sigma } ) }
    $$
    其中 $\widehat\sigma_0$ 在 $\mu=\mu_0$ 时把似然函数最大化，$\widehat\sigma_0$ 在 $\mu\in(-\infty,\infty)$ 时把似然函数最大化

  - 在 $\lambda \left( x _ { 1 } , \dots , x _ { n } \right) < c$ 时拒绝原假设，这等价于 $\left| T _ { n } \right| > k$ ，$k$ 是一个常数，而：
    $$
    T _ { n } = \frac { \overline { X } - \mu _ { 0 } } { S / \sqrt { n } }
    $$
    满足 $n-1$ 维的 t 分布

  - size-$\alpha$ 的检验：当 $\left| T _ { n } \right| > t _ { n - 1 , \alpha / 2 }$ 时（注意 t 分布要考虑双侧，作为对比，卡方分布只要考虑单侧）拒绝零假设—— Student’s t-test



#### LRTs 的渐近分布

- 有时我们无法给出 LRT 的分布，为了得到 size-$\alpha$ 的检验，需要用到渐近分布
- 在零假设下，$T _ { n } = - 2 \log \lambda \left( x _ { 1 } , \ldots , x _ { n } \right) \stackrel { d } { \rightarrow } \chi _ { r } ^ { 2 }$ ，其中 $r = \operatorname { dim } ( \Theta ) - \operatorname { dim } \left( \Theta _ { 0 } \right)$

- 渐近的 size-$\alpha$ 的检验：当 $T _ { n } > \chi _ { r , 1 - \alpha } ^ { 2 }$ 时拒绝零假设



### Neyman-Pearson 检验

- uniformly most powerful (UMP) 检验：

  对于任意的 $\theta\in\Theta_1$ ，功效函数都不小于任何其他 (level-$\alpha$) 检验的功效函数

- 简单零假设和备假设：$H _ { 0 } : \theta = \theta _ { 0 } \text { versus } H _ { 1 } : \theta = \theta _ { 1 }$

- Neyman-Pearson 定理

  - $$
    T _ { n } = \frac { L \left( \theta _ { 1 } \right) } { L \left( \theta _ { 0 } \right) }
    $$

  - 当 $T _ { n } > k$ 时拒绝零假设，$k$ 满足 $P _ { \theta _ { 0 } } \left( T _ { n } > k \right) = \alpha$

  - 这个检验是 UMP level-$\alpha$ 检验



### Wald 检验——适合无约束的模型

- 对于 $p$ 维的 MLE $\hat\theta$ ，大样本下有：
  $$
  \sqrt { n } ( \widehat { \theta } - \theta ) \stackrel { d } { \rightarrow } T \sim N _ { p } \left( 0 , \mathcal { I } ( \theta ) ^ { - 1 } \right)
  $$
  Fisher Information Matrix 如下：
  $$
  \mathcal { I } ( \theta )_{ij} = E \left( - \frac { \partial ^ { 2 } } { \partial \theta _ { i } \partial \theta _ { j } } \log f ( X | \theta ) \right)
  $$





- Cramer-Wald 定理：
  $$
  X _ { n } \stackrel { d } { \rightarrow }X\iff a ^ { T } X _ { n } \stackrel { d } { \rightarrow } a ^ { T } X \text { for all } a \in \mathcal { R } ^ { p }
  $$

- Slutsky 定理：

  对于任意随机向量 $X_n$ 和 $Y_n$ 和任意常数 $c$
  $$
  X _ { n } \stackrel { d } { \rightarrow } X, Y _ { n } \stackrel { P } { \rightarrow } c\Rightarrow\left( \begin{array} { l } { X _ { n } } \\ { Y _ { n } } \end{array} \right) \stackrel { d } { \rightarrow } \left( \begin{array} { l } { X } \\ { c } \end{array} \right)
  $$

- 可能的零假设

  - $C$ 是 $r \times p$ 的**满秩**矩阵，$\theta$ 是 $p\times1$ 向量，$h$ 是一个已知的 $r\times1$ 向量

  - $H _ { 0 } : C \theta = h$

  - 例（把零假设写成矩阵形式）：
    $$
    \theta _ { 1 } = \theta _ { 2 } , \quad \theta _ { 1 } = \theta _ { 3 }\iff\left[ \begin{array} { c c c } { 1 } & { - 1 } & { 0 } \\ { 1 } & { 0 } & { - 1 } \end{array} \right] \theta = \left[ \begin{array} { l } { 0 } \\ { 0 } \\ { 0 } \end{array} \right]
    $$

- Wald 检验：

  - 令 $\widehat { \mathcal { I } ( \theta ) } \stackrel { P } { \rightarrow } \mathcal { I } ( \theta )​$ ，零假设 $H _ { 0 } : C \theta = h​$ 为真
  - Wald 统计量：$W _ { n } = n ( { C } \widehat { \theta } - h ) ^ { \prime } \left( \mathcal { C } \widehat { \mathcal { I } ( \theta ) } C ^ { \prime } \right) ^ { - 1 } ( C \widehat { \theta } - h )$
  - 零假设下：$W _ { n } \stackrel { d } { \rightarrow } \chi ^ { 2 } ( r )$
  - $W_n>\chi _ { r , 1 - \alpha } ^ { 2 }$ 时拒绝零假设



### Score 检验——适合有约束的模型

- Observed Fisher Information 和相合估计量

  - Fisher information 需要计算期望，非常不便

  - 从样本出发，可以得到：
    $$
    \mathcal { J } _ { n } ( \theta )_{ij} = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } - \frac { \partial ^ { 2 } } { \partial \theta _ { i } \partial \theta _ { j } } \log f \left( X _ { i } | \theta \right)
    $$

  - 由强大数定律：
    $$
    \mathcal { J } _ { n } ( \theta ) \stackrel { \text { a.s. } } { \longrightarrow } \mathcal { I } ( \theta )
    $$

  - 可以证明：
    $$
    \mathcal { J } _ { n } ( \hat { \theta } ) \stackrel { \text { a.s. } } { \rightarrow } \mathcal { I } ( \theta )
    $$





- Score 检验

  - $\widehat\theta$ 是 $k\times1$ 的 MLE

  - $H _ { 0 } : \theta = \theta _ { 0 }$ ，$\widehat\theta_0$ 是零假设下的 MLE

  - 由 Score 函数定义：
    $$
    S ( \theta ) =  \frac { \partial l } { \partial \theta },\quad S ( \hat { \theta } ) = 0
    $$

  - 零假设下， $S \left( \widehat { \theta } _ { 0 } \right) \stackrel { d } { \rightarrow } N _ { k } ( 0 , \mathcal { J } )$

  - Score 检验统计量：
    $$
    T _ { n } = S \left( \widehat { \theta } _ { 0 } \right) ^ { \prime } \mathcal { J } ^ { - 1 } \left( \widehat { \theta } _ { 0 } \right) ^ { - 1 } S \left( \widehat { \theta } _ { 0 } \right) \stackrel { d } { \rightarrow } \chi ^ { 2 } ( r )
    $$
    $r$ 是 $H_0$ 约束的个数



### p 值

- p 值是我们拒绝 $H_0$ 的最小 $\alpha$（避免犯 Type II 错误），$\alpha>p$ 时我们拒绝零假设

- 有效的 p 值：对于 $\theta\in\Theta_0$ 和 $0<\alpha<1$ 有 $P _ { \theta } ( p ( X ) \leq \alpha ) \leq \alpha$

- p 值小给出 $H_1$ 正确的证据

- 一个（通常的）定义：

  - $W(X)$ 是一个统计量，大的 $W(X)$ 给出备假设正确的证据，则可以定义：
    $$
    p ( x ) = \sup _ { \theta \in \Theta _ { 0 } } P _ { \theta } ( W ( X ) \geq W ( x ) )
    $$
    此时的 p 值是有效的

  - 这个定义等价于在零分布下，比样本更糟糕的情况出现的概率

  - 在 $H_0$ 下，$p(X)\sim Uniform(0,1)$

- p 值的意义：

  - 我们希望在零假设错误时备假设是正确的
  - 我们无法证明备假设是正确的，但我们可以证明备假设比零假设更靠谱
  - 给定检验统计量的值和零分布，我们想看到这个值是在分布的中间（和零假设相符）还是在分布的尾上（备假设更可靠）
  - 有时我们会考虑单边的尾，有时则是双侧的，这主要由检验统计量和备假设的定义决定
  - p 值**不是零假设成立的概率**，而是在假设零假设成立的前提下计算一组新的样本的检验统计量（相同的公式，新的数据），得到的结果比原结果偏离更远



## 贝叶斯检验

- 贝叶斯检验把样本信息和先验信息结合在一起（利用贝叶斯公式），所有推断都建立在后验分布上

- 我们分别计算概率：
  $$
  \begin{array} { l } { P \left( \theta \in \Theta _ { 0 } | x \right) = P \left( H _ { 0 } \text { is true } | x \right) } \\ { P \left( \theta \in \Theta _ { 1 } | x \right) = P \left( H _ { 1 } \text { is true } | x \right) } \end{array}
  $$

- 贝叶斯假设检验：

  如果 $P \left( \theta \in \Theta _ { 0 } | x \right) \geq P \left( \theta \in \Theta _ { 1 } | x \right)$ 就接受零假设，否则拒绝

- 拒绝域：

  $\mathcal{R}=\left\{ x : P \left( \theta \in \Theta _ { 1 } | x \right) > 1 / 2 \right\}$

- 例：正态分布，$\theta$ 的先验分布也是正态分布，$H _ { 0 } : \theta \leq \theta _ { 0 } \text { versus }H _ { 1 } : \theta > \theta _ { 0 }$

  接受零假设的条件是：
  $$
  \overline { X } \leq \theta _ { 0 } + \frac { \sigma ^ { 2 } \left( \theta _ { 0 } - \mu \right) } { n \tau ^ { 2 } }
  $$




## 并交检验

- 零假设可能对应许多零假设的交集
  $$
  H _ { 0 } : \theta \in \bigcap _ { \gamma \in \Gamma } \Theta _ { \gamma }
  $$

- 设对于每一个 $\gamma$ ，$H _ { 0 \gamma } : \theta \in \Theta _ { \gamma } \text { versus } H _ { 1 \gamma } : \theta \in \Theta _ { \gamma } ^ { c }$ ，拒绝域为 $\left\{ x : T _ { \gamma } ( x ) \in \mathcal { R } _ { \gamma } \right\}$

- 整体的拒绝域为每一个子拒绝域的并集：
  $$
  \bigcup _ { \gamma \in \Gamma } \left\{ x : T _ { \gamma } ( x ) \in R _ { \gamma } \right\}
  $$

- 如果某一个 $H_{0\gamma}$ 被拒绝了，整体的零假设就被拒绝了



## 置换检验

- **非参**检验，不引入任何大样本**渐近**近似

- $X _ { 1 } , \ldots , X _ { n } \sim F,\quad Y _ { 1 } , \ldots , Y _ { m } \sim G$

- $H _ { 0 } : F = G \text { versus } H _ { 1 } : F \neq G$

- 定义 $Z = \left( X _ { 1 } , \ldots , X _ { n } , Y _ { 1 } , \ldots , Y _ { m } \right)$ 和标签 $L = ( 1 , \ldots , 1,2 , \ldots , 2 )$ ，$n$ 个 $1$ ，$m$ 个 $2$ ，可以利用它们来构造统计量，比如：
  $$
  T = \left| \overline { X } _ { n } - \overline { Y } _ { m } \right|=\left| \frac { \sum _ { i = 1 } ^ { N } Z _ { i } I \left( L _ { i } = 1 \right) } { \sum _ { i = 1 } ^ { N } I \left( L _ { i } = 1 \right) } - \frac { \sum _ { i = 1 } ^ { N } Z _ { i } I \left( L _ { i } = 2 \right) } { \sum _ { i = 1 } ^ { N } I \left( L _ { i } = 2 \right) } \right|
  $$
  $T$ 太大时拒绝零假设

- p 值
  $$
  p = \frac { 1 } { N ! } \sum _ { \pi } I \left( T \left( L _ { \pi } \right) > T ( L , Z ) \right)
  $$
  $L_\pi$ 是标签的一种排序，这里对所有可能的排序求和并除以排序总数

  零假设下的 $ T ( L , Z ) $ 是均匀分布，如果 p 值很小，则在零假设下我们观测到的样本出现概率非常小，考虑拒绝零假设

- 对所有排列进行检验运算量太大，常用的做法是随机抽取 $K$ 组，p 值为：
  $$
  p=\frac { 1 } { K } \sum _ { j = 1 } ^ { K } I \left( T ^ { ( j ) } > T \right)
  $$




