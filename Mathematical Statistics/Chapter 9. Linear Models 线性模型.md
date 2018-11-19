# Chapter 9. Linear Models 线性模型



### Adjusted $R^2$

对于简单的线性回归：

- 样本的 $R^2$

- 是总体 $R^2$ 的估计量：
  $$
  1 - \frac { \operatorname { var } ( Y | X ) } { \operatorname { var } ( Y ) }
  $$
  $Var(Y)$ ：人群中的方差；$ Var(X|Y)$ ：回归后的方差

- 这是一个比例， $R_2$ 是有偏的
  although the bias is not large unless the sample size is small or the number of covariates is large.
- Adjusted $R_2$ 是一个近似的对于总体 $R^2$ 的无偏估计量：



### 线性模型潜在的问题

- 固有的非线性性
- $X$ 和 $\epsilon$ 不独立
- 方差不一定是常数
- Outliers：离群数(Y)，对参数估计影响大
- High-leverage point：X差别很大，对参数估计影响大
- Collinearity：多参数时，X之间不线性独立



### 非线性性

- Residual Plots：
  $$
  \epsilon=Y-X'\beta=Y-(\beta_0+\cdots+\beta_pX_p)
  $$

  $$
  e_i\equiv \hat{\epsilon}_i=y_i-x_i'\hat{\beta}
  $$

  作出 $e_i-\hat{y}_i$ (简单线性模型) 或 $e_i-\hat{y}_i$ (多元线性模型) 图，如果线性模型正确，$e_i$ 应该在 $0$ 附近波动 (正态分布)

- 如果线性模型不正确，考虑作变换 (非常行♂为♂艺♂术)



### 残差项不独立

- 对于时间序列，比如 $\epsilon_i$ 和 $\epsilon_{i+1}$ 的符号好像有难♂分♂难♂解的关系 (同样可以由Residual Plots看出来)，独立性就成问题了

- 可以假设：
  $$
  corr(\epsilon_t,\epsilon_{t+q})=\rho^q
  $$
  距离越大，相关性越小；这样的假设下依然可以用极大似然法估计

- 对于一些非时间序列，比如Family Study，考查饮食对高血压的影响，选择一百个家庭作为样本——家庭饮食习惯相似：Clustered data (Multi-level data)


### 残差项方差不同

- Funnel Plots (Residual Plots 呈现烟囱型) ——对 $Y$ 作变换 (对数变换，Box-Cox变换)



### 离群值

- 离群值：一个远离模型估计值的 $y_i$ 
- 来源：可能数据收集时出错，也可能是真值——不能随便去掉
- Residual Plots可以用来分辨离群值



### High Leverage Points

- $x_i$ 的离群值，对最小二乘法有很大影响

- $\beta$ 的LSE可以被写成：
  $$
  \hat{y}=Hy
  $$
  其中 $H=X(X'X)^{-1}X'$ 是一个 $n\times n$ 矩阵，可以证明：

  - $H'=H$ ：对称矩阵
  - $H^2=H$ ：幂等矩阵

- $H=(h_{ij})$ ，较大的 $h_{ij}$ 对 $\hat{y}$ 的影响也大

- 由对称性和幂等性，对角元同时代表 $i$ 行和 $i$ 列的数值：
  $$
  h_{ii}=h_i'h_i=\sum_{j=1}^n h_{ij}^2
  $$





### 共线性

- 两个或更多的predictor variables彼此密切相关，即 $X_i​$ 之间线性相关