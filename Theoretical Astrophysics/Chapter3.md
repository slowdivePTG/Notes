# Chapter 3 恒星大气模型和恒星连续光谱



## 非灰大气辐射平衡理论的一般解法

吸收系数和频率相关——非灰大气



### In this chapter：

1. 研究非灰大气**辐射转移方程**的解法

2. 从理论上得出恒星**连续光谱能量的分布**

3. 研究恒星大气的物理结构——大气内各个物理量随**深度**的分布情况


### 辐射平衡情况

在辐射平衡条件下求解辐射转移方程
$$
\cos \theta \frac { \text{d} I _ { \nu} \left( \theta , \tau _ { \nu } \right) } { \text{d} \tau _ { \nu } } = I _ {\nu} \left( \theta , \tau _ {\nu } \right) - S _ {\nu } \left( \tau _ {\nu } \right)
$$
$\tau_{\nu}$由与频率有关的吸收系数$\chi_{\nu}$决定

回忆辐射转移方程的形式解(向外/内传递)，必须还要求出温度$T$和光深$\tau$的关系
$$
I _ { \nu} \left( { \theta } ,  { \tau } _ {\nu } \right) = \int _ { \tau _ { \nu } } ^ { \infty } S _ { \nu } e ^ { - \left( t _ { \nu} - \tau _ { \nu} \right) \sec \theta } \sec  { \theta } \text{d} t _ { \nu}
$$

$$
I _ { \nu} ^ { \prime } \left( { \psi } ,  { \tau } _ { \nu} \right) = \int _ { 0 } ^ { \tau _ { \nu } } S _ { \nu } e ^ { - \left( \tau _ { \nu} - t _ { \nu } \right) \sec \psi } \sec \boldsymbol { \psi } \text{d} t _ { \nu }
$$

非灰大气下：$S_{\nu}(\tau_{\nu})=B_{\nu}(T_{\tau_{\nu}})$，温度和光深的关系和频率有关，只能采用**逐次近似法**

- 把灰大气的温度分布作为一级近似

- 引入某种对频率的**加权平均吸收系数** $\overline{\chi}$ 来代替 $\chi_\nu$

- 选择一个归一化的权重函数 $W_{\nu}(p_e,T)$ ，对吸收系数进行加权平均：
  $$
  \overline{\chi}(p_e,T)=\int_0^\infty W_{\nu}(p_e,T)\chi_\nu(p_e,T)\text{d}\nu
  $$






- 有时对吸收系数的**倒数**进行加权平均


#### 权重函数的选取

简单、具有一定的物理意义、近似程度足够好使**迭代过程收敛足够快**

1. 罗斯兰 (Rosseland) 平均 (与 $K_\nu$ 相关)

   回忆：Eddington在处理灰大气时引入了三个量$J,H,K$，我们可以引入相应单色量：
   $$
   J _ { \nu } \equiv \frac { 1 } { 4 \pi } \int _ { 4 \pi } I _ { \nu } ( \theta ) \text{d} \omega
   $$

   $$
   H _ { \nu} \equiv \frac { 1 } { 4 \pi } \int _ { 4 \pi } I _ { \nu } ({ \theta } ) \cos  { \theta } \text{d} { \omega } = \frac { 1 } { 4 } F _ { \nu }
   $$

   $$
   K _ { \nu } \equiv \frac { 1 } { 4 \pi } \int _ { 4 \pi } I _ { \nu } ( \theta ) \cos ^ { 2 } \theta \text{d} \omega = \frac { c } { 4 \pi } P _ { R , \nu }
   $$

   以 $\cos \theta \text{d} \omega / 4 \pi$ 乘以辐射转移方程两端并对 $4\pi$ 立体角积分：
   $$
   \frac { 1 } { 4 \pi } \frac { \text{d} } { \text{d} \tau _ { \nu } } \int _ { 4 \pi } I _ { v } \left( \theta , \tau _ { \nu } \right) \cos ^ { 2 } \theta \text{d} \omega = \frac { 1 } { 4 \pi } \int _ { 4 \pi } I _ { \nu } \left( \theta , \tau _ { \nu } \right) \cos \theta \text{d} \omega
   $$

   $$
   \Rightarrow \frac { \text{d}K _ { \nu } } { \text{d} \tau _ { \nu } }=H_\nu=\frac{1}{4}F_\nu=\frac { \text{d}K _ { \nu } } {  \chi _ { \nu }\rho\text{d} h }
   $$

   两端对频率积分，同乘上 $\rho$ ：
   $$
   \frac{\rho}{4}F=\int_0^\infty\frac { \text{d}K _ { \nu } } {  \chi _ { \nu }\text{d} h }\text{d}\nu
   $$
   另一方面，在辐射平衡下，**灰大气的总辐射压**和**总辐射流**之间存在关系：
   $$
   \frac { \text{d} P _ { R } } { d \overline { \tau } } = \frac { \pi } { c } F \Rightarrow \frac { 1 } { \overline { \chi } \rho } \frac { d P _ { R } } { d h } = \frac { \pi } { c } F
   $$
   又因为 $K=\frac{c}{4\pi}P_R$ ，我们得到：
   $$
   \frac { 1 } { \overline{\chi} \rho } \frac { 4 \pi } { c } \frac { \text{d} K } { \text{d} h } = \frac { \pi } { c } F = \frac { 1 } { \overline { \chi } } \frac {\text{d} K } { \text{d} h } = \frac { \rho } { 4 } F
   $$
   从而：
   $$
   \frac { 1 } { \overline { \chi } } \frac {\text{d} K } { \text{d} h } =\int_0^\infty\frac { \text{d}K _ { \nu } } {  \chi _ { \nu }\text{d} h }\text{d}\nu
   $$
   这也就给出了 $\overline{\chi}$ 的定义，即给出了相应的灰大气——**保证等价灰大气给出的总辐射流和非灰大气给出的辐
   射流有同样数值**

   $K_\nu$ 仍然未知，需要进一步变换

   假设辐射场对各向同性偏离很小，$J_\nu\approx B_\nu$对恒星大气**深层**是很好的近似
   $$
   \Rightarrow K_\nu=\frac{1}{2}\int_0^\pi I _ {\nu}(\theta,\tau_\nu)\cos ^ { 2 } \theta \sin \theta \text{d} \theta \simeq \frac { 1 } { 2 } J _ { \nu } \int_0^\pi cos ^ { 2 } \theta \sin \theta \text{d} \theta = \frac { J _ { \nu } } { 3 } \simeq \frac { 1 } { 3 } B _ { \nu }
   $$

   $$
   \Rightarrow \frac{1}{\overline{\chi}_R}=\frac{\displaystyle{\int_0^\infty\frac { \text{d}K _ { \nu } } {  \chi _ { \nu }\text{d} h }\text{d}\nu}}{\displaystyle{\frac {\text{d} K } { \text{d} h } }}
   $$

   $\overline{\chi}_R$ 为Rosseland平均吸收系数

2. 钱德拉塞卡平均 (与 $F_\nu$ 相关)

   钱德拉塞卡发现，在讨论非灰大气的温度分布时，如果实际的恒星大气和灰大气偏离不大，平均吸收系数用下式计算比较好：
   $$
   \overline { \chi } _ { C } = \frac { 1 } { F } \int _ { 0 } ^ { \infty } \chi _ { \nu } F _ { \nu } ^ { ( 1 ) } \text{d} \nu
   $$
   其中 $F _ { \nu } ^ { ( 1 ) }$ 是(待确定的)等价灰大气的单色辐射流

   ##### 确定等价灰大气的单色辐射流

   - 爱丁顿近似：将辐射光分解成向外和向内的两束，然后并分别用方向平均值代替。	

   - 钱德拉塞卡 (分立坐标法)：

     - 将辐射光按角度分解成独立的 $2n$ 束，然后每束用平均值代替，每束光就仅是光深 $\tau_\nu$ 的函数，$I_\nu$ 随方向的变化可以展开成方向的多项式
     - 高斯：在这种情况下，方向积分(平均强度)可以用一个求和准确表示，只是要求第 $i$ 个方向 $μ_i =\cos{\theta}$， $\mu_i$ 是 $2n$ 阶勒让德多项式 $P _{2n} (\mu)$ 的第 $i$ 个零点
     -  $n\to\infty$ ——灰大气的精确解；$n=1$ ——爱丁顿近似解

   - 结论：
     $$
     T ^ { 4 } = \frac { 3 } { 4 } T _ { \mathrm { eff } } ^ { 4 } ( \tau + q ( \tau ) )
     $$

     $$
     q ( 0 ) = 0.577 \leq q ( \tau ) \leq q ( \infty ) = 0.7104
     $$

     $q(\tau)$ 随光深缓慢、单调、平滑增加，爱丁顿近似下 $q(\tau)\equiv2/3$ ——非常稳的近似 
     $$
     \frac { T } { T _ { \mathrm { eff } } } = \left\{ \frac { 3 } { 4 } [ \tau + q ( \tau ) ] \right\} ^ { 1 / 4 } = f ( \tau )
     $$
     局部热动平衡假设下源函数由普朗克函数给出：
     $$
     S _ { v } ^ { ( 1 ) } ( \tau ) = B _ { v } ^ { ( 1 ) } ( \tau ) = \frac { 2 h v ^ { 3 } } { c ^ { 2 } } \left[ e ^ { u / f ( \tau ) } - 1 \right] ^ { - 1 }
     $$

     $$
     u=\frac{h\nu}{kT_{\text{eff}}}
     $$

     利用辐射转移方程的形式解，得到等价灰大气的辐射流：
     $$
     \begin{align}
     F _ { \nu } ^ { ( 1 ) } &= \frac { 1 } {  \pi } \int _ { 4 \pi } I _ { \nu }^{(1)} ({ \theta } ) \cos  { \theta } \text{d} { \omega }=2\int _ { 0 \leq \theta \leq \pi / 2 } I _ { \nu } ^ { ( 1 ) } \cos \theta \sin \theta \text{d} \theta - 2 \int _ { 0 \leq \psi \leq \pi / 2 } I _ { \nu } ^ { ( 1 ) } \cos ( \psi ) \sin ( \psi ) \text{d} \psi \\
     \stackrel{代入形式解}{\Longrightarrow} &= - 2 \int _ { \tau } ^ { \infty } \int _ { 0 } ^ { \pi / 2 } B _ { \nu } ^ { ( 1 ) } ( t ) e ^ { - ( t - \tau ) \sec \theta } d \cos \theta \text{d} t + 2 \int _ { 0 } ^ { \tau } \int _ { 0 } ^ { \pi / 2 } B _ { v } ^ { ( 1 ) } ( t ) e ^ { - ( \tau - t ) \sec \psi } \text{d} \cos \psi \text{d} t\\
     \stackrel{\mu=\cos\theta}{\Longrightarrow}& =2\int _ { \tau } ^ { \infty } B _ { \nu } ^ { ( 1 ) } ( t ) \left[ \int _ { 0 } ^ { 1 } e ^ { - ( t - \tau ) / \mu } \text{d} \mu \right] \text{d} t - 2 \int _ { 0 } ^ { \tau } B _ { \nu} ^ { ( 1 ) } ( t ) \left[ \int _ { 0 } ^ { 1 } e ^ { - ( \tau - t ) / \mu } \text{d} \mu \right] \text{d} t\\
     \stackrel { y = 1 / \mu } { \Longrightarrow }& = 2 \int _ { \tau } ^ { \infty } B _ { \nu } ^ { ( 1 ) } ( t ) \left[ \int _ { 1 } ^ { \infty } \frac { e ^ { - ( t - \tau ) y } } { y ^ { 2 } } \text{d} y \right] \text{d} t - 2 \int _ { 0 } ^ { \tau } B _ { \nu } ^ { ( 1 ) } ( t ) \left[ \int _ { 1 } ^ { \infty } \frac { e ^ { - ( \tau - t ) y } } { y ^ { 2 } } \text{d} y \right] \text{d} t\\
     \stackrel { 引入记号 } { \Longrightarrow }&= 2 \int _ { \tau } ^ { \infty } B _ { \nu } ^ { ( 1 ) } ( t ) E_2(t-\tau) \text{d} t - 2 \int _ { 0 } ^ { \tau } B _ { \nu } ^ { ( 1 ) } ( t )E_2(-t+\tau)  \text{d} t\equiv{ \Phi } _ { \tau } \left\{ B _ { \nu } ^ { ( 1 ) } ( t ) \right\}
     \end{align}
     $$

     只能用数值积分，其中 $E_2(x)$ 是 $E _ { m } ( x ) \equiv \int _ { 1 } ^ { \infty } e ^ { - x y } y ^ { - m } \text{d} y$ 在 $m=2$ 时的情形，而作用算符$\Phi_\tau$ ：
     $$
     \Phi _ { \tau } \{ f ( t ) \} \equiv 2 \int _ { \tau } ^ { \infty } f ( t ) E _ { 2 } ( t - \tau ) \text{d} t - 2 \int _ { 0 } ^ { \tau } f ( t ) E _ { 2 } ( \tau - t ) \text{d} t
     $$
     知道了 $F _ { \nu } ^ { ( 1 ) }$ ，就得到了钱德拉塞卡吸收系数

3. 普朗克平均 (与 $B_\nu$ 相关)

   在局部热动平衡假设下，总发射等于总吸收的**辐射平衡条件**给出
   $$
   \int_0^\infty\chi_\nu B_\nu\text{d}\nu=\int_0^\infty\chi_\nu J_\nu\text{d}\nu
   $$
   定义普朗克平均吸收系数：
   $$
   \overline { \chi } _ { P }=\frac{1}{B}\int_0^\infty\chi_\nu B_\nu\text{d}\nu
   $$




   这样，普朗克平均 (以普朗克函数为权重) 的平均吸收系数能给出正确的**总发射**

#### 构造等价灰大气的方法

1. $T-\tau$ 关系：由灰大气的近似解 (爱丁顿/钱德拉塞卡近似) 给出

2. $\tau-\tau_\nu$ 关系：

   灰大气的光学深度为：
   $$
   \tau = \int _ { 0 } ^ { h } \overline { \chi } \rho \text{d} h
   $$
   真实大气的光学深度和等价灰大气的光学深度的关系为：
   $$
   \tau_\nu=\int_0^h\chi_\nu\rho\text{d}h=\int_0^h\frac{\chi_\nu}{\overline{\chi}}\overline{\chi}\rho\text{d}h=\int_0^\tau\frac{\chi_\nu}{\overline{\chi}}\text{d}t
   $$
   $\chi _ { \nu } / \overline { \chi }$ 一般是 $P_e, T, \nu$ 的函数，从而给定 $\tau-\tau_\nu$ 关系

3. 由 1 和 2 得到 $T-\tau_\nu$ 关系

4. 代入辐射转移方程形式解，给出向外和向内传播的单色辐射强度

5. 求出单色辐射流和总辐射流
   $$
   \pi F_\nu=\int_{4\pi}I_\nu\cos\theta\text{d}\omega,\quad \pi F=\int_{4\pi}I\cos\theta\text{d}\omega
   $$
   这样就得到了**第一近似**的结果

根据辐射平衡理论，总辐射流应和深度无关，但由于等价灰大气模型的近似性，在第一近似下得到的总辐射流是不会和深度无关的——必须**逐次修正**

##### 逐次修正的一般准则

- 利用灰大气近似结果

- 求出新的温度分布，使得辐射平衡条件(总辐射与总吸收相等)总是得到满足，即辐射流在**所有光深 $\tau$ **上等于或最接近于给定的常数 $\sigma T _ { \text { eff } } ^ { 4 }$


#### 逐级近似的方法

1. 斯特龙根 (B. Stroemgren) 方法

   利用钱德拉塞卡近似+Stefan-Boltzmann定律：
   $$
   B ( \tau ) = \frac { 3 } { 4 } F [ \tau + q ( \tau ) ]\Rightarrow\frac { T } { T _ { \text{eff} } } = \left[ \frac { B ( \tau ) } { F } \right] ^ { 1 / 4 } = \left\{ \frac { 3 } { 4 } [ \tau + q ( \tau ) ] \right\} ^ { 1 / 4 } = f ( \tau )
   $$

   - 局部热动平衡下黑体辐射分布和源函数的第一次近似 $\left( u = h v / k T _ { \text { eff } } \right)$：

   $$
   S _ { v } ^ { ( 1 ) } = B _ { v } ^ { ( 1 ) } = \frac { 2 h v ^ { 3 } } { c ^ { 2 } } \left[ \mathrm { e } ^ { u / f ( \tau ) } - 1 \right] ^ { - 1 }
   $$

   - 平均单色辐射强度的第一次近似 (做法很接近求钱德拉塞卡吸收系数那一块)：

   $$
   \begin{align}
   J _ { v } ^ { ( 1 ) } &= \frac { 1 } { 4 \pi } \int _ { 4 \pi } I _ { \nu } ^ { ( 1 ) } d \omega = \frac {1} { 2 } \int _ { 0 \leq \theta \leq \pi / 2 } I _ { \nu } ^ { ( 1 ) } \sin \theta \text{d} \theta + \frac { 1} {2 } \int _ { 0 \leq \psi \leq \pi / 2 } I _ { \nu } ^ { ( 1 ) } \sin \psi \text{d} \psi\\
   &=\frac { 1 } { 2 } \int _ { \tau } ^ { \infty } B _ { \nu } ^ { ( 1 ) } ( t ) \left[ \int _ { 0 } ^ { 1 } e ^ { - ( t - \tau ) / \mu } \frac { \text{d} \mu } { \mu } \right] \text{d} t + \frac { 1 } { 2 } \int _ { 0 } ^ { \tau } B _ { \nu } ^ { ( 1 ) } ( t ) \left[ \int _ { 0 } ^ { 1 } e ^ { - ( \tau - t ) / \mu } \frac { \text{d} \mu } { \mu } \right] \text{d} t\\
   \stackrel { y = 1 / \mu } { \Longrightarrow }&=\frac { 1 } { 2 } \int _ { \tau } ^ { \infty } B _ { \nu } ^ { ( 1 ) } ( t ) \left[ \int _ { 1 } ^ { \infty } \frac { e ^ { - | t - \tau | y } } { y } \text{d} y \right] \text{d} t + \frac { 1 } { 2 } \int _ { 0 } ^ { \tau } B _ { \nu } ^ { ( 1 ) } ( t ) \left[ \int _ { 1 } ^ { \infty } \frac { e ^ { - | \tau - t | y } } { y } \text{d} y \right] \text{d} t \quad(*)\\
   &= \frac { 1 } { 2 } \int _ { 0 } ^ { \infty } B _ { v } ^ { ( 1 ) } ( t ) \left[ \int _ { 1 } ^ { \infty } \frac { e ^ { - | t - \tau | y } } { y } \text{d} y \right] \text{d} t = \frac { 1 } { 2 } \int _ { 0 } ^ { \infty } B _ { v } ^ { ( 1 ) } ( t ) E _ { 1 } ( |t - \tau | ) \text{d} t \\
   &\equiv \Lambda _ { \tau } \left\{ B _ { v } ^ { ( 1 ) } ( t ) \right\} 
   = \Lambda _ { \tau } \left\{ S _ { v } ^ { ( 1 ) }\right\}
   \end{align}
   $$

   >  $(*)$ 行出现绝对值是因为在第一项中，$t$ 取 $\tau$ 到 $\infty$，$t-\tau$ 必然大于零，可加上绝对值；第二项中 $t$ 取 $0$ 到 $\tau$，$\tau-t$ 必然大于零，可加上绝对值

   - 把由此得到的平均单色辐射强度代入辐射平衡条件的右端，得到第二次近似的普朗克函数随光深的分布：

   $$
   \int_0^\infty\chi_\nu B_\nu^{(2)}(\tau)\text{d}\nu=\int_0^\infty\chi_\nu J_\nu^{(1)}(\tau)\text{d}\nu
   $$

   - 第二次近似的源函数：

   $$
   S _ { \nu } ^ { ( 2 ) } = B _ { \nu} ^ { ( 2 ) }
   $$

   - 再用 $\Lambda _ { \tau }$ 算符作用于第二近似下的源函数，得到第二近似下的平均辐射强度：

   $$
   J _ { v } ^ { ( 1 ) }=\Lambda _ { \tau } \left\{ S _ { v } ^ { ( 1 ) }\right\}
   $$

   以此类推，万世不竭

   > 研究表明，这个方法对小光学深度收敛快，但对大的光学深度收敛性差

2. 温索德方法 (先求总辐射流法)

   利用钱德拉塞卡解法得到局部热动平衡下黑体辐射分布和源函数的第一次近似之后

   - 先计算单色辐射流的第一近似：

   $$
   F _ { \nu } ^ { ( 1 ) } ( \tau ) = \Phi _ { \tau } \left\{ B _ { \nu } ^ { ( 1 ) } ( t ) \right\}
   $$

   - 在每一个深度对单色辐射流全频率积分，得到总辐射流的第一近似 $\pi F^{(1)}$，一般不等于给定的 $\pi F$

   - 对于每一光学层，计算 $\Delta F = F - F ^ { ( 1 ) }$ ，得到 $\Delta F-\tau$ 关系

   - 找出新的温度分布 (或源函数) ，使 $\Delta F \rightarrow 0$ ，具体方法：

     - 将辐射转移方程的两端乘以 $\text { d } \omega / 4 \pi$ ，并假定 $\chi _ { v } = \overline { \chi }$ 时有 $\mathrm { d } \tau _ { \nu } = \mathrm { d } \tau$ ，即只考虑**真吸收**，然后对所有频率和立体角积分：
       $$
       \frac { 1 } { 4 } \frac { \text{d} F } { \text{d} \tau } = J - B
       $$
       求差分：
       $$
       \Delta B=\Delta J - \frac { 1 } { 4 } \frac { \text{d} \Delta F } { \text{d} \tau }
       $$

     - 求 $\Delta J$ ：

       由爱丁顿灰大气近似，我们有总辐射压强梯度不随深度变化，以及 $K$ 和 $J$ 的关系：
       $$
       \frac { c } { 4 \pi } \frac { \text{d} P _ { R } } {\text{d} \tau } = \frac { \text{d} K } { \text{d}\tau } = H = \frac { 1 } { 4 } F
       $$

       $$
       K\approx\frac{1}{3}J
       $$

       $$
       \Rightarrow \frac{1}{3}\frac { \text{d} J } { \text{d}\tau }  = \frac { 1 } { 4 } F \Rightarrow \frac { \text{d} \Delta J } { \text{d}\tau }  = \frac { 3 } { 4 } \Delta F \Rightarrow  { \Delta } J = \frac { 3 } { 4 } \int _ { 0 } ^ { \tau } \Delta F \text{d} t + ( \Delta J ) _ { \tau = 0 }
       $$

       爱丁顿近似下，零光深边界上有：
       $$
       \left. \begin{array} { c } { J = \frac { 1 } { 2 } \left( I _ { 1 } + I _ { 2 } \right) } \\ { H = \frac { 1 } { 4 } \left( I _ { 1 } - I _ { 2 } \right) } \end{array} \right\} \Rightarrow ( J ) _ { \tau = 0 } \xlongequal { I _ { 2 } ( 0 ) = 0 } 2 ( H ) _ { \tau = 0 } =  \frac { 1 } { 2 } ( F ) _ { \tau = 0 }
       $$

       $$
       \Rightarrow\Delta J = \frac { 3 } { 4 } \int _ { 0 } ^ { \tau } \Delta F \text{d} t + \frac { 1 } { 2 } ( \Delta F ) _ { \tau = 0 }
       $$



     - 把关于 $\Delta J$ 的方程代入关于 $\Delta B$ 的方程：
       $$
       \Delta B=\Delta J - \frac { 1 } { 4 } \frac { \text{d} \Delta F } { \text{d} \tau }=\frac { 3 } { 4 } \int _ { 0 } ^ { \tau } \Delta F \text{d} t + \frac { 1 } { 2 } ( \Delta F ) _ { \tau = 0 }- \frac { 1 } { 4 } \frac { \text{d} \Delta F } { \text{d} \tau }
       $$


   只要把已知的 $\Delta-\tau$ 关系代入，就可以得到初始温度分布或者源函数的改正 $\Delta B$ 

   > 温索德方法在光学深度较大处能给出较好的结果



#### 以上方法的特点

- 先引入平均吸收系数，构造等价的灰大气
- 用等价灰大气的解作为第一次近似
- 用各种近似方法求温度或者源函数的第二次近似和更高次近似
- 这种程序也不是在任何情况下都是必须的，例如对太阳，可以从观测到的临边昏暗规律定出温度的分布



## 计算恒星大气模型的一般方法





## 早型光谱型恒星的大气模型和连续光谱能量分布*



## 对流
辐射平衡理论是建立在**辐射**是**唯一**的能量转移方式的基础上的，它忽略了**对流**的作用

- 对于处于平衡态的恒星，如果不存在扰动，就不会发生恒星大气内部物质的宏观运动，也就不存在对流，因此恒星大气将处在辐射平衡状态

- 但实际上恒星大气内扰动总是或多或少存在——研究辐射平衡是否稳定

- 如果辐射平衡不稳定，则任何轻微的扰动都会导致大规模的质量运动和能量以对流方式转移。

- 现在我们已经知道，对流在不少恒星以及其它系统中起着重要作用。

### Schwarzchild辐射平衡稳定判据

### 各种光谱型恒星中的对流区
- 极早光谱型恒星大气：氢几乎完全电离，辐射平衡起决定性作用，仅存在与He I电离为He II相联系的很薄、很微弱的对流带，它在能量转移中的作用可忽略。

- 对于A型星,薄的氢电离导致的对流带开始在浅光深($\tau \approx 2$)上出现和发展。

- F型星的对流带相比A型星要更深和更厚些。从F2—F5型的恒星大气里,对流在能量转移中起着相当重要的作用。

- 对于晚型星(温度低，有各种自由度，$\gamma\approx1$)，对流带发展得更深，对流在转移能量上变得非常有效
- 到M型星，整个恒星几乎完全是对流的。

### 能量的对流转移

辐射平衡不满足，但仍满足能量守恒——对流运动本身是物质运动，这种运动会在能量转移上起作用——能量的**对流转移**

在对流带：

- 若有一向上运动的体元，运动后它与邻近物质比较起来压力相等，但密度较小

- 理想气体方程 ($p = \rho k T / u m _ { H }$) 表明其温度较高，体元带着超额的热能向上运动

- 一个向下的体元，因为运动后它与周围环境物质相比有较高的密度，因而有较低的温度，这相当于体元带着不足的热能向下运动

- 总的结果是，不管是向上还是向下的对流运动，都会使能量由下向上转移，即由恒星内向恒星外转移。



当对流存在时，辐射平衡就被破坏：

- 对流把能量从热层带到冷层,使温度梯度减少。晚型星，内外温差小。

- 由于辐射流正比于温度梯度，辐射流也就相应地减少，直至总能流满足(不考虑热传导，效率低)：

$$
\pi F = \pi F _ { \mathrm { rad } } + \pi F _ { \mathrm { conv } } = \sigma T _ { \mathrm { eff } } ^ { 4 }
$$

然后出现一种新的平衡状态

### 混合程理论

恒星大气的对流具有湍动性质，是各种大小不同的湍流元或湍流泡泡的运动及其与周围物质相互作用的一种物理现象

——唯象理论，粗糙但物理图像清晰 (如果使用数值模拟，物理图像不清晰)

#### 混合程 $l$:

- 假定存在一个平均的流体元,它经过一个特征距离 $l$ 之后就完全与周围物质混合而消失

- 这个特征距离 $l$ ，也就是对流元自形成至混合瓦解所走过的距离，称为混合程。

- 在这个过程中，能量转移的结果是使温度梯度减小；在对流的物质运动中，向上(或向下)运动的体元带走多余(或不足)的能量至周围物质

对流不存在时的辐射平衡梯度：$\nabla _ { R } \equiv \left( \frac { d \ln T } { d \ln P } \right) _ { R }$，绝热梯度：$\nabla _ { A } \equiv \left( \frac { d \ln T } { d \ln P } \right) _ { A } = \frac { \gamma - 1 } { \gamma }$，对流元相应的梯度：$\nabla _ { E } \equiv \left( \frac { d \ln T } { d \ln P } \right) _ { E }$对流与辐射同时存在，真实的温度梯度：$\nabla \equiv \left( \frac { d \ln T } { d \ln P } \right)$

• 那么,当大气层处于对流状态时,通常有

#### 对流转移的辐射流

考虑一个上升的体元,如图:
• 如果δT是体元与周围物质的温度差,

• 当体元与周围物质混合时(体元的温度比周围高),单位体积释放的超额能量为:$\rho \mathbf { c } _ { \mathbf { p } } \delta \mathbf { T }$，其中c p 为定压比热

• 当体元以平均速度走过距离 Δr 时,转移的能流是
$$\pi F _ { \text { conv } } = \rho c _ { p } \overline { \mathrm { v } } \delta T = \rho c _ { p } \overline { \mathrm { v } } \left[ \left( - \frac { d T } { d r } \right) - \left( - \frac { d T } { d r } \right) _ { E } \right] \Delta r$$

式中,有下标E的物理量是对流元的温度梯度,而无下标的物理量是辐射和对
流同时存在时(即周围环境)的温度梯度。

• 在给定的大气层,体元所走路程(大小)是混乱分布的。对所有体元求平均,并
取。

• 根据流体静力学平衡方程,$\frac { d P } { d r } = - \rho g$
我们引入压力标高(压力发生显著变化所需要的高度，绝对值因而有负号):
$$H \equiv - \frac { P } { ( d P / d r ) } = - \left( \frac { d \ln P } { d r } \right) ^ { - 1 } = \frac { P } { \rho g }$$

因为梯度(压力标高与温度标高之比,或对数温度随对数压力的变化)

于是,对流转移的辐射流改写为

平均速度
要计算平均速度,令作用在体元上的上浮力(实际为浮力与重力之差)所做的功等于体元获得的动能。

设 为体元与其周围物质的密度差,则浮力可表示为：

微分理想气体物态方程($P = \rho kT/\mu m H $)的对数形式并求导：
$$
\begin{align*} \text{d} ( \ln \rho ) & = \text{d}( \ln P ) - \text{d} ( \ln T ) + \text{d} ( \ln \mu ) = \text{d} ( \ln P ) - \text{d}( \ln T ) + \left( \frac { \partial \ln \mu } { \partial \ln T } \right) \text{d} ( \ln T ) \\ & = \text{d} ( \ln P ) - \left( 1 - \frac { \partial \ln \mu } { \partial \ln T } \right) \text{d} ( \ln T ) = \text{d} ( \ln P ) - Q \text{d} ( \ln T ) \end{align*}
$$

其中

因为在压力平衡下,δP = 0,于是理想气体方程给出：
浮力改写为：
$$
\begin{align*} f _ { b } & = - g \delta \rho = g Q \rho \frac { \delta T } { T } = \frac { g Q \rho } { T } \left[ \left( - \frac { d T } { d r } \right) - \left( - \frac { d T } { d r } \right) _ { E } \right] \Delta r \\ & = \frac { g Q \rho } { T } \left( \frac { T } { H } \nabla - \frac { T } { H } \nabla _ { E } \right) \Delta r = \frac { g Q \rho } { H } \left( \nabla - \nabla _ { E } \right) \Delta r \end{align*}
$$
上式表明，浮力是 Δr 的线性函数(因ρ是典型密度,H的变化在高次项)。

• 对浮力做的功dW=f b dΔr: 作路径Δ积分,并令Δ = l /2(即前半程加速做功，后半程物体减速，主要考虑物体与周围物质的相互作用，前半段浮力为主，后半段粘滞为主一个粗略的假设),

得到作用于体元上的功的平均值

浮力加速体元的同时还需要克服近邻体元的摩擦阻力。

假定所作功的一半用来推动近邻的体元,也就是损失于摩擦;而另一半用来提供体元的动能,
即$$\frac { 1 } { 2 } \boldsymbol { \rho } \overline { \mathbf { v } } ^ { 2 } = \frac { 1 } { 2 } \overline { \boldsymbol { W } }$$
于是求得平均速度
$$\overline { \mathbf { v } } = \left( \frac { \overline { W } } { \rho } \right) ^ { 1 / 2 } = \left( \frac { g Q H } { 8 } \right) ^ { 1 / 2 } \left( \nabla - \nabla _ { E } \right) ^ { 1 / 2 } \left( \frac { l } { H } \right)$$

将平均速度代入辐射流表达式：

上式中,混合程$ l$的大小未知, 通常假定经历大约\textbf{几个压力标高}后,对流元就完
全与周围物质混合而消失,即

• $l = n H$,其中取$n=1, 2,\cdots$
一般$n$取1,2，最多3，bubble就消失了

\noindent 对流的效率参数

在上面的分析计算中,我们忽略了对流元在上升过程中的辐射(绝热膨胀假设)，然而,对流元上升时,因其温度高于周围物质而会向周围物质辐射。

• 由于对流元瓦解时,多余的能量正比于 ( ∇ − ∇ E ) ,而辐射的损失正比于 ( ∇ E − ∇ A )

• 于是,我们定义对流转移能量的\textbf{效率参数}为转移能量与辐射损失能量之比,即
$$\xi = \frac { \nabla - \nabla _ { E } } { \nabla _ { E } - \nabla _ { A } }$$

• 对流元的多余能量可表示为 ρ c P V δ T ,其中V为对流元体积,δT是对流元瓦解
时它与周围的温度差。

辐射损失依赖于对流元是光学薄还是光学厚的:

• 对于\textbf{光学薄极限}，单位时间、单位体积辐射损失率($4\pi$立体角积分)为(由发射率减吸收决定)
$$\Delta E _ { R } \approx 4 \pi j _ { E } \rho - 4 \pi \overline { \chi } B = 4 \pi \rho \overline { \chi } \left( B _ { E } - B \right) = 4 \pi \rho \overline { \chi } \Delta B$$
• 假设对流元在整个路程中的平均温度差为ΔT≈δT/2,其寿命$\tau _ { \mathrm { age } } \approx l / \overline { \mathbf { v } }$,则有
$$\xi _ { \text { thin } } = \frac { \nabla - \nabla _ { E } } { \nabla _ { E } - \nabla _ { A } } = \frac { \rho c _ { p } V \delta T } { 4 \pi \rho \overline { \chi } \Delta B V \tau _ { \text { age } } } = \frac { \rho c _ { p } V \delta T } { 4 \pi \left( 4 \sigma T ^ { 3 } / \pi \right) ( \delta T / 2 ) \rho \overline { \chi } V ( l / \overline { v } ) } \approx \frac { \rho c _ { P } \overline { v } } { 8 \sigma T ^ { 3 } } \frac { 1 } { \tau _ { l } }$$
其中$\pi B=\sigma T^4,\Delta B=4\sigma T^4/\pi,\tau _ { 1 } = \overline { \chi } \rho l$是具有特征长度$l$的对流元的光学厚度

• 对于光学厚,辐射通过单位面积的辐射流为(设A为体元表面积)
$$T^4=\frac{T_{eff}^4}{2}\left(1+\frac{3}{2}\tau\right)\Longrightarrow B=\frac{F}{4}()\Longrightarrow\pi \Delta F \approx \frac { 16 \sigma T ^ { 3 } } { 3 \overline { \chi } \rho } \left( - \frac { d T } { d r } \right)$$

在现在的情况下,令 ( − dT dr ) ≈ ( δ T l ) ,并假设对流元为球状,则对具有特征
长度l 的对流元,我们近似有 V/A= (4/3)π l 3 /4π l 2 ≈ l /3。

于是效率参数变为
$$\xi _ { \text { thick } } \approx \frac { \rho c _ { p } V \delta T } { \left( \frac { 16 \sigma T ^ { 3 } } { 3 \overline { \chi } \rho } \right) \left( \frac { \delta T } { l } \right) A \left( \frac { l } { \overline { v } } \right) } =\frac { \rho c _ { p } \overline { \mathbf { v } } } { 16 \sigma T ^ { 3 } } \cdot 3 \overline { \chi } \rho \left( \frac { V } { A } \right) \approx \frac { \left( \rho c _ { P } \overline { v } \right) } { 16 \sigma T ^ { 3 } } 3 \overline { \chi } \rho \frac { l } { 3 } = \frac { \rho c _ { p } \overline { v } } { 8 \sigma T ^ { 3 } } \frac { 1 } { 2 } \tau _ { 1 }$$

上述效率系数分别是在极端光薄和极端光厚的假设下得到的。我们可以把它们统一起来写为一个桥梁公式
$$\xi \approx \frac { \rho c _ { P } \overline { v } } { 8 \sigma T ^ { 3 } }\frac { \left( 1 + \frac { 1 } { 2 } \tau _ { l } ^ { 2 } \right) } { \tau _ { l } }$$

内插法，此式(桥梁公式)可近似地用于$\tau l\approx1$的情况:

• 对于光学薄的对流元,光学厚度愈小,效率参数愈大;

• 对于光学厚的对流元,光学厚度愈大,效率参数愈大。

把对流也考虑进去的大气模型,比只考虑辐射平衡的模型复杂得多。一般

1. 首先要假设一个初始的温度分布,

2. 利用流体静力学平衡条件计算气体压力、辐射压力等物理量的分布,

3. 然后计算温度的辐射梯度$\nabla_{ R }$ 和绝热梯度$\nabla_{ A }$,根据史瓦西稳定判据确定哪些层
    存在对流(复杂性在于边界处)

4. 在对流存在的区域把对流在能量转移中的作用考虑进去,用总能量守恒代替辐
    射平衡,在非对流区域再重新应用辐射平衡条件;

5. 对温度较低的晚型恒星大气,建立模型时必须考虑对流的影响。

## 其他光谱型恒星的大气模型*
### 太阳型恒星的大气模型
• 太阳大气模型被研究最多,除理论的太阳大气模型外,还有半经验模型。这是因为太阳大气的半经验模型由观测到的太阳临边昏暗现象得到。

观测到的太阳临边昏暗律为
$$\varphi _ { \lambda } ( \theta ) = \frac { I _ { \lambda } ( \theta , 0 ) } { I _ { \lambda } ( 0,0 ) } = A _ { \lambda } + C _ { \lambda } \cos \theta + D _ { \lambda } \cos ^ { 2 } \theta$$
常数可以由观测决定。由向外传递的辐射转移方程的形式解：
$$I _ { \lambda } ( \theta , 0 ) = \int _ { 0 } ^ { \infty } B _ { \lambda } e ^ { - \tau _ { \lambda } \sec \theta } \sec \theta d \tau _ { \lambda }$$
$$\varphi _ { \lambda } ( \theta ) = \frac { I _ { \lambda } ( \theta , 0 ) } { I _ { \lambda } ( 0,0 ) } = \int _ { 0 } ^ { \infty } \frac { B _ { \lambda } ( T ) } { I _ { \lambda } ( 0,0 ) } e ^ { - \tau _ { \lambda } \sec \theta } \sec \theta d \tau _ { \lambda }$$
由于被积函数随光深的增加而呈指数衰减,因此当我们把$B_λ /I_λ$ 展开成$\tau_λ$ 的多项
式时,积分仍是收敛的:
$$\mathbf { B } _ { \lambda } / \mathbf { I } _ { \lambda } = \mathbf { a } _ { \lambda } + \mathbf { c } _ { \lambda } \tau _ { \lambda } + \mathbf { d } _ { \lambda } \tau _ { \lambda } ^ { 2 } + \dots$$
$$
\begin{align*}
	\varphi _ { \lambda } ( \theta ) &= \int _ { 0 } ^ { \infty } \left( a _ { \lambda } + c _ { \lambda } \tau _ { \lambda } + d _ { \lambda } \tau _ { \lambda } ^ { 2 } + \cdots \right) e ^ { - \tau _ { \lambda } \sec \theta } \sec \theta d \tau _ { \lambda }\\
	&= \int _ { 0 } ^ { \infty } \left( a _ { \lambda } + \cos \theta c _ { \lambda } \sec \theta \tau _ { \lambda } + \cos ^ { 2 } \theta \mathrm { d } _ { \lambda } \sec ^ { 2 } \theta \tau _ { \lambda } ^ { 2 } + \cdots \right) e ^ { - \tau _ { 2 } \sec \theta } d \left( \sec \theta \tau _ { \lambda } \right)\\
	&=\int _ { 0 } ^ { \infty } \left( a _ { \lambda } + \cos \theta c _ { \lambda } x + \cos ^ { 2 } \theta d _ { \lambda } x ^ { 2 } + \cdots \right) e ^ { - x } d x = a _ { \lambda } + \cos \theta c _ { \lambda } + 2 \cos ^ { 2 } \theta d _ { \lambda } + \cdots\\
	&=A _ { \lambda } + C _ { \lambda } \cos \theta + D _ { \lambda } \cos ^ { 2 } \theta
\end{align*}
对于任意$\theta$成立，则$\frac { B _ { \lambda } ( T ) } { I _ { \lambda } ( 0,0 ) } = A _ { \lambda } + C _ { \lambda } \tau _ { \lambda } + \frac { 1 } { 2 } D _ { \lambda } \tau _ { \lambda } ^ { 2 }$
$$
• 由太阳邻边昏暗规律定出积分常数后,上式就给出太阳大气中温度随深度分
布的经验规律。

• 有了温度分布后,其它物理量就可用3.2介绍的“计算恒星大气模型的
一般方法”求得。

• 太阳大气的理论模型详细计算超出本课程的内容,因此这里不作介绍。

### 太阳型恒星

太阳型恒星的大气模型基本上分两类:

• 一类是建立在太阳大气半经验模型基础上的比率模型,其温度分布用下式给
出(假设温度分布规律相同)

$$T ( \tau ) = T _ { \odot } ( \tau ) \frac { T _ { e f f } } { T _ { e f f , \odot } }$$

有了温度分布后,其它物理量的分布就由流体静力学平衡条件等导出。

• 另外一类和其它光谱型恒星大气模型一样,是建立在能流守恒基础上的自洽
的理论模型。

### 其它晚型恒星大气模型

在计算晚型恒星大气模型时,主要需注意下列两点:

1. 晚型恒星大气中,分子吸收在晚型恒星大气的不透明度中起支配作用,

2. 必须考虑对流在能量转移中的作用。