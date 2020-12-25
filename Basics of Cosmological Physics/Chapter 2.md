## Chapter 2 Newtonian Cosmology

<img src="./IMG_0619.jpg" style="zoom:30%" />
$$
\vec v_A=H_0 \vec r_A,\ \vec v_B=H_0 \vec r_B
$$

- Recession velocity if B as seen by A is

  $$
  \vec v_{BA}=\vec v_B-\vec v_A=H_0(\vec r_B-\vec r_A)
  $$
  Hubble expansion is a natural property of an expanding universe that obeys the cosmological principle

### Comoving coordinates

- coordinates that are carried along with the expansion

- comoving with space distance $\vec r$, comoving distance $\vec x$ (constant)

  $$
  \vec r_{BA} = a(t)\cdot\vec x_{BA}
  $$
  $a(t)$ is the scale factor - all we want to find out

- Birkhoof's theorem: the net gravitational effect of a uniform **external** medium on a spherical cavity is zero, the net gravitational effect comes from matter internal to radius $r$ (as a mass point)

  total energy of a particle of mass $m$ at A, B, C, D

  $$
  U=T+V=\frac{1}{2}m\dot{r}^2-\frac{GMm}{r}=\frac{1}{2}m\dot{r}^2-\frac{4\pi}{3}G\rho r^2m
  $$

### Friedmann equation

$$
\left(\frac{\dot{a}}{a}\right)^2=\frac{8\pi G}{3}\rho-\frac{kc^2}{a^2},\ \text{where }kc^2=-\frac{2U}{mx^2}
$$

- $k$ must be independent of $x$, therefore $U\propto x^2$ 

- $k$ is a independent of $t$, for $U​$ is conserved

- Thus $k$ is just a constant

  - $k>0\Rightarrow U<0, |V|>T$ , collapse
  - $k<0\Rightarrow U<0, V<T$ , expand forever
  - $k=0\Rightarrow U=0$ , expansion terminates when $t\to\infty$

- Hubble parameter
  $$
  \vec v=H_0\vec r,\ \vec r=a\vec x\\
  \Rightarrow \vec v=|\dot{\vec r}|\hat{\vec r}=\frac{\dot a}{a}\vec r\\
  \Rightarrow H\equiv \frac{\dot a}{a}
  $$
  which is a function of time, so called Hubble constant $H_0$ is the Hubble parameter at present

- Using Hubble parameter we can rewrite Friedmann equation

  $$
  H^2=\frac{8\pi G}{3}\rho-\frac{kc^2}{a^2}
  $$
  if $k=0$ , the **critical density** $\rho$ is then
  $$
  \rho_c=\frac{3H_0^2}{8\pi G}
  $$

- In thermodynamics, the first law points that

  $$
  \text{d} E+P\text dV=T\text d S
  $$
  where $P$ is the pressure, $S$ is the entropy

- Expanding volume $V$ of unit comoving radius $x=1\ (r=a)$, $E=mc^2$, energy within the volume
  $$
  E=\frac{4\pi}{3}a^3\rho c^2\\
  \frac{\text dE}{\text{d} t}=4\pi a^2\rho c^2\frac{\text da}{\text{d} t}+\frac{4\pi}{3} a^3 c^2\frac{\text d\rho}{\text{d} t}\\
  \frac{\text dV}{\text{d} t}=4\pi a^2\frac{\text da}{\text{d} t}
  $$

- Assuming a reservable expansion $\text dS=0​$ , we obtain the **fluid equation** 

  $$
  \dot\rho+3\frac{\dot a}{a}\left(\rho+\frac{P}{c^2}\right)=0
  $$

  - The first term - **the dilution in the density** because the volume has increased
  - The second term - **the loss in energy** because the pressure of the material has done work as the universe’s volume increased.

- Equation of state

  There is a unique pressure associated with each density,
  $$
  P\equiv P(\rho)
  $$

    - For non-relativistic matter, $P=0$ , **dust**
    - For highly-relativistic matter , $P=\rho c^2/3$ , **radiation pressure** of **light**

- Time-derivation on both sides of the Friedmann equation

  $$
  2\frac{\dot a}{a}\frac{a\ddot a-\dot a^2}{a^2}=\frac{8\pi G}{3}\dot\rho+2\frac{kc^2}{a^3}\dot a\\
  \frac{\ddot a}{a}-\left(\frac{\ddot a}{a}\right)^2=\frac{8\pi G}{3}\rho-\frac{kc^2}{a^3}
  $$

- Acceleration equation
  $$
  \frac{\ddot a}{a}=-\frac{4\pi G}{3}\left(\rho+\frac{3P}{c^2}\right)
  $$

- Analytical solution

  - $k=0$

    - Dust, $P=0$
      $$
      \dot\rho+3\frac{\dot a}{a}\rho=0\Rightarrow\frac{\text{d}}{\text{d}t}(\rho a^3)=0
      $$

      $$
      \rho=\frac{\rho_0}{a^3}\Rightarrow\dot a^2=\frac{8\pi G\rho_0}{3}\frac{1}{a}\\\Rightarrow a(t)=\left(\frac{t}{t_0}\right)^{2/3},\ \rho(t)=\frac{\rho_0t_0^2}{t^2}\\
      \Rightarrow H(t)=\frac{\dot a}{a}=\frac{2}{3t},\ t_0=\frac{2}{3H_0}
      $$

      However, the current age of universe $t_0​$ obtained in this model is wrong

    - Radiation, $P=\rho c^2/3$
      $$
      \dot\rho+4\frac{\dot a}{a}\rho=0\Rightarrow\frac{\text{d}}{\text{d}t}(\rho a^4)=0\\
      \Rightarrow a(t)=\left(\frac{t}{t_0}\right)^{1/2},\ \rho(t)=\frac{\rho_0t_0^2}{t^2}\\
      \Rightarrow H(t)=\frac{\dot a}{a}=\frac{1}{2t}<\frac{2}{3t},\ t_0=\frac{1}{2H_0}
      $$

    - Radiation dominated universe
      $$
      a(t)\propto t^{1/2},\ \rho_{rad}\propto t^{-2},\ \rho_{dust}\propto a^{-3}\propto t^{-3/2}
      $$
      Unstable, the radiation density decreases faster than the dust density, the universe will turn to matter dominated on day

    - Matter dominated universe
      $$
      a(t)\propto t^{2/3},\ \rho_{dust}\propto t^{-2},\ \rho_{dust}\propto a^{-4}\propto t^{-8/3}
      $$
      Stable

### Olber's Paradox

- In a shell from $r​$ to $r+\mathrm d r​$, the total number of stars is $4\pi r^2n_0\mathrm d r​$, where $n_0​$ is the number density
- Total intensity of the sky

  $$
  \mu=\int_0^{r_{max}}4\pi r^2n_0\left(\frac{L_0}{4\pi r^2}\right)\mathrm d r=n_0L_0r_{max}\\
  r_{max}\to\infty\Rightarrow \mu\to\infty
  $$

  which is $10^{13}$ times brighter than it actually is

- Thermodynamic problem
  - Infinite volume
  - Infinite time to reach thermodynamic equilibrium
  - BUT the universe is not homogeneous (not the temperature of CMB)
