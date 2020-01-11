# Chapter 4 吸收线内的辐射转移



## 引言

- 建立研究吸收线的辐射转移方程
- 介绍几种常用的解吸收线内转移方程的方法
- 导出谱线轮廓和深度的理论公式

### 描述吸收线的物理量

#### 剩余强度

- 剩余的辐射与连续谱的比值
  $$
  r _ { \nu } = \frac { I _ { \nu } ( \theta ) } { I _ { \nu } ^ { 0 } ( \theta ) }=\frac { F _ {\nu} } { F _ { \nu } ^ { 0 } }
  $$
  辐射强度的比对应于圆面上一点的辐射，辐射流的比对应于整个圆面的辐射

- 吸收线内 $r_\nu<1$ ，吸收线外 $r_\nu=1$

- 线心频率 $\nu_0$ 处剩余强度最小——中心剩余强度

#### 谱线轮廓

- 以 $\nu$ 为横坐标，$r_\nu$ 为纵坐标得到的曲线
- 谱线的中心部分称为线心，由中心向外延伸的最外面部分叫线翼

#### 线深度

- $R_\nu=1-r_\nu$
- 谱线轮廓图中,由连续背景到剩余相对强度的深度

#### 谱线总吸收

- 吸收线轮廓与连续背景所包围的面积
  $$
  W_\nu=\int R_\nu\mathrm{d}\nu,\text{ or }W_\nu=\int R_\lambda\mathrm{d}\lambda
  $$
  积分沿整条谱线进行

- 总吸收越大，谱线越强

#### 等值宽度

- 谱线总吸收强度(面积)用一个面积相等、高度为一个单位的矩形面积来代替时，矩形的宽度
- 数值上等于谱线总吸收
- 单位常为埃



## 吸收线的产生机制

### 选择吸收 (线吸收)

- 在恒星大气的辐射转移中，吸收线所在频率范围内的辐射比其**附近的连续光谱**遭到**更多的减弱**，形成了吸收线
- 基本物理过程：原子在两个**分立能级**之间的跃迁
- 选择真吸收：再发射过程具有**热辐射性质**，在局部热动平衡假设下满足基尔霍夫定律
  - 吸收光量子跃迁到高能级之后，**碰撞退激发**
  - 吸收光量子跃迁到高能级之后，**再吸收光量子电离**
- 选择散射：与热辐射无关
  - 吸收光量子跃迁到高能级之后，**跳回原能级，辐射光子** (自发辐射各向同性)

> 如果吸收光量子跃迁到高能级之后，跳回另一个能级——不是真吸收也不同于前面的散射

- 联锁效应：把在某条谱线里吸收的能量转移到其它谱线，引起同一种原子不同谱线之间的能量交换
  - 多种多样，极其复杂
  - 基尔霍夫定律不适用，必须根据**散射过程的定义**来导出**再发射系数**和**散射系数**之间的关系



### 散射辐射系数

- $\sigma_\nu$： 单位质量的散射系数，因为散射是各向同性的，$\sigma_\nu$ 与角度无关

- 单位质量物质在单位时间、单位频率间隔内由于散射过程引起的辐射能量减弱为
  $$
  \sigma_\nu\int_{4\pi}I_\nu(\theta)\text{d}\omega
  $$
  这个能量就是被散射到各个方向的能量

- 假设**散射是相干的**，即再辐射出去的光量子频率准确地和原来入射的频率相同 (事实上能级有一定的宽度，这是由不确定性关系 $\Delta E\Delta t\ge\hbar/2$ 决定的，入射频率和散射频率并不一定一样，这个不同是本质上的) ，只是方向发生了变化，则单位质量的散射辐射系数为：
  $$
  j _ { \nu } = \frac { 1 } { 4 \pi } \sigma _ { \nu } \int _ { 4 \pi } I _ { \nu } ( \theta ) \text{d} \omega = \sigma _ { \nu } J _ { \nu }
  $$





## 吸收线的辐射转移方程

在吸收线所在频率处及辐射向外转移的过程中，一般来说不仅仅遭受到连续真吸收和连续散射，还受到选择真吸收和选择散射——建立吸收线内辐射转移方程

- 根据能量守恒
  $$
  \begin{align*}
  &\cos \theta \frac { \text{d} I _ { \nu } ( \theta , h ) } { \text{d} h }\\
  =& (体元吸收的能量) - (体元辐射的能量)\\
  =&+(连续真吸收的能量) + (连续散射的能量) \\
  &+ (选择真吸收的能量) + (选择散射的能量)\\
  &-(连续热辐射的能量) - (连续散射辐射的能量) \\
  &- (选择热辐射的能量) - (选择散射辐射的能量)
  \end{align*}
  $$
  右端的所有能量都在单位时间、单位体积、单位立体角和单位频率间隔内

- 对恒星大气中任意一条确认的谱线，吸收线占据的波长范围很窄 ( $T=5800$ K 时，谱线半高全宽 $3$ km/s )

  > 半高全宽 (FWHM) 
  >
  > 波峰一半处对应的展宽为 $\Delta \lambda$ ，类比多普勒效应：
  > $$
  > \frac{\Delta \lambda}{\lambda}=\frac{v}{c}
  > $$
  > 则我们可以用 $v$ 表示谱线的展宽

- 连续吸收系数随频率或波长的变化一般来说相当缓慢——一条吸收线范围内，近似为常数

- 选择吸收系数变化剧烈——必须加下标 $\nu$ 

- 对所讨论的谱线

  - 连续真吸收系数 $\chi$
  - 连续散射系数 $\sigma$
  - 选择真吸收系数 $\chi_\nu=\epsilon_\nu l_\nu$ ，$l_\nu$ 是总选择吸收系数，$\epsilon_\nu$ 是真吸收在其中的比例
  - 选择散射系数 $\sigma_\nu=l_\nu-\chi_\nu=(1-\epsilon_\nu)\chi_\nu$

  从而得到各种能量：

  - 连续真吸收能量 $I _ { \nu } \chi \rho$
  - 连续热辐射能量 $\left( \rho j _ { \nu } = \rho \chi j _ { \nu } / \chi = \rho \chi S _ { \nu} = \right) \chi \rho B _ { \nu} ( T )$
  - 连续散射的能量 $I _ { \nu } \sigma $
  - 连续散射辐射的能量 $\sigma \rho J _ { \nu } ( h )$
  - 选择真吸收的能量 $I _ { \nu } \chi _ { \nu } \rho = I _ { \nu} \varepsilon _ { \nu} l _ { \nu} \rho$
  - 选择热辐射的能量 $\left[ \rho j _ { \nu } = \rho \chi _ { \nu} \left( j _ { \nu} / \chi _ { \nu } \right) = \right] \chi _ { \nu } \rho B _ { \nu } ( T ) = \epsilon _ { v } l _ { \nu } \rho B _ { \nu } ( T )$
  - 选择散射的能量 $I _ { \nu } \sigma _ { \nu } \rho = I _ { \nu } \left( 1 - \varepsilon _ { \nu } \right) l _ { \nu } \rho$
  - 选择散射辐射的能量 $\sigma _ { \nu } \rho J _ { \nu } ( h ) = \left( 1 - \epsilon _ { \nu } \right) l _ { \nu } \rho J _ { \nu} ( h )$

- 代入化简即得**吸收线内辐射转移方程**
  $$
  \begin{align*}
  \cos \theta \frac { \text{d} I _ { \nu } ( \theta , h ) } { \rho \text{d} h } &= \left( \chi + \sigma + \chi _ { \nu } + \sigma _ { \nu } \right) I _ { \nu } ( \theta , h )   - \left( \sigma + \sigma _ { \nu } \right) J _ { \nu } ( h ) - \left( \chi + \chi _ { \nu } \right) B _ { \nu } ( T ) \\
  &= \left( \chi + \sigma + l _ { \nu } \right) I _ { \nu } ( \theta , h ) - \sigma J _ { \nu } ( h ) - \left( 1 - \epsilon _ { \nu } \right) l _ { \nu } J _ { \nu } ( h ) - \chi B _ { \nu } ( T ) - \epsilon _ { \nu } l _ { \nu } B _ { \nu } ( T )
  \end{align*}
  $$
  对于非O、B型星，则连续散射 (主要是电子散射) 的作用可忽略不计，取连续散射系数 $\sigma=0$ ：
  $$
  \begin{align*}
  \cos \theta \frac { \text{d} I _ { \nu } ( \theta , h ) } { \rho \text{d} h } &=\left( \chi + \chi _ { \nu } + \sigma _ { \nu } \right) I _ { \nu } ( \theta , h )- \sigma _ { \nu } J _ { \nu } ( h ) - \left( \chi + \chi _ { \nu } \right) B _ { \nu } ( T )\\
  &= \left( \chi + l _ { \nu } \right) I _ { \nu } ( \theta , h ) -  \left( 1 - \epsilon _ { \nu } \right) l _ { \nu } J _ { \nu } ( h ) - \chi B _ { \nu } ( T ) - \epsilon _ { \nu } l _ { \nu } B _ { \nu } ( T )
  \end{align*}
  $$

- 两个隐含假设：

  - 散射是相干的，散射光量子频率不变——实际上往往非相干
  - 没有考虑联锁效应
    - 吸收的能量和再辐射能量之间没有很直接的联系，类似于真吸收



## 反变层模型(S-S模型)下辐射转移方程的解

### 反变层模型

- 恒星的连续光谱是由恒星光球发出,而吸收线则是在一个比较冷的、位于光球之上的大气层产生,这个大气层就称为反变层

#### 恒星表面连续谱辐射强度与角度的关系

- 相当于考虑临边昏暗
  $$
  \frac { I _ { \nu } ^ { 0 } ( \theta ) } { I _ { \nu } ^ { 0 } ( 0 ) } = \frac { \left( 1 + \beta _ { 0 } \cos \theta \right) } { \left( 1 + \beta _ { 0 } \right) }
  $$

- 这里的 $\beta_0$ 对应将 $B_\nu(T)$ 在 $\tau$ 处展开时得到的线性项
  $$
  B_\nu(T)=B _ { \nu } \left( T _ { 0 } \right) \left( 1 + \beta _ { 0 } \tau \right)
  $$


#### 求解辐射转移方程

- 吸收线产生时没有连续谱产生，连续谱散射为 $0$ 

- 只讨论纯散射过程，真吸收为 $0$
  $$
  \chi=0,\ \sigma=0,\ \chi_\nu=0
  $$

- 辐射转移方程
  $$
  \cos \theta \frac { \mathrm{d} I _ { \nu } ( \theta , h ) } { \rho  \mathrm{d} h } = \sigma _ { \nu } I _ { \nu } ( \theta , h ) - \sigma _ { \nu } J _ { \nu } ( h )
  $$
  对立体角积分，左边为单色辐射流对光深的导数，右边为 $0$ ，从而单色辐射流和光深无关

#### 剩余强度

- 辐射强度平均法（爱丁顿近似）：$I_\nu$ 和 $I_\nu'$ 分别代表向外和向内的平均辐射强度
  $$
  \frac{2}{3}\frac { \mathrm{d} \left( I _ { v } + I _ { v } ^ { \prime } \right) } { \mathrm{d}\tau _ { v } } = \left( I _ { v } - I _ { v } ^ { \prime } \right)=4H_\nu
  $$

- 利用 $H_\nu=F_\nu/4$ 和 $F_\nu$ 为常数
  $$
  I _ { \nu } + I _ { \nu } ^ { \prime } = 6 H _ { \nu } \tau _ { \nu } + 4H _ { \nu }
  $$

- 引入反变层在 $\nu$ 处因选择散射引起的光深 $\tau^\sigma_\nu$ ，反变层底部由光球发出，进入反变层的平均辐射强度 $( I ) _ { \tau ^ { \sigma }_\nu }$ 
  $$
  H _ { \nu } = \frac{\left( I _ { \nu } \right) _ { \tau _ { \nu } ^ { \sigma } } } {\left[ 4 \left( 1 + \frac { 3 } { 4 } \tau _ { \nu } ^ { \sigma } \right) \right]}
  $$
  在表面上 $H_\nu=(I_\nu)_{\tau_\nu^\sigma}/4$

- 累积辐射剩余强度
  $$
  r _ { \nu } = \frac { F _ { \nu } } { F _ { \nu } ^ { 0 } } = \frac { H _ { \nu } } { H _ { \nu } ^ { 0 } } = \left( 1 + \frac { 3 } { 4 } \tau _ { \nu } ^ { \sigma } \right) ^ { - 1 }
  $$

- 精确解
  $$
  r_\nu=\left[ 1 + \tau _ { \nu } ^ { \sigma } \varphi \left( \tau _ { \nu } ^ { \sigma } \right) \right] ^ { - 1 }
  $$

- 光深很小时 $\varphi\to1$ ，光深很大时 $\varphi\to 3/4$

#### 星面上某点的辐射强度剩余强度

相当复杂

#### 缺点

-  认为吸收线和连续光谱分别产生于截然分开的大气层
  - 作为近似：谱线处吸收系数比连续谱吸收系数大，对应光深小，形成吸收线大气更浅
  - 若线吸收系数比连续谱吸收系数大得多，近似较好

## M-E模型*
