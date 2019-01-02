# Chapter 1 恒星大气辐射理论基础



## 引言

### 恒星大气

- 恒星大气是指恒星上能被直接观测到的表面层
- 太阳大气的三个主要层次
  - 光球
    - 大气底层密度较大的部分叫作光球,也就是能用白光观测到的表面层
    - 它的厚度与恒星半径相比一般很小（太阳：500 km，太阳半径的 0.04%）
    - 光学辐射基本上是光球发出的(黑体辐射)，恒星亮度基本上由光球决定:连续(黑体)谱和吸收线谱是在光球层内产生的
  - 色球
    - 紧接着光球的是色球(用单色光可看到的大气部分)
    - 太阳色球层厚度约 2000 km，半径的 0.3%
    - 可在日全食的时既和生光前短暂时刻观测到,也可以用单色光进行观测——红色的辉光，$\ce{H}\alpha$ 线主导
    - 光谱远紫外区和射电波段有显著贡献,但对可见光区的贡献可忽略不计
    - 在F—M型晚型星和O—A型早型星等大量恒星中观测到与太阳色球物理性质相似的恒星色球层
  - 日冕
    - 太阳大气最外层
    - 厚度数百万千米，远大于太阳半径
    - 可见光辐射可忽略——日全食或日冕仪观测
    - 从射电直至X-射线(韧致辐射或自由-自由辐射)波段都有辐射
    - 观测表明,几乎所有光谱型恒星(除非常冷的超巨星和某些巨星)都有冕
  - 绝大多数恒星的光谱：连续谱+吸收线，在厚度比恒星半径小得多的光球层内形成
  - 极个别有发射线：大气厚度可与恒星的半径相比拟甚至大得多——这种大气称为延展的大气或恒星包层

- 恒星大气理论的主要任务：通过对恒星光谱的解释来研究恒星大气的**物理状态**、**物理过程**和**化学组成**

  - 恒星大气模型的建立：它的任务是研究恒星大气各个物理量，如温度、压力和密度等随深度的分布
  - 恒星连续光谱的研究
  - 恒星吸收光谱的研究
  - 恒星发射光谱的研究
  - 恒星大气化学组成的研究


## 宏观描写辐射场的几个基本物理量

### 辐射强度 $I$

- 单色辐射强度：在空间中 $P$ 点，在单位时间内，穿过辐射方向 $\theta$ 上单位横截面积，在单位立体角和单位频率间隔内的辐射能量
  $$
  I=I(P,\theta,t,\nu)
  $$

- 单位 $\mathrm { erg }\cdot \mathrm { cm } ^ { - 2 } \cdot \mathrm { sec } ^ { - 1 } . \mathrm { Hz } ^ { - 1 } \cdot\mathrm { Sr } ^ { - 1 }$

- 与选择面元方向无关（只考虑单位横截面积，也就是面元在辐射方向垂直平面上的投影）

### 辐射流 $\pi F$

- 单色辐射流：在空间中 $P$ 点，在单位时间内，穿过单位面积，在单位频率间隔内的辐射能量(正向通过与反向通过之差)
  $$
  \pi F_\nu=\int_{4\pi}I_\nu\cos\theta\text{d}\omega
  $$

- 单位 $\mathrm { erg }\cdot \mathrm { cm } ^ { - 2 } \cdot \mathrm { sec } ^ { - 1 } \cdot\mathrm { Hz } ^ { - 1 } $

- 与面元在空间里的**位置**和**方向**都有关——辐射流矢量
  $$
  \vec { f } ( P ,\nu , t ) \equiv \int _ { 4 \pi } I _ { \nu } \vec { l } \mathrm{d} \omega,\ F=\vec f\cdot\vec n
  $$
  $\vec l$ 是立体角元的单位法向矢量，$\vec n$ 是面元单位法向矢量，辐射流是辐射流矢量在法线上的投影

- 在真空中,沿辐射传播方向的路径上,辐射强度不变,但辐射流与到辐射源距离的平方成反比

  - 真空中总能量守恒，球面积 $\sim r^2$ ，辐射流 $\sim r^{-2}$
  - 单位面积立体角 $\sim \mathrm{d}\sigma/r^2$ 也是与距离成平方反比，所以辐射强度不随距离变化

- 沿着半径向外的辐射流——恒星大气和内部我们往往只关注向外的能流，$0<\theta<\pi/2$
  $$
  \pi F_\nu=2 \pi \int _ { 0 } ^ { \frac{\pi}{2} } I _ { \nu } ( \theta ) \cos \theta \sin \theta \mathrm{d} \theta
  $$
  这里我们已经假设了 $I_\nu$ 与 $\phi$ 无关（旋转对称性）

### 平均辐射强度 $J$

- 单色平均辐射强度：取辐射强度对方向的平均
  $$
  J_\nu=\frac{1}{4\pi}\int_{4\pi}I_\nu\mathrm{d}\omega
  $$

- 单位 $\mathrm { erg }\cdot \mathrm { cm } ^ { - 2 } \cdot \mathrm { sec } ^ { - 1 } \cdot\mathrm { Hz } ^ { - 1 }$ ——这里已经把立体角积掉了

- 各向同性的辐射：$I_\nu=J_\nu$

### 辐射密度 $U$

- 单色辐射密度：某一时刻单位体积内所包含的单位频率间隔的辐射能量
  $$
  U_\nu=\frac{1}{c}\int_{4\pi}I_\nu\mathrm{d}\omega
  $$

- 单位 $\mathrm { erg } \cdot \mathrm { cm } ^ { - 3 } \cdot \mathrm { Hz } ^ { - 1 }$

### 辐射压力 $P_R$

- 单色辐射压：单位时间通过单位面积的单位频率间隔辐射所携带的动量——单色辐射垂直施加于单位面积的压力
  $$
  P_{R,\nu}=\frac{1}{c}\int_{4\pi}I_\nu\cos^2\theta\mathrm{d}\omega
  $$

- 单位 $\mathrm { erg } \cdot \mathrm { cm } ^ { - 3 } \cdot \mathrm { Hz } ^ { - 1 }$，与能量密度同量纲

- 对于各向同性的辐射（热动平衡）
  $$
  P_{R,\nu}=\frac{2}{3}U_\nu
  $$

- 辐射压力是张量

  - 辐射压力依赖于面元的取向,随面元法线的方向不同而不同

  - 辐射本身是矢量,它可以是沿着不同方向传播到该面元，于是总辐射压力是三个方向辐射产生的分压力的矢量叠加

  - 辐射压力还可在空间三个方向上进行分解，同一总压力可以是不同分量组合得到——辐射压力是一个张量
    $$
    [{ P } _ {R,\nu} ( r , t )]_{jk} = \frac { 1 } { c } \int _ { 4 \pi } I _ { \nu } ( r , \vec { l } , t ){ l}_j{ l }_k d \omega
    $$







## 发射系数、消光(吸收)系数和源函数

### 发射系数 $j_\nu$

- 单位质量的物质在单位时间、单位频率间隔和 $\theta$ 方向单位立体角内发射的能量
- 单位 $\mathrm{ erg } \cdot \mathrm{g}^ { - 1 } \cdot \sec ^ { - 1 } \cdot \mathrm { sr } ^ { - 1 } \cdot\mathrm{Hz} ^ { - 1 }$
- 通常是位置、方向和频率的函数

### 吸收系数 $\chi_\nu$

- 质量吸收系数：辐射通过单位质量的物质后辐射强度的相对减弱
  $$
  \mathrm{d}I_\nu=-\chi_\nu\rho I_\nu\mathrm{d}s
  $$
  经过厚度为 $s$ 的吸收层后，辐射强度指数衰减
  $$
  I_\nu=I_\nu(0)\exp(-\int_0^s\chi_\nu\rho\mathrm{d}s)\equiv I_\nu(0)\exp(-\tau_{\nu})
  $$
  指数 $\tau_\nu$ 称为吸收层的光深

  - $\tau_\nu>1$ ，光学厚；反之光学薄

- 单位 $\mathrm { cm } ^ { 2 } \cdot\mathrm { g } ^ { - 1 }$

### 源函数 $S_\nu$ 

- 发射系数与吸收系数之比
  $$
  S_\nu\equiv j_\nu/\chi_\nu
  $$







## 辐射转移方程

- 当辐射通过一个既能发射辐射又能吸收辐射的介质时，**辐射强度**随**厚度**会发生变化

### 静止介质中的辐射转移方程

- 在介质中取一块圆柱体薄片，令光线垂直进入，能量会发生改变，改变量等于体积元发射与吸收之差

- 辐射转移方程
  $$
  \frac{\mathrm{d}I_\nu}{\mathrm{d}s}=(-I_\nu\chi_\nu+j_\nu)\rho
  $$

- 恒星大气层厚度远小于恒星半径——平面平行层近似

  - 取恒星大气层垂直线深度 $h$ 作自变量(沿视线由外向内为正) 
    $$
    \mathrm{d}h=-\cos\theta\mathrm{d}s\\
    \cos\theta\frac{\mathrm{d}I_\nu}{\mathrm{d}h}=(I_\nu\chi_\nu-j_\nu)\rho
    $$

  - 利用光深 $\rho\chi_\nu\mathrm{d}h=\mathrm{d}\tau$
    $$
    \cos\theta\frac{\mathrm{d}I_\nu}{\mathrm{d}\tau_\nu}=I_\nu-S_\nu
    $$

- 恒星大气厚度与半径相当——球坐标系

  - 普遍的一阶微分方程
    $$
    \cos \theta \frac { \partial I _ { \nu } } { \partial r } - \frac { \sin \theta } { r } \frac { \partial I _ { \nu } } { \partial \theta } = I _ { \nu } \chi _ { , } \rho - j _ { \nu } \rho
    $$

- 与时间有关的辐射场

  - 含时的微分方程
    $$
    \frac { \partial I _ { \nu } } { \partial s } + \frac { 1 } { c } \frac { \partial I _ { \nu } } { \partial t } = - I _ { \nu } \chi _ { \nu } \rho + j _ { \nu } \rho
    $$







## 辐射转移方程的解及其物理意义

### 辐射转移方程的解

- 把光球内每一点向外的辐射和向内的辐射分开处理

- 向外辐射，辐射方向用 $\theta\in[0,\pi/2)$ 表示，$\cos\theta>0$ 

- 向内辐射，辐射方向用 $\psi\equiv\pi-\theta\in[0,\pi/2)$表示

- 辐射转移方程化为两个方程，具有相似的解

- 向外辐射的形式解，注意在介质表面上光深为 $0$
  $$
  I_\nu(\theta,\tau_\nu)=C_\nu e^{\tau_\nu\sec\theta}+\int_{\tau_\nu}^\infty S_\nu e^{-(t_\nu-\tau_\nu)\sec\theta}\sec\theta\mathrm{d}t_\nu
  $$

  - 物理意义

    - 第二项：光深大于 $\tau_\nu$ 的所有物质层的发射传播到光深 $\tau_\nu$ 处的叠加

    - 第一项：上述物质辐射以外的附加成分——只能来自光深无穷处，强度为无穷大的辐射，实际上不存在，因而第一项为 $0$
      $$
      C_\nu e^{\tau_\nu\sec\theta}=\lim_{t_\nu\to\infty}C_\nu e^{t_\nu\sec\theta} e^{-(t_\nu-\tau_\nu)\sec\theta}
      $$

  - 一般表达式
    $$
    I_\nu(\theta,\tau_\nu)=\int_{\tau_\nu}^\infty S_\nu e^{-(t_\nu-\tau_\nu)\sec\theta}\sec\theta\mathrm{d}t_\nu
    $$

- 向内辐射的形式解（与向外辐射符号有区别）
  $$
  I_\nu(\psi,\tau_\nu)=D_\nu e^{-\tau_\nu\sec\psi}+\int_0^{\tau_\nu} S_\nu e^{(t_\nu-\tau_\nu)\sec\psi}\sec\psi\mathrm{d}t_\nu
  $$

  - 物理意义

    - 第二项：光深小于 $\tau_\nu$ 的所有物质层的发射传播到光深 $\tau_\nu$ 处的叠加
    - 第一项：上述物质辐射以外的附加成分——来自光球层外
      - 一般可以忽略
      - 密近双星不能忽略
      - 受主星照射的行星大气、受冕照射的吸积盘不能忽略

  - 一般表达式
    $$
    I_\nu(\psi,\tau_\nu)=\int_0^{\tau_\nu} S_\nu e^{(t_\nu-\tau_\nu)\sec\psi}\sec\psi\mathrm{d}t_\nu
    $$

- 形式解包含源函数，必须知道源函数的形式及其随光深的分布



## 局部热动平衡假设

### 理想热动平衡

对于绝热封闭系统中的辐射场

- 可以定义温度（在体系各处相同），且温度不随时间改变

- 热辐射均匀而各向同性，数值由普朗克函数决定
  $$
  B _ { \nu } ( T ) = \frac { 2 h \nu ^ { 3 } } { c ^ { 2 } } \frac { 1 } { e ^ { h \nu / k T } - 1 }
  $$

- 热发射系数和热吸收系数之间的关系满足基尔霍夫定律(吸收与发射达到平衡)
  $$
  j_\nu=\chi_\nu B_\nu(T)
  $$

- 电子的速度分布、原子的激发和电离可以分别用与系统温度T对应的麦克斯韦速度分布定律、波尔兹曼公式和萨哈公式来描述

### 局部热动平衡假设

- 恒星内部存在温度梯度——引入温度描述系统的局部性质
    - 对恒星大气内每一点 $P$，可以用一个温度 $T$ 来描述(碰撞足够多)
    - $P$ 点附近的体元就像绝热地封闭在一个温度为 $T$ 的封闭系统中一样
    - 对于这个小体元，与局部温度对应的理想热动平衡严格成立

- 实际应用时需要检验

    - 把理论结果与观测进行对比
    - 检查假设下解出的恒星大气物理条件是否允许局部热动平衡规律成立

- 源函数 $S_\nu=j_\nu/\chi_\nu=B_\nu(T)$

- 辐射转移方程简化为
    $$
    \cos\theta\frac{\mathrm{d}I_\nu}{\mathrm{d}\tau_\nu}=I_\nu(\theta,\tau_\nu)-B_\nu
    $$
    仍需了解 $B_\nu(T)$ 随光深的分布



## 辐射平衡

### 辐射平衡条件

- 每一体元单位时间获得和损失的总能量相等 $\Rightarrow$ 发射=吸收

- 考虑体元 $\mathrm{d}V=\mathrm{d}\sigma\cdot\mathrm{d}s$ 的全部立体角和辐射的所有频率
  $$
  E_+=\mathrm{d}m\int_0^\infty\mathrm d\nu\int_{4\pi} \chi_\nu I_\nu \mathrm d\omega\\
  E_-=\mathrm{d}m\int_0^\infty\mathrm d\nu\int_{4\pi}j_\nu \mathrm d\omega
  $$

- 两者相等，$\chi_\nu$ 各向同性
  $$
  \int_0^\infty\mathrm d\nu\int_{4\pi} \chi_\nu I_\nu \mathrm d\omega=\int_0^\infty\mathrm d\nu\int_{4\pi}j_\nu \mathrm d\omega\\
  \Rightarrow 4\pi\int_0^\infty\mathrm \chi_\nu J_\nu d\nu =\int_0^\infty\mathrm d\nu\int_{4\pi}j_\nu \mathrm d\omega
  $$

- 利用局部热动平衡假设可以进一步化简
  $$
  \int_0^\infty\chi_\nu J_\nu\mathrm d\nu=\int_0^\infty\chi_\nu B_\nu\mathrm d\nu
  $$





### 辐射平衡条件下的总辐射流

- 在辐射平衡的平面平行层大气里，**总辐射流**是一个不随深度变化的常数
  $$
  \frac{\mathrm{d}}{\mathrm d h}(\pi F)=0
  $$

- 单色辐射流和延伸(非平面平行)光球的总辐射流不满足这样的规律

### 辐射平衡条件下的辐射压

- 单色辐射压
  $$
  \frac { \mathrm d P _ { R,\nu } } { \mathrm d h } = \frac { \pi } { c } \chi _ { \nu } \rho F _ { \nu }
  $$

- 总辐射压
  $$
  \frac { \mathrm d P _ { R } } { \mathrm d h } = \int_0^\infty\frac { \pi } { c } \chi _ { \nu } \rho F _ { \nu }\mathrm d\nu\equiv\frac { \pi } { c } \overline\chi  \rho F
  $$
  $\overline\chi$ 是以单色辐射流为权重，对频率加权的平均吸收系数

- 引入平均光深，$\mathrm d\overline\tau=\overline\chi\rho\mathrm d h$ ，得到辐射压随光深的变化率
  $$
  \frac { \mathrm d P _ { R } } { \overline\chi  \rho\mathrm d h } = \frac { \mathrm d P _ { R } } { \mathrm d \overline\tau }=\frac { \pi } { c }  F
  $$
  是一个常数——在辐射平衡条件下，总辐射压力对光学厚度的微商是常数

- 仍然需要知道温度随光深的分布，这要求给出吸收系数随光深的分布



## 灰大气的温度分布和辐射强度的第一近似

- 灰色物质：吸收系数与频率无关——灰大气

- 辐射转移方程简化为 ($\mathrm{d}\tau=\mathrm{d}\tau_\nu$)
  $$
  \cos\theta\frac{\mathrm{d}I(\theta,\tau)}{\mathrm{d}\tau}=I(\theta,\tau)-B(T)
  $$

- 辐射平衡条件简化为
  $$
  B(T)=\int_0^\infty J_\nu\mathrm d\nu=J(\tau)
  $$
  此时辐射转移方程
  $$
  \cos\theta\frac{\mathrm{d}I(\theta,\tau)}{\mathrm{d}\tau}=I(\theta,\tau)-J(\tau)
  $$
  是关于 $\tau$ 的积分微分方程

### 爱丁顿近似法（辐射强度平均法）

- 引入三个针对方向平均的参量
  $$
  J=\frac{1}{4\pi}\int_{4\pi}I(\theta)\mathrm{d}\omega\\
  H=\frac{1}{4\pi}\int_{4\pi}I(\theta)\cos\theta\mathrm{d}\omega=\frac{1}{4}F\\
  K=\frac{1}{4\pi}\int_{4\pi}I(\theta)\cos^2\theta\mathrm{d}\omega=\frac{c}{4\pi}P_R
  $$

- 辐射平衡下，$H$ 是常数，$K$ 对 $\tau$ 的导数恰为 $H$，$K=H\tau+C$

- 爱丁顿引入第一近似，假设辐射强度随方向缓变，对于 $0\le\theta<\pi/2$ 和 $\pi/2\le\theta<\pi$ 分别取泰勒展开的零级近似 $I_1$ 和 $I_2$，代表向外和向内的辐射强度，它们与方向无关，仅与光深有关
  $$
  J=\frac{1}{2}(I_1+I_2),\ H=\frac{1}{4}(I_1-I_2),\ K=\frac{1}{3}J
  $$

- $\tau=0$ 时没有传入的辐射，$I_2(0)=0$ 
  $$
  J(0)=\frac{1}{2}I_1(0),\ H=\frac{1}{4}I_1(0),\\
  K(0)=\frac{1}{3}J(0)=\frac{2}{3}H\\
  \Rightarrow K=\left(\tau+\frac{2}{3}\right)H,\ J=\left(3\tau+2\right)H
  $$

- 由 Stefan-Boltzmann 定律
  $$
  \pi B=\sigma T^4,\ \pi F=\sigma T_{eff}^4
  $$
  $T$ 是特定体元的温度，$T_{eff}$ 是整个恒星的有效温度，可以由观测给出

- 结合辐射平衡条件 $B=J$ 和定义 $H=F/4$ 
  $$
  T ^ { 4 } = \frac { T _ { e f f } ^ { 4 } } { 2 } \left( 1 + \frac { 3 } { 2 } \tau \right)
  $$

- $\tau=0$ 给出表面温度
  $$
  T_0=\frac{T_{eff}^4}{2}
  $$

- 解出有效温度对应的光深 $\tau=2/3$ ——有效层

- 得到向内和向外的辐射强度
  $$
  { I _ { 1 } = J + 2 H  =H( 4 + 3 \tau ) } \\ 
   { I _ { 2 } = J - 2H = 3 H \tau }
  $$




## 太阳圆面的临边昏暗规律

- 太阳圆面(日轮)各处的亮度是不均匀的。圆面中心亮度最大,愈向边缘,亮度愈小,颜色越黄。边缘区域亮度只有中心的40%左右——临边昏暗
- 等价于考虑 $I_\nu(\theta,0)$ 随 $\theta$ 的分布，$\theta$ 是太阳圆面上一点对应半径与观测者视线方向夹角，从中心到边缘由 $0$ 变化到 $\pi/2$

### 定性研究

- 对于太阳表面
  $$
  I_\nu(\theta,0)=\int_{0}^\infty B_\nu e^{-t_\nu\sec\theta}\sec\theta\mathrm{d}t_\nu
  $$

- 由于
  $$
  \int_{0}^\infty e^{-t_\nu\sec\theta}\sec\theta\mathrm{d}t_\nu=1
  $$
  $I_\nu$ 可以看作 $B_\nu$ 在分布函数 $e^{-t_\nu\sec\theta}\sec\theta$ 下的期望，显然光深较小时的 $B_\nu$ 的权重更大

- 对于较小的 $\theta$ ，$\sec\theta$ 小，有显著贡献的光深更大，而光深越大温度越高，$B_\nu$ 也就越大，从而此时的辐射强度较大，对应日轮中心更明亮

### 定量研究

- 化成总辐射强度，并引入温度分布规律
  $$
  \begin{aligned}
  I(\theta,0)&=\int_{0}^\infty B e^{-\tau\sec\theta}\sec\theta\mathrm{d}\tau\\
  &=\frac{F}{4}\int_{0}^\infty (2+3\tau) e^{-\tau\sec\theta}\sec\theta\mathrm{d}\tau\\
  &=\frac { F } { 2 } \left( 1 + \frac { 3 } { 2 } \cos \theta \right)
  \end{aligned}
  $$

  $$
  \Rightarrow I(0,0)=\frac{5}{4}F,\ I(\theta,0)=I ( 0,0 ) \left( \frac { 2 } { 5 } + \frac { 3 } { 5 } \cos \theta \right) = I ( 0,0 ) \left( 1 - u + u\cos \theta \right)
  $$

- 这里 $u=0.6$ ，观测给出 $u=0.56$

- 取 $\theta=\pi/2$ ，辐射强度为中心的 40%，符合得很好

