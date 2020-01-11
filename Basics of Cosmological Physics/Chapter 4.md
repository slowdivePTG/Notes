## Chapter 4 World Models

- Scalar factor: $a(t)$
   natural units: $c=1$
   $$
   \left(\frac{\dot a}{a}\right)^2 + \frac{k}{a^2} = \frac{8\pi}{3}G\rho\\
    H(t)\equiv \frac{\dot a}{a},\quad \rho_\Lambda=\frac{\Lambda}{8\pi G}\\
    H^2 + \frac{k}{a^2} = \frac{8\pi G}{3}\left(\sum_i\rho_i+\rho_\Lambda\right)
   $$

    $k=0​$, flat
   $$
   \rho_\text{tot} = \sum_i\rho_i+\rho_\Lambda=\frac{3H^2}{8\pi G}\equiv\rho_\text{crit}
   $$
    define $\Omega_i\equiv\rho_i/\rho_\text{crit}​$
   $$
   \left\{
    \begin{aligned}
    &\Omega_m: \text{matter}\\
    &\Omega_r: \text{radiation}\\
    &\Omega_\Lambda: \text{dark energy}
    \end{aligned}
    \right.
   $$
    all are functions of time.
    Deriving
   $$
   \frac{k}{a^2H^2}=\sum_i\Omega_i + \Omega_\Lambda - 1
   $$
    define 
   $$
   \Omega_k \equiv -k/a^2H^2\\
   \Rightarrow \sum_i\Omega_i+\Omega_\Lambda+\Omega_k=1
   $$
   

### Flat FRW Cosmologies

- Friedmann-Robertson-Walker: FRW models

- Assuming pressureless matter $ P=0$
   $$
   \rho_m = \rho_{m,0}\left(\frac{a}{a_0}\right)^{-3}
   $$
   define $a_0\equiv1$
   $$
   \left(\frac{\dot a}{a}\right)^2 = \frac{8\pi G}{3}\rho_{m,0}a^{-3}+\frac{\Lambda}{3}\\
    \dot a^2=H_0^2\Omega_{m,0}a^{-1} + H_0^2\Omega_{\Lambda,0}a^2\\
    \Omega_{m,0}+\Omega_{\Lambda,0}=1
   $$

    - $\Lambda>0$
      $$
      u=\frac{2\Omega_{\Lambda,0}}{\Omega_{m,0}}a^3\\
      \dot u^2 = 9H_0^2\Omega_{\Lambda,0}(2u+u^2)=3\Lambda(2u+u^2)
      $$
      do integration to $u$, derive
      $$
      a^3=\frac{\Omega_{m,0}}{2\Omega_{\Lambda,0}}[\cosh(3\Lambda)^{1/2}t-1]
      $$

       - For small $t$, $a\propto t^{2/3}$
      - For large $t$, $a\propto e^{[(\Lambda)/3]^{1/2}t}$

    - $\Lambda<0$
      $$
      u=-\frac{2\Omega_{\Lambda,0}}{\Omega_{m,0}}a^3\\
      a^3=\frac{\Omega_{m,0}}{2(-\Omega_{\Lambda,0})}\{1-\cosh[3(-\Lambda)]^{1/2}t\}
      $$

       - For small $t$, $a\propto t^{2/3}$
       - For large $t$, $a\propto -e^{[(-\Lambda)/3]^{1/2}t}​$

    - $\Lambda=0​$
      Einstein-de Sitter
      $$
      a = \left(\frac{t}{t_0}\right)^{2/3}\\
      t_0=\frac{2}{3H_0}\\
      a = \left(\frac{9}{4}H_0^2t^2\right)^{1/3}
      $$

   - A flat, pressureless universe with a small, but non-zero, cosmological constant **initially evolves as if it were Einstein-deSitter**

### Cosmologies with $k\neq0,\ \Lambda=0$ 

$$
\left(\frac{\dot a}{a}\right)^2+\frac{k}{a^2}=\frac{8\pi G}{3}\rho\\
\dot a^2=\Omega_{m,0}H_0^2a^{-1}-k=\Omega_{m,0}H_0^2a^{-1}+\Omega_{k,0}H_0^2\\
\Omega_{m,0}+\Omega_{k,0} = 1
$$

- $\Omega_{k,0}>0, k<0$, negative curvature
  $$
  \dot a^2\sim\Omega_{k,0}H_0^2=-k>0, \ a\propto t
  $$
  $a$ grows linearly with time

- $\Omega_{k,0}<0, k>0​$, positive curvature

  let $\dot a=0$, derive $a_{max}$
  $$
  a_{\max }=\frac{\Omega_{\mathrm{m}, 0}}{\left|\Omega_{\mathrm{k}, 0}\right|}
  $$

![](/Users/chang/Desktop/宇宙学/fig/a_t.png)

|      | $\Omega_{m,0}$ | $\Omega_{\Lambda,0}$ | $\Omega_{k,0}$ |            Concordance cosmology             |
| :--: | :------------: | :------------------: | :------------: | :-----------------------------------: |
|  1   |      0.3       |         0.7          |       0        |      $a\propto\exp[(\Lambda/3)^{1/2}t]$      |
|  2   |      0.3       |          0           |      0.7       |                 $a\propto t$                 |
|  3   |       1        |          0           |       0        | $a = \left(\frac{9}{4}H_0^2t^2\right)^{1/3}$ |
|  4   |       4        |          0           |       -3       |                $a_{max}=4/3$                 |

- The age of universe can be an indirect proof for acceleration of universe expansion, for only universe with high $\Omega_\Lambda$ can give a universe age old enough (global cluster)
