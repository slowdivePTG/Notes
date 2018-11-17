# Chapter 2. Estimation 估计



## 三种估计的方法

- 矩估计（MOM）
- 极大似然估计（MLE）
- 贝叶斯估计



## 衡量估计量优劣的方法

- 偏差和方差
- 均方偏差（MSE）
- Minimax 理论
- 大样本理论



## 参数点估计

- 一个点估计量是样本的一个任意函数，也就是任意一个统计量
- 估计量和估计值
  - 估计量（Estimator）是样本的函数，是随机向量 $X^n$ 的函数
  - 估计值（Estimate）是在得到样本之后估计量的取值，是样本实际值 $x^n$ 的函数



### 矩估计(MOM)

- 定义
  $$
  \begin{array} { r l } &{ m _ { 1 }= \frac { 1 } { n } \sum _ { i = 1 } ^ { n } x _ { i } , } &{ \mu _ { 1 } ( \theta )}{ = E ( X ) } \\ { } & { \vdots } &{\vdots}\\ &{ m _ { k }  = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } x _ { i } ^ { k } },& { \mu _ { k } ( \theta ) = E \left( X ^ { k } \right) } \end{array}
  $$
  矩估计量 $\widehat { \theta } = \left( \widehat { \theta } _ { 1 } , \ldots , \widehat { \theta } _ { k } \right)$ 满足 
  $$
  m _ { j } = \mu _ { j } ( \widehat { \theta } ) , \quad j = 1 , \ldots , k
  $$
  即令样本的前 $k$ 阶矩和理论的前 $k$ 阶矩相等

- 例：正态分布（一阶矩 $\beta$，二阶矩 $\sigma^2+\beta^2$）MOMs：
  $$
  \widehat { \beta } = \overline { X } , \quad \widehat { \sigma } ^ { 2 } = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \left( X _ { i } - \overline { X } \right) ^ { 2 }
  $$

- 例：二项分布（一阶矩 $kp$ ，二阶矩 $kp(1-p)+k^2p^2$）MOMs：
  $$
  \widehat { p } = \frac { \overline { X } } { \widehat { k } } , \quad \widehat { k } = \frac { \overline { X } ^ { 2 } } { \overline { X } - \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \left( X _ { i } - \overline { X } \right) ^ { 2 } }
  $$
  这个估计不是最好的，因为 $\widehat{k}$ 可能是负值

 

### 极大似然估计(MLE)

- 似然函数：
  $$
  L ( \theta | x ) = p \left( x _ { 1 } , \ldots , x _ { n } ; \theta \right) \stackrel { ( \text { i.i.d } ) } { \longrightarrow } \prod _ { i = 1 } ^ { n } p \left( x _ { i } ; \theta \right)
  $$

- 对数似然函数：
  $$
  l ( \theta | x ) = \log L ( \theta | x )
  $$

- 目标

  - 找到似然函数的全局最大值
  - 确保估计量对数据微小的改变是稳定的

- 求MLE：

  - 对于可微的似然函数，考虑一阶导数为0，二阶导数小于0的所有极大值点，加上参数取值的边界点，比较得到全局最大值

  - 直接求最大值——找到上界，找到取这个值的唯一点

    - 例：对于 $X _ { 1 } , \ldots , X _ { n } \sim  \text { Uniform } ( 0 , \theta )$ ，似然函数满足：
      $$
      L ( \theta ) = \frac { 1 } { \theta^n } I \left( 0 < X _ { ( n ) } < \theta \right)
      $$
      当且仅当 $\theta\ge X_{(n)}$ 时 $L(\theta)> 0$，此时 $L(\theta)$ 关于 $\theta$ 递减，从而 $\widehat { \theta } = X _ { ( n ) }$

- 受限MLE：实际情况中参数取值可能有限制，此时求得的MLE和参数自由时求得的MLE不同

- 对于不能解析求解的情况，可以由计算机求数值解——同样需要考虑局域最大和全局最大

  - 例：二项分布，试验次数 $k$ 位置，单次概率 $p$ 已知，估计 $k$ 的MLE

    - 似然函数：
      $$
      L ( k | x , p ) = \prod _ { i = 1 } ^ { n } \left( \begin{array} { l } { k } \\ { x _ { i } } \end{array} \right) p ^ { x _ { i } } ( 1 - p ) ^ { \left( k - x _ { i } \right) }
      $$
      $k<x_{(n)}$ 时 $L=0$

    - 由于 $k$ 是整数，又涉及到阶乘，我们不能求导了

    - 考虑 $k \geq x _ { ( n ) }$ 满足：
      $$
      \frac { L ( k | x , p ) } { L ( k - 1 | x , p ) } \geq 1 , \frac { L ( k + 1 | x , p ) } { L ( k | x , p ) } < 1
      $$
      而：
      $$
      \frac { L ( k | x , p ) } { L ( k - 1 | x , p ) } = \frac { ( k ( 1 - p ) ) ^ { n } } { \prod _ { i = 1 } ^ { n } \left( k - x _ { i } \right) }
      $$
      从而不等式化为：
      $$
      \begin{align*}  ( k ( 1 - p ) ) ^ { n } &\geq \prod _ { i = 1 } ^ { n } \left( k - x _ { i } \right)  \\  ( ( k + 1 ) ( 1 - p ) ) ^ { n } &< \prod _ { i = 1 } ^ { n } \left( k + 1 - x _ { i } \right)  \end{align*}
      $$

      $$
      \Rightarrow (1-p)^n= \prod _ { i = 1 } ^ { n } \left( 1 - x _ { i } z \right)
      $$

      这里 $z=1/k$

    - 等式右边关于 $z$ 递减，$z=0$ 时取 $1$ ，$z=1/x_{(n)}$ 时取 $0$

    - 从而 $z$ 有唯一解 $\widehat{z}$ （数值求解），当然 $1/\widehat{z}$ 不一定是整数，$\widehat{k}$ 是最接近 $1/\widehat{z}$ 的整数

- MLE的稳定性

  当似然函数在最大值的领域附近**非常平坦**，或者不存在**有限**的最大值的时候，样本数据的轻微改变可能就会造成MLE的巨大变化

- MLE的等价性

  - $\eta=g(\theta)$ 是 $\theta$ 的函数，如果 $\theta$ 的MLE是 $\widehat\theta$ ，那么 $\eta$ 的MLE是 $g(\widehat\theta)$ 



### 贝叶斯估计

- 贝叶斯派将 $\theta$ 看成随机变量，其先验分布为 $p(\theta)$ 

- $X _ { 1 } , \ldots , X _ { n } , \theta$ 的联合分布为：
  $$
  p \left( x _ { 1 } , \ldots , x _ { n } , \theta \right) = p \left( x _ { 1 } , \ldots , x _ { n } | \theta \right) p ( \theta )
  $$

- 根据贝叶斯公式，我们可以得到相应的后验分布：
  $$
  p ( \theta | x _ { 1 } , \ldots , x _ { n } ) = \frac { p \left( x _ { 1 } , \ldots , x _ { n } | \theta \right) p ( \theta ) } { p \left( x _ { 1 } , \ldots , x _ { n } \right) }
  $$

  $$
  p \left( x _ { 1 } , \ldots , x _ { n } \right) = \int p \left( x _ { 1 } , \ldots , x _ { n } | \theta \right) p ( \theta ) \text{d} \theta
  $$

  这相当于：
  $$
  p ( \theta | x _ { 1 } , \ldots , x _ { n } ) \propto L ( \theta ) p ( \theta ) = \text { Likelihood } \times \text { prior }
  $$








> 似然函数等于条件分布 $p \left( x _ { 1 } , \ldots , x _ { n } | \theta \right)$ 而不是联合分布 $p \left( x _ { 1 } , \ldots , x _ { n } , \theta \right)$ 是因为在 贝叶斯估计中，$\theta$ 是一个随机变量，实际的 $x^n$ 的联合分布是在取定 $\theta$ 后得到的，相当于条件分布；而在极大似然估计中，$\theta$ 只是一个参数，本身是固定的，不存在这样的条件分布

#### 贝叶斯估计量

贝叶斯估计量依赖于后验分布

- 一种贝叶斯估计量是后验分布的均值
  $$
  \begin{align*} { \widehat { \theta } }&{= E ( \theta | x _ { 1 } , \ldots , x _ { n } ) = \int \theta p ( \theta | x _ { 1 } , \ldots , x _ { n } ) d \theta } \\ &={  \frac { \int \theta p \left( x _ { 1 } , \ldots , x _ { n } | \theta \right) p ( \theta ) d \theta } { \int p \left( x _ { 1 } , \ldots , x _ { n } | \theta \right) p ( \theta ) d \theta } } 
  \end{align*}
  $$

- 例：伯努利分布，$X _ { 1 } , \ldots , X _ { n } \sim \text { Bernoulli} ( \theta )$ ，$\theta$ 的先验分布 $\theta \sim \operatorname { Beta } ( \alpha , \beta )$ ，即：
  $$
  p ( \theta ) = \theta ^ { \alpha - 1 } ( 1 - \theta ) ^ { \beta - 1 } / \left( \frac { \Gamma ( \alpha + \beta ) } { \Gamma ( \alpha ) \Gamma ( \beta ) } \right)\propto \theta ^ { \alpha - 1 } ( 1 - \theta ) ^ { \beta - 1 }
  $$
  而似然函数满足：
  $$
  L(\theta)=p(x_1,\cdots,x_n|\theta)=\theta ^ { Y } ( 1 - \theta ) ^ { n - Y }
  $$
  这里 $Y = \sum X _ { i }$ 

  则后验分布 
  $$
  p ( \theta | x _ { 1 } , \ldots , x _ { n } )\propto\underbrace { \theta ^ { Y } ( 1 - \theta ) ^ { n - Y } } _ { \text { Likelihood } } \times \underbrace { \theta ^ { \alpha - 1 } ( 1 - \theta ) ^ { \beta - 1 } } _ { \text { Prior } } = \theta ^ { Y + \alpha - 1 } ( 1 - \theta ) ^ { n - Y + \beta - 1 }
  $$






- 共轭先验：先验分布和后验分布属于同一分布族

  - 例：$X _ { 1 } , \ldots , X _ { n } \sim N \left( \mu , \sigma ^ { 2 } \right)$ ，$\sigma^2$ 未知

    $\mu$ 又有一个先验分布：$\mu \sim N \left( m , \tau ^ { 2 } \right)$

    后验分布：
    $$
    \begin{align*}
    p ( \mu | X _ { 1 } , \ldots , X _ { n } )&\propto \exp\left[{-\frac{\sum(X_i-\mu)^2}{2\sigma^2}}\right]\exp\left[{-\frac{(\mu-m)^2}{2\tau^2}}\right]\\
    &\propto\exp\left[-\left(\frac{n}{2\sigma^2}+\frac{1}{2\tau^2}\right)\mu^2+2\left(\frac{n\overline{X}}{2\sigma^2}+\frac{m}{2\tau^2}\right)\mu^2\right]\\
    &\propto \frac{1}{\sqrt{2\pi}\sigma'}\exp\left[\frac{(\mu-\mu')^2}{2\sigma'^2}\right]
    \end{align*}
    $$
    这说明正态分布族是自己的共轭族，可以得到相应的贝叶斯估计量：
    $$
    \widehat\mu=E ( \mu | X ) =\mu'=\frac { \tau ^ { 2 } } { \tau ^ { 2 } + \sigma ^ { 2 } / n } \overline { X } + \frac { \sigma ^ { 2 } / n } { \tau ^ { 2 } + \sigma ^ { 2 } / n } m
    $$

    $$
    \widehat\sigma^2=\operatorname { Var } ( \mu | X )=\sigma'^2=\frac { \sigma ^ { 2 } \tau ^ { 2 } / n } { \tau ^ { 2 } + \sigma ^ { 2 } / n }
    $$

    - 这里得到的是先验和样本平均的线性组合
    
    - 如果先验的方差趋于无穷，$\widehat{\mu}\to\overline{X}$ ，$\widehat{\sigma}^2\to\sigma^2/n$ ，信息主要来自样本
    
    - 如果先验的方差趋于很小，先验信息很好，则$\widehat{\mu}\to\ m$ ，$\widehat{\sigma}^2\to\tau^2 $ ，信息主要来自先验分布 



## 评价估计量的方法



### 均方偏差 (MSE)：$E _ { \theta } ( \widehat { \theta } - \theta ) ^ { 2 }$

$$
\int \ldots \int \left( \widehat { \theta } \left( x _ { 1 } , \ldots , x _ { n } \right) - \theta \right) ^ { 2 } p \left( x _ { 1 } ; \theta \right) \ldots p \left( x _ { n } ; \theta \right) \text{d} x _ { 1 } \ldots \text{d} x _ { n }
$$

- 偏差 $B = E _ { \theta } ( \widehat { \theta } ) - \theta$
- 方差 $V = \operatorname { Var } _ { \theta } ( \widehat { \theta } )$
- 均方偏差 $\mathrm { MSE } = B ^ { 2 } + V$
- 如果偏差为 $0$ ，则一个估计量是无偏估计量，MSE=方差，但这时方差可能很大
- MSE是 $\theta$ 的函数
- Minimax方法是取**MSE在 $\theta$ 上的最大值**进行比较的评估估计量的方法



### 最好的无偏估计量

一致最小最大方差无偏估计量 (UMVUE)：

- $W$ 是 $\tau(\theta)$ 的UMVUE，如果：
  - $E _ { \theta } ( W ) = \tau ( \theta )$ ，任取 $\theta$
  - 如果 $E _ { \theta } ( W' ) = \tau ( \theta )$ ，那么 $\operatorname { Var } _ { \theta } ( W ) \leq \operatorname { Var } _ { \theta } \left( W ^ { \prime } \right)$

- Cramer-Rao 不等式给出了任何无偏估计量方差的下界：
  $$
  \operatorname { Var } _ { \theta } ( W ) \geq \frac { \left( \frac { d } { d \theta } E _ { \theta } W \right) ^ { 2 } } { E _ { \theta } \left[ \left( \frac { \partial } { \partial \theta } \log f ( X ; \theta ) \right) ^ { 2 } \right] } = \frac { \left( \tau ^ { \prime } ( \theta ) \right) ^ { 2 } } { I _ { n } ( \theta ) }
  $$

  > Cramer-Rao 不等式：
  >
  > $X _ { 1 } , \dots , X _ { n }$ 独立同分布于 $f ( x | \theta )$ ，$T = t \left( X _ { 1 } , \dots , X _ { n } \right)$ 是 $\theta$ 的一个无偏估计量，则在光滑性假设下：
  > $$
  > \operatorname { Var } ( T ) \geq \frac { 1 } { n I ( \theta ) }
  > $$
  >
  > $$
  > I ( \theta ) = \operatorname { Var } \left( \frac { \partial \log f ( X | \theta ) } { \partial \theta } \right)
  > $$
  >

- Rao-Blackwell 定理
  - $W$ 是 $\tau(\theta)$ 的一个无偏估计量，$T$ 是一个充分统计量
  - 定义 $W'=\phi(T)=E(W|T)$ ，那么有 $E(W')=E(E(W|T))=E(W)=\tau(\theta)$ ——无偏估计量 
  - 且 $W'$ 方差不大于 $W$ 的方差（证明需要用到 $E(\theta^*-\theta)^2\ge[E(\theta^*-\theta)]^2​$ ）