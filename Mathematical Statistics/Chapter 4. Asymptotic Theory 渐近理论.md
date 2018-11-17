# Chapter 4. Asymptotic Theory 渐近理论



## MLE 的渐近性质

在满足正则条件的前提下：

- 相合性：$\widehat { \theta } \stackrel { P } { \rightarrow } \theta _ { 0 }$ ，$\theta_0$ 是真值
- 渐近正态分布：$\sqrt { n } ( \widehat { \theta } - \theta ) / \widehat { s e } \stackrel { d } { \rightarrow } N ( 0,1 )$
- 大样本有效性：较好的估计量中，大样本下MLE方差最小
- 大样本下近似于贝叶斯估计量（参见第3章）



### 正则条件

1. 参数可分辨（不同参数给出的分布是不同的）
2. 分布函数有共同支集
3. 每一个随机变量独立同分布
4. 参数空间包含一个开集 $\omega$ ，$\theta_0\in\omega$ ，且是一个内点（不在边界上）



- 在假设 $1\sim3$ 下，$P _ { \theta _ { 0 } } \left( L \left( \theta _ { 0 } | X \right) > L ( \theta | X ) \right) \rightarrow 1$ ，这里的 $L$ 是似然函数



## 相合性

- 在正则条件下，假定任取 $x$ ，$f(x|\theta)$ 对 $\theta\in\omega$ 可导，且似然方程对 $x,n$ 有唯一解 $\hat\theta_n$ ，那么 $\hat\theta_n$ 是相合的
- 如果参数个数与 $n$ 有关，则可能不相合

## 渐近正态
- Score Function & Fisher Information

  - Score Function

  $$
  S _ { n } ( \theta ) = [\log L ( \theta )] ^ { \prime } = \frac { \partial \log p \left( X _ { 1 } , \ldots , X _ { n } ; \theta \right) } { \partial \theta } = \sum _ { i } \frac { \partial \log p \left( X _ { i } ; \theta \right) } { \partial \theta }
  $$

  - Fisher Information

  $$
  I ( \theta ) = \operatorname{Var}_\theta(S(\theta)),\quad I _ { n } ( \theta ) = \operatorname { Var } _ { \theta } \left( S _ { n } ( \theta ) \right)= n I ( \theta )
  $$

  $$
  I ( \theta )=- E \left( \frac { \partial ^ { 2 } \log p ( X ; \theta ) } { \partial \theta ^ { 2 } } \right)
  $$

  ​	可以看到 Fisher information 有两种等价的定义，证明并不复杂，只需用到：
  $$
  E(S_n(\theta))=0
  $$

  $$
  I(\theta)=\operatorname{Var}_\theta(S_n(\theta))=E(S_n(\theta)^2)-E^2(S_n(\theta))=E(S_n(\theta)^2)
  $$

  $$
  \begin{align*}\frac { \partial ^ { 2 } } { \partial \theta ^ { 2 } } \log f ( X ; \theta )& = \frac { \frac { \partial ^ { 2 } } { \partial \theta ^ { 2 } } f ( X ; \theta ) } { f ( X ; \theta ) } - \left( \frac { \frac { \partial } { \partial \theta } f ( X ; \theta ) } { f ( X ; \theta ) } \right) ^ { 2 }\\& = \frac { \frac { \partial ^ { 2 } } { \partial \theta ^ { 2 } } f ( X ; \theta ) } { f ( X ; \theta ) } - \left( \frac { \partial } { \partial \theta } \log f ( X ; \theta ) \right) ^ { 2 }
  \end{align*}
  $$

  即可证明：
  $$
  \begin{align*}
  E(S(\theta)^2)&=E\left( \frac { \partial } { \partial \theta } \log f ( X ; \theta ) \right) ^ { 2 }\\
  &=\int\frac { \frac { \partial ^ { 2 } } { \partial \theta ^ { 2 } } f ( X ; \theta ) } { f ( X ; \theta ) } f(X;\theta)\text{d}\theta- E \left( \frac { \partial ^ { 2 } \log p ( X ; \theta ) } { \partial \theta ^ { 2 } } \right)\\
  &=- E \left( \frac { \partial ^ { 2 } \log p ( X ; \theta ) } { \partial \theta ^ { 2 } } \right)
  \end{align*}
  $$


  - 对于向量的情况，Fisher Information 是一个矩阵

  $$
  I _ { n } ( \theta ) ( r , s ) = - E \left( \frac { \partial ^ { 2 } l ( \theta ) } { \partial \theta _ { r } \partial \theta _ { s } } \right)
  $$

- 渐近正态性

  假定：

  - 参数个数不随 $n$ 变化
  - $p(x;\theta)$ 是 $\theta$ 的光滑函数（任意阶求导）
  - $\frac{\partial }{\partial\theta}$ 和 $\int\text{d}x$ 可交换
  - $X$ 的范围不依赖于参数

  则有：
  $$
  \sqrt { n } \left( \widehat { \theta } _ { n } - \theta \right) \stackrel { d } { \rightarrow } N \left( 0 , \frac { 1 } { I ( \theta ) } \right)
  $$

  $$
  \widehat { \theta } _ { n } = \theta + O _ { P } \left( \frac { 1 } { \sqrt { n } } \right)
  $$

- Slutsky 定理

  若 $X _ { n } \stackrel { d } { \rightarrow } X, Y _ { n } \stackrel { P } { \rightarrow } a$ ，则有：

  $$
  \begin{array} { l } { Y _ { n } X _ { n } \stackrel { d } { \rightarrow } a X } \\ { Y _ { n } + X _ { n } \stackrel { d } { \rightarrow } a + X } \end{array}
  $$


- 多元Delta方法

  - $Y _ { 1 } , \ldots , Y _ { n }$ 满足$\sqrt { n } \left( Y _ { n } - \theta \right) \stackrel { d } { \rightarrow } N _ { p } ( 0 , \Sigma )$

  - 如果 $g(\theta)'$ 存在且不为 $0$ ，那么

     $$
     \sqrt { n } \left( g \left( Y _ { n } \right) - g ( \theta ) \right) \stackrel { d } { \rightarrow } N \left( 0 , \left( \frac { \partial g ( \theta ) } { \partial \theta } \right) ^ { \prime } \Sigma \left( \frac { \partial g ( \theta ) } { \partial \theta } \right) \right)
     $$





- 证明：

  - 考虑 Score Function

    $S(\hat\theta)=0, S(\theta)=\sum\frac{\partial}{\partial\theta}l(x_i;\theta)$

  - 由相合性，当 $n$ 很大时 $\hat\theta-\theta_0$ 是小量，因此可以对 $S(\hat\theta)$ 展开：
    $$
    0=S(\hat\theta)\approx S(\theta_0)+\left[\frac{\partial S(\theta)}{\partial\theta}\right]_{\theta_0}(\hat\theta-\theta_0)
    $$
    得到：
    $$
    \hat\theta-\theta_0= -\frac{S(\theta_0)}{\left[\frac{\partial S(\theta)}{\partial\theta}\right]_{\theta_0}}
    $$

  - 求出期望和方差：
  $$
  \begin{align*}
    E_{\theta_0}(S(\theta_0))&=\sum E_{\theta_0}\left(\frac{\partial\ln f(x_i;\theta)}{\partial\theta}\right)_{\theta_0}=\sum E_{\theta_0}\left(\frac{ f(x_i;\theta)'}{f(x_i;\theta)}\right)_{\theta_0}\\
    &=\sum\int\left(\frac{ f(x_i;\theta)'}{f(x_i;\theta)}\right)_{\theta_0}f(x_i;\theta_0)\text{d}\theta_0\\
    &=\sum\int f(x_i;\theta_0)'\text{d}\theta_0\\
    &=\frac{\text{d}}{\text{d}\theta_0}\int f(x_i;\theta)\text{d}x\\
    &=0
    \end{align*}
  $$

  $$
  \begin{align*}
  nI(\theta)&=\operatorname { Var }_{\theta_0}(S(\theta_0))=n\operatorname { Var }_{\theta_0}\left(\frac{\partial\ln f(x_i;\theta)}{\partial\theta}\right)_{\theta_0}\\&\equiv {n}\operatorname { Var }_{\theta_0}(\omega_i(\theta_0))
  \end{align*}
  $$

  - 从而可以得出 $S(\theta_0)$ 满足的分布：
    $$
    \sqrt { n } \left( \frac{1}{n}S(\theta_0)\right) \stackrel { d } { \rightarrow } N \left( 0 , \operatorname { Var }_{\theta_0}(\omega_i(\theta_0))  \right)
    $$

  - 最后得到 $\hat\theta$ 的分布：
    $$
    \hat\theta-\theta_0= -\frac{S(\theta_0)}{\left[\frac{\partial S(\theta)}{\partial\theta}\right]_{\theta_0}} \stackrel { d } { \rightarrow } N \left( 0 , \frac{n\operatorname { Var }_{\theta_0}(\omega_i(\theta_0))}{\left[\frac{\partial S(\theta)}{\partial\theta}\right]^2_{\theta_0}}  \right)=N\left(0,\frac{1}{nI(\theta)}\right)
    $$




## 大样本的有效性

在正则条件下，对于MLE $\hat\theta$ 和一个表现良好的估计量 $\tilde{\theta}$：
$$
\widehat { \theta } = \theta + \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \psi ^ { * } \left( X _ { i } \right) + o _ { P } \left( n ^ { - 1 / 2 } \right)
$$

$$
\tilde { \theta } = \theta + \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \psi \left( X _ { i } \right) + o _ { P } \left( n ^ { - 1 / 2 } \right)
$$

可以证明在大样本情况下：
$$
\operatorname { Var } ( \psi ( X ) ) \geq \operatorname { Var } \left( \psi ^ { * } ( X ) \right)
$$


### 相对有效性

如果 $\sqrt { n } \left( W _ { n } - \theta \right) \stackrel { d } { \rightarrow } N \left( 0 , \sigma _ { W } ^ { 2 } \right) , \sqrt { n } \left( V _ { n } - \theta \right) \stackrel { d } { \rightarrow } N \left( 0 , \sigma _ { \mathrm { V } } ^ { 2 } \right)$ ，则渐近的相对有效性 (ARE) 为：
$$
A R E \left( V _ { n } , W _ { n } \right) = \sigma _ { W } ^ { 2 } / \sigma _ { V } ^ { 2 }
$$


### 强健性

- MLE只在模型正确的时候有较小的方差，如果模型错误，MLE的方差可能会很糟糕
  - 可以使用非参方法
  - 可以把MLE换成其他更强健的估计量
- 例：正态分布下的MLE是均值，与中位数相比，$ARE=0.64$ ；若正态分布混入一定概率的柯西分布，则均值的方差发散，中位数的方差变化不大



## 概率的收敛性



## 概率不等式

