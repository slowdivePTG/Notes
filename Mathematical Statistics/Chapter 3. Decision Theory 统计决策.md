# Chapter 3. Decision Theory 统计决策



## 决策规则

- 统计决策：在观察到样本 $X$ 之后，我们采取的一个行为，例如关于总体 $P$ 的结论

- 行动空间：$A$ 是所有可能采取的行动的集合，$\mathcal { F } _ { A }$ 是一个 $A$ 上的 $\sigma-\text{ field}$，则可测空间 $( A , \mathcal { F } )$ 被称为行动空间

  > $\sigma-\text{field }\mathcal{F}$：
  >
  > - $\mathcal{F}$ 包含空集
  > - 如果 $E \in \mathcal { F } , E ^ { c } \in \mathcal { F }$
  > - 如果 $E _ { 1 } , E _ { 2 } , \dots , E _ { i } \in \mathcal { F },\cup _ { i = 1 } ^ { \infty } E _ { i } \in \mathcal { F }$

- 决策规则：从样本空间 $\left( \mathcal { X } , \mathcal { F } _ { X } \right)$ 到行动空间 $\left( A , \mathcal { F } _ { A } \right)$ 的一个可测函数 $T$ ，如果观测到 $X$ ，则采取行动 $T(X)$ 



## 损失函数

损失函数用来评价决策规则的优劣

- 单参数：$L ( \theta , \widehat { \theta } )$
  - 平方误差损失：$L ( \theta , \widehat { \theta } ) = ( \theta - \widehat { \theta } ) ^ { 2 }$
  - $L _ { p }$ 损失：$L ( \theta , \widehat { \theta } )=| \theta - \widehat { \theta } | ^ { p }$
  - $0-1$ 损失：$L ( \theta , \widehat { \theta } ) = 0 \text { if } \theta = \widehat { \theta } \text { or } 1 \text { if } \theta \neq \widehat { \theta }$
  - Kullback-Leibler损失：$L ( \theta , \widehat { \theta } ) = \int \log \left( \frac { p ( x ; \theta ) } { p ( x ; \widehat \theta ) } \right) p ( x ; \theta ) \text{d} x$

- 多参数（常用的）：
  $$
  L ( \theta , \widehat { \theta } ) = \| \theta - \widehat { \theta } \| ^ { 2 } = \sum _ { j = 1 } ^ { K } \left( \widehat { \theta } - \theta _ { j } \right) ^ { 2 }
  $$

  $$
  L ( \theta , \widehat { \theta } ) = \| \theta - \widehat { \theta } \| _ { p } = \left( \sum _ { j = 1 } ^ { K } \left( \widehat { \theta } - \theta _ { j } \right) ^ { p } \right) ^ { 1 / p }
  $$




- 随机化决策：按一定的概率取用决策空间中的决策



## 风险函数

损失函数依赖于样本，而估计量 $ \widehat\theta$ 的风险函数是损失函数的期望，是参数 $\theta$ 的函数
$$
R ( \theta , \widehat { \theta } ) = E _ { \theta } ( L ( \theta , \widehat { \theta } ) )= \int L \left( \theta , \widehat { \theta } \left( x _ { 1 } , \ldots , x _ { n } \right) \right) p \left( x _ { 1 } , \ldots , x _ { n } ; \theta \right) d x
$$

> 如果损失函数是平方误差的话，风险函数恰为MSE

- 最优规则

  - $\widehat{\theta}_1$ 同 $\widehat{\theta}_2$ 一样好：
    $$
    R \left( \theta , \widehat { \theta } _ { 1 } \right) \leq R \left( \theta , \widehat { \theta } _ { 2 } \right) \text { for any } P \in \mathcal { P }
    $$

  - $\widehat{\theta}_1$ 同 $\widehat{\theta}_2$ 等价：
    $$
    R \left( \theta , \widehat { \theta } _ { 1 } \right) = R \left( \theta , \widehat { \theta } _ { 2 } \right) \text { for any } P \in \mathcal { P }
    $$

  - 最优性：$\mathcal T$ 是一系列决策规则的集合，$T^*$ 是 $\mathcal T-$最优的，当且仅当 $T^*$ 和 $\mathcal T$ 中任意其他规则一样好——因为要对所有 $P$ 成立，实际不一定存在

  - 可容性：$\mathcal T$ 是一系列决策规则（随机化、非随机化）的集合，$T^*$ 是 $\mathcal T-$可容的，当且仅当 $\mathcal T$ 中没有任何规则比 $T^*$ 更好——或者 $T^*$ 是 $\mathcal T-$最优的，或者不存在最优决策

  - Rao-Blackwell 定理（不可容性）：

    - $T$ 是 $P \in \mathcal{P}$ 的充分统计量，$T_0$ 是一个期望有限的非随机化决策规则，$T_1$ 满足 $T _ { 1 } = E \left( T _ { 0 } ( X ) | T \right)$
    - 那么 $R(P, T_1 ) \le R(P, T_0 )$ ，任取 $P$
    - 如果损失函数 $L$ 严格下凸，$T_0$ 不是 $T$ 的函数，那么它不可容

  - 可以利用上述定理，找出不可容的决策并排除掉，但剩下来的决策可能依然很多——两种选择方法
    - 选择具有我们想要的一些特征（比如无偏性）的决策规则，再在其中选取最佳的
    - 对于一个给定的决策规则，考虑风险函数的一些特征（比如上界）$R(T)$ ，再将 $R(T)$ 最小化：
      - 贝叶斯规则
      - 极小化极大规则



### 不同估计量的比较方法：极大风险和贝叶斯风险



#### 极大风险

$$
\overline { R } ( \widehat { \theta } ) = \sup _ { \theta \in \Theta } R ( \theta , \widehat { \theta } )
$$

- 比较不同估计量风险函数取极大值的情况



##### 极小化极大估计量

- 极小化极大风险

$$
R _ { n } = \inf _ { \widehat { \theta } } \sup _ { \theta } R ( \theta , \widehat { \theta } )
$$

- 极小化极大估计量：
  $$
  \sup _ { \theta } R ( \theta , \widehat { \theta } ) = \underset { \hat\theta } { \inf } \sup _ { \theta } R ( \theta , \widehat { \theta } )
  $$

- 相当于选择所有决策中最糟糕的情况相对最好的一个

- 决策理论：

  - 找到极小化极大风险

  - 找到达到这个风险的估计量

    - 有时可以直接找

    - 有时只能找渐近的极小化极大估计量
      $$
      \sup _ { \theta \in \Theta } R \left( \theta , \widehat { \theta _ { n } } \right) \sim \inf _ { \tilde { \theta } } \sup _ { \theta \in \Theta } R ( \theta , \tilde { \theta } ) , \text { as } n \rightarrow \infty
      $$

    - 有时只能找
      $$
      \sup _ { \theta \in \Theta } R ( \theta , \widehat { \theta } ) \between \inf _ { \tilde { \theta } } \sup _ { \theta \in \Theta } R ( \theta , \tilde { \theta } ) , \text { as } n \rightarrow \infty
      $$
      这表示两者之比有界


#### 先验 $\pi$ 下的贝叶斯风险

$$
B _ { \pi } ( \widehat { \theta } ) = \int R ( \theta , \widehat { \theta } ) \pi ( \theta ) \text{d} \theta
$$

- 比较不同估计量的贝叶斯风险


##### 贝叶斯估计量

- 将贝叶斯风险最小化的估计量
  $$
  B _ { \pi } ( \widehat { \theta } ) = \inf _ { \tilde { \theta } } B _ { \pi } ( \tilde { \theta } )
  $$




- 决策理论：同样需要寻找贝叶斯统计量

  - 后验分布：
    $$
    \begin{aligned} P ( \theta \in A | x ^ { n } ) & = \frac { \int _ { A } p \left( x _ { 1 } , \ldots , x _ { n } | \theta \right) \pi ( \theta ) \text{d} \theta } { \int p \left( x _ { 1 } , \ldots , x _ { n } | \theta \right) \pi ( \theta ) \text{d} \theta } \\ & = \frac { \int _ { A } L ( \theta ) \pi ( \theta ) \text{d} \theta } { \int _ { \Theta } L ( \theta ) \pi ( \theta ) \text{d} \theta } \end{aligned}
    $$
    $L(\theta)$ 是似然函数

  - 后验分布密度：
    $$
    \pi ( \theta | x ^ { n } ) = \frac { p \left( x ^ { n } | \theta \right) \pi ( \theta ) } { m \left( x ^ { n } \right) }
    $$
    $m \left( x ^ { n } \right) = \int p \left( x ^ { n } | \theta \right) \pi ( \theta ) \text{d} \theta$ 是 $x^n$ 的边缘分布

  - 后验风险：
    $$
    r ( \widehat { \theta } | x ^ { n } ) = \int L ( \theta , \widehat { \theta } ) \pi ( \theta | x ^ { n } ) \text{d} \theta
    $$

  - 定理：对每一个 $x^n$ ，将后验风险最小化的估计量就是贝叶斯估计量

- 特定损失函数下的贝叶斯估计量（后验风险对 $\hat\theta$ 求导为 $0$ ）

  - 平方误差损失：
    $$
    \widehat { \theta } \left( x ^ { n } \right) = \int \theta \pi ( \theta | x ^ { n } ) \text{d} \theta = E ( \theta | X = x ^ { n } )
    $$

  - $0-1$ 损失：后验分布的众数



#### 极小化极大估计量和贝叶斯估计量的联系

- 定理：$\widehat{\theta}$ 是一定先验下的贝叶斯估计量，如果风险是常数，那么它也是极小化极大估计量



#### 极大似然估计量

- 大样本情况下（参数维数不变，样本容量增加），极大似然估计量趋向于极小化极大估计量

- 大样本下，方差远大于偏差，因而均方偏差近似为方差

- MLE的方差近似为 $\operatorname { Var } ( \widehat { \theta } ) \approx \frac { 1 } { n I ( \theta ) }，从而：
  $$
  n R ( \theta , \widehat { \theta } ) \approx \frac { 1 } { I ( \theta ) }
  $$

