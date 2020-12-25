# Chapter 10 Model Selection 模型选择



## Discrepancy Criteria

- 在比较不同模型的表现时，使用一个measure来代表lack of fit，与真模型比较

- 拟合不足的衡量——discrepancy

- $g^{(I)}_\theta$ 是 $I$ 个等宽区间直方图的pdf

- Discrepancy due to approximation (和真模型的差距，偏差)
  $$
  \Delta(f,g^{(I)}_\theta)=\int_0^{100}(f(x)-g^{(I)}_\theta)^2\text{d}x
  $$

- Discrepancy due to estimation (估计精确度决定，方差)
  $$
  \Delta(f,g^{(I)}_\theta)=\int_0^{100}(g^{(I)}_{\hat \theta}-g^{(I)}_\theta)^2\text{d}x
  $$




### 常用的Discrepancy (统计差异)

- Kullback-Leibler Discrepancy
  $$
  \Delta=-E_F(\log g_\theta(X))=-\int\log g_\theta(x)f(x) \text{d} x
  $$

- Pearson chi-squared discrepancy
  $$
  \Delta=-\sum_x(f(x)-g_\theta)^2/g_\theta
  $$

- Gauss discrepancy
  $$
  \Delta =\sum_x(f(x)-g_\theta)^2
  $$

- 差异的期望（参数未知，只能求出期望）：差异的期望的估计量被称为模型选择标准——与样本无关

- 渐近标准


## 模型选择方法

- 找到给出最佳预测的模型，不对模型真实性进行假设

- 假定其中一个模型是真实模型，再找出这个模型


### AIC——最佳预测

- 假定有 $k$ 个模型 $M_i$ ，$n$ 个数据 $Y_i$ 来自 分布函数 $p$ ，$p$ 不一定在这些模型中

- $\hat\theta_j$ 是模型 $j$ 的 MLE ，$p$ 的估计量 $\hat p(y)=p(y;\hat\theta_j)$

- Kullback-Leibler Disdance:
  $$
  K(p,\hat p_j)=\int p(y)\log\frac{p(y)}{\hat p_j(y)}\text{d} y
  $$
  使其最小化相当于使下式最大化（与 $j$ 有关的部分）
  $$
  K_j=\int p(y)\log \hat p_j(y)\text{d} y=E(\log p(Y_j;\hat \theta_j))
  $$

- 均值为：
  $$
  \overline K_j=\frac{1}{n}\sum\log p(Y_j;\theta_j)=\frac{l_j(\hat \theta_j)}{n}
  $$
  但偏差很大，因为数据被用了两次（选模型、作推断）

- Akaike 证明了偏差大约为 $d_j/n=\dim (\Theta_j)/n$ ，在参数空间维度不太大的时候偏差不大

- 从而可以使用估计量：
  $$
  \widehat K_j=\overline K_j-\frac{d_j}{n}
  $$
  定义：
  $$
  AIC(j)=2n\widehat K_j=2l_j(\hat\theta_j)-2d_j
  $$
  $2n$ 的选择要考虑到历史的进程



### Cross-Validation——最佳预测

- 把数据分为训练集和测试集，通常这样的划分会进行多次并取平均值——每一次推断过程中避免数据的重复使用

- 简单起见，只划分一次

-  $k$ 个模型，$2n$ 个数据点，随机分为 $D=(Y_1,\cdots,Y_n)，T=(Y^*_1,\cdots,Y^*_n)$

- 用 $D$ 去找 MLE $\hat\theta_j$ 

- 用 $T$ 中的数据定义（不需要消除偏差）：
  $$
  \widehat K_j=\frac{1}{n}\sum\log p(Y_i^*;\hat\theta_j)
  $$
  可以证明：
  $$
  E(\widehat K_j)=K
  $$




### BIC——真实模型

- BIC——贝叶斯信息标准
  $$
  BIC(j)=l_j(\hat\theta_j)-\frac{d_j}{2}\log n
  $$
  penalty 更大，倾向于选择更简单的模型

- $M_1 $ $M_2$ ，先验分布 $p(M_1),P(M_2)$ 

- 收集数据之后，计算：
  $$
  \frac{p(M_1|D)}{p({})}
  $$
