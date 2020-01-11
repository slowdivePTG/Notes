# Chapter 5 磁场中的光谱

## 原子的磁矩

1. 电子轨道运动
   $$
   \mu_l=\frac{e}{2m}p_L=\sqrt{l(l+1)}\frac{e\hbar}{2m}\equiv\sqrt{l(l+1)}\mu_B
   $$
   其中 $\mu_B=e\hbar/2m$ 是 Bohr 磁子

   这可以用安培分子环流理论解释，即认为原子的磁矩由电子圆轨道运动引起的电流产生

2. 电子自旋
   $$
   \mu_s=\frac{e}{m}p_s=\sqrt{s(s+1)}\frac{e\hbar}{m}\equiv\sqrt{3}\mu_B
   $$

3. 核子自旋磁矩非常小，因为其质量远大于电子质量

### 单电子原子总磁矩

- 磁矩和角动量方向相反
  $$
  \vec \mu_s=-\frac em\vec P_s,\   \vec \mu_L=-\frac e{2m}\vec P_L
  $$
	从而
  $$
  \frac{\mu_s}{P_s}\neq\frac{\mu_L}{P_L}
  $$
这直接导致了总磁矩和总角动量不平行
  
  ![](/Users/chang/Desktop/天体光谱学/fig/5_1.eps)
  
- $\vec\mu$ 在 $\vec P_j$ 反向延长线上的投影为有效磁矩 $\vec \mu_j$，自旋和轨道角动量磁矩绕其旋进

- $\mu_j$ 的计算
  $$
  \begin{align*}
  \mu_j&=\mu_l\cos\langle l,j\rangle+\mu_s\cos\langle s,j\rangle\\
  &=\frac e{2m}(P_l\cos\langle l,j\rangle+2P_s\cos\langle l,j\rangle)\\
  &=\frac e{2m}\left(\frac{P_s^2+P_j^2-P_l^2}{2P_j}+\frac{P_l^2+P_j^2-P_s^2}{P_j}\right)\\
  &=\frac{e}{2m}P_j\left(1+\frac{P_j^2+P_s^2-P_l^2}{2P_j^2}\right)\\
  &\equiv g\cdot\frac{e}{2m}P_j=g\cdot\frac{\mu_B}{\hbar}P_j
  \end{align*}
  $$
  其中 $g$ 是朗德因子
  $$
  g\equiv1+\frac{P_j^2+P_s^2-P_l^2}{2P_j^2}=1+\frac{j(j+1)+s(s+1)-l(l+1)}{2j(j+1)}
  $$

- 强磁场的特殊情况

  - $s=0,\ j=l\Rightarrow g_l=1$
    $$
    \mu_l=\frac{g_l\mu_BP_l}{\hbar}
    $$

  - $s=l,\ j=0\Rightarrow g_s=2$
    $$
    \mu_s=\frac{g_s\mu_BP_s}{\hbar}
    $$

### 多电子原子总磁矩

- 情况与单原子情形相似，对于 L-S 耦合
  $$
  g=1+\frac{J(J+1)+S(S+1)-L(L+1)}{2J(J+1)}
  $$

## 外磁场的附加能量

$$
\Delta E=\vec \mu_J\cdot \vec B=\mu_JB\cos\theta=g\cdot\frac{\mu_B}{\hbar}\cdot B\cdot P_J\cos\theta
$$

- 其中 $P_J\cos\theta$ 是 $\vec P_J$ 在 z 轴的投影，满足量子化条件
  $$
  P_J\cos\theta=M_J\hbar
  $$
  $M_J$ 取 $-J,\ -J+1,\ ,\cdots,J-1,\ J$ 

- $\Delta E$ 分裂成 $2J+1$ 层
  $$
  \Delta E=gM_J\mu_BB
  $$
  其中 $g$ 和 $M_J$ 是我们需要重点关注的

- 例：$^2\text{P}_{3/2}$

  - $L=1,\ S=\frac{1}{2},\ J=\frac32$
    $$
    g=1+\frac{\frac32(\frac32+1)-1(1+1)+\frac12(\frac12+1)}{2\cdot\frac32(\frac32+1)}=\frac{4}{3}
    $$

    $$
    M_J=-\frac32,-\frac12,\ \frac12,\ \frac32
    $$

    $$
    \Rightarrow gM_J=2,-\frac32,\ \frac32,\ 2
    $$

  - 当有磁场时，$^2\text{P}_{3/2}$ 就会分裂成四个能级

### 强磁场的附加能量

- L-S耦合被破坏

  - $\mu_S=2\mu_BS_z,\ S_z=-S,-S+1,\cdots,S$

  - $\mu_L=\mu_BM_L$

  - 附加能量
    $$
    \Delta E=\Delta E_S+\Delta E_L=\mu_BB(M_L+2S_z)
    $$

- 例：$\ce{OI}$ 1s$^2$2s$^2$2p$^4$ 的一个态 $^3\text{P}$ 在强磁场（10 T 以上）下的情形

  - $L=1\Rightarrow M_L=-1,0,1$
  - $S=1\Rightarrow S_z=-1,0,1$

  | $M_L$ | $S_z$ | $M_L+2S_z$ |
  | :---: | :---: | :---: |
  |  -1   |  -1   |     -3     |
  |   0   |  -1   |     -2     |
  |  -1   |   0   |     -1     |
  |  +1   |  -1   |     -1     |
  |   0   |   0   |     0      |
  |  +1   |   0   |     1      |
  |  -1   |  +1   |     1      |
  |   0   |  +1   |     2      |
  |  +1   |  +1   |     3      |

  9 种组合，对应 7 个不同能级

## Zeeman 效应（弱磁场中的光谱）

### 正常 Zeeman 效应

- 单态：$S=0,\ g=1$
- $\Delta E=gM_J\mu_BB=M_J\mu_BB$，间隔 $\mu_BB$

### 反常 Zeeman 效应

- 多重态：$S\neq0$
- 例：$\ce{OI}$ 的基态 $^3\text{P}_2$
  - $S=1,\ L=1,\ J=2,\ M_J=-2,-1,0,1,2$
  - $g=\frac{3}{2}$，能级间隔 $\frac{3}{2}\mu_BB$
  - 取 $B=0.1\text{ T}$，能级间隔 $8.7\times10^{-6}\text{ eV}$，波数 $0.07\text{ cm}^{-1}$，当 $\lambda=5000\ \overset{\circ}{\text{A}}$ 时，$\Delta\lambda=0.0175\ \overset{\circ}{\text{A}}$ 
- 同一光谱项的不同能级对应不同的谱线分裂

## 磁场中的光谱

- 考虑能级 1 与 2 之间的跃迁

  - 无磁场：$h\nu=E_2-E_1$

  - 有磁场：$h\nu'=h\nu+(\Delta E_2-\Delta E_1)=h\nu+(g_2M_2-g_1M_1)\mu_BB$

  - 频率偏移
    $$
    \nu-\nu'=\frac{(g_2M_2-g_1M_1)\mu_BB}{h}=(g_2M_2-g_1M_1)\frac{eB}{4\pi m}\equiv(g_2M_2-g_1M_1)\omega_L
    $$
    $\omega_L$ 是拉莫尔频率

  - 波数偏移
    $$
    \Delta\frac1\lambda=\frac{(g_2M_2-g_1M_1)eB}{4\pi cm}\equiv\frac{(g_2M_2-g_1M_1)\mu_BB}{hc}\equiv({g_2M_2-g_1M_1})L
    $$
    $L$ 是 Lorentz 单位
    
    

### 选择定则

- $\Delta M_J=0$ ——产生线偏振 $\pi$ 线

- $\Delta M_J=\pm1$ ——产生圆偏振 $\sigma$ 线

- 例：正常 Zeeman 效应，$^1\text{D}_2\to\ ^1\text{P}_1$

  - $S=0\Rightarrow g_J=g_L=1$
  - $^1\text{D}_2,\ S=0,\ L=2,\ J=2\Rightarrow M_J=-2,-1,0,1,2$
  - $^1\text{P}_1,\ S=0,\ L=1,\ J=1\Rightarrow M_J=-1,0,1$
  - $\Delta\frac{1}{\lambda}=(g_2M_2-g_1M_1)L$

  | $g_2M_2$ | $g_1M_1$ | $\Delta gM$ |   偏振   |
  | :------: | :------: | :---------: | :------: |
  |    2     |    1     |      1      | $\sigma$ |
  |    1     |    1     |      0      |  $\pi$   |
  |    1     |    0     |      1      | $\sigma$ |
  |    0     |    1     |     -1      | $\sigma$ |
  |    0     |    0     |      0      |  $\pi$   |
  |    0     |    -1    |      1      | $\sigma$ |
  |    -1    |    0     |     -1      | $\sigma$ |
  |    -1    |    -1    |      0      |  $\pi$   |
  |    -2    |    -1    |     -1      | $\sigma$ |

  共 9 种跃迁，分为三层
  $$
  \Delta\frac1\lambda=-L,0,L
  $$

- 例：反常 Zeeman 效应，$\ce{NaI}\ ^2\text{P}_{3/2,1/2}\to\ ^2\text{S}_{1/2}$ （钠双线）

  - $^2\text{P}_{3/2},\ S=\frac12,\ L=1,\ J=\frac32\Rightarrow\ g=\frac43,\  M_J=-\frac32,-\frac12,\frac12,\frac32$
  - $^2\text{P}_{1/2},\ S=\frac12,\ L=1,\ J=\frac12\Rightarrow\ g=\frac23,\  M_J=-\frac12,\frac12$
  - $^2\text{S}_{1/2},\ S=\frac12,\ L=0,\ J=\frac12\Rightarrow\ g=2,\  M_J=-\frac12,\frac12$
  - $^2\text{P}_{3/2}\to\ ^2\text{S}_{1/2}$
  
  | $g_2M_2$ | $g_1M_1$ | $\Delta gM$ |   偏振   |
  | :------: | :------: | :---------: | :------: |
  |    2     |    1     |      1      | $\sigma$ |
  |   3/2    |    1     |     1/2     |  $\pi$   |
  |   3/2    |    -1    |     5/2     | $\sigma$ |
  |   -3/2   |    1     |    -5/2     | $\sigma$ |
  |   -3/2   |    -1    |    -1/2     |  $\pi$   |
  |    -2    |    -1    |     -1      | $\sigma$ |
  
  共 6 种跃迁，分为 6 层，其中原位置光谱消失
  
  - $^2\text{P}_{1/2}\to\ ^2\text{S}_{1/2}$
  
  | $g_2M_2$ | $g_1M_1$ | $\Delta gM$ |   偏振   |
  | :------: | :------: | :---------: | :------: |
  |   1/3    |    1     |    -2/3     |  $\pi$   |
  |   1/3    |    -1    |     4/3     | $\sigma$ |
  |   -1/3   |    1     |    -4/3     | $\sigma$ |
  |   -1/3   |    -1    |     2/3     |  $\pi$   |
  
  共 4 种跃迁，分为 4s 层，其中原位置光谱消失
  
- 应用：测量磁场

  - 磁场导致谱线分裂，测量谱线分裂程度可以反推出磁场
  - 例：太阳黑子