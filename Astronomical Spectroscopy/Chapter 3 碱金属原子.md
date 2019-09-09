# Chapter 3 碱金属原子

## 碱金属和类碱金属原子

### 重要性

- 简单：最外层只有一个电子——化学性质类似，光谱简单
- 在天文光谱中普遍存在

### 原子实和轨道贯穿

- 轨道穿透：原子外围价电子穿透内层电子云深入到核区，受到原子核更大的吸引力，电势能降低

  - 电子轨道能级为
    $$
    \begin{aligned}
    E_{n l}&=-R_{\infty} \frac{\mu}{m_{\mathrm{e}}} \frac{Z_{\mathrm{eff}}^{2}}{n^{2}}
    \end{aligned}
    $$

  - 外围电子感受到的核电荷增加

  - 或外围电子轨道的主量子数减小 $n'=n-\mu_{nl}$
    $$
    E_{n l}=-R_{\infty} \frac{\mu}{m_{\mathrm{e}}} \frac{Z_{\mathrm{eff}}^{2}}{\left(n-\mu_{n l}\right)^{2}}
    $$

## 钠原子光谱

- $\ce{Na}$ 虽然具有类氢结构，但由于贯穿效应的影响，相同主量子数下的简并打破（量子亏损不同），不同 l 态的能级分裂，s < p < d
- $\ce{Na}$ 原子 s​ 轨道穿透效应明显，$\mu_{ns}>1$，d 轨道效应不明显，因此电子先排满 4s​ 轨道再排 ​3d​ 轨道

### 钠的光谱序列

- 主要在光学波段
- 主线系 ( **P**rinciple series，双线 )，高级的 p 到 3s——最重要：钠双线
- 锐线系􏰑 ( **S**harp series􏰈􏰌􏰕􏰒，双线 )，高级的 s 到 3p
- 弥散线系 ( 􏰑**D**iffuse series􏰈􏰆􏰕􏰒，三线 )，高级的 d 到 3p
- 基本线系 ( **F**undamental series，三线 )，高级的 f 到 3d

## 精细结构

- 双线——s轨道
- 三线——不包含s轨道

### 电子自旋磁矩

- 轨道-自旋相互作用——光谱项分裂，产生精细结构分裂

- 最重要：**自旋磁矩**和**电子轨道运动**产生的磁场的相互作用
  $$
  \boldsymbol{\mu}_{s}=-2 \frac{\mu_{\mathrm{B}}}{\hbar} \mathbf{s},\text{ where } \mu_{\mathrm{B}}=\frac{e \hbar}{2 m_{e}}
  $$

### 电子轨道运动产生的磁场

$$
\mathbf{B}=\frac{\hbar^{2}}{2} \frac{\mathbf{v} \times \mathbf{r}}{c^{2} r} \frac{d V}{d r}=-\frac{\hbar^{2}}{2} \frac{\mathbf{l}}{m_{e} c^{2} r} \frac{d V}{d r}
$$

- $V$ 是电势，对于 Coulomb 相互作用
  $$
  V=-\frac{1}{r}, \quad \frac{d V}{d r}=-\frac{1}{r^{2}}\\
  \Rightarrow \mathbf{B}=\frac{\hbar^{2}\mathbf{l}}{2m_{e} c^{2} r^3}
  $$

  $\mathbf{l}$ 是角动量

### 自旋轨道相互作用

- 附加能量 $-\boldsymbol{\mu} \cdot \mathbf{B}$

- 对于多电子原子，附加能量算符为
  $$
  \hat{\mathrm{H}}_{\mathrm{so}}=\frac{A(L, S)}{\hbar^{2}} \hat{\mathrm{L}} \cdot \hat{\mathrm{S}}
  $$
  $A(L,S)$ 是正比于 $\frac{1}{r} \frac{d V}{d r}$ 的常数
  $$
  \hat{\mathrm{L}} \cdot \hat{\mathrm{S}}=\frac{1}{2}\left(\hat{\mathrm{J}}^{2}-\hat{\mathrm{L}}^{2}-\hat{\mathrm{S}}^{2}\right)
  $$
### 精细结构
$$
  \Delta E_{\mathrm{so}}=\frac{A(L, S)}{2}[j(j+1)-l(l+1)-s(s+1)]
$$

- 对于氢来说相对论效应很弱，对于碱金属原子则不可忽略
- 例：中性钠、中性碳

### 电偶极跃迁选择定则

- 对电偶极跃迁
  - $\Delta n$ 任意
  - $\Delta l=\pm1$
  - $\Delta s=0$ ，对中性氢，$s$ 恒为 $1/2$
  - $\Delta m_l=0,\pm1$ ，仅当磁场存在时重要
- 电四级跃迁、磁偶极跃迁等对应各种禁线

### 精细结构下的电偶极跃迁选择定则

- $\Delta j=0, \pm 1$ ，且 $j$ 不能从 0 到 0

- $\Delta m_{j}=0, \pm 1$ ，当 $j=0$ 时不能为 0

- 在两个光谱项之间跃迁产生的一组精细结构谱线称为一多重线

- 在一组多重线中，谱线的强度正比于简并因子与光谱项线强度的乘积，其中简并因子
  $$
  \frac{g_{终态}}{g_{初态}},\ g=2j+1
  $$

  例如 $\ce{NaI}$ 多重线 M4 由 3p $^2P^o_{3/2}$ 跃迁至 3d $^2D_{3/2,5/2}$ 产生的两条吸收线的强度比为
  $$
  \frac{2\times5/2+1}{2\times3/2+1}:\frac{2\times3/2+1}{2\times3/2+1}=3:2
  $$

### 原子谱线强度

- 偶极辐射——由电子的电偶极矩决定
- 电四级辐射、磁偶极辐射——禁戒跃迁——特定条件（稀薄气体等）下可以很强

### $\ce{NaI}$ 谱线的一些例子
  - $\ce{NaI}$ D线（钠双线），共振吸收，3s 到 3p，强度比为 2:1（光学薄）
      - 在普通恒星的光谱中普遍存在，通常**饱和**
      - 星际弥散星云有很强的D线吸收
  - $\ce{NaI}$ M2线，共振吸收，3s 到 4p，比D线弱很多
      - 在D双线饱和时可以用于确定 Na 的丰度
      - 落在臭氧吸收的紫外区域，较难观测
  - $\ce{NaI}$ 弥散线系，3d 到 3p 

## 其他碱金属原子光谱

- $\ce{KI}$ ，$4^2S_{1/2}\to4^2P_{3/2}$ 和 $4^2S_{1/2}\to4^2P_{1/2}$
- $\ce{Rb}$，$5^2S_{1/2}\to5^2P_{3/2}$ 和 $5^2S_{1/2}\to5^2P_{1/2}$

## 类碱金属离子光谱

- 有效电荷较大，精细结构分裂效应强得多，多重线线距较大