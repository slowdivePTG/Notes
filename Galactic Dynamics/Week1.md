# Week1

## Measure the universe

### From Kepler to Newton

**Kepler III**
$$
P^2\propto a^3
$$
where $a$ is the semi-major axis

**Acceleration of circular motion**
$$
f=\frac{v^2}{r}
$$
By assuming circular orbits of planets, we have
$$
f= v^2r^{-1}\propto \frac{r}{P^2}\propto\frac{r}{r^3}=r^{-2}
$$
which is consistent with **Newton II**
$$
F=\frac{Gm_1m_2}{r^2}
$$

### Various astrophysical objects

Using the tool
$$
\frac{v^2}{r}=\frac{GM}{r^2}\Rightarrow M=\frac{v^2r}{G}
$$
we can measure

#### The sun

For the first time we are able to measure the **solar mass**
$$
P=2\pi\sqrt{\frac{a^3}{GM_{\odot}}}\Rightarrow M_{\odot}=\frac{4\pi^2a^3}{GP^2}=\frac{4\pi^2\times(1.5\times10^8\text{ km})^3}{G\times(1\text{ yr})^2}=2\times10^{33}\text{ g}
$$

#### Star cluster

$$
R\sim1\text{ pc},\ \sigma\sim 20\text{ km/s}\Rightarrow M\sim10^5M_{\odot},\ \rho\sim10^5\ M_{\odot}\text{/pc}^{-3}
$$

Dynamic mass $\sim$ Visible mass

#### Galaxy

$$
R\sim10\text{ kpc},\ \sigma\sim 200\text{ km/s}\Rightarrow M\sim10^{11}M_{\odot},\ \rho\sim10^{-1}\ M_{\odot}\text{/pc}^{-3}
$$

**Discovery of dark matter** - Dynamic mass $>$ Visible mass

#### SMBH (Sgr A*)

$$
R\sim0.01\text{ pc},\ \sigma\sim 500\text{ km/s}\Rightarrow M\sim2\times10^{6}M_{\odot},\ \rho\sim2\times10^{12}\ M_{\odot}\text{/pc}^{-3}
$$

In such high mass density, the average distance between two stars (solar mass) is
$$
D\sim\frac{1}{2^{1/3}}\times10^{-4}\text{ pc}\sim20\text{ AU}
$$

#### Cosmology

Typical acceleration

Estimation using **hubble timescale** and **speed of light**
$$
a\sim\frac{v^2}{r}\sim\frac{c^2}{10\text{ Gyr}\cdot c}\sim10^{-7}\text{cm/s/yr}
$$

## Two-body problem

Assuming two point mass $m_1$ and $m_2$ rotating around the common CoM
$$
m_1\ddot{\vec{r}}_1=\frac{Gm_1m_2}{|\vec r_2-\vec r_1|^3}\left(\vec r_2-\vec r_1\right)\\
m_2\ddot{\vec{r}}_2=-\frac{Gm_1m_2}{|\vec r_2-\vec r_1|^3}\left(\vec r_2-\vec r_1\right)
$$
Let $\vec r=\vec r_2-\vec r_1$, we have
$$
m_1\ddot{\vec{r}}_1=\frac{Gm_1m_2}{r^3}\vec r,\quad 
m_2\ddot{\vec{r}}_2=-\frac{Gm_1m_2}{r^3}\vec r
$$

**Trajectory**

In an **effective one-body problem**, we consider only the evolution of $\vec r$
$$
\ddot{\vec r}=-\frac{G(m_1+m_2)}{r^3}\vec r\equiv-\frac{Gm}{r^3}\vec r
$$

- Test mass moves around $m_1+m_2$

**Energy**
$$
\begin{align*}
E&=\frac{1}{2}m_1\dot{\vec r}_1^2+\frac{1}{2}m_2\dot{\vec r}_2^2-\frac{Gm_1m_2}{r}\\
&=\frac{1}{2}\left[m_1\left(\frac{m_2}{m_1+m_2}\right)^2+m_2\left(\frac{m_1}{m_1+m_2}\right)^2\right]\dot{\vec r}^2-\frac{Gm_1m_2}{r}\\
&=\frac{1}{2}\frac{m_1m_2}{m_1+m_2}\dot{\vec r}^2-\frac{Gm_1m_2}{r}\\
&=\frac{m_1m_2}{m_1+m_2}\left[\frac{1}{2}\dot{\vec r}^2-\frac{G(m_1+m_2)}{r}\right]
\end{align*}
$$
where
$$
\mu=\frac{m_1m_2}{m_1+m_2}
$$
is the **reduced mass**, and
$$
\frac{1}{2}\dot{\vec r}^2-\frac{G(m_1+m_2)}{r}
$$
is known as the **specific energy** in the effective one-body system

**Angular momentum**
$$
\begin{align*}
\vec J&=m_1\vec r_1\times\dot{\vec r}_1+m_2\vec r_2\times\dot{\vec r}_2\\
&=\left[m_1\left(\frac{m_2}{m_1+m_2}\right)^2+m_2\left(\frac{m_1}{m_1+m_2}\right)^2\right]\vec r\times\dot{\vec r}\\
&=\mu\vec r\times\dot{\vec r}
\end{align*}
$$
where
$$
\vec r\times\dot{\vec r}
$$
is the **specific angular momentum**