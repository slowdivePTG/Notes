# Chapter 7. Equation of State

Here we discuss two effects producing pressure. Above all, for ideal gas, the EoS gives
$$
P_\text{gas}=\frac{\rho k_BT}{\mu m_p}
$$

## Radiation Pressure

$$
P_\text{rad}=\frac13aT^4
$$

Let us consider gas-radiation mixed fluid
$$
P=P_\text{gas}+P_\text{rad}=\frac{\rho k_BT}{\mu m_p}+\frac13aT^4
$$
Define
$$
\beta\equiv\frac{P_\text{gas}}{P}
$$

>Let's check the $\beta$ value for different stars
>
>- Sun: $\rho_c\sim150$ g/cm$^3$, $T_c\sim10^7$ K, $\Rightarrow\beta\sim1$
>- Massive star ($20\ M_\odot$): $\rho_c\sim5$ g/cm$^3$, $T_c\sim4\times10^7$ K, $\Rightarrow\beta\sim0.84$

Since the density
$$
\rho=\frac{\mu m_p}{k_BT}\left(P-\frac a3T^4\right)=\rho(P,T)
$$
We can define two derivatives
$$
\alpha\equiv\left(\frac{\partial \ln \rho}{\partial \ln P}\right)_T=\frac{P}{P_\text{gas}}=\frac1\beta,\quad \delta\equiv-\left(\frac{\partial \ln \rho}{\partial \ln T}\right)_P=\frac{P+3P_\text{rad}}{P_\text{gas}}=\frac{4-3\beta}{\beta}
$$
The specific internal energy is
$$
e(\rho,T)=e_\text{gas}+e_\text{rad}=\frac{3}{2}\frac{k_B}{\mu m_p}T+\frac1\rho aT^4
$$
Thus the specific heat capacity (when the pressure is a constant) is
$$
\begin{align*}
c_P&\equiv\left(\frac{\text d e}{\text d T}\right)_P=\left(\frac{\partial e}{\partial T}\right)_P+P\left[\frac{\partial (1/\rho)}{\partial T}\right]_P\\
&=\left(\frac{\partial e}{\partial T}\right)_\rho+\left(\frac{\partial e}{\partial \rho}\right)_T\left(\frac{\partial \rho}{\partial T}\right)_P-\frac{P}{\rho^2}\left(\frac{\partial \rho}{\partial T}\right)_P\\
&=\frac{k_B}{\mu m_p}\left[\frac{3}{2}+(4+\delta)\frac{3P_\text{rad}}{P_\text{gas}}\right]+\frac{k_B}{\mu m_p}\frac{\delta P}{P_\text{gas}}\\
&=\frac{k_B}{\mu m_p}\left[\frac{3}{2}+\left(4+\frac{4-3\beta}{\beta}\right)\frac{3(1-\beta)}{\beta}+\frac{4-3\beta}{\beta^2}\right]\\
&=\frac{k_B}{\mu m_p}\left[\frac{3}{2}+\frac{3(4+\beta)(1-\beta)}{\beta^2}+\frac{4-3\beta}{\beta^2}\right]
\end{align*}
$$
When gas pressure dominates, $\beta=1$, thus
$$
c_P=\frac52\frac{k_B}{\mu m_p}
$$
When radiation dominates, $\beta=0$, and $c_P$ diverges.

The adiabatic temperature gradient
$$
\begin{align*}
\nabla_\text{ad}&=\frac{\delta}{\rho c_P}\frac PT=\frac{k_B}{\mu m_pc_P}\frac{\delta}{\beta}\\
&=\left[\frac{3}{2}+\frac{3(4+\beta)(1-\beta)}{\beta^2}+\frac{4-3\beta}{\beta^2}\right]^{-1}\frac{4-3\beta}{\beta^2}\\
&=\frac{8-6\beta}{32-24\beta-3\beta^2}
\end{align*}
$$
The heat index is
$$
\begin{align*}
\gamma&\equiv\left(\frac{\partial \ln P}{\partial\ln \rho}\right)_s=\left[\left(\frac{\partial \ln \rho}{\partial\ln P}\right)_T+\left(\frac{\partial \ln \rho}{\partial\ln T}\right)_P\left(\frac{\partial \ln T}{\partial\ln P}\right)_s\right]^{-1}\\
&=\frac1{\alpha-\delta\nabla_\text{ad}}\\
&=\frac{32-24\beta-3\beta^3}{24-21\beta}\\
&=\left\{
\begin{array}{l}
5/3,\quad \beta=1\\
4/3+\beta/6+\mathcal{O}(\beta^2),\quad \beta\to0\\
\end{array}
\right.
\end{align*}
$$
This fact is extremely important for the stability of a star.

- We revisit the virial theorem,
  $$
  E_\text{tot}=\frac{3\gamma-4}{3(\gamma-1)}E_\text g
  $$
  When $\beta\to0$, $E_\text{tot}\to\beta E_\text g/2$. Since $E_\text g<0,\ \beta>0$, the star can exist (thanks to the fact that $\beta>4/3$).

- We try to compress a star of the mass $M$ and discuss the stability afterwards.

  The gravitational force and the pressure gradient force are
  $$
  F_\text g\sim-\frac{GM}{R^2},\quad F_{P}\sim\frac1\rho\frac{P}{R}\propto\frac{\rho^{\gamma-1}}{R}
  $$
  Since $M\propto\rho R^3$ is fixed, $\rho\propto R^{-3}$, thus
  $$
  F_\text g\propto-R^{-2},\quad F_{P}\propto\frac{\rho^{\gamma-1}}{R}\propto R^{-3\gamma+2}\propto R^{-3(\gamma-4/3)-2}
  $$
  Obviously, when $\gamma>4/3$, when $R$ is compressed, $F_\text{g}+F_P>0$, so the net force resists the compression. If $\gamma<4/3$, the star is dynamically unstable and the star would finally collapse.



## Degenerate Electron Gas

