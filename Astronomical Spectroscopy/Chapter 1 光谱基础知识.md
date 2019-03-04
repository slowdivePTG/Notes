#Chapter 1 光谱基础知识

> http://kiaa.pku.edu.cn/~jiang/teaching.html#teach=class2



## 热动平衡下的统计函数和统计方程

全同近独立子系 $N,E,V$，能级 $\epsilon_1,\epsilon_2,\epsilon_3,\cdots$，简并度 $g_1,g_2,g_3,\cdots$，粒子数 $n_1,n_2,n_3,\cdots​$
$$
\sum_i n_i=N,\ \sum_in_i\epsilon_i=E
$$

- 玻尔兹曼分布

  粒子可分辨体系最概然分布
  $$
  n_i=g_ie^{-\alpha-\beta\epsilon_i}
  $$

- 玻色分布和费米分布

  Bose分布：粒子不可分辨，每个量子态可容纳的粒子数不受限制
  $$
  n_i=\frac{g_i}{e^{\alpha+\beta\epsilon_i}-1}
  $$
  Fermi分布：粒子不可分辨，每个量子态只能有一个粒子
  $$
  n_i=\frac{g_i}{e^{\alpha+\beta\epsilon_i}+1}
  $$
  在经典极限下，$e^\alpha\gg1​$，三种分布等价

- 玻尔兹曼方程
  $$
  n_i=e^{-\alpha}g_ie^{-\beta\epsilon_i}\Rightarrow N=e^{-\alpha}\sum_i g_ie^{-\beta\epsilon_i}\equiv e^{-\alpha}G
  $$
  $G$ 是配分函数，从而有玻尔兹曼方程
  $$
  \frac{n_i}{N}=\frac{g_i}{G}e^{-\epsilon_i/kT}
  $$

- 麦克斯韦方程

  定义广义坐标 $x,y,z,p_x,p_y,p_z$

  $\mathrm{d}p_x\mathrm{d}p_y\mathrm{d}p_z​$ 内的粒子数
  $$
  f=\frac{V}{h^3}g_ie^{-\alpha-\beta\epsilon_i}\mathrm{d}p_x\mathrm{d}p_y\mathrm{d}p_z
  $$
  利用全空间内积分为 $N$ 得到
  $$
  f=N\left(\frac{1}{2\pi mkT}\right)^{3/2}e^{-(p_x^2+p_y^2+p_z^2)/2mkT}\mathrm{d}p_x\mathrm{d}p_y\mathrm{d}p_z
  $$



## 原子电子的能级、跃迁和电离

> 理论天体物理笔记 Chapter 2
>
> **原子的激发和电离**



## 辐射场的宏观描述和辐射转移

### 辐射场

### 吸收与光学厚度

### 辐射转移方程

### 源函数

> 理论天体物理 Chapter 1
>
> **宏观描写辐射场的几个基本物理量**
>
> **发射系数、消光(吸收)系数和源函数**
>
> **辐射转移方程**



### 亮温度与激发温度

#### 亮温度

[Brightness temperature](https://en.wikipedia.org/wiki/Brightness_temperature)
$$
I_\nu(\tau=0)=B_\nu(T)(1-e^{-\tau_m})\\
I_\nu=B_\nu(1-e^{-\tau})
$$

长波近似下满足瑞利-金斯公式
$$
T_B=\frac{c^2}{2\kappa}\frac{I_\nu(\mathrm{obs})}{\nu^2}
$$
$I_\nu​$ 是观测的辐射强度

#### 激发温度

[Excitation temperature](https://en.wikipedia.org/wiki/Excitation_temperature)
$$
T_{ex}=\frac{c^2}{2\kappa}\frac{S_\nu}{\nu^2}
$$

$S_\nu$ 是源函数



## 光谱简介

### 太阳光谱

- 夫琅和费谱线（太阳光谱中近600条暗线，其他恒星中也有）
- 基尔霍夫解释
  - 热的致密固体、液体和气体产生**连续谱**（恒星内部）
  - 热的稀薄气体产生**发射线**
  - 连续辐射通过冷的、稀薄的气体后产生**吸收线**（恒星大气）
- 星系光谱：所有**发光天体**的光谱叠加



### 类星体光谱

- 从X射线到射电波段的强辐射
- Type I 类星体：紫外和光学
  - 连续谱（幂律谱，$10^6\sim10^{10}M_\odot$）+一系列宽发射线
- 星际介质吸收
  - Ly$\alpha$ 森林
- 自吸收——宽吸收线类星体



### 天体光谱中的信息

- 化学成分：比较观测和实验室中各种元素的谱线

- 温度：如氢巴尔末线系在A型星中最显著（温度过高，氢原子电离；温度过低，没有足够的能量用来跃迁），氦的谱线随温度降低减弱

- 磁场：Zeeman效应：磁场导致谱线分裂，由谱线分裂程度推断磁场强度

- 压力（速度）：谱线的压力致宽

- 距离（星际介质吸收）：研究类星体的吸收线——宇宙学

- BPT diagram：[The BPT diagrams (named after "Baldwin, Phillips & Telervich") are a set of nebular emission line diagrams used to distinguish the ionization mechanism of nebular gas.](https://sites.google.com/site/agndiagnostics/home/bpt)

   

### 光谱观测

#### 天体光谱分析

- 什么原子（分子、离子）发出的——物质组成（定性）

- 什么跃迁，基态、激发态——物理条件（温度、密度）、激发源性质（光度、温度、谱型）

- 跃迁有多强——气体质量、元素丰度（定量）

  这里需要考虑是否光厚，对一些禁线、超精细结构谱线，全空间几乎光薄，强度即可以对应丰度

- 谱线轮廓——压强（碰撞展宽）、气体（宏观）运动（多普勒展宽）

- 谱线的分裂——磁场强度

#### 天体观测的基本类型

- 单天体、多天体（一次观测一片天区）、巡天
- 测光观测
  - 单历元
    - 天体的探测和发现；在天球上的位置和分布；视亮度和颜色（温度）；天体的形态；物理性质
    - 难以处理暂现源：爆发、宇宙线等（SDSS多色测光、互相比较）
  - 多历元
    - 视差（距离）、自行、变源/暂现源（变星、新星、超新星、伽马暴、潮汐瓦解）
- 分光观测
  - 天体的视向速度、物理性质（温度、密度、质量）、化学组分（丰度）
- 测光+分光
  - 三维位置、速度
  - 分布、运动、结构、性质、形成、演化

#### 光谱观测的基本类型

- 无缝光谱：棱镜
  - 优点：什么都记录
  - 缺点：分辨率低、天光背景高（空间观测无此问题）、不同天体光谱叠加在一起（结合狭缝使用；精确知道天体的形状和位置，可以分辨出特定天体的光谱）
- 长（单）缝观测
- 二维长缝观测
- 􏰐􏰏􏰂􏰈􏰀􏰆􏰑􏰄􏰉􏰁􏰐􏰏􏰂􏰈􏰀􏰆􏰑􏰄􏰉三维积分视场光谱观测（IFU）
- 多缝（多目标）光谱观测
  - 遥远星系（每一个狭缝可以扣除自己的天光，适合观测暗弱天体）
  - 狭缝冲突——限制了同时观测的目标数
- 多光纤（多目标）光谱观测
  - 一次观测获取大量数据，视场很大