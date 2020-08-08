# Week8: Orbits

## Angular-action variables

Since elementary Newtonian or Lagrangian mechanics restricts our choice of coordinates to ones that are rarely integrals, we work in the more general framework of Hamiltonian mechanics.

Thus, we shall focus on a particular set of canonical coordinates, called **angular-action** variables.

- The three momenta are integrals - **actions**
- The conjugate variables - **angles**
- An orbit fortunate enough to possess angle-action variables is called a **regular orbit**

Let us denote the angle-action variables by $(\vec\theta,\vec J)$. We assume that the momenta $\vec J=(J_1,J_2,J_3)$ are integrals of motion, then Hamilton's equations read
$$
0=\dot J_i=-\frac{\partial H}{\partial\theta_i}
$$
Therefore, the Hamiltonian must be independent of the coordinates $\vec\theta$. Consequently,
$$
\dot\theta_i=\frac{\partial H}{\partial J_i}\equiv\Omega_i(\vec J)
$$
is independent of $\vec\theta$, so
$$
\theta_i(t)=\theta_i(0)+\Omega_it
$$


### Orbital tori

We restrict our attention to bound orbits, so that $x_i$ are periodic functions of the $\theta_i$. We can scale $\theta_i$ so that $\vec x$ returns to its original value every time $\theta_i$ has increased by $2\pi$. Then we can expand $\vec x$ in a Fourier series
$$
\vec x\left(\vec \theta,\vec J\right)=\sum_{\vec n}\vec X_{\vec n}(\vec J)\mathrm e^{i\vec n\cdot\vec\theta}=\sum_{\vec n}\vec X_{\vec n}(\vec J)\mathrm e^{i\vec n\cdot\vec\theta_0}\mathrm e^{i\vec n\cdot\vec\Omega t}
$$
where the sum is over all vectors $\vec n$ with integer components. The spatial coordinates are Fourier series in time, in which every frequency is a sum of integer multiples $(n_1,n_2,n_3)$ of the three **fundamental frequencies** $\Omega_i(\vec J)$. Such a time series is said to be **conditionally periodic** or **quasiperiodic**.

>*Quasiperiodic* here is like *quasicrystal* - a structure whose Fourier transform is discrete, but in which there are more fundamental frequencies than independent variables

An orbit is said to be **resonant** when its fundamental frequencies satisfy a relation of the form $\vec n \cdot\vec \Omega = 0$ for some integer triple $\vec n\neq \vec 0$. Usually this implies that two of the frequencies are commensurable, that is the ratio $ \Omega_i/ \Omega_j$ is a rational number $(−n_j/n_i)$.

In fact, incrementing $\theta_1$ by $2\pi$ while leaving $\theta_2,\theta_3$ fixed brings one back to the same point in phase space, which is also true for $\theta_2$ and $\theta_3$. In this way, we can sew together each pair of opposite edges of the corresponding *rectangular* region in phase space $(\theta_1,\theta_2,\theta_3)$. Thus we generate a **three-torus**.

We use the **Poincaré invariants** to label these three-tori
$$
J_i'\equiv\frac{1}{2\pi}\iint_{\text{interior of }\gamma_i}\text d\vec q\text d\vec p=\frac{1}{2\pi}\iint_{\text{interior of }\gamma_i}\sum_{j=1,2,3}\text d q_j\text d p_j
$$
where the integral is over any surface that is **bounded** by the path $\gamma_i$ on which $\theta_i$ increase from $0$ to $2\pi$ while everything else is held constant. Since angle-action variables are canonical, $\text d\vec q\text d\vec p=\text d\vec \theta\text d\vec J$, we have
$$
J_i'\equiv\frac{1}{2\pi}\iint_{\text{interior of }\gamma_i}\text d\vec \theta\text d\vec J=\frac{1}{2\pi}\iint_{\text{interior of }\gamma_i}\text d\theta_i\text dJ_i
$$
![](./pq.png)

If we rescale $\vec q$ and $\vec p$ so that $\gamma_i$ becomes a circle, $J_i'$ is in fact closely related to the area, and thus the radius, of the circle.
$$
J_i'=\frac{A_i}{2\pi}=\frac{r_i^2}{2}\Rightarrow r_i=\sqrt{2J_i'}
$$
So $(\theta_i,J_i)$ is closely analogous to plane polar coordinates (though $J_i$ is more analogous to the area). As a result, there is a coordinate singularity within the domain of integration. With the sigularity excluded, we can derive
$$
J_i'=\frac{1}{2\pi}\left(\oint_{\gamma_i}J_i\text d\theta_i-\oint_{J_i=J_i^c}J_i\text d\theta_i\right)=J_i-J_i^c
$$
where $J_i^c$ is some definite value of a small circle around the singularity. If we set $J_i=0$ at the singularity, $J_i'=J_i$. Henceforce we assume this choice has been made.

Of course in the $(\vec q,\vec p)$ phase space there is no singularity. Therefore we can simply replace the surface integral with a line integral
$$
J_i=\oint_{\gamma_i}\vec p\text d\vec q
$$

1. **Time averages theorem**

   When a regular orbit is non-resonant, the average time that the phase point of a star on that orbit spends in any region $D$ of its torus is proportional to the integral
   $$
   V(D)=\int_D\text d^3\vec\theta
   $$
   Proof:

   Let
   $$
   f_D(\vec\theta)=\left\{
   \begin{array}{cc}
   1,&\vec\theta\in D\\
   0,&\vec\theta\notin D
   \end{array}\right.=\sum_{\vec n}F_{\vec n}\exp\left(i\vec n\cdot\vec\theta\right)
   $$
   $F_\vec n$ is the Fourier coefficient.

2. 