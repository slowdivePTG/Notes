

# Chapter 5 线吸收系数



## 原子的线吸收系数和它的积分公式

把形式解定量化——需要知道 (单位质量) 线吸收系数 $l_\nu$ 和真吸收占比 $\epsilon_\nu$

观测表明：谱线有内禀展宽——线吸收系数在一个**频率间隔**内都有数值

- 确定线吸收系数物理机制
  - 辐射阻尼
  - 多普勒效应
  - 压力效应
- 这些机制确定的线吸收系数如何随频率分布
- 先讨论每一种机制单独作用，然后讨论几种机制的联合作用



### 原子线吸收系数 $a_\nu$

考虑某一条吸收谱线，单位体积内谱线低能级原子数为 $N_j$ ；在谱线频率范围内，$\theta$ 方向的辐射的衰减满足：
$$
\text{d}I_\nu\equiv-I_\nu a_\nu N_j \text{d}h
$$
$a_\nu$ 反应辐射经过一个吸收原子后 (等效) 的减弱比率

单位时间、单位体积在 $\text{d}\nu$ 内，被谱线吸收的能量为：
$$
N_j\cdots
$$
对频率积分，得到吸收总能量：
$$

$$
$a_\nu$ 充分大的谱线都很窄，$J_\nu$ 的变化很小，近似为常数：
$$

$$
由原子受激跃迁概率 $B_{jk}$ 定义，也可以得到吸收总能量：
$$
N_{j}B_{jk}J_\nu h\nu_{jk}
$$
两者相等，得到吸收系数的积分公式：
$$
\int_\nu a_\nu\text{d}\nu=\frac{h\nu_{jk}}{4\pi}B_{jk}
$$

- 原子的吸收系数沿自己谱线的积分只依赖于**原子特性**，和谱线致宽的**物理机制**无关

- $a_\nu$ 不包括负吸收，如果辐射强度大则必须考虑负吸收，得到
  $$
  4\pi N_j\int_\nu a_\nu'\text{d}\nu=N_j{h\nu_{jk}}B_{jk}-N_k{h\nu_{jk}}B_{kj}
  $$

  $$
  \int_\nu a_\nu'\text{d}\nu=\frac{}{}
  $$

- 如果局部热动平衡成立，可以利用玻尔兹曼公式：
  $$
  \int_\nu a_\nu'\text{d}\nu=\frac{h\nu_{jk}}{4\pi}B_{jk}(1-e^{-h\nu_{jk}/kT})
  $$
  这是考虑负吸收之后的吸收系数积分公式，$a_\nu'=a_\nu(1-e^{-h\nu_{jk}/kT})$



## 辐射阻尼和谱线的自然致宽



### 辐射阻尼的经典理论

发射、吸收来自带电粒子组成的谐振子的振动

- 发射：激发态谐振子简谐振动，辐射总功率满足拉莫尔公式：
  $$
  P=\frac{2e^2}{3c^3}|\dot{v}|^2
  $$

- 吸收：在入射光波作用下，谐振子受迫振动

- 发射过程中，辐射带走能量动量，考虑辐射场对电子的反作用——**辐射阻尼**

- 一维谐振子辐射的电磁波不是**等幅波**，振幅指数衰减
  $$
  \epsilon(t)=Ae^{-\gamma_0t/2}\cdot e^{-i\omega_0t}=A\int_{-\infty}^{\infty}E(\omega)e^{-i\omega_0t}\text{d}\omega
  $$
  $E(\omega)$ 是辐射波在频率空间的分布，它不是一个 $\delta$ 函数，而有一定展宽：
  $$
  E(\omega)=-\frac{1}{}
  $$

















- 吸收系数为振幅的平方
  $$
  k_\omega=\frac{4\pi e^2}{m_e c}\frac{\gamma_0}{4(\omega-\omega_0)^2+\gamma_0^2}
  $$

















- 辐射阻尼常数 $\gamma_0$ ，依赖于辐射振子的固有频率：
  $$
  \gamma_0=\frac{8\pi^2e^2\nu_0^2}{3m_ec^3}=\frac{2}{3}\frac{r_e}{c}(2\pi\nu_0)^2
  $$
  具有圆频率量纲，在可见光区远小于可见光光谱频率

- 谐振子在频率 $|\nu-\nu_0|<\gamma_0$ 范围内的吸收都较明显

- 以波长为标度的辐射阻尼系数：
  $$
  \gamma_0=\left|\frac{\text{d}\lambda}{\text{d}\nu}\right|\Delta\nu=
  $$
  和谱线波长无关——也就是和谱线无关！

- 辐射阻尼常数=吸收系数的半高全宽

  - 由吸收系数公式确定
  - 谱线的这种宽度被称为**自然宽度**，这种致宽称为**自然致宽** (辐射阻尼不可避免)

- 性质：

  - 吸收系数相对谱线中心对称，中心数值最大，两侧迅速减小——洛伦兹轮廓

- 振子强度和跃迁概率系数的关系：

  把积分上下限扩展到无穷：

  与原子的线吸收系数积分公式进行比较，得到



### 辐射阻尼的量子理论

吸收线：低能级的原子在入射光波的作用下跃迁到高能级

- 激发态的原子既能**自发向下跃迁**，也能**受迫向上、向下跃迁**，不可能永远处于同一能级，$\Delta t$ 有限
- 由不确定性关系：$\Delta E\Delta t\ge\hbar/2$ ，$\Delta E$ 有一定宽度
- 两个能级之间跃迁发生在一个频率范围内，发射线或吸收线有一定的宽度



#### 原子在某一能级上的平均寿命 $\tau=\Delta t$

- $t=0$ 时，单位体积有 个原子处在 能级，**忽略受激跃迁**，则  减小的速度由原子自发地从 $k$ 跃迁至所有可能低能级 $j$ 的概率决定，即：

  $$
  \frac{1}{N_k}\frac{\text{d}N_k}{\text{d}t}=
  $$

- 对时间积分即得：

  $$
  N_k=N_k^0e^{-\gamma_kt}
  $$
















​	$\gamma_k$ 被称为辐射阻尼常数

- 处在能级 $k$ 的平均寿命：
  $$
  \tau_k=\frac{1}{\gamma_k}
  $$

- 如果**考虑所有受激跃迁**
  $$
  \frac{1}{N_k}\frac{\text{d}N_k}{\text{d}t}=-\gamma_k
  $$

  $$
  \gamma_k=\frac{1}{\tau_k}=
  $$

  - 右端第一项：$k$ 向下的自发跃迁

  - 第二项：$k$ 向上的受激跃迁

  - 第三项：$k$ 向下的受激跃迁

- 对于忽略受激跃迁的氢原子，能级越高，对应的 $\gamma_k$ **越小**

  - 对于低激发态，$\gamma_k$ 相当大，能级寿命短，能级相当宽
  - 随着能级号增大，$\gamma_k$ 逐渐减小，寿命越来越长

- 辐射的量子理论给出，当能级寿命有限时，位于能级 $k$ 的原子能量在 $(E,E+\text{d}E)$ 内的概率等于：
  $$
  
  $$
  绝大多数原子的能级都接近能级的平均能量



#### 吸收系数按能级的分布



## 微观多普勒致宽

原子杂乱运动对谱线宽度和吸收系数的影响

- 来源
  - 热运动
  - 湍流，**气体团**的杂乱运动
- 效应
  - 被原子吸收的辐射频率会有不同的多普勒位移
  - 即使每个原子只吸收线心频率的辐射，吸收线也会有一定宽度



### 原子杂乱运动所确定的吸收系数

- 假设没有其他致宽因素，每一个原子只吸收线心频率的辐射

- 取接近观测者速度为正，远离观测者速度为负

- 视向速度为零的原子吸收 $\nu_{jk}$

- 视向速度在 $(\zeta,\zeta+\text{d}\zeta)$ 内的原子所能吸收的频率及其间隔：

- 这种原子的相对数目：
  $$
  a _ { \nu } \text{d} \nu \propto \text{d} n / n
  $$





#### 热运动

- 一般说来，麦克斯韦分布可用：
  $$
  \frac { d n } { n } = \frac { e ^ { - \mu m _ { H } \left( v _ { x } ^ { 2 } + v _ { y } ^ { 2 } + v _ { x } ^ { 2 } \right) / 2 k T } } { \left( 2 \pi k T / \mu m _ { H } \right) ^ { 3 / 2 } } d v _ { x } d v _ { y } d v _ { z }
  $$

- 设 $v_x=\zeta$ 沿视线方向，视向速度在区间内的相对原子数：
  $$
  \frac{\text{d}n}{n}\text{d}\zeta=\frac { 1 } { \sqrt { \pi } } e ^ { - \left( \zeta / \zeta _ { 0 } \right) ^ { 2 } } \frac { d \zeta } { \zeta _ { 0 } }
  $$
  $\zeta_0$ 最概然速度：$\zeta _ { 0 } ^ { 2 } = 2 k T / \mu m _ { H }$



#### 湍动

- 考虑微湍动——湍动元的尺度小于光子平均自由程（光薄）
- 假设完全杂乱，则湍动也服从麦克斯韦分布
- 大量微湍动存在，原子同时参与两种杂乱运动：$\zeta=v_x+\zeta_t$ ——分布为两个高斯函数的乘积 
- 如果湍动不服从高斯分布，则分布为两个分布函数的卷积



## 宏观多普勒致宽

### 宏观湍动

- 湍动元的尺度比光子自由程大(光学厚)的湍动
  - 光学独立，各湍动元彼此无关
  - 不同的湍动视向速度形成独立的谱线吸收
  - 总谱线轮廓是每个轮廓的**加权求和**
  - 求和权重是每个轮廓对应湍动元的**视面积**与恒星**总面积**之比
  - 通常还要考虑**临边昏暗**的影响
- 处理方法
  - 不把它和分子热运动进行卷积
  - 得到对湍动元的辐射转移的局部解之后，再考虑总效果——类似于自转致宽
- 特性
  - 不影响谱线的**等值宽度**（总吸收体保持不变，不增加总吸收），只是线心深度减小，谱线变宽

### 恒星自转

- 假定半径为 $R$ 的恒星以角速度 $\Omega$ 作刚体自转，取恒星中心为坐标原点，$z$ 轴指向观测者，自转轴在 $y-z$ 平面内，自转轴和 $z$ 轴夹角为 $i$ 

- 恒星表面任一点 $(x,y,z)$ 的视向速度
  $$
  v_z=\vec{e}_z\cdot(\vec\Omega\times \vec R)=\vec\Omega\cdot(\vec R\times \vec e_z)=-x\Omega\sin{i}\equiv-\frac{x}{R}v_{{eq}}x\sin i
  $$

- 对应的多普勒位移（取恒星半径为单位长度）
  $$
  \Delta \lambda = - \frac { \lambda } { c } v _ { z } = \frac { \lambda } { c } v _ { e q } x \sin i
  $$

- 设 $\lambda_0'$ 是恒星视面 $(x,y)$ 发出的某条谱线的线心波长，$\beta$ 是该点法线与视线夹角，在波长为 $\lambda$ 处沿视线的辐射强度和连续谱的辐射强度分别为 $I_\beta(\lambda-\lambda_0')$ 和 $I_\beta^0(\lambda)$ 

- 谱线深度
  $$
  R _ { \lambda } = 1 - r _ { \lambda } = \frac { \iint \left[ I _ { \beta } ^ { 0 } ( \lambda ) - I _ { \beta } \left( \lambda - \lambda _ { 0 }' \right) \right] \text{d} x \text{d} y } { \iint I _ { \beta } ^ { 0 } ( \lambda ) \text{d} x \text{d} y } = \frac { \iint R _ { \beta } \left( \lambda - \lambda _ { 0 }' \right) I _ { \beta } ^ { 0 } ( \lambda ) \text{d} x \text{d} y } { \iint  { I _ { \beta } ^ { 0 } } ( \lambda ) \text{d} x \text{d} y }
  $$

- 假定 $R_\beta(\lambda-\lambda_0')$ 与 $\beta$ 无关并考虑临边昏暗，得到
  $$
  R _ { \lambda } =  \frac { \iint R\left( \lambda - \lambda _ { 0 }' \right) I _ { \beta } ^ { 0 } ( \lambda ) \phi(\lambda,\beta)\text{d} x \text{d} y } { \iint  { I _ { \beta } ^ { 0 } } ( \lambda )\phi(\lambda,\beta) \text{d} x \text{d} y }
  $$

- 代入 $\Delta \lambda$ 的表达式，得到
  $$
  R _ { \lambda } =  \frac { \iint R\left[ \lambda - \lambda _ { 0 }(1+x\sin iv_{eq}/c) \right] I _ { \beta } ^ { 0 } ( \lambda ) \phi(\lambda,\beta)\text{d} x \text{d} y } { \iint  { I _ { \beta } ^ { 0 } } ( \lambda )\phi(\lambda,\beta) \text{d} x \text{d} y }
  $$






## 阻尼效应和微观多普勒效应的联合作用

- 在恒星大气里,阻尼效应和原子的杂乱热运动总是同时存在

- 考虑视向速度在 $(\zeta,\zeta+\text{d}\zeta)$ 内的原子

- **阻尼效应**导致它们不再吸收线心频率的辐射，而是按照洛伦兹轮廓
  $$
  a _ { v } = \frac { e ^ { 2 } } { m _ { e } c } \delta _ { j k } \cdot \frac { f _ { i k } } { \left( \nu - \nu _ { j k } \right) ^ { 2 } + \delta _ { j k } ^ { 2 } }
  $$
  吸收（阻尼效应的量子理论给出 $\delta _ { j k } = \left( \gamma _ { j } + \gamma _ { k } + \gamma _ { c } \right) / 4 \pi$ 是上下能级阻尼常数和碰撞阻尼常数之和）

- **微观多普勒效应**导致线心频率不再是 $\nu_{jk}$ ，而是 $\nu_{jk}+\frac{\zeta}{c}\nu_{jk}$ ，吸收系数修正为
  $$
  a _ { v } = \frac { e ^ { 2 } } { m _ { e } c } \delta _ { j k } \cdot \frac { f _ { i k } } { \left( \nu - \nu _ { j k }-\Delta\nu \right) ^ { 2 } + \delta _ { j k } ^ { 2 } }
  $$

- 其他速度的原子也可以在频率为 $\nu$ 处产生吸收，总的吸收系数为
  $$
  a_\nu=\int _ { - \infty } ^ { + \infty } \frac { e ^ { 2 } } { m _ { e } c } \delta _ { j k } \cdot \frac { f _ { j k } } { \left( \nu - \nu _ { j k } - \Delta \nu \right) ^ { 2 } + \delta _ { j k } ^ { 2 } } \cdot \frac { 1 } { \sqrt { \pi } } e ^ { - \left( \Delta\nu / \Delta \nu _ { D } \right) ^ { 2 } } \frac { \text{d} ( \Delta \nu ) } { \Delta \nu _ { D } }
  $$
  记 $ { y } = \Delta { \nu } / \Delta \nu_ { { D } } , \quad { P } = \left( { v } -  { v } _ { { ik } } \right) / \Delta  { v } _ {  { D } } , \quad  { a } = \delta _ {  { ik } } / \Delta{ v } _ {  { D } }$

  回忆只由多普勒效应确定的吸收系数 
  $$
  a _ { \nu} = \frac { \sqrt { \pi } \mathrm { e } ^ { 2 } } { m _ { \mathrm { e } } c } \frac { f _ { j k } } { \Delta \nu_ { D } } e ^ { - \left[ \left( \nu- \nu _ { j k } \right) / \Delta \nu _ { D } \right] ^ { 2 } } = a _ { \nu _ { 0 } } e ^ { - \left[ \left( \nu - \nu _ { j k } \right) / \Delta \nu _ { D } \right] ^ { 2 } }
  $$
  沿用 $a_{\nu0}$ 定义，则
  $$
  \frac { a _ { \nu } } { a _ {\nu _ { 0 } } } = \frac { a } { \pi } \int _ { - \infty } ^ { + \infty } \frac { e ^ { - y ^ { 2 } } } { ( P - y ) ^ { 2 } + a ^ { 2 } } \text{d} y \equiv H ( a , P )
  $$

- 积分称为 Voigt 函数，只能数值计算，对于 $a\ll1$ 也可以展开成 $a$ 的幂级数计算

- 恒星大气中，多普勒宽度通常远大于阻尼常数， $a=\delta _ {  { ik } } / \Delta{ v } _ {  { D } }\ll1$ 

- 此时谱线中心部分仅由多普勒效应 $P$ 决定

- 离线心较远处吸收系数仅由辐射阻尼效应决定

- 过渡部分必须用联合公式计算——相当小，实际上可分成两部分分别计算，除非 $a$ 很大



## 压力效应的碰撞阻尼理论



- 压力效应：通过粒子之间相互作用导致的谱线致宽，与气体的压力有密切关系
- 碰撞阻尼理论（碰撞相移理论）——碰撞对辐射**结果**的影响
  - 辐射原子(振子;或吸收原子)经常遭受到周围质点的撞击，每次碰撞使振子振动辐射光波发生中断一个短暂时间,或者相位产生变化,结果由振子发出的光波被打成一段、一段彼此独立无关的“波段”，这种波在傅里叶分析后的能谱(强度)上,是一条有一定宽度的光谱线
- 统计致宽理论——碰撞对辐射**过程**的影响
  - 辐射原子(或吸收原子)在周围质点的作用下,能级发生了变化，分裂的能级导致分裂的谱线，不同谱线的重叠导致谱线具有一定宽度



### 碰撞阻尼理论

碰撞对辐射**结果**的影响

- 两次碰撞之间，忽略辐射阻尼，振子按正常频率振动，因而按正常频率辐射

- 于是振子只在时间间隔 $T$ 内有辐射：
  $$
  \epsilon(t)=Ae^{i\omega_0 t}\\
  \epsilon(0)=0
  $$

- 傅里叶变换：
  $$
  \epsilon(t)=\frac{1}{2\pi}\int_{-\infty}^{\infty}E(\omega)e^{i\omega t}\text{d}\omega
  $$
  $E(\omega)$ 为波在 $\omega$ 上的振幅，也即时间长度为 $T$ 的波段产生的辐射强度分布
  $$
  E(\omega)=A\int_{-T/2}^{T/2} e^{i(\omega_0-\omega)t}\text{d} t=A\cdot\frac{\sin\left(\frac{\omega_0-\omega}{2}T\right)}{\left(\frac{\omega_0-\omega}{2}\right)}
  $$

- 辐射强度与振幅平方成正比
  $$
  P(\omega)\propto\left[\frac{\sin\left(\frac{\omega_0-\omega}{2}T\right)}{\left(\frac{\omega_0-\omega}{2}\right)}\right]^2
  $$

- 每次碰撞的时间间隔不同，服从一定的分布，碰撞时间间隔 $\text{d}T$ 内的粒子数满足：
  $$
  \text{d} N=N\text{d}T
  $$
  得到指数分布：
  $$
  N=N_0e^{-T/\tau_c}
  $$

- 不同时间间隔段的波段产生的辐射强度 $I_\nu$ 为该指数分布下辐射强度的期望

- 碰撞阻尼理论确定的吸收系数与 $I_\nu$ 成正比，并利用吸收系数积分公式确定比例系数，最终得到
  $$
  a _ { \nu } = \frac { e ^ { 2 } } { m _ { c } c } \frac { \gamma _ { c } } { 4 \pi } \frac { f } { \left( \nu _ { 0 } - \nu \right) ^ { 2 } + \left( \gamma _ { c } / 4 \pi \right) ^ { 2 } }
  $$
  与辐射阻尼确定的吸收系数在形式上完全一样，只是阻尼常数不同，为碰撞平均时间间隔倒数的两倍
  $$
  \gamma_c=\frac{2}{\tau_c}=2N\overline v\sigma
  $$

- 从而两者的物理意义也一样，都是吸收系数的半高全宽

- 碰撞阻尼引起的加宽将随扰动粒子的密度（压力）增大而增大



### 碰撞阻尼常数的确定

- 扰动粒子经过辐射振子**附近**，与辐射振子**相互作用**而使辐射振子振动频率改变——固有频率获得增量 $\eta$ ，简称**相移**

- $\eta\ge\eta_0$ 时，振子振动的顺序性被打断或者破坏，碰撞前后的辐射彼此无关——碰撞即为这样的相互作用

- $t$ 时刻辐射振子与扰动粒子之间的距离为
  $$
  r=\sqrt{\rho^2+\overline v^2(t-t_0)^2}
  $$
  $\rho$ 为瞄准距离，$\overline v$ 为平均相对速度，$t_0$ 为两者最近的时刻

- 扰动粒子经过辐射粒子**附近**时，辐射振子频率改变（相当于作功）与距离的关系可以一般性地近似表示为
  $$
  \Delta\nu=\frac{C_n}{r_n},\quad\Delta\omega=2\pi\Delta\nu
  $$
  $n$ 是一个正整数，取决于振子-粒子相互作用的形式

- 总相移
  $$
  \begin{align*}
  \eta ( \rho )& =  \int _ { - \infty } ^ { + \infty } \frac { 2 \pi C _ { n } } { \left[ \rho ^ { 2 } + \overline { v } ^ { 2 } \left( t - t _ { 0 } \right) ^ { 2 } \right] ^ { n / 2 } } \text{d} \left( t - t _ { 0 } \right)\\
  &= \int _ { - \frac{\pi}{2} } ^ { \frac{\pi}{2}} \frac { 2 \pi C _ { n } } { \overline v\rho^{n-1}\sec^{n-2} \theta} \text{d}\theta\\
  &=\frac { 2 \pi C _ { n } } { \overline { v } \rho ^ { n - 1 } } \alpha _ { n }
  \end{align*}\\
  \text{where }\alpha_n=\frac{\sqrt{\pi}\Gamma\left(\frac{n}{2}\right)}{\Gamma\left(\frac{n-1}{2}\right)}
  $$

- 临界相移对应的瞄准距
  $$
  \rho _ { 0 } = \left( \frac { 2 \pi C _ { n } } { \overline { v } \eta _ { 0 } } \alpha _ { n } \right) ^ { 1 / ( n - 1 ) }
  $$
  即推出碰撞截面
  $$
  \sigma_0=\pi\rho_0^2
  $$
  碰撞阻尼常数
  $$
  \gamma_c=2N\overline v\sigma=2 \pi N \overline { v } \left( \frac { 2 \pi C _ { n } \alpha _ { n } } { \overline { v } \eta _ { 0 } } \right) ^ { 2 / ( n - 1 ) }
  $$

- 如果考虑碰撞前后波的相关性，吸收系数的对称频率（极大值）不再是谱线线心频率处，而要加上修正 $\beta$ ——碰撞相移理论

- 只有当碰撞阻尼常数 $\gamma_c$ 已知或碰撞截面 $\sigma$ 已知时，由碰撞阻尼确定的吸收系数才是完全确定的

- 计算 $\sigma$

  - $C_n$ 是与 $n$ 有关的由相互作用方式决定的常数

  - $N$ 是单位体积内的扰动粒子数

  - $\overline v$ 是吸收(或辐射)原子和扰动粒子间的平均相对速度，$\mu_1,\mu_2$ 分别是吸收和辐射原子的分子量
    $$
    \overline {  { v } } = \sqrt { \frac { 8 } { \pi } R T \left( \frac { 1 } { \mu _ { 1 } } + \frac { 1 } { \mu _ { 2 } } \right) }
    $$

  - 可据此计算 $\sigma$ 

  - $\gamma_c\propto\overline v^{(1-\frac{2}{n-1})}$ ，常见相互作用 $n=3,4,6$ ，$n=3$ 时与平均相对速度无关，$n$ 越大，平均相对速度的影响越大 



### 碰撞阻尼和辐射阻尼的联合作用

- 只有辐射阻尼：辐射电磁波的振幅不断衰减，谱线内辐射强度按频率的分布为：
  $$
  I(\omega')\text{d}\omega'=C\cdot\frac{\text{d}\omega'}{(\omega'-\omega_0)^2+(\gamma_0/2)^2}
  $$
  自发发射的光波由上式确定的单色等幅波叠加而成

- 考虑碰撞效应：单色波被碰撞效应展宽
  $$
  I(\omega')\text{d}\omega'=C'\cdot\frac{1}{(\omega-\omega')^2+(\gamma_c/2)^2}\cdot\frac{\text{d}\omega'}{(\omega'-\omega_0)^2+(\gamma_0/2)^2}
  $$
  总强度：
  $$
  \begin{align*}
  I(\omega)&=C'\int_{-\infty}^\infty\frac{1}{(\omega-\omega')^2+(\gamma_c/2)^2}\cdot\frac{\text{d}\omega'}{(\omega'-\omega_0)^2+(\gamma_0/2)^2}\\
  &=const\cdot\frac{(\gamma_c+\gamma_0)/2}{(\omega-\omega_0)^2+[(\gamma_c+\gamma_0)/2]^2}
  \end{align*}
  $$
  得到联合作用下的辐射吸收系数
  $$
  a_\nu=\frac{e^2}{mc}\cdot\frac{\gamma_0+\gamma_c}{4\pi}\cdot\frac{f}{(\nu-\nu_0)^2+[(\gamma_c+\gamma_0)/4\pi]^2}
  $$

- 把经典的辐射阻尼常数 $\gamma_0$ 换成量子理论得到的辐射阻尼常数 $\gamma_j+\gamma_k$
  $$
  \begin{align*}
  a_\nu&=\frac{e^2}{mc}\cdot\frac{\gamma_j+\gamma_k+\gamma_c}{4\pi}\cdot\frac{f}{(\nu-\nu_0)^2+[(\gamma_j+\gamma_k+\gamma_c)/4\pi]^2}\\
  &\equiv\frac{e^2}{mc}\cdot\delta_{jk}\cdot\frac{f}{(\nu-\nu_0)^2+\delta_{jk}^2}
  \end{align*}
  $$








## 压力效应的统计理论

碰撞对辐射**物理过程**的影响——只研究斯塔克效应



### 斯塔克效应

- 辐射原子处于电场中，谱线分裂成若干条子线（原有对称性被电场打破，能量的简并被打破），各条子线和原来线心频率 $\nu_0$ 之间的差别（裂距），与电场强度大小有关

- 对于氢原子，当场强不太大（ $<10^5\text{ V/m}$ ，此时场强远小于氢原子内质子和电子的库仑场 $\sim10^6\text{ V/m}$ ）时，各条子线的裂距和场强一次方成正比——线性斯塔克效应（高斯单位制）：
  $$
  \Delta E=\frac{3}{8\pi^2}\frac{h^2}{em_e}nn_FF
  $$
  $n_F$ 为所谓电量子数，取 $0,\pm1,\cdots,\pm n$

  - 分裂后的能级对于原能级对称，裂距和数目都随主量子数增加而增加

  - 原来的子线：$E_{n}-E_{n'}=h\nu$ ，现在的子线：$E_{n_F}-E_{n_F'}=h\nu_F$ ，有一个 $\Delta\nu$ ，$n,n'$ 分别是上下能级主量子数

  - 分裂子线到正常线心的距离
    $$
    \begin{align*}
    \Delta \lambda (\text{cm})&= \frac { \lambda ^ { 2 } } { c } \Delta \nu \\
    &= \frac { \lambda ^ { 2 } } { c } \frac { \left( E _ { n _ { F } } - E _ { n _ { F }' } \right) - \left( E _ { n } - E _ { n' } \right) } { h } \\
    &= \frac { \lambda ^ { 2 } } { c } \frac { \left( E _ { n _ { F } } - E _ { n } \right) - \left( E _ { n _ { F }' } - E _ { n' } \right) } { h }\\
    &= \frac { \lambda ^ { 2 } } { c } \frac { \Delta E _ { n_F } - \Delta E _ { n _ { F } '} } { h }\\
    & = \frac { \lambda ^ { 2 } } { ch }\frac { 3 } { 8 \pi ^ { 2 } } \frac { h ^ { 2 } } {  e m _ { e } }  \left( n n _ { F } - n' n _ { F }'\right) F \\&= 0.0192 \lambda ^ { 2 } \left( n n _ { F } - n' n _ { F }' \right) F
    \end{align*}
    $$

- 当场强很大，各子线的裂距变为与场强平方成正比——二次斯塔克效应

- 对于其他原子谱线（除了某些氦线），通常只有二次斯塔克效应，无线性斯塔克效应——价层电子离原子核较远，库仑场小

在恒星大气中，一般没有很强的宏观电场，但大量离子和自由电子在运动到辐射原子附近时会产生一个很强的微观电场

- 微观电场随时间变化
- 含时的薛定谔方程——非常困难



### 压力的统计理论

- 假设

  - 辐射原子和扰动原子没有相对运动——均匀、静止场近似

    - 对于离子,由于它的热运动速度很小(因为质量大)，这个假设近似成立
    - 但对于自由电子,由于热运动速度很大(因为质量小)，通常假设不成立

    由于微观场的电场强度由辐射原子和其周围带电粒子的**相对位置**确定，而这种相互位置对于不同的辐射原子一般互不相同，因而场强值应该**服从一定的概率分布** $\Phi(F)$

  - 在电场作用下,所讨论的谱线分裂为 $n$ 条极窄的子线

    - 若第 $k$ 条子线的相对强度为 $I_k$ ，则其贡献为 $I_k\Phi(F_k)\text{d}F$

    - 对所有子线求和，就得到辐射的相对强度在谱线内按波长分布的表达式
      $$
      I ( \Delta \lambda ) \text{d} ( \Delta \lambda ) = \sum _ { k } I _ { k } \Phi \left( F _ { k } \right) \text{d}F _ { k }
      $$

  - 最后利用 $a(\Delta\lambda)\propto I(\Delta\lambda)$ 得出 $a(\Delta\lambda)$




  #### 微观场强分布函数

考虑辐射原子周围，**最靠近**的扰动粒子形成的微观场强分布，这在场强较大时是很好的近似

对于球壳 $( r , r + \text{d}r )$ 

  - 最靠近的扰动粒子在球壳中的概率为 $P(r)\text{d}r$

  - $W^*(r)$ 表示半径为 $r$ 的球内没有扰动粒子的概率，球壳内有一个扰动粒子的概率为 $W(r+\text{d}r)$ ，则有
    $$
    P ( r ) \text{d} r = W ^ { * } ( r ) W ( r , r + \text{d} r )
    $$

  - 单位体积内的扰动粒子数 $N$ 满足
    $$
    W(r+\text{d}r)=N\cdot4\pi r^2\text{d}r
    $$
    再考虑没有扰动粒子的概率
    $$
    \begin{align*}
    &W^* ( r + \text{d} r )= W ^ { * } ( r ) (1-W ( r , r + \text{d} r ))\\
    \Rightarrow &\frac { \text{d} W ^ { * } ( r ) } { W ^ { * } ( r ) } = - W ( r , r + \text{d} r ) = - 4 \pi N r ^ { 2 } d r\\
    \Rightarrow&W ^ { * } ( r ) =  e ^ { - \frac { 4 \pi } { 3 } N r ^ { 3 } },\text{where }W^*(0)=1 
    \end{align*}
    $$

  - 代入 $P ( r ) \text{d} r $ 表达式得到
    $$
    P ( r ) \text{d} r = e ^ { - \frac { 4 \pi } { 3 } N r ^ { 3 } } N\cdot4\pi r^2\text{d}r
    $$

  - 考虑一个粒子所占体积 $1/N=4\pi r_0^3/3$ ，有
    $$
    P ( r ) \text{d} r = e ^ { - \left(\frac { r } { r_0 }\right)^3}\text{d}\left(\frac { r } { r_0 }\right)^3
    $$

  - 在恒星大气中通常最丰富的氢只能电离一次,而恒星大气温度不够高,因此氦的二次电离数量较少;在晚型星大气中温度太低,氢和氦基本上都是中性的,只有金属能够电离提供电子,但因为温度低因而只能电离一次

    ——假设扰动粒子带电 $e$ ，在辐射原子处产生场强 $F=e/r^2$

  - 引入常数
    $$
    F _ { 0 } \equiv \frac { e } { r _ { 0 } ^ { 2 } } = e \left( \frac { 4 \pi N } { 3 } \right) ^ { 2 / 3 } = 2.60 e N ^ { 2 / 3 } , \quad \beta \equiv \frac { F } { F _ { 0 } } = \left( \frac { r _ { 0 } } { r } \right) ^ { 2 } \Rightarrow \frac { r } { r _ { 0 } } = \beta ^ { - 1 / 2 }
    $$
    代入概率表达式，得到所要求的、由最近邻扰动粒子所确定的微观场强的分布函数
    $$
    W(\beta)\text{d}\beta\equiv P ( r ) \text{d} r =\frac { 3 } { 2 } \beta ^ { - 5/2 } e ^ { - \beta ^ {- 3/2 } } \text{d} \beta
    $$

  - 更复杂的计算可以得出全体扰动粒子形成的归一化微观场强分布函数
    $$
    W ( \beta ) = \frac { 2 } { \pi \beta } \int _ { 0 } ^ { \infty }{ v } \sin  { v } e ^ { - ({ v } / \beta ) ^ { 3 / 2 } }  \mathrm { d }v\\
    \text{where }\beta=\frac{F}{F_0},\quad F_0=2.61eN^{2/3}
    $$
    $\beta$ 很小时可将 $\sin v$ 展开，写成 $\Gamma$ 函数的无穷级数；$\beta$ 很大时可以将指数项展开成 $\beta^{-3/2}$ 的幂级数并积分



#### 吸收系数表达式

- 线性斯塔克效应：$\Delta \lambda_k = 0.0192 \lambda ^ { 2 } \left( n n _ { F } - n ' n' _ { F } \right) F\equiv C_kF$ 

  - 已经有 $I ( \Delta \lambda ) \text{d} ( \Delta \lambda ) = \sum _ { k } I _ { k } \Phi \left( F _ { k } \right) \text{d}F _ { k }$ ，进一步利用上一节的结果，同时 $\beta=F/F_0$
    $$
    I( \Delta \lambda ) \text{d} ( \Delta \lambda ) =\sum _ { k } I _ { k } W \left( \beta_k\right) \text{d}\beta_k=\sum _ { k } I _ { k } W\left( \frac { \Delta \lambda } { C _ { k } F _ { 0 } } \right) \frac { \text{d} ( \Delta \lambda ) } { C _ { k } F _ { 0 } }\equiv S ( \alpha ) d \alpha\\
    \text{where }\alpha\equiv\frac{\Delta\lambda}{F_0}
    $$

  - 我们知道吸收系数按波长分布和辐射强度相对分布有相同形式，则
    $$
    a ( \Delta \lambda ) \text{d} ( \Delta \lambda ) = A S ( \alpha ) \text{d} \alpha
    $$
    根据吸收系数定义
    $$
    \text{d} I _ { \nu } \text{d} v = - I _ { \nu } a _ { \nu } N _j \text{d} h \text{d} \nu = \text{d} I _ { \lambda } \text{d} \lambda = - I _ { \lambda } a _ { \lambda } N _ { j } \text{d} h \text{d} \lambda\\
    \Rightarrow a(\Delta\lambda)=a(\Delta\nu)
    $$

    将吸收系数与 $S(\alpha) $ 关系对整条谱线积分
    $$
        \int A S ( \alpha )\text{d} \alpha = A = \int a _ { \lambda } \text{d}  \lambda = \int a _ { \nu } \frac { \lambda ^ { 2 } } { c } \text{d}  \nu= \frac { \pi e ^ { 2 } } { m _ { e } c ^ { 2 } } \lambda ^ { 2 } f
    $$

  - 吸收公式
    $$
    \begin{align*}
    a ( \Delta \lambda )\text {d}( \Delta \lambda )& = \frac { \pi e ^ { 2 } } { m _ { e } c ^ { 2 } } \lambda ^ { 2 } f \sum _ { k } I _ { k } W \left( \frac { \alpha } { C _ { k } } \right) \frac { \text{d} \alpha } { C _ { k } } \\&= \frac { \pi e ^ { 2 } } { m _ { e } c ^ { 2 } } \lambda ^ { 2 } f \sum _ { k } I _ { k } W \left( \frac { \Delta \lambda } { C _ { k } F _ { 0 } } \right) \frac { \text{d}  ( \Delta \lambda ) } { C _ { k } F _ { 0 } }
    \end{align*}
    $$

  - 对于线翼，$\Delta\lambda$ 很大，对应的电场大，$\beta$ 很大，此时有
    $$
    W ( \beta ) = 1.496 \beta ^ { - 5 / 2 } \left( 1 + 5.107 \beta ^ { - 3 / 2 } + 14.43 \beta ^ { - 3 } + \cdots \right) \approx 1.496 \beta ^ { - 5 / 2 }
    $$

  - 代入得到线翼中的吸收系数公式
    $$
    \begin{align*}
    a ( \Delta \lambda ) d ( \Delta \lambda )&= \frac { \pi e ^ { 2 } } { m _ { e } c ^ { 2 } } \lambda ^ { 2 } f \sum _ { k }\frac {  I _ { k }  } { C _ { k } F _ { 0 } }\left[1.496 \left( \frac { \Delta \lambda } { C _ { k } F _ { 0 } } \right)^{-5/2} \right]\\
    &=1.496 \frac { \pi e ^ { 2 } } { m _ { e } c ^ { 2 } } \lambda ^ { 2 } f \frac { F _ { 0 } ^ { 3 / 2 } } { ( \Delta \lambda ) ^ { 5 / 2 } } \sum _ { k } I _ { k } C _ { k } ^ { 3 / 2 } \\&\equiv C \frac { F _ { 0 } ^ { 3 / 2 } } { ( \Delta \lambda ) ^ { 5 / 2 } }
    \end{align*}
    $$

  - $C_k=0.0192 \lambda ^ { 2 } \left( n n _ { F } - n ' n' _ { F } \right) $ ，对于巴耳末系的高号码谱线，吸收系数公式可近似为
    $$
    a ( \Delta \lambda ) = 0.299 \frac { \pi e ^ { 2 } } { m _ { e } c ^ { 2 } } \lambda ^ { 2 } f \frac { \left( S _ { n } F _ { 0 } \right) ^ { 3 / 2 } } { ( \Delta \lambda ) ^ { 5 / 2 } }\\
    \text{where }S _ { n } = 0.0192 \lambda ^ { 2 } [ n ( n - 1 ) + 2 ]
    $$



- 二次斯塔克效应


  - $\Delta \lambda _ { k } = C _ { k } ^ { \prime } F ^ { 2 } = C _ { k } ^ { \prime } F _ { 0 } ^ { 2 } \beta ^ { 2 }$ 

  - $\beta _ { k } = \sqrt { \Delta \lambda / \left( C _ { k } ^ { \prime } F _ { 0 } ^ { 2 } \right) }$ 

  - $S ( \Delta \lambda ) \text{d} ( \Delta \lambda )= \sum _ { k } I _ { k } W \left( \beta _ { k } \right) \text{d} \beta _ { k }$

  - 代入得到
    $$
    S ( \Delta \lambda ) \text{d} ( \Delta \lambda )=\sum _ { k } I _ { k } \frac { W \left( \sqrt { \Delta \lambda / \left( C _ { k } F _ { 0 } ^ { 2 } \right) } \right) } { \sqrt { \Delta \lambda / \left( C _ { k } F _ { 0 } ^ { 2 } \right) } } \frac { \text{d} ( \Delta \lambda ) } { 2 C _ { k } F _ { 0 } ^ { 2 } }
    $$
    



## 碰撞理论和统计理论的应用范围



### 按谱线轮廓——线心和线翼分别讨论

- 线心部分
  - 碰撞理论隐含假设：
    - 不碰撞时，按 $\nu_0$ 辐射
    - 忽略碰撞时的辐射——瞬间完成碰撞
  - 假设适用于谱线改变较小部分，即线心部分
- 线翼部分
  - 统计理论讨论的是碰撞进行时的辐射，碰撞过程中辐射频率改变大，在线翼里给出辐射
- 临界频率 $\Delta\omega_c= \overline { { v } } ^ { n/ ( n - 1 ) } / \left( 2 \pi C _ { n } \alpha _ { n } ^ { n } \right) ^ { 1 / ( n - 1 ) }$ 在吸收系数相等时给出
- 压力效应致宽的谱线，线心用碰撞理论，线翼用统计理论
- 对于过渡区 $\Delta\omega$ 附近，用一般性理论
-  $\Delta\omega$ 很大，几乎整条谱线都可以用碰撞理论； $\Delta\omega$ 很小，几乎整条谱线都可以用统计理论



### 按相互作用的类型讨论

$\Delta\nu=C_n/r^n$ 

- $n=2$ ，一次电离原子、自由电子产生的库仑场——线性斯塔克效应——氢的谱线、氦的某些谱线

  - $\Delta\omega_c= \overline { { v } } ^ {2} / \left( 2 \pi C _ {2 } \alpha _ { 2 } ^ { 2 } \right) $ ，相对速度越大，临界频率越大
  - 例：巴尔末系前四条谱线，因离子（质子）的致宽需要用统计理论，因自由电子的致宽需要用碰撞理论——自由电子热运动速度比离子大得多，$\Delta \omega_c$ 也就大得多

- $n=4$ ，二次斯塔克效应

  - $\Delta\omega_c= \overline { { v } } ^ { 4/3} / \left( 2 \pi C _ { 4 } \alpha _ { 4 } ^ { 4 } \right) ^ { 1 / 3 }$，相对速度越大，临界频率越大，但速度的影响不如线性斯塔克效应大
  - 自由电子的致宽需要用碰撞理论
  - 对于离子，当 $C_4$ 较小时，也需要用碰撞理论；当 $C_4$ 较大时，线心碰撞理论，线翼统计理论
  - 但此时统计效应比碰撞作用小得多，这是因为
    - 频率改变随距离变化剧烈，作用过程**中**效应明显的时间短暂，效应小
    - 离子对谱线的碰撞展宽比电子作用小得多
  - 通常忽略离子效应，只考虑自由电子碰撞致宽

- $n=3$ ，原子和中性扰动原子（极化场）相互作用，扰动粒子和吸收原子是**同一种**，自己压力致宽（电子屏蔽、原子极化等效应）

  - 自我压力致宽依赖于本身数密度平方，碰撞阻尼系数正比于密度，因而这种效应对金属不重要（不够多）
    $$
    \gamma_c=2 \pi N \overline v \left( \frac { 2 \pi C _ { 3 } \alpha _ { 3 } } { \overline { v } \eta _ { 0 } } \right)=4 \pi ^ { 3 } C _ { 3 } N=\frac {\pi  e ^ { 2 }f _ { j k } } { 2 m _ { e } v _ { 0 } }N 
    $$

  - 出现在较冷恒星巴尔末系的前几条谱线里，因为中性氢很丰富

  - 例：太阳光谱中 $\ce{H}\alpha$ 线（ $\ce{H}\beta$ 开始致宽机制主要是线性斯塔克效应） 

- $n=6$ ，原子和中性扰动原子（极化场）相互作用，吸收原子和**其他**中性原子或者分子的碰撞——范德瓦尔斯力

  > 范德瓦尔斯力：电中性分子之间的电磁引力
  >
  > - 极性分子永久偶极矩之间的相互作用
  > - 极性分子诱导非极性分子极化，产生诱导偶极矩并相互作用
  > - 非极性分子瞬时偶极矩之间的作用（色散力）

  - 用碰撞理论处理

  - $$
    \gamma _ { c } = \gamma _ { 6 } = 2 \pi N \overline {  { v } } \left( \frac { 2 \pi C _ { 6 } \alpha _ { 6 } } { \overline { { v } } \eta _ { 0 } } \right) ^ { 2 / 5 } = ( 2 \pi ) ^ { 7 / 5 } \left( \frac { \alpha _ { 6 } } { \eta _ { 0 } } \right) ^ { 2 / 5 } C _ { 6 } ^ { 2 / 5 } \overline { \mathrm { v } } ^ { 3 / 5 } N=17.0 C _ { 6 } ^ { 2 / 5 } \overline {  { v } } ^ { 3 / 5 } N
    $$

  - $\alpha=6.63\times10^{-25}\text{ cm}^3$ 是中性氢原子的极化率

  - 扰动原子为氢原子时，$C _ { 6 } = \frac { e ^ { 2 } \alpha } { h } \overline { R _ { k } ^ { 2 } }$

  - $\overline { R _ { k } ^ { 2 } }$ 是高能级 $k$ 的轨道的平方平均半径，重要情形：
    - 对于钠的D线，$\overline { R _ { k } ^ { 2 } }=41a_0^2$

    - 对于 $\ce{CaII}$ 的共振线H和K，$\overline { R _ { k } ^ { 2 } }=23a_0^2$ 

    - 对于钙的共振线 $\lambda4227$，$\overline { R _ { k } ^ { 2 } }=69a_0^2$

    - 对于没有详细计算过的情形，特别是许多轻金属的高激发能级，可以近似为
      $$
      \overline { R _ { k } ^ { 2 } } = \frac { n ^ { * 2 } } { 2 ( r + 1 ) ^ { 2 } } \left[ 5 n ^ { * 2 } + 1 - 3 l ( l + 1 ) \right] a _ { 0 } ^ { 2 }
      $$
      $n^*$ 是有效量子数，$l$ 是角量子数，$r$ 是电离级

    - $a_0=0.529\ \overset\circ{\text{A}}$ 是玻尔半径 



### 小结

- 有效温度低于 $6000\text{ K}$ ，氢主要是中性的
  - 大多数谱线的压力致宽是由辐射原子和中性氢的碰撞产生，$n=6$
  - $C_4$ 充分大（如部分铁线、镁线和氦线），自由电子碰撞致宽（二次斯塔克效应）也很重要
- 有效温度高于 $8000\text{ K}$ ，氢基本完全电离
  - $n=6$ ：吸收原子和中性氦的碰撞
  - 原子同电子和离子的碰撞致宽
    - 巴尔末谱线的线翼在大多数情形下由统计理论决定，主要是离子的扰动致宽

    - 对于氢原子，同时致宽；在谱线的远翼部分，电子致宽甚至可能超过离子致宽
      $$
      a ( \Delta \lambda ) = a _ { \mathrm { H } } ( \Delta \lambda ) \left[ 1 + R \left( N _ { e } , T _ { e } \right) \Delta \lambda ^ { 1 / 2 } \right]
      $$

      - 第一项是离子的微观场强分布函数所确定的、对线性斯塔克效应而言的、线翼的吸收系数公式
        $$
        a _ { \mathrm { H } } ( \Delta \lambda ) = C \frac { F _ { \mathrm { o } } ^ { 3 / 2 } } { ( \Delta \lambda ) ^ { 5 / 2 } }
        $$

      - 第二项反映的是电子对谱线致宽的贡献，随 $\Delta\lambda$ 的增大而单调上升——在谱线的远翼部分，电子致宽作用可以达到甚至超过离子作用

      - $R(N_e,T_e)$ 是电子密度和电子温度的函数，对于氢的莱曼和巴耳末系的头十条谱线，可以查表或用近似公式计算
        $$
        R \left( N _ { e } , T _ { e } \right) = \frac { 4.6 Y \left( n _ { u } \right) } { T ^ { 1 / 2 } } \left[ \lg \left( \frac { 4 \times 10 ^ { 6 } T } { n _ { u } ^ { 2 } N _ { e } ^ { 1 / 2 } } \right) - 0.125 \right] \frac { n _ { u } ^ { 5 } + n _ { l } ^ { 5 } } { n _ { u } ^ { 2 } n _ { l } ^ { 2 } \left( n _ { u } ^ { 2 } - n _ { l } ^ { 2 } \right) ^ { 1 / 2 } }
        $$
        $n_u,n_l$ 分别是谱线的高、低能级主量子数；对于巴耳末系头四条谱线，$Y(n)$ 分别为 $1.5, 1.12, 1.06, 0.96$



## 选择散射在选择吸收中的比例

- 求 $1-\epsilon_\nu$ 的近似表达式
- 低能级原子吸收了光子跃迁到高能级后，可能：
  - 通过相反的跃迁返回原能级，每秒钟 $A_{kj}$ 次——散射
  - 通过向下的跃迁跳到其他能级，每秒钟 $\sum A_{ki}$ 次——联锁效应
  - 光致电离，每秒钟 $R_{kf}$ 次——真吸收
  - 碰撞电离，每秒钟 $C_{kf}$ 次——真吸收
  - 第二类碰撞（碰撞退激发），每秒钟 $\sum C_{ki}$ 次——真吸收
  - 忽略受激跃迁和碰撞激发

$$
1-\epsilon_\nu=\frac{A_{kj}}{A_{kj}+\sum A_{ki}+R_{kf}+C_{kf}+\sum C_{ki}}
$$

- 在整条谱线内是一个常数



### 共振线情形

- 通过容许跃迁产生于基态和低激发态之间的谱线
- 从共振线高能级跃迁到基态的概率比跃迁到其他能级的概率高得多（存在禁戒跃迁）——近似计算中，可以认为只有到基态的跃迁
  - 联锁效应一般不重要
  - 高能级是低激发态，离连续态较远，需要的电离能高，碰撞电离和光致电离与上述跃迁相比可以小好几个量级
  - 近似于纯散射，$\epsilon_\nu$ 很小



### 辅线系谱线的情形

- 低能级都是激发态，低能级以下还可能有其他激发态
  - 高能态原子有很大概率跃迁到比谱线低能级更低的基态和激发态上去
  - 高能级是高激发态，离连续态近，碰撞电离和光致电离概率较大
  - $\epsilon_\nu\approx1$



## 单位质量的线吸收系数

- 讨论 $l_\nu$ 和 $a_\nu$ 的关系

- 设谱线低能级为 $(r,j)$ 态，电离级为 $r$ ，能级为 $j$

- 辐射通过 $\text{d} h$ 后，原子产生的辐射强度减弱
  $$
  \text{d}I_\nu=-I_\nu a_\nu N_{r,j}\text{d}h=-I_\nu l_\nu\rho\text{d}h\\
  \Rightarrow l_\nu=a_\nu\frac{ N_{r,j}}{\rho}
  $$

  其中 $\rho = \sum _ { s } N _ { s } m _ { s } = m _ { H} \sum _ { s } N _ { s } \frac { m _ { s } } { m _ { H } } = m _ { H } \sum _ { s } N _ { s } \mu _ { s }$

- 进一步
  $$
  \begin{align*}
  l _ { \nu }& = a _ {\nu } \frac {  N _ { r , j } } { \sum _ { r , j } N _ { r , j } } \cdot \frac { \sum _ { r , j } N _ { r , j } } { N _ { H } } \cdot \frac { N _ { H } } { \rho } \\
  &= a _ { \nu } \frac { N _ { r , j } } { N _ { E } } \cdot \frac { N _ { E } } { N _ { H } } \cdot \frac { N _ { H } } { \rho } \\
  &= a _ { \nu } \frac { N _ { r , j } } { N _ { E } } \cdot \frac { N _ { E } } { N _ { H } } \cdot \frac { 1 } { m _ { H } \mu _ { 0 } }
  \end{align*}
  $$
  $\mu_0$ 为平均分子量，$N_E$ 为该元素的总原子数

- 第一项可拆为

  $$
  \frac { N _ { r , j } } { N _ { E } } =\frac { N _ { r , j } } { N _ { r } } \frac { N _ { r } } { N _ { E } }
  $$
  利用玻尔兹曼公式（对第一项）和萨哈公式（反复运用在第二项上）可以表示成温度 $T$ 和电子压力 $P_e$ 的函数（局部热动平衡假设）

  - 近似解法中可以取温度和电子压力的某一近似值来计算
  - 准确解法中需要考虑二者随温度的分布，分层计算

- 第二项为该元素的相对含量，认为已知
  $$
  \frac { N _ { E } } { N _ { H } }=a_S
  $$

- 考虑 $a_\nu$ ——一般只考虑贡献大的机制

  - 碰撞致宽：${ a _ { v } } = { a _ { v _ { 0 } } } H ( a , P )$ 

    - 需要估计各种机制阻尼常数的大小，只考虑大的

  - 线性斯塔克效应致宽
    $$
    \begin{align*}
    a ( \Delta \lambda )& = C \frac { F _ { 0 } ^ { 3 / 2 } } { ( \Delta \lambda ) ^ { 5 / 2 } } = C \frac { \left( 2.61 e N ^ { 2 / 3 } \right) ^ { 3 / 2 } } { ( \Delta \lambda ) ^ { 5 / 2 } }\\
    & \approx ( 2.61 e ) ^ { 3 / 2 } \frac { P _ { e } } { k T } \frac { C } { ( \Delta \lambda ) ^ { 5 / 2 } } \\
    &= 321 \frac { P _ { e } } { T } \frac { C } { ( \Delta \lambda ) ^ { 5 / 2 } }
    \end{align*}
    $$
    这里用到了 $P=NkT\approx N_ekT$，$C$ 是由谱线特性决定的常数
    $$
    C = 1.496 \frac { \pi e ^ { 2 } } { m _ { e } c ^ { 2 } } \lambda ^ { 2 } f \sum _ { k } I _ { k } C _ { k } ^ { 3 / 2 }
    $$


