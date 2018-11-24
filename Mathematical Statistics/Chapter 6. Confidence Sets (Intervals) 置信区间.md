# Chapter 6. Confidence Sets (Intervals) 置信区间



## 置信集和置信区间

- $\mathcal{P}$ 是一个统计模型，$C _ { n } \equiv C _ { n } \left( X _ { 1 } , \ldots , X _ { n } \right)$ 是一个来自样本的集合

- 称 $C_n$ 是 $\theta$ 的一个 $( 1 - \alpha ) 100 \%$ 的置信集，如果：
  $$
  P \left( \theta \in C _ { n } \right) \geq 1 - \alpha \text { for all } P \in \mathcal { P }
  $$

  $$
  \iff \inf _ { P \in \mathcal { P } } P \left( \theta \in C _ { n } \right) \geq 1 - \alpha
  $$

- 当 $C_n= [ L ( \boldsymbol { X } ) , U ( \boldsymbol { X } ) ]$ ，则它是一个置信区间

  - 对于一个区间估计量 $ [ L ( \boldsymbol { X } ) , U ( \boldsymbol { X } ) ]$ ，覆盖率为：
    $$
    P _ { \theta } ( \theta \in [ L ( \boldsymbol { X } ) , U ( \boldsymbol { X } ) ] )
    $$

  - 置信度为：
    $$
    \inf _ { \theta } P _ { \theta } ( \theta \in [ L ( \boldsymbol { X } ) , U ( \mathbf { X } ) ] )
    $$

  - 区间估计量和置信度合在一起，称为置信区间



## 构造置信区间的方法

- 概率不等式
- 将假设检验过程倒置
- 枢轴量
- 大样本近似



### 概率不等式



#### Hoeffding 不等式

对严格有界 ( $[a_i,b_i]$ 之内 ) 的独立随机变量 $X _ { 1 } , \ldots , X _ { n }$ ：
$$
P ( | \overline { X } - E ( \overline { X } ) | \geq t ) \leq 2 \exp \left( - \frac { 2 n ^ { 2 } t ^ { 2 } } { \sum _ { i = 1 } ^ { n } \left( b _ { i } - a _ { i } \right) ^ { 2 } } \right)
$$

- 例：对于伯努利分布，随机变量的取值有界——只能取 $0,1$，可以利用该不等式：

  - $\hat p=\overline X, E(\overline X)=p$ ，代入不等式得到：
    $$
    P ( | \hat { p } - p | > \epsilon ) \leq 2 e ^ { - 2 n \epsilon ^ { 2 } }
    $$

  - 令 $\epsilon _ { n } = \sqrt { \log ( 2 / \alpha ) / 2 n }$ ，则 $P \left( | \hat { p } - p | > \epsilon _ { n } \right) \leq \alpha$

  - 从而得到置信度为 $( 1 - \alpha ) 100 \%$ 的置信区间 $C = \left( \hat { p } - \epsilon _ { n } , \hat { p } + \epsilon _ { n } \right)$



#### VC 理论

- 和统计学习紧密相关，包括至少四个部分

  - 学习过程的相合性：在什么条件下，基于经验风险最小化的学习过程是相合的？

    > 经验风险最小化（ERM, Empirical risk minimization）
    >
    > - 机器学习的目的是根据一些训练样本，寻找一个最优的函数，使函数对输入的估计与实际输出之间的期望风险（损失函数的期望）最小化
    > - 但期望风险是无法获得的，只能利用已知的经验数据（训练样本）来代替，也即用经验风险（损失函数的算术平均值）来逼近期望风险

  - 学习过程收敛速率的非渐近理论：学习过程收敛得有多快？

  - 学习过程的控制和泛化能力理论：我们如何控制收敛速度（泛化能力）？

    > 泛化能力
    >
    > - 学习到的模型对未知数据的预测能力——学习的目的是学到隐含在数据对背后的规律，对具有同一规律的学习集以外的数据，经过训练的网络也能给出合适的输出
    > - 在实际情况中，我们通常通过测试误差（期望风险）来评价学习方法的泛化能力

  - 构建学习机器的理论：我们如何构建算法来控制泛化能力？

- 置信带

  - $F_n=F _ { n } ( x ) = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } I _ { \left( X _ { i } \leq t \right) }$ 是样本的经验分布函数（ $0-1$ 损失的经验风险）

  - 由 VC 理论：
    $$
    P \left( \sup _ { x } \left| F _ { n } ( x ) - F ( x ) \right| > \epsilon \right) \leq e ^ { - 2 n \epsilon ^ { 2 } }
    $$

  - 令 $\epsilon _ { n } = \sqrt { \log ( 2 / \alpha ) / 2 n }$ ，则 $P \left( \sup _ { x } \left| F _ { n } ( x ) - F ( x ) \right| > \epsilon _ { n } \right) \leq \alpha$

  - $P _ { F } ( L ( t ) \leq F ( t ) \leq U ( t ) \text { for all } t ) \geq 1 - \alpha$ ，其中 $L ( t ) = \widehat { F } _ { n } - \epsilon _ { n } $，$U ( t ) = \widehat { F } _ { n } + \epsilon _ { n }$ ——置信带，包含整体未知函数曲线的概率是 $1-\alpha$ 



### 将检验倒置

- 检验的接受域和置信集满足如下定理：

  - 任取参数空间中的 $\theta_0$ ，$A(\theta_0)$ 是一个 level-$\alpha$ 检验的接受域，零假设为 $\theta=\theta_0$ ，则：
    $$
    P _ { \theta _ { 0 } } \left( X \notin A \left( \theta _ { 0 } \right) \right) \leq \alpha\Rightarrow P _ { \theta _ { 0 } } \left( X \in A \left( \theta _ { 0 } \right) \right) \geq 1 - \alpha
    $$

  - 定义一个参数空间的子集 $C(X)$ 满足：
    $$
    C ( X ) = \left\{ \theta _ { 0 } : X \in A \left( \theta _ { 0 } \right) \right\}
    $$
    显然有：
    $$
    \theta\in C(X)\iff X\in A(\theta)
    $$

    $$
    P(\theta\in C(X))=P(X\in A(\theta))
    $$

  - 则 $C(X)$ 就是一个 $1-\alpha$ 置信集，任取 $\theta$ ：
    $$
    P _ { \theta } ( \theta \in C (  { X } ) ) \ge 1 - \alpha
    $$

  - 相反的过程也是成立的

  - 从而 level-$\alpha$ 检验的接受域和 $1-\alpha$ 置信集一一对应

- 单侧置信区间

  - 倒置单侧检验可以得到单侧置信区间

  - 例：正态分布，构造参数 $\mu$ 的 $1-\alpha$ 置信区间：
    $$
    C(x)=(-\infty,U(x)]
    $$

    - 倒置单侧检验：$H _ { 0 } : \mu = \mu _ { 0 } \text { versus } H _ { 1 } : \mu < \mu _ { 0 }$

    - size-$\alpha$ 的 LRT 拒绝零假设的条件是：
      $$
      \frac { \overline { X } - \mu _ { 0 } } { S / \sqrt { n } } < - t _ { n - 1 , \alpha }
      $$

    - 接受域：
      $$
      A \left( \mu _ { 0 } \right) = \left\{ x : \overline { x } \geq \mu _ { 0 } - t _ { n - 1 , \alpha } \frac { s } { \sqrt { n } } \right\}
      $$

    - 单侧置信区间：
      $$
      C (x ) = \left\{ \mu _ { 0 } : \overline { x } \geq \mu _ { 0 } - t _ { n - 1 , 1-\alpha } \frac { s } { \sqrt { n } } \right\}
      $$

      $$
      U(x)=\overline x+t _ { n - 1 , \alpha } \frac { s } { \sqrt { n } }
      $$






### 枢轴量

- 如果函数 $Q \left( X _ { 1 } , \ldots , X _ { n } , \theta \right)$ 的分布与 $\theta$ 无关，则它为枢轴量

- 例如正态分布 $N(\theta,1)$ ，$\overline X-\theta\sim N(0,1/n)$ 为一个枢轴量

- 如果对于所有 $\theta$ 有：
  $$
  P _ { \theta } ( a \leq Q ( X , \theta ) \leq b ) = 1 - \alpha
  $$
  那么可以得到 $1-\alpha$ 置信区间：
  $$
  C ( x) = \{ \theta : a \leq Q ( x , \theta ) \leq b \}
  $$




- 例：均匀分布 $Uniform(0,\theta)$

  - 令 $Q=X_{(n)}/\theta$ ，则：
    $$
    P ( Q \leq t ) = \prod _ { i } P \left( X _ { i } \leq t \theta \right) = t ^ { n }
    $$
    即 $Q$ 是一个枢轴量

  - 由于 $P(0\le Q\le c_n)=\alpha,c_n=\alpha^{1/n}$ ，有
    $$
    \begin{align*} 1 - \alpha & = P \left( c _ { n } \leq Q \leq 1 \right) \\ & = P \left( c _ { n } \leq \frac { X _ { ( n ) } } { \theta } \leq 1 \right) \\  & = P \left( X _ { ( n ) } \leq \theta \leq \frac { X _ { ( n ) } } { c _ { n } } \right) \end{align*}
    $$

  - 从而一个 $1-\alpha$ 置信区间是：
    $$
    \left( X _ { ( n ) } , \frac { X _ { ( n ) } } { \alpha ^ { 1 / n } } \right)
    $$






### 基于大样本的置信区间



#### Wald 区间

- 正则条件下，对于样本容量为 $n$ 的样本，我们有：
  $$
  \frac { \widehat { \theta } - \theta } { s e } \stackrel { d } { \rightarrow } N ( 0,1 )
  $$
  这里 $\hat\theta$ 是 MLE ，$s e = 1 / \sqrt { I_ { n } ( \widehat { \theta } ) }$ ，从而这是一个渐近的枢轴量 

- 一个渐近的置信区间为：
  $$
  \left( \widehat { \theta } - z _ { 1 - \alpha / 2 } s e , \widehat { \theta }  + z _ { 1 - \alpha / 2 } s e \right)
  $$

- 对于 $\theta$ 的函数 $\pi(\theta)$ ，利用 Delta 方法得到：
  $$
  \frac { \pi(\hat { \theta } ) - \pi(\theta) } { s e } \stackrel { d } { \rightarrow } N ( 0,|\pi'(\hat\theta)|^2 )
  $$
  一个置信区间为：
  $$
  \left( \pi  (\widehat { \theta } ) - z _ { 1 - \alpha / 2 } \operatorname { se } \left| \pi ^ { \prime } ( \widehat { \theta } ) \right| , \pi ( \widehat { \theta } ) + z _ { 1 - \alpha / 2 } \operatorname { se } \left| \pi ^ { \prime } ( \widehat { \theta } ) \right| \right)
  $$






#### 基于似然函数的置信集

- $H _ { 0 } : \theta = \theta _ { 0 } \text { versus }H _ { 1 } : \theta \neq \theta _ { 0 }$ ，$\theta$ 是 $k\times1$ 向量

- 第5章中给出：在零假设下，$T _ { n } = - 2 \log \lambda \left( x _ { 1 } , \ldots , x _ { n } \right) \stackrel { d } { \rightarrow } \chi _ { r } ^ { 2 }$ ，其中 $r = \operatorname { dim } ( \Theta ) - \operatorname { dim } \left( \Theta _ { 0 } \right)$ 

- 渐近的接受域：
  $$
  A _ { \theta } = \left\{ X : \lambda(X) > e ^ { - \chi _ { k , 1 - \alpha } ^ { 2 } / 2 } \right\}
  $$
  渐近的置信区间：
  $$
  C_n = \left\{ \theta : \lambda(x) > e ^ { - \chi _ { k , 1 - \alpha } ^ { 2 } / 2 } \right\}
  $$




- 例：伯努利分布：$X _ { 1 } , \ldots , X _ { n } \sim \text { Bernoulli } ( p )$ ，记 MLE 为 $\hat p$

  - 分布函数：
    $$
    f(X;p)=\left\{
    \begin{array}{c}
    p,\quad X=1\\
    1-p,\quad X=0
    \end{array}
    \right.
    $$

    $$
    \log f(X;p)=\left\{
    \begin{array}{c}
    \log p,\quad X=1\\
    \log (1-p),\quad X=0
    \end{array}
    \right.
    $$




  - 一维的 Wald 检验
    $$
    \frac{\sqrt{n}(\hat p-p)}{\sqrt{1/\mathcal{I(\hat\theta)}}}\sim N(0,1)
    $$

    $$
    \begin{align*}
    \mathcal{I}(\theta)&=-E\left[\frac{\partial^2}{\partial p^2}\log f(x_i;p)\right]\\
    &=\frac{p}{p^2}+\frac{1-p}{(1-p)^2}\\
    &=\frac{1}{p}+\frac{1}{1-p}=\frac{1}{p(1-p)}
    \end{align*}
    $$

    从而：
    $$
    \frac{\sqrt{n}(\hat p-p)}{\sqrt{\hat p(1-\hat p)}}\sim N(0,1)
    $$
    渐近的置信区间：
    $$
    \left( \widehat { p } - z _ { 1 - \alpha / 2 } \sqrt{\hat p(1-\hat p)/n} , \widehat { p }  + z _ { 1 - \alpha / 2 } \sqrt{\hat p(1-\hat p)/n} \right)
    $$

  - LRTs

    记 $\sum X_i=Y$
    $$
    \lambda(x)=\frac{ p_0^Y(1- p_0)^{n-Y}}{\hat p^Y(1-\hat p)^{n-Y}}
    $$
    而置信集为：
    $$
    C_n = \left\{ p : - 2 \log \left( \frac { p ^ { Y } ( 1 - p ) ^ { n - Y } } { \hat { p } ^ { Y } ( 1 - \hat { p } ) ^ { n - Y } } \right) \leq \chi _ { 1,1 - \alpha } ^ { 2 } \right\}
    $$
    由 $p_0$ 的任意性已经将其记为 $p$ 

  - 虽然两个置信区间不同，但在大样本下它们几乎是相同的



## 贝叶斯区间

- 置信集是频率学派的产物，贝叶斯学派使用可信集

- 令 $\pi(\theta|x)$ 是 $\theta$ 在给定样本 $X=x$ 后的后验分布，对参数空间的任意一个子集 $A$ ，可信概率是：
  $$
  P ( \theta \in A | x ) = \int _ { A } \pi ( \theta | x ) \text{d}\theta
  $$
  且 $A$ 是参数的一个可信集



## 正态分布的区间估计补充

- 已知 $\sigma^2$ 估计 $\mu$
  $$
  \overline{X}\sim N(\mu,\frac{\sigma^2}{n})\\
  \Rightarrow\frac{\overline X-\mu}{\sqrt{\sigma^2/n}}\sim N(0,1)\\
  \Rightarrow\mu\in\left[\overline X-\sqrt{\frac{\sigma^2}{n}}z_{1-\alpha/2},\overline X+\sqrt{\frac{\sigma^2}{n}}z_{1-\alpha/2}\right]
  $$

- 未知 $\sigma^2$ 估计 $\mu$ ，用无偏估计量 $S^2$ 代替 $\sigma^2$
  $$
  T=\frac{\overline X-\mu}{\sqrt{S^2/n}}=\frac{\sqrt{n}(\overline X-\mu)/\sigma}{\sqrt{ S ^ { 2 } / \sigma ^ { 2 }}}
  $$
  不服从标准正态分布

  有一组有用的引理：

  - 令 $X _ { 1 } , \ldots , X _ { n }$ 是来自正态分布的随机样本，则：
    1. 均值和方差是独立随机样本
    2. $\overline { X } \sim N \left( \mu , \sigma ^ { 2 } / n \right)$
    3. $( n - 1 ) S ^ { 2 } / \sigma ^ { 2 }\sim\chi^2_{n-1}$

  则 $T$ 的分子分母独立，且分子 $\sim N(0,1)$ ，${n-1}$ 倍的分母 $\sim{\chi^2(n-1)}$ ，则这是一个自由度为 $n-1$ 的 t 分布
  $$
  \Rightarrow\mu\in\left[\overline X-\sqrt{\frac{s^2}{n}}t_{n-1,\alpha/2},\overline X+\sqrt{\frac{s^2}{n}}t_{n-1,\alpha/2}\right]
  $$

- 未知 $\mu $ 估计 $\sigma^2$ ，用无偏估计量 $\overline X$ 代替 $\mu $
  $$
  ( n - 1 ) S ^ { 2 } / \sigma ^ { 2 }\sim\chi^2_{n-1}
  $$
  查 $\chi^2$ 表找到 $\lambda_1,\lambda_2$ 使得：
  $$
  P(Y<\lambda_1)=P(Y>\lambda_2)=\frac{\alpha}{2}\\
  \Rightarrow \sigma^2\in\left[\frac{( n - 1 ) S ^ { 2 }} {\lambda_1},\frac{( n - 1 ) S ^ { 2 }} {\lambda_2}\right]
  $$

